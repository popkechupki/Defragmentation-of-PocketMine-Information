# Minecraftサーバーについて
xboxマルチプレイやRealmsと異なり、BDSやpmmpといったMinecraftサーバーソフトでは人数上限をより多くした状態でサーバーを開くことができます。

ただし、サーバーに人を入れるためにはサーバーソフトを起動してPCを起動させたままにする必要があります。常に起動ができない環境であれば、外部のサーバーであるVPSを利用することもできます。

## サーバーの種類
MinecraftのBedrockサーバーを立てる場合には以下のソフトウェアが利用できます。

- **Bedrock Dedicated Server(BDS)** 公式・安定・フル互換
    - Minecraft公式によるサーバーソフトです。Minecraftに実装されたすべての機能が利用できます。
    - pmmpのプラグインは利用できません。
    - Windows/Ubuntu上で動作します。armでは動作しません。
- **PocketMine-MP(pmmp)** 非公式・高機能・一部機能未実装
    - 非公式のサーバーソフトです。サーバーに追加機能を加えるプラグインやマルチワールドが利用できます。
    - Minecraft本来のすべての機能が使えるわけではありません。pm4では1.12.xまでのBedrockのワールドが利用できます。
    - Windows/Mac/Linux/Android上で動作します。

## PocketMine-MPでのサーバーの立て方
[サーバーの立て方](/building/README.md)から見ることができます。

<!-- TODO
## Bedrock Dedicated Serverでのサーバーの立て方 -->


## サーバーに外部から入れるようにする
外部からサーバーを入れるためには**ポートフォワーディング**(しばしば**ポート開放**)という作業が必要になります。
ポートフォワーディングというのは外部であるインターネットから来たパケットをサーバーがある内部のネットワークに転送する機能です。

自宅サーバーの場合UPnPを利用したり、手動でルーターの設定をいじることでポートフォワーディングすることができます。ただし、ネットワークの問題でできないこともあります。

VPSの場合は大抵ポートフォワーディングを設定できる画面があるため、そこで変更することでポートフォワーディングすることができます。

!!! warning
    ポートフォワーディングはネットワークに穴を開けるような行為であり、設定によっては危険を伴います。設定がどのように働くかを理解したうえで設定することを推奨します。

## Windows10版でサーバー機と同じPCでサーバーに入る
ループバックを有効にすることで入ることができます。
Powershellを開いて

```powershell
CheckNetIsolation LoopbackExempt -a -n="Microsoft.MinecraftUWP_8wekyb3d8bbwe"
```
を実行します。

参考記事: <https://yomi-note.com/games/minectaft/477/> on 2021/11/13