#  Classes用于存放工程中的开发模式及相关实现内容[UIViewController、UIView等具体的页面和试图]

一、「模塊文件」------ 子文件夾分類說明：
                                                                                                                                Dobi_login & Register_Module
                                                                                                                                                    |
                                                                                               ---------------------------------------------------------------------------
                                                                                               |                                                    |                                                   |                                            
                                                                                       Cell&View                                    ViewModel                                ViewController
                                                                                               |                                                    |                                                   |
                                                                [登錄註冊模塊的Cell及定制視圖]            [登錄註冊模塊的viewModel]              [登錄註冊模塊的Controller]
                                                                                                                                                                                                       
                         
+[以下说明为登录注册模块为例]+

Cell&View : DobiLocCodeSubscriptView[手機區號右側的索引定制視圖]、DobiMobileLocCodeCell[手機區號的cell]、DobiRegisterCell[登錄、註冊、谷歌郵箱驗證、忘記密碼等相關的輸入框Cell]

ViewModel：DobiMobileLocCodeViewModel[手機區號的VM]、DobiGoogleEmailViewModel[谷歌驗證碼及忘記密碼的VM]、DobiUserRegisterViewModel[登錄註冊的VM]，其中，DobiMobileLocCodeViewModel和DobiGoogleEmailViewModel均繼承自DobiUserRegisterViewModel

ViewController：DobiMobileLocCodeViewController[手機驗證碼VC]、DobiProtocolWebViewController[用戶協議的web-VC]、DobiGoogleEmailViewController[驗證谷歌驗證碼的VC]、DobiForgetPasswordViewController[忘記密碼的VC]、DobiUserRegisterViewController[登錄註冊的VC]，其中DobiMobileLocCodeViewController、DobiGoogleEmailViewController和DobiForgetPasswordViewController均繼承自DobiUserRegisterViewController
                                


二、子文件夹说明

    1、Dobi_Guide_Module：引导页模块
    2、Dobi_QRCode_Module：二维码相机模块
    3、Dobi_Login & Register_Module：登录和注册模块
    4、Dobi_User_Module：我的模块
    5、Dobi_FB_Module：法币模块---web
    6、Dobi_BB_Module：币币模块
    7、Dobi_Market_Module：行情模块
    8、Dobi_LaunchScreenViewController_Module：自定义启动页模块


