# 正規表現

## 検索置換
例えば
```
<div className="sample-class">
```
を
```
<div className={styles['sample-class']}>
```

にしたいとき。

## 1.サンプルケースをコピってくる
置換したい場所をまるっともってくる

```
className="sample-class"
```
## 2.エスケープするべき文字をエスケープする

「正規表現　エスケープ」とかでぐぐりましょう。
今回はエスケープしないといけない文字はないので省略

## 3.置換後のパターンをつくる
今回はこう

```
className={styles['sample-class']}
```

## 4.任意の文字列になるべきところを置き換える
今回は`sample-class`のところが任意の文字列になればいいので

```
<div className="(.*)">
```

とし、置換後の文字列を

```
className={styles['$1']}
```
とする。

### それぞれの意味
`()`置き換えるブロック。この中身を引き継ぐ。
`.*` => `.`は「適当な文字」、`*`は「０回以上繰り返し」なので`.*`は「何かしら文字列が存在したら」
`$1` => `()`の中身を引き継ぐ









