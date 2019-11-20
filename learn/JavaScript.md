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
- `debug()`でshallowWrapperやReactWrapperの中身を`String`にした上で確認できる(例)`console.log(shallow(<button>start</button>).debug())`

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

## Ui-material
- <Button>タグについて
  - 最終的に<button>タグを参照するHTMLを返してる。
  ```
  <StartButton>
    <WithStyles(ForwardRef(Button)) variant="contained" color="primary" className="start" onClick={[Function: bound handleClick]}>
      <ForwardRef(Button) classes={{...}} variant="contained" color="primary" className="start" onClick={[Function: bound handleClick]}>
        <WithStyles(ForwardRef(ButtonBase)) className="MuiButton-root MuiButton-contained start MuiButton-containedPrimary" component="button" disabled={false} focusRipple={true} focusVisibleClassName="Mui-focusVisible" type="button" onClick={[Function: bound handleClick]}>
          <ForwardRef(ButtonBase) classes={{...}} className="MuiButton-root MuiButton-contained start MuiButton-containedPrimary" component="button" disabled={false} focusRipple={true} focusVisibleClassName="Mui-focusVisible" type="button" onClick={[Function: bound handleClick]}>
            <button className="MuiButtonBase-root MuiButton-root MuiButton-contained start MuiButton-containedPrimary" onBlur={[Function]} onClick={[Function: bound handleClick]} onFocus={[Function]} onKeyDown={[Function]} onKeyUp={[Function]} onMouseDown={[Function]} onMouseLeave={[Function]} onMouseUp={[Function]} onDragLeave={[Function]} onTouchEnd={[Function]} onTouchMove={[Function]} onTouchStart={[Function]} tabIndex={0} type="button" disabled={false}>
              <span className="MuiButton-label">
                stop
              </span>
              <NoSsr>
                <WithStyles(undefined) center={false}>
                  <ForwardRef(TouchRipple) classes={{...}} center={false}>
                    <span className="MuiTouchRipple-root">
                      <TransitionGroup component={{...}} exit={true} childFactory={[Function: childFactory]} />
                    </span>
                  </ForwardRef(TouchRipple)>
                </WithStyles(undefined)>
              </NoSsr>
            </button>
          </ForwardRef(ButtonBase)>
        </WithStyles(ForwardRef(ButtonBase))>
      </ForwardRef(Button)>
    </WithStyles(ForwardRef(Button))>
  </StartButton>
  ```
