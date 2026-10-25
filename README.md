# Aqara Hub E1 中国版固件备份

型号：`lumi.gateway.aqcn02`。保存原始固件及可核验的来源、大小与摘要。二进制文件在 [Releases](https://github.com/hitsmaxft/aqara-e1-firmware/releases)，Git 仅保存目录和说明。

| 版本 | 文件 | 大小（字节） | 来源类型 |
| --- | --- | ---: | --- |
| `4.3.8_0023` | `Network-Co-Processor.ota` | 190,786 | Stock component from community archive |
| `4.5.60_0031.0013` | `aqara-official-4.5.60_0031.0013.bin` | 16,117,864 | Official Aqara CN OTA package |
| `4.3.8_0023` | `kernel_4.0.6_0010_4.3.8_0023` | 2,254,636 | Stock component from community archive |
| `3.1.6_0001` | `mihome-official-3.1.6_0001.bin` | 12,311,897 | Official Xiaomi CN MIOT OTA package |
| `4.3.8_0023` | `rootfs_4.0.6_0010_4.3.8_0023.sqfs` | 13,234,176 | Stock component from community archive |

## 来源与验证

- `4.5.60_0031.0013`：通过 Aqara 中国区 App 协议的已认证固件查询获得官方 CDN 地址；已下载完整 LMFW 包，大小、MD5、CRC32 与接口一致。查询未触发 OTA。
- `4.3.8_0023`（米家版本 `4.0.6_0010`）：来自 [niceboygithub/AqaraCameraHubfw](https://github.com/niceboygithub/AqaraCameraHubfw/tree/38f602a3b839ceb75ef9746ff5fe157017008db0/original/E1/4.0.6_0010_4.3.8_0023) 固定提交的 original 目录。它们是独立原始组件，不是完整官方 OTA 包，也不是从个人设备读回的镜像。
- `3.1.6_0001`：通过小米中国区接口按型号查询获得的旧版完整 OTA 包。清单仅保留不含临时签名参数的 CDN 路径，该路径不保证长期可直接下载。
- 每个文件的 SHA256、MD5、原始来源见 [manifest.json](manifest.json)。下载同一 Release 的文件和 `SHA256SUMS` 后执行 `shasum -a 256 -c SHA256SUMS`。

摘要校验用于确认文件一致性，不代表已验证厂商数字签名或通过实际刷写测试。归档未改变设备固件，不提供跨版本混刷结论；不包含修改版固件。

## 范围与权利

本仓库仅归档中国版 E1 固件；不包含账号、密码、会话令牌、设备 DID、MAC、家庭或房间信息。固件版权属于相应权利人，本仓库不对厂商固件授予额外许可证。
