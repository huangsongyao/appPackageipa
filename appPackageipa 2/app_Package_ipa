#!/usr/bin/env bash

#.app包和脚本的绝对路径请保持一致
#app包名
App_Name="DOBI"
#获取要打包的.app包的目录的绝对路径
work_path=$(dirname $0)
#当前位置跳到脚本位置
cd ${work_path}
#先删除ipaPayload文件夹，避免上次缓存遗留
rm -rf ipaPayload
#再创建ipaPayload文件夹
mkdir ipaPayload
#在文件夹里面创建Payload文件夹
mkdir ipaPayload/Payload
#将当前目录下的App_Name.app复制到Payload里面
cp -r $App_Name.app ipaPayload/Payload/$App_Name.app
#移动到ipaPayload文件夹下
cd ipaPayload
#压缩多个目录zip FileName.zip 目录1 目录2 目录3...
#zip -r $App_Name.ipa Payload iTunesArtwork
#开始打包ipa...
zip -r $App_Name.ipa Payload
echo 'package completed!'

exit 0
