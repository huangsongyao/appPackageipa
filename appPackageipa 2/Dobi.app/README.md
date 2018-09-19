# 工程简要说明

1、工程采用VMVC设计模式，脱于MVVM模式下，将MVVM中传统的View和ViewModel整合为一个ViewModel，用于处理数据更新和交互逻辑，Controller对于ViewModel执行管理和监听，只负责UI渲染操作；

2、由于iOS无Java的pack包概念，所以当前工程目录下已划分好区域，包括HeaderFile、Config、Cache、Manager、Networking、Custom、Basic、Classes等，相关文件夹的存放内容已使用.md文件做说明，可根据需要和具体划分区域区分文件对；

3、开源库及插件采用cocoapods作为管理者，当前已添加的开源库包括：
                1.AFNetworking[http、https网络请求框架]、
                2.CocoaAsyncSocket[socket网络请求框架]、
                3.FMDB[基于原生Sql3的数据库框架]、
                4.HSYCocoaKit[开源的私有库开源框架，涵盖设计模式、基类、功能模块定制等，GitHub地址为:https://github.com/huangsongyao/HSYCocoaKit.git]、
                5.JSONModel[JSON数据解析开源库]、
                6.lottie-ios[JSON动画文件解析开源库，由UI导出复杂的组合动画的JSON文件，可用此库做动画文件解析]、
                7.Masony[自动布局开源库]、
                8.MBProgressHUD[提示框、提示语、loading狂等相关UI的可定制的开源UI库]、
                9.RegexKitLite[正则表达式封装的开源库]、
                10.SDWebImage[加载网络图片的开源框架]、
                11.TKRoundedView[区分圆角、视图层的一个开源UIView]、
                12.TYAttributedLabel[支持图+文、图+UIView、UIView+文、图+文+UIView的富文本开源框架]、
                13.UITableView+FDTemplateLayoutCell[UITableView自动算高的开源库]、
                14.UITextView+Placeholder[UITextView添加Placeholder功能的开源库]；

4、主工程文件统一使用Dobi作为文件名前缀，例如：DobiBaseViewController，主工程中所有的方法、函数、以及属性成员[init开头的入口方法、继承自JSONModel的json数据映射类的属性名，“只读”属性名称除外]均使用"dobi_"作为前缀，例如@property (nonatomic, copy) NSString *dobi_title;  - (void)dobi_objectForKey:(NSString *)key; 通过对文件名称和方法、函数以及熟悉的前缀话，统一工程命名规则以及对代码、文件混淆的做预埋点；

5、为了避免过度累积和代码杂乱，请保持每个类[Class]的代码行数在500行以内，可以的话实现文件也保持在500行以内，以维持更新迭代的以及代码的质量，如碰到复杂逻辑请一定做逻辑封装和抽取，以防代码耦合过高；

6、主工程使用多target模式，其中：1、名称为“Dobi”的target为debug开发服，当build该target时，Base URL会自动适配为http的debug服地址；
                                                          2、名称为“Dobi_test”的target为test测试服，当build该target时，Base URL会自动适配为https://test的测试服地址；
                                                          3、名称为“Dobi_release”的target为生产正式服，当build该target时，Base URL会自动适配为https://dobi的生产正式服地址；

7、当使用Dobi_test或者Dobi_release打包时，ipa包内禁止模拟器运行，即：当Dobi_test和Dobi_release下的ipa在模拟器上安装后，会自动执行exit(0)函数，退出应用，开发时请使用Dobi作为开发的target，该Dobi target所打的ipa包不会禁止模拟器运行。并且，当创建新的文件时，需要默认勾选的所有的target，如有遗漏，请选中未添加的.n/.h文件，在右侧栏勾选。

8、混淆脚本说明：工程根目录下，有名为“kDobiConfuse.sh”的shell脚本，“Dobi_Text”和“Dobi_release”两个target已经在Build Phases中生成好了脚本，需要混淆时，请打开脚本中的注释，首次编译后，会在工程“$PROJECT_DIR/Dobi/”的绝对路径下生成好“.list”和“.h”两个文件，在生成好后，请将两个文件“add file”到主工程中，并打开“.pch”全局头文件定义文件内的注解。

