---
theme: default
title: ボードゲームを作ってみよう！
info: CoderDojo 青山 #12
colorSchema: light
aspectRatio: 16/9
fonts:
  sans: M PLUS Rounded 1c
  weights: '400,700,800'
transition: slide-left
layout: cover
class: text-center
---

<div class="text-7xl mb-4">🎲 ♟️ 🧩</div>

# ボードゲームを作ってみよう！

<div class="text-2xl font-bold mt-4">CoderDojo 青山 #12</div>
<div class="text-lg mt-2 opacity-70">青学つくまなラボ</div>

---

# きょうやること

じぶんだけの **オリジナルボードゲーム** を作って、みんなであそぼう！

<div class="steps mt-6">
<div class="card"><div class="icon">💡</div><h3>かんがえる</h3>どんなゲームにする？</div>
<div class="arrow">▶</div>
<div class="card"><div class="icon">🛠️</div><h3>つくる</h3>駒・ダイス・盤</div>
<div class="arrow">▶</div>
<div class="card"><div class="icon">🎮</div><h3>あそぶ</h3>ためして、なおす</div>
<div class="arrow">▶</div>
<div class="card"><div class="icon">📣</div><h3>みせる</h3>みんなにしょうかい</div>
</div>

<div class="note">きょう完成しなくても大丈夫。「あそべるところまで」をめざそう。</div>

---

# ボードゲームは何でできている？

<div class="cards c4 mt-4">
<div class="card"><div class="icon">🗺️</div><h3>盤（ばん）</h3>駒をおく場所。マスや道がかいてある。</div>
<div class="card"><div class="icon">♟️</div><h3>駒（こま）</h3>プレイヤーやキャラクター。動かしてあそぶ。</div>
<div class="card"><div class="icon">🎲</div><h3>ダイス</h3>ふって数をきめる。運（うん）の要素。</div>
<div class="card"><div class="icon">📜</div><h3>ルール</h3>どう動かす？ どうなったら勝ち？</div>
</div>

<div class="note">ぜんぶ使わなくてもいい。ダイスなしのゲームも、盤なしのゲームもある。</div>

---

# 見本：どうぶつしょうぎ

<div class="flex gap-10 items-center">
  <DobutsuBoard />
<div class="flex-1">

- マスは **3 × 4** の 12 マスだけ
- 駒は **4 しゅるい**、ひとり 4 個
- かわりばんこに 1 個ずつ動かす
- 相手の駒がいるマスに動くと、**その駒をとれる**
- とった駒は、じぶんの駒として **あいているマスにおける**

<div class="note">小さな盤・少ない駒でも、しっかり考えるゲームになる！</div>

</div>
</div>

---

# どうぶつしょうぎ：駒の動き

<div class="flex justify-around mt-6 text-center">
<div><Piece emoji="🦁" name="ライオン" :size="110" :dirs="['n','ne','e','se','s','sw','w','nw']" /><div class="text-base mt-1">まわり 8 方向</div></div>
<div><Piece emoji="🐘" name="ぞう" :size="110" :dirs="['ne','se','sw','nw']" /><div class="text-base mt-1">ななめ 4 方向</div></div>
<div><Piece emoji="🦒" name="きりん" :size="110" :dirs="['n','e','s','w']" /><div class="text-base mt-1">たて・よこ 4 方向</div></div>
<div><Piece emoji="🐥" name="ひよこ" :size="110" :dirs="['n']" /><div class="text-base mt-1">前に 1 マスだけ</div></div>
<div><Piece emoji="🐔" name="にわとり" :size="110" :dirs="['n','ne','e','s','w','nw']" /><div class="text-base mt-1">ひよこが成長！</div></div>
</div>

<div class="mt-6">

- どの駒も動けるのは **1 マスだけ**。赤い点の方向に動ける
- ひよこは、いちばんおくの列に入ると **にわとり** にかわる
- 勝ち方は 2 つ：相手のライオンをとる **「キャッチ」**／じぶんのライオンがいちばんおくの列に入る **「トライ」**

</div>

---

# どうぶつしょうぎの「うまい工夫」

じぶんのゲームにも使えるアイデアがいっぱい。

<div class="cards c2 mt-4">
<div class="card"><h3>🔴 動き方が駒にかいてある</h3>赤い点を見ればわかるので、ルールをおぼえなくていい。</div>
<div class="card"><h3>📏 盤が小さい</h3>12 マスだけ。すぐ作れて、1 回のゲームもすぐおわる。</div>
<div class="card"><h3>🐥 駒がへんしんする</h3>ひよこ → にわとり。うらがえすだけでパワーアップ。</div>
<div class="card"><h3>🏁 勝ち方がはっきり</h3>「ライオンをとる」「おくまで行く」。だれが見てもわかる。</div>
</div>

---

# じぶんのゲームを考えよう

<div class="cards c2 mt-2">
<div class="card">

### 🧠 きめること

- **テーマ**：うちゅう？ おばけ？ おすし？
- **盤**：マスはいくつ？ どんな形？
- **駒**：何しゅるい？ どう動く？
- **勝ち方**：ゴールする？ 相手をとる？
- **ダイス**：使う？ 使わない？

</div>
<div class="card">

### 🎯 ゲームのタイプの例

- **すごろく型**：ダイスをふってゴールをめざす
- **たいせん型**：どうぶつしょうぎのように駒をとりあう
- **じんとり型**：マスをたくさんとった人の勝ち
- **きょうりょく型**：みんなでクリアをめざす

</div>
</div>

<div class="note">まよったら「どうぶつしょうぎの駒とテーマだけ変える」からはじめよう。</div>

---

# 作り方は 3 つ。組み合わせても OK

<div class="cards c3 mt-4">
<div class="card"><div class="icon">🖨️</div><h3>3D プリンター</h3>Layerling で形を作ってプリント。<br>駒・ダイス・盤、どれも作れる。</div>
<div class="card"><div class="icon">✏️</div><h3>紙</h3>手がき、またはパソコンで作って印刷。<br>盤を作るのにぴったり。</div>
<div class="card"><div class="icon">🐱</div><h3>Scratch</h3>画面の中にゲームを作る。<br>ダイスだけ Scratch、でもいい。</div>
</div>

<div class="note">おすすめ：<b>駒とダイスは 3D プリンター</b>、<b>盤は紙</b>。プリントには時間がかかるので、盤は紙だと早くあそべる。</div>

---

# Layerling で駒を作る ①　はじめかた

<div class="mt-2">

<span class="num">1</span> ブラウザーでここをひらく

<div class="big-url ml-10"><a href="https://tukumana.si.aoyama.ac.jp/3dp/cd-aoyama" target="_blank">tukumana.si.aoyama.ac.jp/3dp/cd-aoyama</a></div>

<span class="num">2</span> **「参加する」** をおす

<span class="num">3</span> **「表示名」** にニックネームを入れる（本名は入れない）

<span class="num">4</span> もういちど **「参加する」** をおして、作品を作りはじめる

</div>

<div class="note">「PIN」に 4 けたの数字を入れておくと、べつのパソコンからもつづきができる。<br>前に参加したことがある人は「ログイン ID」と「PIN」でログイン。</div>

---

# Layerling で駒を作る ②　形の作り方

<div class="steps mt-4">
<div class="card"><div class="icon">🟦</div><h3>おく</h3>プレートにシェイプ（形）をおく</div>
<div class="arrow">▶</div>
<div class="card"><div class="icon">↔️</div><h3>のばす</h3>ドラッグして大きさをきめる</div>
<div class="arrow">▶</div>
<div class="card"><div class="icon">🕳️</div><h3>あなにする</h3>2 つめのシェイプを「穴」にする</div>
<div class="arrow">▶</div>
<div class="card"><div class="icon">🔗</div><h3>くっつける</h3>えらんで「グループ化」</div>
</div>

<div class="mt-5">

- ボックス、円柱、球、円すい、**文字** などのシェイプがある
- 角は **フィレット** でまるく、**面取り** でななめにできる
- こまったら <a href="https://layerling.com/guide/index.html" target="_blank">Layerling ユーザーガイド</a> かメンターに聞こう

</div>

---

# 駒づくりのコツ

<div class="cards c2 mt-2">
<div class="card"><h3>📐 大きさは 2 cm くらい</h3>小さすぎるとつまみにくい。大きすぎるとプリントに時間がかかる。</div>
<div class="card"><h3>⬇️ 底はたいらに</h3>プレートにぴったりつく面があると、きれいにプリントできて、たおれない。</div>
<div class="card"><h3>👀 しゅるいが見てわかる</h3>形・高さをかえる。文字や絵をほる。動ける方向に点をつけるのもいい。</div>
<div class="card"><h3>🎨 だれの駒かわかる</h3>プレイヤーごとに色（フィラメント）をかえる。向きがわかる形にする。</div>
</div>

<div class="note">時間はかぎられている。まずは <b>1 しゅるい作ってプリントに出す</b> → まっている間につぎを作ろう。</div>

---

# ダイスを作る

<div class="flex gap-8 items-start">
<div class="flex-1">

<span class="num">1</span> **ボックス** をおいて、たて・よこ・高さを同じにする（16 mm くらい）

<span class="num">2</span> 角を **フィレット** でまるくする（よくころがる）

<span class="num">3</span> 小さな円柱や文字を **穴** にして、目をほる

<span class="num">4</span> ぜんぶえらんで **グループ化**

<div class="note">ふつうのダイスは、うらおもての目をたすと <b>7</b>。<br>1 のうらは 6、2 のうらは 5、3 のうらは 4。</div>

</div>
<div class="card w-80">

### 🌟 オリジナルダイス

- 目は数字じゃなくてもいい
  「⭐ もう 1 回」「💤 1 回休み」
- 1・2・3 が 2 つずつのダイス
- 6 面じゃないダイス
  （多角柱をころがす）

</div>
</div>

---

# 盤を作る

<div class="cards c3 mt-2">
<div class="card"><div class="icon">✏️</div><h3>紙に手がき</h3>いちばん早い。じょうぎでマスをかいて、絵や色もじゆうに。すぐになおせる。</div>
<div class="card"><div class="icon">🖨️</div><h3>紙に印刷</h3>パソコンでかいて印刷。Scratch のステージにかいた盤を印刷してもいい。</div>
<div class="card"><div class="icon">🧱</div><h3>3D プリンター</h3>うすい板にマスのみぞをほる。駒がずれにくい。大きいと時間がかかるので小さめに。</div>
</div>

<div class="mt-4">

- マスの大きさは **駒より少し大きく**（駒が 2 cm なら、マスは 2.5〜3 cm）
- スタート・ゴール、とくべつなマスは **色や絵** でわかるように

</div>

<div class="note">さいしょは紙の盤であそんでみて、ルールがきまってから 3D プリンターで作るのもおすすめ。</div>

---

# Scratch で作る

<div class="flex gap-8 items-start">
<div class="flex-1">

子供の科学の記事 **「みんなで遊べるすごろくをつくろう」** が見本になる。

- `1` キーをおすと、サイコロをふる
  （**1 から 6 までの乱数**）
- 出た目の数だけ、駒がマスを進む
- **緑のマス** にとまると「3 マスもどる」
- ほかにも「ふりだしにもどる」「ワープする」「1 回休み」など、しかけをふやせる

<a href="https://www.kodomonokagaku.com/experience/programming/32384/" target="_blank">すごろくに「3マス戻る」のマスを追加する（コカネット）</a>

</div>
<div class="card w-80">

### 📦 見本プロジェクト

記事のページから `sugoroku.zip` をダウンロード
→ ひらいて出てくる `sugoroku.sb3` を Scratch で読みこむ

<div class="text-sm opacity-70 mt-2">監修：阿部和広さん<br>子供の科学 2022 年 1 月号</div>

</div>
</div>

---

# 組み合わせのアイデア

<div class="cards c2 mt-4">
<div class="card"><h3>🧩 + ✏️　3D の駒 × 紙の盤</h3>駒とダイスをプリントしている間に、紙に盤をかく。いちばん作りやすい。</div>
<div class="card"><h3>♟️ + 🐱　ほんものの駒 × Scratch のダイス</h3>ダイスは Scratch でふる。「10 から 60 までの乱数」など、とくべつなダイスもすぐ作れる。</div>
<div class="card"><h3>🐱 → 🖨️　Scratch の盤を印刷</h3>Scratch のステージにかいたすごろくの盤を印刷して、3D の駒であそぶ。</div>
<div class="card"><h3>🗺️ + 🐱　ほんものの盤 × Scratch のイベント</h3>とくべつなマスにとまったら、Scratch が「何がおこるか」をきめてくれる。</div>
</div>

---

# あそんで、なおそう

作ったら、**すぐにあそんでみる** のがいちばん大事。

<div class="cards c3 mt-4">
<div class="card"><div class="icon">⏱️</div><h3>長すぎない？</h3>おわらないときは、盤を小さく、ゴールを近く。</div>
<div class="card"><div class="icon">⚖️</div><h3>ずるくない？</h3>先にやる人ばかり勝つなら、ルールをかえる。</div>
<div class="card"><div class="icon">😆</div><h3>もりあがる？</h3>ぎゃくてんできるしかけを入れてみる。</div>
</div>

<div class="note">ルールは紙にかいておこう。はじめての人が読んであそべたら、かんせい！</div>

---
layout: center
class: text-center
---

# さあ、作ってみよう！

<div class="text-left inline-block mt-4">

- Layerling（CoderDojo 青山のルーム）
  <a href="https://tukumana.si.aoyama.ac.jp/3dp/cd-aoyama" target="_blank">tukumana.si.aoyama.ac.jp/3dp/cd-aoyama</a>
- Layerling ユーザーガイド
  <a href="https://layerling.com/guide/index.html" target="_blank">layerling.com/guide</a>
- Scratch ですごろく（コカネット）
  <a href="https://www.kodomonokagaku.com/experience/programming/32384/" target="_blank">kodomonokagaku.com/experience/programming/32384</a>
- Scratch
  <a href="https://scratch.mit.edu/" target="_blank">scratch.mit.edu</a>

</div>

<div class="text-lg mt-6 opacity-70">わからないことは、メンターに聞いてね 🙋</div>
