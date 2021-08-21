## 第一部 多国通貨

### 第5章 原則をあえて破る時

#### TODO
* [ ] $5 + 10CHF = $10
* [x] $5 * 2 = $10
* [ ] amountをprivateにする
* [x] Dollar sideeffect
* [ ] Moneyの丸め処理
* [ ] *equals()*
* [ ] hashCode
* [ ] nullとの等価性能比較
* [ ] 他のオブジェクトとの等価性能比較
* [ ] **5CHF * 2 = 10CHF**

1. テストを書く
2. コンパイラを通す
3. テストを走らせ、失敗を確認する
4. テストを通す
5. 重複を排除する

#### この章の振り返り

* 大きいテストに立ち向かうにはまだ早かったので、次の一歩を進めるために小さなテストを捻り出した
* 恥知らずにも既存のテストをコピー&ペーストして、テストを作成した
* さらに恥知らずにも、既存のモデルコードを丸ごとコピー&ペーストしてテストを通した
* この重複を排除するまでは家に帰らないと心に決めた

### 第6章 テスト不足に気づいたら

#### TODO
* [ ] $5 + 10CHF = $10
* [x] $5 * 2 = $10
* [x] amountをprivateにする
* [x] Dollar sideeffect
* [ ] Moneyの丸め処理
* [x] *equals()*
* [ ] hashCode
* [ ] nullとの等価性能比較
* [ ] 他のオブジェクトとの等価性能比較
* [x] 5CHF * 2 = 10CHF
* [ ] DollarとFrancの重複
* [ ] **equalsの一般化**
* [ ] timesの一般化

#### この章の振り返り
* Dollarクラスから親クラスMoneyへ段階的にメソッドを移動した
* 2つ目のクラス(Franc)も同様にサブクラス化した
* 2つ目のequalsメソッドの差異をなくして、サブクラス側の実装を削除した

#### TODO
* [ ] $5 + 10CHF = $10
* [x] $5 * 2 = $10
* [x] amountをprivateにする
* [x] Dollar sideeffect
* [ ] Moneyの丸め処理
* [x] *equals()*
* [ ] hashCode
* [ ] nullとの等価性能比較
* [ ] 他のオブジェクトとの等価性能比較
* [x] 5CHF * 2 = 10CHF
* [ ] DollarとFrancの重複
* [x] equalsの一般化
* [ ] timesの一般化

### 第7章 疑念をテストに翻訳する

#### TODO
* [ ] $5 + 10CHF = $10
* [x] $5 * 2 = $10
* [x] amountをprivateにする
* [x] Dollar sideeffect
* [ ] Moneyの丸め処理
* [x] *equals()*
* [ ] hashCode
* [ ] nullとの等価性能比較
* [ ] 他のオブジェクトとの等価性能比較
* [x] 5CHF * 2 = 10CHF
* [ ] DollarとFrancの重複
* [x] equalsの一般化
* [ ] timesの一般化
* [ ] **FrancとDollarを比較する**

#### この章の振り返り
* 頭の中にある悩みをテストとして表現した(FrancとDollarを比較したらどうなる？)
* 完璧ではないものの、まずまずのやり方(constoructor.name===constructor.name)でテストを通した
* 更なる設計は、本当に必要になる時まで先延ばしすることにした

#### TODO
* [ ] $5 + 10CHF = $10
* [x] $5 * 2 = $10
* [x] amountをprivateにする
* [x] Dollar sideeffect
* [ ] Moneyの丸め処理
* [x] *equals()*
* [ ] hashCode
* [ ] nullとの等価性能比較
* [ ] 他のオブジェクトとの等価性能比較
* [x] 5CHF * 2 = 10CHF
* [ ] DollarとFrancの重複
* [x] equalsの一般化
* [ ] timesの一般化
* [x] **FrancとDollarを比較する**

### 第8章 実装を隠す

#### TODO
* [ ] $5 + 10CHF = $10
* [x] $5 * 2 = $10
* [x] amountをprivateにする
* [x] Dollar sideeffect
* [ ] Moneyの丸め処理
* [x] *equals()*
* [ ] hashCode
* [ ] nullとの等価性能比較
* [ ] 他のオブジェクトとの等価性能比較
* [x] 5CHF * 2 = 10CHF
* [ ] **DollarとFrancの重複**
* [x] equalsの一般化
* [ ] timesの一般化
* [x] FrancとDollarを比較する

#### この章の振り返り
* 重複を除去できる状態に一歩近づけるために、DollarとFrancにある2つのtimesメソッドのシグニチャを合わせた
* せめてメソッド宣言だけは親クラスに移動した
* Factory Methodパターンを導入してテストコードから2つのクラスの存在を隠した
* サブクラスを隠した結果、いくつかのテストが冗長なものになったことに気づいたが、今はそのままにしておいた

### 第9章

#### TODO
* [ ] $5 + 10CHF = $10
* [x] $5 * 2 = $10
* [x] amountをprivateにする
* [x] Dollar sideeffect
* [ ] Moneyの丸め処理
* [x] *equals()*
* [ ] hashCode
* [ ] nullとの等価性能比較
* [ ] 他のオブジェクトとの等価性能比較
* [x] 5CHF * 2 = 10CHF
* [ ] DollarとFrancの重複
* [x] equalsの一般化
* [ ] timesの一般化
* [ ] **通貨の概念**
* [x] FrancとDollarを比較する

#### この章の振り返り
* 大きめの設計変更にのめり込みそうになったので、その手前にある小さめの変更に着手した
* 差異を呼び出し側(Facotry Method)に移動することで2つのサブクラスのコンストラクタを近づけて行った
* リファクタリングの途中で、少し寄り道をしてtimesメソッドの中でFactory Methodを使うようにした
* Francに行ったリファクタリングをDollarにも同様に、今度は大きい歩幅で一気に適用した
* 完全に同じ内容になった2つのコンストラクタを親クラスに引き上げて、子クラスはsuper()に移行した
  
#### TODO
* [ ] $5 + 10CHF = $10
* [x] $5 * 2 = $10
* [x] amountをprivateにする
* [x] Dollar sideeffect
* [ ] Moneyの丸め処理
* [x] equals()
* [ ] hashCode
* [ ] nullとの等価性能比較
* [ ] 他のオブジェクトとの等価性能比較
* [x] 5CHF * 2 = 10CHF
* [ ] **DollarとFrancの重複**
* [x] equalsの一般化
* [ ] timesの一般化
* [x] 通貨の概念
* [x] FrancとDollarを比較する

#### 個人的な考え

### 第10章 テストに聞いてみる
#### 目的
この章が終わる頃には、Moneyを表現するクラスは1つになっていることだろう。

##### 個人の考え(やる前)
テストに聞いてみるってなんだよ

#### TODO
* [ ] $5 + 10CHF = $10
* [x] $5 * 2 = $10
* [x] amountをprivateにする
* [x] Dollar sideeffect
* [ ] Moneyの丸め処理
* [x] equals()
* [ ] hashCode
* [ ] nullとの等価性能比較
* [ ] 他のオブジェクトとの等価性能比較
* [x] 5CHF * 2 = 10CHF
* [ ] **DollarとFrancの重複**
* [x] equalsの一般化
* [ ] **timesの一般化**
* [x] 通貨の概念
* [x] FrancとDollarを比較する

##### 個人の考え(やったあと)
* やったこと自体はシンプルで、Factoryメソッドの引数にサブクラスごとに異なる変数を入れてるだけ。これでサブクラスが持つtimesを一般化することができた
* console.log(constructor.name)がMoneyクラスとDollarクラスの比較になりテストがこける

##### 振り返り
* サブクラスのtimesメソッドの実装の差異をなくすために、まずはメソッド呼び出しをインライン化し、次にベタ書きの値を変数に置き換えた
* デバッグの用途のみに使うtoStringメソッドを、テストを書かずに実装した
* Francの代わりにMoneyを返す試みをしてみる、うごかくか動かないかはテストに聞いてみた

#### TODO
* [ ] $5 + 10CHF = $10
* [x] $5 * 2 = $10
* [x] amountをprivateにする
* [x] Dollar sideeffect
* [ ] Moneyの丸め処理
* [x] equals()
* [ ] hashCode
* [ ] nullとの等価性能比較
* [ ] 他のオブジェクトとの等価性能比較
* [x] 5CHF * 2 = 10CHF
* [ ] DollarとFrancの重複
* [x] equalsの一般化
* [x] **timesの一般化**
* [x] 通貨の概念
* [x] FrancとDollarを比較する