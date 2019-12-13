> 第一步：下载拓展

![1571710504038](assets/1571710504038.png)

> 第二步：下载`RESTlet.js`（`vscodeExtensionRestlet.js`）文件,在拓展的细节页面有git的最新下载地址，当不可用时请前往git下载最新版，并请`将该文件部署到ns系统`，`创建脚本记录`。得到其`外部URL`。

![1571710547015](assets/1571710547015.png)

> 地址：`https://github.com/netsuite-upload-org/netsuite-upload/blob/master/netSuiteRestlet/vscodeExtensionRestlet.js`

> 第三步：配置`settings.json`文件,加入如下类容

1. 部署 `vscodeExtensionRestlet.js`脚本，将其外部URL设置给 `netSuiteUpload.restlet`

```json
	// Script Deployment URL for the deployed vscodeExtensionRestlet.js
    "netSuiteUpload.restlet": "xxxx",  	// vscodeExtensionRestlet.js 部署外部url（项目不同需要更改）
```

​    2.设置上传下载文件的`文件柜根目录`，默认`SuiteScripts`

```json
    // Base NetSuite folder path to upload script to. Default if unset is "SuiteScripts".
    "netSuiteUpload.rootDirectory": "xxxx", //文件柜根目录 要与本地文件目录结构相同（项目不同需要更改）
```

   3.设置`文件比对`的`文件柜文件下载临时存放`目录

```json
	// Temporary folder - used for diffing files between local and remote.
    "netSuiteUpload.tempFolder": "xxx",  // 本地文件与文件柜文件比对，下载的文件柜文件存放目录
```

​	4.设置OAuth权限验证的密钥，秘密

> `ps`: 新建管理集合时，请勾选（`基于令牌的身份验证 (TBA)`），并去掉勾选（`TBA：授权流程`），
>
> 请`注意保存如下四个密钥`，因为只有首次初始化会显示，后期会隐藏，如忘记密钥，只能重新生成。

```json
	// If using OAuth, set all of these.
    // Oauth NetSuite Key or Token ID
    "netSuiteUpload.netSuiteKey": "xxx",//设置/用户角色/访问令牌/新建 令牌ID（）
    // Oauth NetSuite Secret
    "netSuiteUpload.netSuiteSecret": "xxx", //设置/用户角色/访问令牌/新建 令牌秘密
    // Oauth NetSuite Consumer Key
    "netSuiteUpload.consumerToken": "xxx",// 设置/集成/管理整合/新建  顾客密钥
    // Oauth NetSuite Consumer Secret
   "netSuiteUpload.consumerSecret": "xxx", // 设置/集成/管理整合/新建 消费者密钥
```

5.设置公司科目ID，也就是NS数字化账号

```json
	// Account number
    "netSuiteUpload.realm": "xxx",  //   设置/公司/公司资料/科目ID
```

> 第四步：动手开发吧。你已经完成了全部的配置，可以开心的玩了。

基本使用命令：ctrl+shift+p  输入命令，这可以让你添加模块

基本使用：

![1571711699713](assets/1571711699713.png)



- `Pull file from NetSuite` - downloads a file from NetSuite
- `Push file to NetSuite` - uploads a file to NetSuite
- `Delete file in NetSuite` - deletes a file in NetSuite
- `Compare file with NetSuite` - diff your local version with the NetSuite version
- `Pull folder from NetSuite` - Download the folder and all contents from NetSuite


