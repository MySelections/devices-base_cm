devices/base_cm

cm-11.0基础机型，是所有cm-11.0机型“插桩”的基础，也是生产“patch”的工厂。

Base device for CyanogenMod 11.0, as a basis for all the other CyanogenMod 11.0 devices, but also as a factory of producing patch.

目前的patch基于CM-11.0的M11版本制作，会跟随CM-11.0的大版本进行同步更新。

base_cm使用方法：

1. 下载

   为了减少repo库的体积，base_cm暂时没有放在repo下载列表里，因此下载base_cm推荐使用git clone下载，第一次下载时先cd到devices目录，然后输入：

   git clone -b coron-4.4 https://github.com/baidurom/devices-base_cm.git

   即开始下载，下载完成后建议对其重命名, cd到devices目录，输入：mv ./devices-base_cm ./base_cm，即将其重命名为base_cm

   以后base_cm的更新则只需要cd到devices/base_cm目录，输入git pull即可下载base_cm的更新。

   如果不使用git clone下载，则需要每次下载整个zip包进行覆盖，较为不便。

2. 使用

   正确下载后，devices目录下应存在除了base目录外的base_cm目录以及你的机型目录。

   与使用默认方式来patch（即使用base来patch）的各项操作相同，只需要额外进行一项配置即可。

   要使用指定base（如base_cm）的patch需要在你的机型目录下的Makefile文件中进行配置，配置项为：BASE :=

   在base及base_cm目录下的Makefile文件中均有示例说明，将其写入你的机型目录下的Makefile文件中并进行正确配置。

   如：BASE :=base_cm，base_cm是你下载base_cm的目录名。

   配置完成后，即可使用分别使用coron patchall和coron upgrade来进行patch和更新。

   需要注意的是：

   base_cm的正确运行需要对baidu/release下的部分apk或者资源文件进行定制，但是定制的文件并没有体现在patchall及upgrade中，

   因此，你需要查看base_cm下对apk或者资源文件进行定制的文件以及其相应的配置信息，将配置文件和配置信息一并写在你的机型中。

   对apk或者资源文件进行定制的方法请参考manifest目录下的文档或者在百度云OS论坛上开发者学院板块进行查找。
