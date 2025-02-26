# VGM Player powered by Longan Nano で動く VGM プレーヤー (デュアル YM2203 版)

![](https://github.com/Fujix1/NanoDrive-Dual-OPN/workflows/Build/badge.svg)

## これはなに? / What's this?

RISC-V マイコン Longan Nano (GD32V) を使って VGM ファイルを再生します。SD カード内のフォルダに保存した vgm 拡張子のファイルを順番に再生します。<br>
。初期版は可能な限り表面実装部品を使うものでしたが、より誰でも気軽に製作できるようにスルーホール部品版も制作しました。<br>
YM2203 を 2 発搭載しているので、オールドカプコン、タイトーなどのアーケードゲーム、PC-8801 や PC-9801 の PC ゲームのほか、AY-3-8910 PSG 単体（MSX など）にも対応します。<br>
I2C デジタルボリュームを搭載しているので、フェードアウトや音量のノーマライゼーションができます。
<br>
<br>
This is a vgm player working with a Longan Nano RISC-V microcomputer. This version supports dual YM2203 OPN chips which is capable to play old Campcom arcades (1943, GnG, Commando etc.), MSX, PC-8801 and PC-9801 musics. VGM data is stored in a SD card.<br>
<br>
**DIP Version (release 1.21)**<br>
<img src="https://github.com/Fujix1/NanoDrive-Dual-OPN/assets/13434151/3f1da835-5f18-4ec3-a513-0341ec99999c" width="800"><br>

## PDF マニュアル (Release 1.21)

[NanoDriveYM2203_r121.pdf](https://github.com/Fujix1/NanoDrive-Dual-OPN/files/12903515/NanoDriveYM2203_r121.pdf)


## コンパイルとマイコンへの書き込み / Compile and Upload to Longan Nano

Visual Studio Code + PlatformIO IDE を使用します。具体的な使用法については以下を参照してください。<br>
Use Visual Studio Code and Platform IO IDE.

- https://beta-notes.way-nifty.com/blog/2019/12/post-b8455c.html<br>
- http://kyoro205.blog.fc2.com/blog-entry-666.html
  <br>
  <br>

## 基板 / PCB for KiCad7

https://github.com/Fujix1/NanoDrive-Dual-OPN_PCB

## 配線図 / Schematics

**【注】音量の増幅率を決める R6 と R7 が音量小さめの 20kΩ になっていますが、通常は 15kΩ にしてください。**


** Note: R6 and R7 are 20kohm but it was originally to avoid clipping in some arcade titles. Use 15k ohm usually.**

![schematic](https://github.com/Fujix1/NanoDrive-Dual-OPN/assets/13434151/e8bde6fc-cf50-4615-a771-cecad57921ed)



## 使用部品 / Parts

|     番号                             |     部品                                  |     個数    |     説明                                                                                                                        |     秋月電子通販コード例             |
|--------------------------------------|-------------------------------------------|-------------|---------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
|     C1, C2, C4, C5, C12, C13, C19    |     0.1uF                                 |     7       |     パスコン。5mmピッチ                                                                                                         |     [P-10147](https://akizukidenshi.com/catalog/g/gP-10147/)                          |
|     C8-C11, C15-C18              |     10uF                                  |     8       |     電解コンデンサ。2.5mmピッチ                                                                                                   |     [P-15828](https://akizukidenshi.com/catalog/g/gP-15828/), [P-04624](https://akizukidenshi.com/catalog/g/gP-15828/) など       |
|     C3                               |     100uF                                 |     1       |     電源用。2.5mmピッチ                                                                                                         |     [P-02724](https://akizukidenshi.com/catalog/g/gP-02724/)                          |
|     C6                               |     10uF                                 |     1       |     電源用。2mmピッチ                                                                                                         |     [P-17897](https://akizukidenshi.com/catalog/g/gP-17897/)                          |
|     C7                               |     1000uF                                |     1       |     電源用。OS-CON 1000uF 6.4V                                                                                                  |    [P-08293](https://akizukidenshi.com/catalog/g/gP-08293)                          |
|     C14                              |     1000pF                                |     1       |     ローパス用                                                                                                                  |    [P-14587](https://akizukidenshi.com/catalog/g/gP-14587/)                          |
|     D1                               |     LED                                   |     1       |     5mm LED 3Vくらい。好きな色で                                                                                                |                                      |
|     R2, R3, R14, R16-R22             |     1K                                    |     10      |     抵抗。よくある6.3mmのもの                                                                                                   |     [R-25102](https://akizukidenshi.com/catalog/g/gR-25102/), [R-16876](https://akizukidenshi.com/catalog/g/gR-16876/)               |
|     R8 - R9                          |     10K                                   |     2       |     R6とR7は基板上に20Kとありますが、15Kを使ってください                                                                    |     [R-25103](https://akizukidenshi.com/catalog/g/gR-25103/), [R-16877](https://akizukidenshi.com/catalog/g/gR-16877/)               |
|     R6 - R7                          |     15K                                   |     2       |     R6とR7は基板上に20Kとありますが、15Kを使ってください                                                                    |    同梱               |
|     R4, R5                           |     20K                                   |     2       |     抵抗。                                                                                                                      |       同梱                           |
|     R1, R11                          |     2K                                    |     2       |     抵抗。                                                                                                                      |       同梱                           |
|     R12                              |     330                                   |     1       |     抵抗。                                                                                                                      |       同梱                           |
|     R13                              |     620                                   |     1       |     抵抗。                                                                                                                      |       同梱                           |
|     R15                              |     3.3K                                  |     1       |     抵抗。                                                                                                                      |       同梱                           |
|     J1                               |     MJ-8435                               |     1       |     3.5mmステレオミニジャック                                                                                                   |     [C-09060](https://akizukidenshi.com/catalog/g/gC-09060/)                          |
|     FM1, FM2                         |     YM2203C                               |     2       |     FM音源IC                                                                                                                    |    別売り                                 |
|     DAC1, DAC2                       |     YM3014(B)                             |     2       |     DAC IC                                                                                                                      |    別売り                                |
|     RV1, RV2                         |     ボリューム   10ｋΩＡ                  |     2       |     音量用ボリューム。   ALPS ALPINE製 RK09D117000C                                                                             |     同梱<br>[P-14773](https://akizukidenshi.com/catalog/g/gP-14773/)                          |
|                                      |     ボリュームつまみ                      |     2       |     軸6mm。D型シャフトかイモネジ固定タイプ。直径19mm 程度まで                                                                   |     [P-16279](https://akizukidenshi.com/catalog/g/gP-16279/), [P-12202](https://akizukidenshi.com/catalog/g/gP-12202/), [P-00999](https://akizukidenshi.com/catalog/g/gP-00999/)    |
|     SW1～SW5                         |     タクトスイッチ                        |     5       |     4本足タクトスイッチ。中華製はボタンが固い。軽い操作感なら日本メーカー製                                                     |             別売り                         |
|     U1                               |     LonganNano マイコン  GD32VF103CBT6    |     1       |     Flash128KB／SRAM 32KB版   【注意】マイコン付属属のピンヘッダは太くてソケットに入りません。細いピンヘッダを使ってください    |     [K-14678](https://akizukidenshi.com/catalog/g/gK-14678)                          |
|                                      |    丸ピンＩＣ用連結ソケット40P                     |     1       |     マイコン用ピンヘッダ                                                                                                        |     [P-01382](https://akizukidenshi.com/catalog/g/gP-01382)                          |
|                                      |     丸ピンIC用   ソケット 1x40            |     1       |     マイコン用ソケット                                                                                                          |     [P-01591](https://akizukidenshi.com/catalog/g/gP-01591/)                          |
|     U2                               |     4回路オペアンプ                       |     1       |     速めのオペアンプならOK。LMC6484AIN, TLC274BCN, LME49740NA, NJM2747D など。                                     |     [I-03685](https://akizukidenshi.com/catalog/g/gI-03685/), [I-09117](https://akizukidenshi.com/catalog/g/gI-09117/) など       |
|     U3                               |     AE-Si5351A                            |     1       |     I2Cクロック生成モジュール                                                                                                   |     [K-10679](https://akizukidenshi.com/catalog/g/gK-10679/)                          |
|     U5                               |     2回路オペアンプ   NJM3414             |     1       |     ミキシング用オペアンプ。3414以外でもOK。NJM4580DD、NJM2732Dなどで動作確認済み。                                                                                      |                      同梱                |
|     U6                               |     PT2257    デジタルボリューム          |     1       |     I2C制御のデジタルボリューム                                                                                                 |     同梱                             |
|                                      |     ICソケット8P                          |     5       |                                                                                                                                 |     [P-00035](https://akizukidenshi.com/catalog/g/gP-00035/)                          |
|                                      |     ICソケット14P                         |     1       |                                                                                                                                 |     [P-00028](https://akizukidenshi.com/catalog/g/gP-00028/)                          |
|                                      |     ICソケット40P                         |     2       |                                                                                                                                 |     [P-00034](https://akizukidenshi.com/catalog/g/gP-00034/)                          |

## VGM データの保存方法など

SD カードにディレクトリを作って、その中に VGM フォーマットファイルを保存します。ファイルには「.vgm」の拡張子が必要です。ZIP 圧縮された VGM ファイルである「\*.vgz」は認識しません。解凍して .vgm の拡張子をつけてください。不要なファイル、空のディレクトリは削除してください。

## フォルダ単位の音量減衰設定

YM2203 はアーケードとパソコンでは音量レベルが全然異なるため、このプログラムではフォルダ単位で音量低減率を指定できます。<br>
各フォルダに「att4」「att6」「att8」「att10」「att12」「att14」という名前の空ファイルを配置すると、それぞれ 4 ～ 14dB 音量を低減できます。例えば、PC-8801 版「YsII」とアーケード版「戦場の狼」を同じくらいの音量にしたいなら、戦場の狼のフォルダを att8 ～ att10 くらいにすればいい感じになります。

## ノイズについて

### SD カードのアクセスノイズ

SD カードにデータ読み込みをするときにブツブツとノイズが出ることがあります。これはアクセス時に大きく電圧降下が起こるのが原因で、SD カードの種類によってノイズが目立つものと目立たないものがあります。いろいろ試してノイズの少ないものを使うのがおすすめです。

### PC 電源のノイズ

PC から USB で電源供給を行い、さらに音声を PC に入力すると大きなグランドのループができて、ノイズが増幅されることがあります。電源は可能な限りクリーンなもの（モバイルバッテリーなど）を使ってください。
<br>
<br>

## 既知の問題点

- 一部の vgm ファイルで音が間延びする。
<br><br>

### Old DIP Version (Release 1.1)
**DIP Version (黒基板）**<br>
<img src="https://user-images.githubusercontent.com/13434151/195284256-cfec6f33-9b92-4837-a669-27ec8e1c7c0f.jpg" width="800"><br>
<br>
<br>
**DIP Version (白基板）**<br>
<img src="https://user-images.githubusercontent.com/13434151/202901795-4f4dd9eb-9767-4a9e-bcf6-8ced674c2f6d.jpg" width="800"><br>
<br>

### SOP Version
<img src="https://user-images.githubusercontent.com/13434151/120786824-a1b28000-c569-11eb-9812-0c7c2944c75d.jpg" width="640">
<br>
<img src="https://user-images.githubusercontent.com/13434151/120786795-9b240880-c569-11eb-9b5f-49e75440f9e1.jpg" width="640">

### GD32 DFU Tool
https://github.com/SeeedDocument/GD32VF103/blob/master/res/GD32_MCU_Dfu_Tool_V3.8.1.5784_1.rar
