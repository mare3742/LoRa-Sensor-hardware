# LoRa 環境モニタ — ハードウェア

基板と筐体のデータ。親機も子機も同じ基板を使う。ファームウェアと表示側は [LoRa-Sensor-public](https://github.com/mare3742/LoRa-Sensor-public)。

| ファイル | 中身 |
|---|---|
| [`jlcpcb/`](jlcpcb/) | 基板の JLCPCB 発注データ（ガーバー・BOM・CPL）。SMD 部品は実装済みで届く |
| `筐体_2台分_ABS.gcode.3mf` | 筐体（本体・ふた・電池ふた）2台分のスライス済みデータ。ABS |

## 1台に必要なもの

- 基板（上の発注データ）
- Seeed XIAO ESP32S3
- E220-900T22S-JP と、対応するアンテナ（好きなものでよい）
- Grove SHT35
- DS18B20 と黒球（自作。詳細は後述予定）
- エネループ 4 本
- 基板に挿すピンソケット（JLCPCB では実装されないので手はんだ）

## 基板に挿すもの

| 場所 | 挿すもの |
|---|---|
| J2 / J3 | XIAO ESP32S3 |
| J1 | E220 |
| J5 | 電池 |
| J6 | SHT35 |
| J8 | DS18B20 |
| J7 | 何も挿さない（SCD30 用の空き） |

DS18B20 のデータ線のプルアップ抵抗は基板に載っていない。DS18B20 側で 4.7kΩ を付ける。

E220 は挿す前に `set` で子機用の設定を書き込んでおく（[手順](https://github.com/mare3742/LoRa-Sensor-public/blob/main/firmware/README.md#e220-の設定set)）。

## 親機

XIAO と E220 だけを挿し、USB でラズパイにつなぐ（電源もそこから取る）。E220 は `set` で親機用に設定する。ラズパイ側は [pi/README.md](https://github.com/mare3742/LoRa-Sensor-public/blob/main/pi/README.md)。

## 黒球・DS18B20

（準備中）
