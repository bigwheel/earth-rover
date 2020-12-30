# sasori-kakko-kari とは？

[無限の可能性](https://github.com/swanmatch/MxLEDBitPCB)から生まれた機械生命体です。
普段はマクロパッドに擬態して人間と共生しています。

# ビルドガイド

一度自作キーボードを作ったことがある人を想定して書いています。
初めての作成でもできなくないかもしれませんが特に道具などの使い方について詳しくないためより丁寧な説明が書かれている[Claw44ビルドガイド \| yfuku docs](https://yfuku.com/claw44/buildguide/)などを参考にしてください。

## 構成要素

| 名前 | 数 | 備考 |
|:-|:-|:-|
| 無限の可能性(以下のどれか1つ) | | |
| 1. [無限の可能性『ConTaiNeR』\(kailhソケット版\) \- 魔界鍵盤製作所 \- BOOTH](https://swanmatch.booth.pm/items/1940367) | 1枚(14セル) | [スイッチ用PCBソケット（10個入り） \| 遊舎工房](https://yushakobo.jp/shop/a01ps/)(MX用)も14個必要 |
| 2. [無限の可能性『SuXeN』 \- 魔界鍵盤製作所 \- BOOTH](https://swanmatch.booth.pm/items/1940247) | 1枚(14セル) | |
| 3. [Chocっとした可能性\(ロープロ挟ピッチ版\) \- 魔界鍵盤製作所 \- BOOTH](https://swanmatch.booth.pm/items/1940394) | 1枚(18セル) | これを使用する場合は以下14個を18個へ適時読み替えてください|
| [ProMicroSocket\(プロマイクロのおうち\) \- 魔界鍵盤製作所 \- BOOTH](https://swanmatch.booth.pm/items/1073313) | 1個 | |
| [Pro Micro （コンスルー付き） \| 遊舎工房](https://yushakobo.jp/shop/promicro-spring-pinheader/) | 1個 | |
| [【保守部品】タクタイルスイッチ \| 遊舎工房](https://yushakobo.jp/shop/a0800ts-01-1/) | 1個 | |
| [【保守部品】ダイオード　リードタイプ（100個入り） \| 遊舎工房](https://yushakobo.jp/shop/a0800di-01-100/) | 14本 | |
| キースイッチ | 14個 | 選択した無限の可能性に合わせてMX互換またはchoc互換のものを選んでください |
| キーキャップ | 1u 14個 | |
| エナメル線またはリード線 | | |

MX用とChoc用のどちらの無限の可能性でも作成できますが、全長がProMicroSocket依存なのでChoc用のほうが小さいわけではないです。
むしろChoc用のほうがぎりぎり収まらないために全長がMX用より長くなっています(ProMicroSocketの不要部分を切る、あるいはProMcroへ直接配線するなどでより小さく作ることは可能ですが、配線やファームウェアなどの調整が必要になります)。

## 育成方法

### 外骨格の作成

無限の可能性からsasori-kakko-kariの外骨格を作ります。

まず無限の可能性の方向を自分と正対するように目の前に置きます(文字が自然に読める方向 & ダイオードのアイコンが手前側です)。
次に以下の部分をニッパーで切ってください。

<figure>
<figcaption>ConTaiNeRまたはSuXeNの場合</figcaption>
<img src="./cut-container.jpg" height=256px />
</figure>

<figure>
<figcaption>Chocっとした可能性の場合</figcaption>
<img src="./cut-choc.jpg" height=256px />
</figure>

※ 別の切り方もできますがダイオードの方向が変わってくるためこの後説明しやすい切り方にしています

最後にニッパーで切ったときにできた尖った部分を棒ヤスリなどでなめらかにしましょう(僕は[これ](https://www.amazon.co.jp/dp/B00FPJH02C)を使っています)。sasori-kakko-kariは文字通り外骨格が外部に露出しているため尖った部分が残っていると指を切る可能性があります。
棒ヤスリがない場合はニッパーでなるべくギリギリまで切ってから紙やすりでなめらかにしましょう(あれば)。

<figure>
<figcaption>ヤスリがけ前の状態</figcaption>
<img src="./togatteru.jpg" height=256px />
</figure>

<figure>
<figcaption>最終的な外骨格1セット</figcaption>
<img src="./yasuri-ed.jpg" height=256px />
</figure>

### 神経節の取り付け

ダイオードを外骨格へ取り付けます。

| ![](./diode-raw.jpg) | ![](./diode-set.jpg) |
| ---- | ---- |
| ダイオードの足を折ります。ベンダーがあると便利です。 | ダイオードを外骨格上へ仮止めします。マスキングテープがあると便利です |
| ![](./diode-set2.jpg) | ![](./diode-finish.jpg) |
| 裏から見るとこんな感じ | はんだ付けを行いニッパーで余分な足を切ります。このとき切った足は後で使いますので残しておきましょう。 |


### 鱗の根っこを付ける

無限の可能性ConTaiNeRを使用している人はここで[スイッチ用PCBソケット（10個入り） \| 遊舎工房](https://yushakobo.jp/shop/a01ps/)を付けます。
ソケットには上下があるのでシルクに合わせて取り付けましょう。

<figure>
<img src="./socket.jpg" height=256px />
</figure>

PCBソケットははんだ付けがしやすい反面、見た目でハンダされているかが分かりづらかったりハンダされていなくても通電することがあるので後になって接触不良による動作不良の原因になりやすいです。
このタイミングで以下の点を確認しましょう。

1. 浮いているソケットがないこと
2. ハンダされていない足がないこと
3. 向きが間違っているソケットがないこと
