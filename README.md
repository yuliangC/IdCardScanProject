# IdCardScanProject
基于腾讯优图的身份证扫描程序，使用相机拍照读取身份证上的信息
##说明
####公司项目需要实现一个扫描身份证自动录入信息的功能，开始尝试自己读取，使用[tess-two](https://github.com/rmtheis/tess-two)来实现，但是发现对汉字的解析相当一般，基本一段只能识别出几个正确的结果,后来用了腾讯优图，基本达到需求，但是识别效率和照片的清晰度有很大关系，但是总体尚可，有兴趣和需求的可以下载试下......


图片压缩的实现
```
public static String zoomBitMapFromPath(Context context, String path) {
        String newPath;
        File f = new Compressor.Builder(context)
                .setMaxWidth(1920)
                .setMaxHeight(1080)
                .setQuality(100)
                .setCompressFormat(Bitmap.CompressFormat.JPEG)
                .setDestinationDirectoryPath(context.getCacheDir().getAbsolutePath())
                .build()
                .compressToFile(new File(path));
        newPath = f.getPath();
        return newPath;
    }
```
改变此处的宽高和quality可以改变压缩图片的清晰度，上传的图片越清晰，识别率越高，但是如果图片太大，腾讯服务器则无法解析，可以根据自己的需求更改此处的配置。

##Demo APK下载地址
<img src="screenshoot/download.png"  width="200" height="200" />

<img src="screenshoot/Screenshoot.png"  width="225" height="400" />
