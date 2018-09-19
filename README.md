#  shell脚本实现xxx.app包打包为ipa包说明

1、请保证xxx.app包和app_Package_ipa.sh的shell脚本处于相同的绝对路径。

2、请在app_Package_ipa.sh脚本中输入对应的xxx.app的包名。

3、已经编辑好的app_Package_ipa.sh脚本并转为exec可执行文件，该exec文件中的.app包为：DOBI，是用于测试的，如需要赋予权限，请打开终端：1、cd 至app_Package_ipa.sh和xxx.app包同一绝对路径下；2、执行 mv app_Package_ipa.sh app_Package_ipa 移除.sh后缀；3、执行 sudo chmod +x app_Package_ipa 把移除后缀后的app_Package_ipa.sh文件转为exec可执行文件

