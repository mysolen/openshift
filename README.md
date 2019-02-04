
<h1 align="center"> 免责声明 </h1>


<p align="center">
只面向海外华人用户且仅供科研学习之用，切勿用于其他用途
<br>
中国居民请自觉关闭本项目并24小时之内删掉与本项目相关的一切内容，否则出现一切问题，项目作者概不负责
</p>
<hr>

特别注意：

    首次登陆openshift官网申请开通项目时，如果用中国大陆区IP登陆，将无法验证网页，页面有一个“促销代码”的选项是不需要填的！
	实际上只需先fan梯，用美国地区或中国大陆以外地区的IP登陆，页面就会显示图片验证选项，验证通过就进入排队申请状态了，
	等候大概几分钟后刷新页面即可，有时可能要等两三天到一周左右才能通过项目审核。
	另外这种免费项目有效期只有两个月，每60天后就会自动过期！需要重新申请，比较麻烦

	布署页面中
	1、镜象名称填写 mysolen/openshift  点击搜索
	2、环境变量填写 CONFIG_JSON
	3、UUID为 c53****-*****-****-******3337 (此UUID值在v2ray客户端连接时也需要填入一样的) 在线生成UUID网站为 https://www.uuidgenerator.net/  可以随时在线生成新的UUID
	
      原图文教程详细贴子地址，请参照此贴一步步执行  https://51network.blogspot.com/2018/09/openshiftv2ray1080p.html

视频教程 https://www.youtube.com/watch?v=s83EXZbb8vQ


# v2ray 部署在 openshift starter
鉴于转载网友太多，甚至还发到了国内网站上宣传，为避免不必要麻烦，docker镜像已经删除，需要的请自行fork本
项目，然后照着这个视频 https://youtu.be/gImm4CfAnRs 自行部署镜像！ 2018/09/26

（fork于wangyi2005/v2ray修改前）

环境变量： CONFIG_JSON（配置）、


用notepad++将上述变量中 \r\n 替换为\\n，变成一行，导入容器。

客户端： android Actinium、windows v2ray 可用同一个服务端。

youtube频道：https://www.youtube.com/channel/UClceV39J1Z_9D4_mHkBZrMg

{
  "log": {
    "loglevel": "warning"
  },
  "inbound": {
    "protocol": "vmess",
    "port": 8080,
    "settings": {
      "clients": [
        {
          "id": "c53****-*****-****-******3337"此处uuid换成你自己的,
          "alterId": 64,
          "security": "chacha20-poly1305加密方式自己选"
        }
      ]
    },
    "streamSettings": {
      "network": "ws"
    }
  },
  "inboundDetour": [],
  "outbound": {
    "protocol": "freedom",
   "settings": {}
  }
}
