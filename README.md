# 图片下载
## java 后端代码:

    @RestController
    public class ImgViewController {

        @RequestMapping(value = "/imgShow")
        public void imgShow(String imgPath, HttpServletResponse response) {
            FileInputStream fis = null;
            response.setContentType("image/gif");
            try {
                OutputStream out = response.getOutputStream();
                File file = new File("G:" + File.separator + imgPath);
                fis = new FileInputStream(file);
                byte[] b = new byte[fis.available()];
                fis.read(b);
                out.write(b);
                out.flush();
            } catch (Exception e) {
                e.printStackTrace();
            } finally {
                if (fis != null) {
                    try {
                        fis.close();
                    } catch (IOException e) {
                        e.printStackTrace();
                    }
                }
            }

        }
    }
## 前端代码:
#### 第一种方式：
    <img src="http://localhost:8080/imgShow?imgurl"> 
    直接将图片的请求放入src
    优点:简单，方便 请求可以是get请求，可以获取不同图片
    缺点:只能是get请求
 #### 第二种方式：   
    //通过请求后response
    let blob = new Blob([res.data]);
    let imgUrl = window.URL.createObjectURL(blob);
    将imgUrl 赋值到<img src="imgUrl">
