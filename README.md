ぷよぷよは、現在では、[ぷよぷよプログラミング](https://puyo.sega.jp/program_2020/)でソースコードが公開されて、
手軽にプログラミングできるようになっています。

ぷよぷよプログラミングは、最終的な形が用意されていて、それを写経することでプログラミングを学んでいきます。
それはそれでとても良い方法と思うのですが、もう少しゲームを少しずつ作れないかなぁと感じていました。

ゲーム制作の学習の手始めは、ゲームエンジンやプログラミング言語を学ぶことが多いのではないでしょうか。
ただ、それでゲームが作れるようになれるかと言えばさにあらず。
面白そうなゲームを考えたとしても、何をどのように実現すれば完成するのか事を網羅的に列挙しなくてはなりません。
これは骨の折れる仕事ですが、その方法はなかなか説明されていないように思います。
そもそも、ゲーム開発は、少しづつ作って、できたものを見て修正しながら完成を目指すスタイルも多いです。
であれば、途中過程を残しながらゲームを実際に作ってみるのがゲームの設計方法を学ぶのに良いのではないかと考えました。

今回の試みは、そのような考え方の手始めの物で、
まっさらな状態から、だんだんとぷよぷよを作っていこうと思います。

ぷよぷよプログラミングのコードを見ないで作っているので、微妙に本物と処理が違っていると思いますが、その点はごめんなさい。

# 各ステップ

## 1. 仮想空間にオブジェクトを置いてみる

[`解説へ飛ぶ!`](https://github.com/puzzle-study/01_create_project) Unityのプロジェクトを作って枠やぷよっぽいものを置いてみます。

![結果1](images/result_01.png)

## 2. 動かすキャラクターを置く

[`解説へ飛ぶ!`](https://github.com/puzzle-study/02_prefab) Unityのプレハブ機能を使って、スクリプト付きのオブジェクトを素材として扱ってみます。

![結果2](images/result_02.png)

## 3. 盤面をモデル化する

[`解説へ飛ぶ!`](https://github.com/puzzle-study/03_board) 仮想的な3次元空間とは別に２次元配列を用意して、物体の配置を管理します。

![結果3](images/result_03.png)

## 4. 左右移動

[`解説へ飛ぶ!`](https://github.com/puzzle-study/04_player)  キー入力を受けて、左右に動かせるようにします。

<video src="https://user-images.githubusercontent.com/936545/155824085-2426c928-6faf-4c8d-9627-8e74e8992b76.mp4" controls="controls" style="max-width: 100%;"></video>

## 5. 回転

[`解説へ飛ぶ!`](https://github.com/puzzle-study/05_rotate) ぷよぷよを回転させます。おまけとして、上を押した時に瞬間的に移動するクイックドロップも実装してみます。

<video src="https://user-images.githubusercontent.com/936545/155824493-863e47eb-75f6-4682-8d92-05b47fe7f5df.mp4" controls="controls" style="max-width: 100%;"></video>

## 6. アニメーションして動く

[`解説へ飛ぶ!`](https://github.com/puzzle-study/06_animation) 何フレームかかけて移動・回転するアニメーションさせてみます。

<video src="https://user-images.githubusercontent.com/936545/155825023-d2ec379d-8ce1-40a9-8131-c3ac43f4f866.mp4" controls="controls" style="max-width: 100%;"></video>

## 7. ロジックの固定フレームレート化

[`解説へ飛ぶ!`](https://github.com/puzzle-study/07_fixed_update) ゲームロジックを固定フレームレートの処理に変えて、ゲームのプレイ感覚をPC等のスペックに依存しないようにします。

今回の結果は、前回と違いがありません。

## 8. 重力落下

[`解説へ飛ぶ!`](https://github.com/puzzle-study/08_fall) 少しずつぷよぷよを落とします。

<video src="https://user-images.githubusercontent.com/936545/155826203-08534a20-c7ec-482e-9e8a-fc33dbe2762b.mp4" controls="controls" style="max-width: 100%;"></video>

## 9. 次のぷよぷよを落とす

[`解説へ飛ぶ!`](https://github.com/puzzle-study/09_next) ぷよが下に着いたら、ランダムな色の新しいぷよを出します。

<video src="https://user-images.githubusercontent.com/936545/155825884-d5c6e4ae-dc41-4ed9-8770-cedcf61f5190.mp4" controls="controls" style="max-width: 100%;"></video>

## 10. ゲームの流れを作る

[`解説へ飛ぶ!`](https://github.com/puzzle-study/10_gameover) ゲームオーバーになったらリスタートするようにします。

<video src="https://user-images.githubusercontent.com/936545/155826116-5ef255ec-5d9c-49f1-8b31-2a7c25045321.mp4" controls="controls" style="max-width: 100%;"></video>

## 11. 下が空間なら落ちる

[`解説へ飛ぶ!`](https://github.com/puzzle-study/11_falling_state) ぷよぷよが固定されたとき、下の空間に何もなければ、千切れて下に落ちます。

<video src="https://user-images.githubusercontent.com/936545/155828110-8f43b9f8-1fe4-4fd2-9933-8d8a227cc16c.mp4" controls="controls" style="max-width: 100%;"></video>

## 12. 4つ以上くっついたぷよは消す

[`解説へ飛ぶ!`](https://github.com/puzzle-study/12_erase) ぷよが固定された時に、4つ以上の同じ色のぷよがくっついていたら消します。

<video src="https://user-images.githubusercontent.com/936545/155828497-2a1c9ba8-1496-43e0-93d7-388f7fd400b1.mp4" controls="controls" style="max-width: 100%;"></video>

## 13. 得点を計算する

[`解説へ飛ぶ!`](https://github.com/puzzle-study/13_score) 得点計算をして表示します。

<video src="https://user-images.githubusercontent.com/936545/155828911-2c03fc47-ec24-40c3-9cb0-72178c2e1e59.mp4" controls="controls" style="max-width: 100%;"></video>

## 14. タイトル画面の追加

[`解説へ飛ぶ!`](https://github.com/puzzle-study/14_title) タイトル画面をつけて、ゲーム全体の流れをつけます。

<video src="https://user-images.githubusercontent.com/936545/155829021-4bb291f4-bdfa-4b6b-8eab-6cb9a34f09c7.mp4" controls="controls" style="max-width: 100%;"></video>

