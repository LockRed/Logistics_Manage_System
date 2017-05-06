# Logistics_Manage_System #

基于Java 中 SSH 框架的 物流配送管理系统

目前该系统应用于我本人的大四毕业设计

一键快速部署，移植性强

------------------------------------------------------------------

## 项目运行准备工作 ##
 - 数据库文件为conf目录下的db.properties，这是导入项目后需要看的第一个文件，也是你项目运行需要唯一注意的文件
 - 项目启动前，看一下db.properties这个文件是不是和你本地的数据库统一（用户名以及密码），我用的是mysql数据库，之后你要创建一个名为logistics的数据库，之后启动项目就好了，数据库表的工作就交给hibernate，它会为你自动创建数据库表的。至此项目成功启动
 - 因为该项目没有使用Maven工程的构建方式，所以你不需要考虑jar包的 问题，项目中所涉及到的jar包都放在了WEB-INF下的lib目录文件下
 - 完成以上的几点你的项目就已经成功跑起来了~

## 目录结构介绍 ##

	|-- build                                                      // 配置文件无需考虑
	|-- conf                                                       // 项目有关的配置文件
	|   |-- applicationContext.xml                                 // 应用上下文配置文件
	|   |-- applicationContext-beans.xml                           // JavaBean配置文件
	|   |-- db.properties                                          // 数据库配置文件
	|   |-- hibernate.cfg.xml                              	       // hibernate配置文件
	|   |-- struts.xml                                             // 与Struts有关的配置
	|-- src                                                        // 源码目录
	|   |-- com
	|       |-- wt
	|           |-- action
	|               |-- AdminAction.java                           // 管理员处理类
	|               |-- CreateImageAction.java                     // 验证码生成处理类
	|               |-- OrderAction.java                           // 订单处理类
	|               |-- UserAction.java                            // 用户处理类
	|               |-- VerifyCodeAction.java                      // 另一种验证码生成处理类
	|           |-- dao
	|               |-- AdminDao.java                              // 管理员处理dao层部分
	|               |-- BaseDao.java                               // 可被其他dao层重复利用进行减少代码冗余的dao层部分
	|               |-- OrderDao.java                              // 订单处理dao层部分
	|               |-- UserDao.java                               // 用户处理dao层部分
	|           |-- entity
	|               |-- Admin.java                                 // 管理员实体类 
	|               |-- Admin.hbm.xml
	|               |-- Book.java                                  // 书籍实体类 
	|               |-- Book.hbm.xml
	|               |-- Order.java                                 // 订单实体类
	|               |-- Order.hbm.xml
	|               |-- User.java                                  // 用户实体类
	|               |-- User.hbm.xml                               
	|               |-- Warehouse.java                             // 仓库实体类
	|               |-- Warehouse.hbm.xml
	|           |-- fileHandle
	|               |-- FileHandle.java                            // 文件处理类
	|           |-- interceptor
	|               |-- AdminLoginInterceptor.java                 // 管理员拦截器处理类 
	|               |-- UserLoginInterceptor.java                  // 用户登录拦截器处理类 
	|               |-- UserLoginLogisticsInterceptor.java         // 用户登录物流配送中心拦截器处理类 
	|               |-- UserLoginShoppingInfoInterceptor.java      // 用户登录商城拦截器处理类
	|           |-- jsonHandle
	|               |-- AdminLoginJsonHandle.java                  // 管理员登录json数据处理类 
	|               |-- ApplyResetPasswordJsonHandle.java          // 邮件发送json数据处理类
	|               |-- LoginJsonHandle.java                       // 用户登录json数据处理类 
	|               |-- RegisterJsonHandle.java                    // 注册用户json数据处理类
	|               |-- ResetPasswordJsonHandle.java               // 修改密码json数据处理类
	|               |-- UserValidate.java                          // 用户验证处理类
	|           |-- service
	|               |-- AdminService.java                          // 管理员service层处理类 
	|               |-- OrderService.java                          // 订单service层处理类 
	|               |-- UserService.java                           // 用户service层处理类 
	|           |-- utilMail
	|               |-- ApplyResetPassword.java                    // 发送邮件修改密码模拟类
	|               |-- MailSenderInfo.java                        // 邮件注册信息
	|               |-- MyAuthenticator.java                       // 获取发送邮件者信息
	|               |-- SimpleMailSender.java                      // 以文本格式发送邮件   
	|               |-- Test.java                                  // 邮件发送测试类，可单独运行进行邮件发送测试
	|           |-- template
	|               |-- emailTemplate.vm
	|   |-- WebContent 	// 页面入口文件由于其中涉及的都是前端页面以及js、css部分这里不做过多介绍，根据命名也能很好的推测出
	|       |-- WEB-INF 
	|           | -- lib                 			       // jar 包存放位置
	|           | -- web.xml             			       // 项目及工具的依赖配置文件
	|-- README.md                        			       // 说明


