一：直接 skynet 下 运行 skynet.xcodeproj


二：自己网上下载安装包配置过程

1.解压 ./skynet-1.0.0-alpha.zip 到 ./skynet

2.解压 ./jemalloc-3.6.0.tar.bz2 到 ./skynet/3rd/jemalloc/

3.编译 jemalloc
   cd 到 jemalloc 目录下
   ./configure 

4.编译 skynet
make 'macosx'

5.为了能在mac下运行
去掉 lua 及 luac 的main 函数

lua.c
#ifdef LUA_DEBUG
int mainlua (int argc, char **argv) {
#else
int main (int argc, char **argv) {
#endif

luac.c
#ifdef LUA_DEBUG
int mainluac(int argc, char* argv[])
#else
int main (int argc, char **argv)
#endif

6.xcode调试
直接打开skynet/skynet.xcodeproj 点击运行


7
报错处理Need a config file. Please read skynet wiki : https: github.com cloudwu skynet wiki Config usage: skynet configfilename
https://github.com/sosilen/skynet-xcode-debug-or-read/wiki/%E6%8A%A5%E9%94%99%E5%A4%84%E7%90%86Need-a-config-file.-Please-read-skynet-wiki-:-https:--github.com-cloudwu-skynet-wiki-Config-usage:-skynet-configfilename
