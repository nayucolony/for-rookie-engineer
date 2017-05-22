# Gitの使い方

### リモートブランチから新しくブランチを切るとき
```
git checkout -b [new branch] [remote branch]
```

`checkout`はブランチを切り替えるためのコマンドだが、オプションで`-b`をつけることで「指定したブランチ名でブランチを作成し、チェックアウトする」という操作ができる。
いちいちブランチを切っては移動して、と二段階に及ぶ必要がない。

ちなみにもし`-b`を使わないとしたら
```
git checkout master  //元ブランチに移動
git fetch  // 最新の情報に更新
git branch feature/fix-top-module  //ブランチを切る
git checkout feture/fix-top-module  // チェックアウト
```

ex.
```
git checkout -b feature/fix-top-module origin/master
```

`origin/master`は「`origin`というリモートリポジトリの`master`ブランチ」を指す。

もしも
```
git checkout -b feature/fix-top-module master
```
とした場合、ローカルブランチの`master`ブランチから派生ブランチが切られる。
「リモートリポジトリが正しい状態にある」がGit開発の原則なので、常にリモートリポジトリから切ること。

もちろん、ローカルブランチの`master`が最新（=`origin/master`と差異がない)場合は問題ない。
たとえば

```
git fetch 
```
してリモートリポジトリから情報を取得した上で

```
git checkout -b feature/fix-top-module master
```

とするなど。
