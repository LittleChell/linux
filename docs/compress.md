# linux 压缩与解压缩

###	tar.xz文件

---

xz这个压缩可能很多都很陌生，不过您可知道xz是绝大数Linux默认就带的一个压缩工具。<br>
之前xz使用一直很少，所以几乎没有什么提起。<br>
我是在下载phpmyadmin的时候看到这种压缩格式的，phpmyadmin压缩包xz格式的居然比7z还要小，这引起我的兴趣。<br>
最新一段时间会经常听到xz被采用的声音，像是最新的archlinux某些东西就使用xz压缩。不过xz也有一个坏处就是压缩时间比较长，比7z压缩时间还长一些。不过压缩是一次性的，所以可以忽略。<br>

**xz压缩文件方法或命令**<br>

xz -z 要压缩的文件

如果要保留被压缩的文件加上参数 -k ，如果要设置压缩率加入参数 -0 到 -9调节压缩率。如果不设置，默认压缩等级是6.<br>
xz解压文件方法或命令<br>

xz -d 要解压的文件

同样使用 -k 参数来保留被解压缩的文件。<br>
创建或解压tar.xz文件的方法<br>
习惯了 tar czvf 或 tar xzvf 的人可能碰到 tar.xz也会想用单一命令搞定解压或压缩。其实不行 tar里面没有征对xz格式的参数比如 z是针对 gzip，j是针对 bzip2。

创建tar.xz文件

只要先 tar cvf xxx.tar xxx/ 这样创建xxx.tar文件先，然后使用 xz -z xxx.tar 来将 xxx.tar压缩成为 xxx.tar.xz

解压tar.xz文件

先 xz -d xxx.tar.xz 将 xxx.tar.xz解压成 xxx.tar 然后，再用 tar xvf xxx.tar来解包。

