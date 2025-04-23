# Is It Really Secure?

这样传输文件真的安全吗？

题目给了一个流量包 `ThisIsReallySecure.pcapng`，用 Wireshark 打开，查看一下统计就能够看到流量包里面有 FTP 流量

![](https://cdn.jsdelivr.net/gh/GDUTMeow/Challenge-Is-It-Really-Secure/img/image-20250423212024966.png)

而众所周知，FTP 是明文传输，所以我们可以尝试把它的文件提取出来，Wireshark 给了傻瓜式提取法

![](https://cdn.jsdelivr.net/gh/GDUTMeow/Challenge-Is-It-Really-Secure/img/image-20250423212101000.png)

![](https://cdn.jsdelivr.net/gh/GDUTMeow/Challenge-Is-It-Really-Secure/img/image-20250423212129291.png)

发现有个 `Encrypted_ZIP.zip` 文件，拿出来后发现要密码

![](https://cdn.jsdelivr.net/gh/GDUTMeow/Challenge-Is-It-Really-Secure/img/image-20250423212155399.png)

可以尝试一下 FTP 的密码 `my-Str0ng_p@55w0Rd`，但是会说不对，所以考虑一下伪加密

用 ZipCracker 爆一下发现就是伪加密

![](https://cdn.jsdelivr.net/gh/GDUTMeow/Challenge-Is-It-Really-Secure/img/image-20250423213001169.png)

把图片拿出来以后，发现是个二维码

![](https://cdn.jsdelivr.net/gh/GDUTMeow/Challenge-Is-It-Really-Secure/img/flag.png)

找个东西扫一下就能得到 flag

![](https://cdn.jsdelivr.net/gh/GDUTMeow/Challenge-Is-It-Really-Secure/img/image-20250423213050467.png)

`flag{D0_yoU_THlnk_ftP-l5_ReaL1Y_53CurE??_1-tHInk-YOU_m4y-knOw-THat_n0W}`

