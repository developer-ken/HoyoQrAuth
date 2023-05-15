# HoyoQrAuth 米游社扫码登录协议实现  
本仓库是一个米游社扫码登录协议的C#实现。它模拟一个米游社客户端，调用相关API实现PC端游戏的扫码登录。  
** 二维码到URI的识别已有诸多开源实现，不包含在本仓库内 **  
  
# 使用例程
```
const string COOKIESSTR = "";                   //https://user.mihoyo.com/ 登录后复制Cookies字符串
const string QRURI = "";                        //登录二维码指向的URI
HoyoLogin hoyo = new HoyoLogin(COOKIESSTR);     //初始化HoyoLogin库
var scan = hoyo.GetQRScanHandler();             //获取二维码处理装置
var qrcode = new LoginQr(QRURI);                //解析二维码URI，生成LoginQr对象
scan.Scan(qrcode);                              //使用二维码处理器“扫描”LoginQr
scan.ConfirmLogin();                            //确认登录游戏
```
