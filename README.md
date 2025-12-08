自用 1panel + x-ui 安装备忘录，删除了我用不到的功能，不建议使用。原版：https://github.com/xeefei/X-Panel

## 通过Docker安装

1. **安装1panel+Docker**

   ```sh
   curl -sSL https://resource.1panel.pro/quick_start.sh -o quick_start.sh && bash quick_start.sh
   ```

2. **克隆项目仓库**

   ```sh
   git clone https://github.com/xeefei/x-panel.git
   cd x-panel
   ```

3. **构建并启动服务**：

   ```sh
   docker build -t x-ui-test .
   ```

   ```sh
   docker run -itd -e XRAY_VMESS_AEAD_FORCED=false -v /root/xui/db/:/etc/x-ui/ -v /root/xui/cert/:/root/cert/ --network=host --restart=unless-stopped --name x-ui-test x-ui-test:latest
   ```

4. **bbr**：

   选 11 ，bbr+bbr模块，重启vps

   ```sh
   wget -O tcpx.sh "https://github.com/ylx2016/Linux-NetSpeed/raw/master/tcpx.sh" && chmod +x tcpx.sh && ./tcpx.sh
   ```

## 连接

   默认端口 13688

   使用1panel进入容器shell，重置密码
   ```sh
   /usr/bin/x-ui setting -username 用户名 -password 密码
   ```