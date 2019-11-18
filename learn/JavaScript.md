# JavaScript note
JavaScript関連の学び所感のメモ書き

## React
- 2019/11/17時点で考える良さげな開発の流れ
  - 各動作、UI部品を構成するパーツでコンポーネント作成
  - 意味や配置上のまとまりで↑をラップするコンポーネント作成
  - 全体をラップする

## Jest
- `describe`と`it`しか見当たらないので文脈をどこに書くか悩み中
- assertと組み合わせて`assert(hogehoge)`とするか`expect(...)`とするのどっちがいいか思案

## Enzyme
- `find(selector)`は`shallowWrapper`,`exists(selector)`は`boolean`を返すので使い分け注意[参考](https://airbnb.io/enzyme/docs/api/ShallowWrapper/find.html)

## WebPack

## babel
- Jestで使うときに.babelrcに`@babel/preset-env`,`@babel/preset-react`を追加した
  - ↑が必要な理由は要確認 [参考](https://qiita.com/sand/items/af2af0766ca00558457d)
- presetは@org/nameの形式で配布されてるらしい

## ESLint
- デフォルトだとdevdependencyのライブラリのimportで怒られる
  - spec/.eslintrc.jsonに'devDependencies: true'を追加して許してもらった.
  - 他にも`devDependencies: [import可能としたいファイル名]`とするのもありらしい。
- テスト系の構文をESLintくんが認識してくれないので、spec.jsファイルの冒頭に`/* eslint-env jest */と書いて認識してもらった
