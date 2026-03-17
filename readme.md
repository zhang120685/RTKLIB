这份关于 **RTKLIB 2.4.3 Betas** 的更新日志已整理为 Markdown 格式：

---

# RTKLIB 2.4.3 Betas 更新日志

## 项目说明
[cite_start]RTKLIB 2.4.3 的开发分支 [cite: 1]。

---

## 历史更新详情

### 2020/12/30 (2.4.3 b34)
#### **常规更新 (GENERAL)**
* [cite_start]**卫星系统支持**：完整支持 NavIC (IRNSS) [cite: 30][cite_start]；新增 BDS-3 和 QZSS 新信号 [cite: 31]。
* [cite_start]**协议与标准**：支持 RINEX 3.04 [cite: 31][cite_start]；支持 RTCM 3.3 amendment-1，添加 MT1041/1131-7 (NavIC) [cite: 31][cite_start]；支持 RTCM3 MT1230 (GLONASS 代码相位偏差) [cite: 32] [cite_start]及 MT4076 (IGS SSR) [cite: 32]。
* [cite_start]**信号标识**：GNSS 信号 ID 变更为：L1, L2, L3, L4, L5 [cite: 32]。
* [cite_start]**平台支持**：仅支持 Windows 64位应用程序，删除了 32位程序 [cite: 33][cite_start]；支持 Windows 高 DPI 屏幕缩放 [cite: 33]。
* [cite_start]**结构调整**：重组了 `RTKLIB/app` 和 `RTKLIB/data` 目录 [cite: 34][cite_start]；明确了开源许可（详见 `RTKLIB/LICENSE.txt`） [cite: 34]。
* [cite_start]**问题修复**：修复了 GitHub 上的多个 Issue (#461, #477, #480, #514, #540, #547, #555, #560) [cite: 34]。

#### **库 API (LIBRARY API)**
* [cite_start]**新增 API**：包括 `code2freq()`, `sat2freq()`, `code2idx()`, `timereset()`, `setseleph()`, `getseleph()`, `decode_gal_fnav()`, `decode_irn_nav()` [cite: 35]。
* [cite_start]**删除 API**：删除了包括 `lam_carr[]`, `satwavelen()`, `csmooth()`, `input_gw10()`, `input_cmr()`, `pppcorr_*` 等在内的多项旧接口 [cite: 36, 37]。
* [cite_start]**修改类型**：更新了 `obsd_t`, `eph_t`, `nav_t`, `rtcm_t`, `prcopt_t`, `raw_t` 等核心结构体 [cite: 37]。

#### **接收机支持 (RECEIVER SUPPORTS)**
* [cite_start]**BINEX**：支持 NavIC/IRNSS 原始观测数据 (0x7f-05) [cite: 37][cite_start]、解码星历 (0x01-07) [cite: 38] [cite_start]及测站信息 (0x00) [cite: 38]。
* [cite_start]**NovAtel**：支持 OEM7 及其相关消息（如 RANGEB, GLOEPHEMERISB, BDSEPHEMERISB 等） [cite: 39]。
* [cite_start]**Septentrio**：重写了 SBF 代码以支持 Mosaic-X5 [cite: 39][cite_start]，支持 MEAESPOCH 等消息 [cite: 40]。
* [cite_start]**u-blox**：支持 UBX-CFG-VALDEL/GET/SET [cite: 40][cite_start]；为北斗 GEO 卫星添加了 UBX-RXM-RAWX 半周期相位偏移处理 [cite: 41][cite_start]；支持 QZSS L1S [cite: 41]。

#### **应用软件更新**
* **RTKPLOT**：
    * [cite_start]地图视图支持 Leaflet 和标准地图切片（如 OpenStreetMap） [cite: 42]。
    * [cite_start]新增 Resid-EL（残差-高度角）绘图 [cite: 43]。
    * [cite_start]停止支持 TEQC 观测数据质检，删除相关菜单 [cite: 45, 46]。
    * [cite_start]删除 Google Earth 视图及相关按钮 [cite: 46]。
* **RTKCONV**：
    * [cite_start]支持 RINEX 3.04 输出 [cite: 47]。
    * [cite_start]新增 "Phase Shift" 选项以对齐载波相位 [cite: 51]。
    * [cite_start]停止支持 GW10, CMR/CMR+ 和 TERSUS 格式 [cite: 55]。
* **RTKPOST**：
    * [cite_start]改进了 Galileo 和 BDS 的 TGD/BGD 处理 [cite: 60]。
    * [cite_start]链接 OpenBLAS 替代 Intel MKL 以加速矩阵计算 [cite: 63]。
    * [cite_start]删除了 `RTKPOST_WIN64` 和 `RTKPOST_MKL` 应用程序 [cite: 64]。
* [cite_start]**RTKNAVI**：支持 NMEA ID GQ 和 GI (QZSS/NavIC) [cite: 66]。

---

### 2014 - 2019 重要更新摘要
* [cite_start]**2019/08/19 (b33)**: 支持串行流 460800 和 921600 bps [cite: 30]。
* [cite_start]**2018/10/10 (b30)**: 支持 **u-blox ZED-F9P** [cite: 25]。
* [cite_start]**2017/05/26 (b28)**: 添加 `rcv/tersus.c` 以支持 Tersus BX306 [cite: 25]。
* [cite_start]**2016/09/03 (b20)**: 增加 **NTRIP Caster** 功能 [cite: 20]。
* [cite_start]**2016/07/19 (b13)**: 支持 **RINEX 3.03** [cite: 12]。
* [cite_start]**2016/01/23 (b6)**: 支持 Septentrio [cite: 8]。
* [cite_start]**2014/10/21 (b2)**: 为北斗增加 `pos2-bdsarmode` 模糊度固定选项 [cite: 3]。

---

## 限制与已知问题
* [cite_start]**QT 端口**：已移动到 `RTKLIB/app/qtapp`，但**不再维护** [cite: 78]。
* [cite_start]**文档**：`RTKLIB/doc` 目录下的文档**未更新** [cite: 79]。

---

**您需要我为您详细解释其中的某项具体技术更新（例如具体的 API 变更或新支持的 RTCM 消息）吗？**
