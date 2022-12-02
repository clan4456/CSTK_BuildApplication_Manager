# CLAN Studio Toolkits - BuildApplication Manager

仓库地址：[CSTK_BuildApplication_Manager](https://github.com/clan4456/CSTK_BuildApplication_Manager)

下载地址：[clan_studio_lib_cstk_buildapplication_manager-1.0.0.1.vip](https://github.com/clan4456/CSTK_BuildApplication_Manager/releases/download/v1.0.0.1/clan_studio_lib_cstk_buildapplication_manager-1.0.0.1.vip)

SHA-256：c3a6d9f24c2093b5156c9dbe2199df6bcfe2fc14ca007289df2a208f2098d8a1

## 1. 简介

![](http://pic2.clan4456.com/clan-picgo/202212021644619.gif)

本工具主要用于对编译生成的EXE应用程序文件进行简易版本管理，可规范化地进行修改日志记录、程序文件打包等操作，方便日后回溯和管理。

本工具仅对生成的EXE应用程序进行版本管理，如需对源码进行版本管理，建议使用Git或SVN等专业版本管理工具进行管理。

## 2. 前置库

本工具使用到以下前置库，需通过VIPM提前安装，亦可在安装本工具时自动安装。

- JKI JSON >= 1.1.10.37
- JKI Serialization >= 1.0.1.14
- JKI Unicode >= 1.0.0.7
- OpenG Array Library >= 4.1.1.14
- OpenG Error Library >= 4.2.0.23
- OpenG Variant Data Library >= 5.0.0.27

## 3. 安装Build Application Manager

下载Release中的`clan_studio_lib_cstk_buildapplication_manager-1.0.0.1.vip`，并双击通过VIPM进行安装。（需安装VIPM 2017或以上版本）

## 4. 使用方法

该工具主要通过在项目管理器中自动创建并插入 ***Post-Build Action*** ，来实现对编译生成的EXE应用程序进行日志记录、打包ZIP等操作。

安装 ***Build Application Manager*** 后，可在项目浏览器中，通过菜单 *工具* --> *CLAN Studio Toolkits* --> *CSTK_BuildApplication Manager* 进行自动创建并插入。

插入成功后，项目文件夹根目录中会增加一个`CSTK_BuildApplication_Manager_Post-Build Action.vi`文件，同时可在 *应用程序生成规范* --> *[规范名称]属性页* --> *生成前/后操作* 页面中查看到已自动插入的 Post-Action。 

![Snipaste_2022-12-02_17-35-47.png](http://pic2.clan4456.com/clan-picgo-core/images/2022/12/02/Snipaste_2022-12-02_17-35-47-fce38157afbfcd032cd13fdfe7388a55.png!small)

此时，即可按照正常操作流程，生成 EXE 应用程序，生成成功后，将会自动弹出对话框，询问是否进行日志记录或打包ZIP文件操作。

![Snipaste_2022-12-02_17-38-02.png](http://pic2.clan4456.com/clan-picgo-core/images/2022/12/02/Snipaste_2022-12-02_17-38-02-8df8a6167acffb7cd37c929701b8c114.png!small)

选择`记录/打包` 按钮后，即弹出 ***Build Application Manager*** 对话框，即可在此界面中输入该次生成的EXE应用程序的修改记录，并选择是否进行ZIP打包。

![Snipaste_2022-12-02_17-39-34.png](http://pic2.clan4456.com/clan-picgo-core/images/2022/12/02/Snipaste_2022-12-02_17-39-34-7168a64411c07c4e1ddeb581929683f7.png!small)

记录日志后，将生成两个日志文件，一个是项目修改记录，该文件生成在 ***目标目录***  的上一级文件夹中，按版本号顺序记录每次打包的修改日志。另外一个是EXE应用程序修改记录，该文件生成在EXE应用程序文件的同级目录中，只记录当前版本的修改日志。

打包生成的ZIP文件，按 `[规范名称]_[版本号]_[生成日期].zip` 的文件名格式，生成在 ***目标目录*** 的上一级文件夹中。

![Snipaste_2022-12-02_17-50-23.png](http://pic2.clan4456.com/clan-picgo-core/images/2022/12/02/Snipaste_2022-12-02_17-50-23-e0eb79e70e05b42bdc066f3db9c8a7e0.png!small)

## 5. 已知问题

### 1）窗口叠加问题

由于LabVIEW编译过程中的 `生成状态` 窗口为模态并置顶，导致在生成结束后自动弹出的 ***Build Application Manager*** 对话框无法置于最顶层并处于激活状态，因此此时需先点击 `完成` 按钮，关闭`生成状态` 窗口后，才能进行 ***Build Application Manager*** 对话框操作。

![Snipaste_2022-12-02_17-52-51.png](http://pic2.clan4456.com/clan-picgo-core/images/2022/12/02/Snipaste_2022-12-02_17-52-51-02820cd43fa4a0d3bddd9a4593f05bf2.png!small)

该问题暂未找到方便又合适的方法解决，因此该问题暂时搁置，用户需先手动点击 `完成` 按钮后，才能进行操作。

## 6. 开源许可

本工具遵循BSD开源协议，可任意分发或二次开发使用。但需保留UI界面上的 `CLAN Studio` 标志即可。

## 7. 关于捐赠

作者开发不易，如对本工具使用效果满意，同时经济允许的情况下，可向作者相赠一杯咖啡，感谢！本工具为免费开源，仅接受微信公众号（请使用微信扫描下方二维码关注 `CLAN Studio` 公众号）文章打赏，其他途径均非作者本意，请注意分辨，谢谢！

![公众号二维码_500px.png](http://pic2.clan4456.com/clan-picgo-core/images/2022/11/04/%E5%85%AC%E4%BC%97%E5%8F%B7%E4%BA%8C%E7%BB%B4%E7%A0%81_500px-515fa711dc785a71dd8819fa999ebd07.png)
