# OPEN USB PS V3 Web BLE 控制台

Web Bluetooth 只允许在安全上下文运行。不要直接双击 `index.html`，请在本目录启动本地服务器：

```powershell
python -m http.server 8000
```

然后使用 Windows/macOS/Android 上的 Chrome 或 Edge 打开：

```text
http://localhost:8000
```

点击“连接设备”，从浏览器设备选择器中选择 uart2ble。iPhone/iPad Safari 不支持 Web Bluetooth。

页面使用自定义 GATT Service `00009822-ae15-bc10-5201-856a95fcd178`，没有第三方依赖。

## 电流设置协议扩展

页面使用以下命令设置限流值：

```text
c_cfg=1.500@\n
```

表示 1.500 A。MCU 的 `usr_main_app.c` 已加入该命令，需要重新编译、烧录 MCU 固件后电流设置才会生效。
