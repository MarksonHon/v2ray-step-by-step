# CDN

目前和V2Ray兼容的CDN国外有Cloudflare，国内阿里云，这两家的CDN是支持WebSocket的。剩下的几家不支持WebSocket，也不会keep TCP connection。因此HTTP/2回源也不支持（访问支持HTTP/2和回源支持HTTP/2是两回事）。
另外，使用国内CDN需要域名备案并服务商实名认证。使用有风险，入坑需谨慎。

## 配置

参照WebSocket + TLS + Web部分，只是 TLS 证书需要使用来自 CDN 服务商提供的证书。这种证书一般都是 CDN 服务商会承认而各个浏览器不承认的，也不能通过脚本来导入，因此你需要手动把私钥保存为 key 文件、把公钥保存为 crt 文件来使用。CDN 提供商那边的设置需要修改为“全程使用 TLS ”或者开启类似的选项。
