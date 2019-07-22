Threejs大型obj文件的秒加载实现

原理: https://www.jianshu.com/p/5c2cafcea26c

例子中的3d模型使用的是100m的陆羽模型 原下载地址 https://www.artec3d.com/3d-models/lu-yu.

![image.png](https://upload-images.jianshu.io/upload_images/17792779-6e508a5adf53ceb3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

luyu.obj  obj模型文件

luyu.gltf obj转gltf文件  (obj2gltf -i luyu.obj -o luyu.gltf)

luyu2.gltf gltf文件压缩后的文件 (gltf-pipeline -i luyu.gltf -o luyu2.gltf -d)


1 安装BrowserSync  npm install -g browser-sync

2 执行 browser-sync start --server --files "css/*.css, *.html"

3 打开 [http://localhost:3000/loadobj.html](http://localhost:3000/loadobj.html)

  这里面的代码是加载obj文件和gltf文件
  
![image.png](https://upload-images.jianshu.io/upload_images/17792779-a635467889829cad.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

4打开 [http://localhost:3000/login.html](http://localhost:3000/login.html) 

这是模拟登陆页面 在这个页面启动webwork 异步加载和解压缩模型


![image.png](https://upload-images.jianshu.io/upload_images/17792779-de6e59cd7b892a06.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

5 点击链接进入模型页 使用indexdb加载模型 加载只需要1.3s

![image.png](https://upload-images.jianshu.io/upload_images/17792779-8e78021df4960701.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
