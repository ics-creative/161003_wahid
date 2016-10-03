# CreateJS互換ライブラリ「wahid」を試してみた

「[CreateJS 互換ライブラリ wahid の開発 — Mobage Developers Blog](http://developers.mobage.jp/blog/createjs-wahid)」を読んで、興味をもったので試してみました。

私が管理するサイト「[CreateJS入門サイト](https://ics.media/tutorial-createjs/index.html)」のデモをwahidに移植。ほとんどのコードはそのままコピペするだけで動きました！

## 移植したサンプル

パーティクル

- [wahid版](https://ics-creative.github.io/161003_wahid/samples/particle.html)
- [CreateJS版](https://ics-creative.github.io/tutorial-createjs/samples/particle_colorful.html)

シューティングゲーム

- [wahid版](https://ics-creative.github.io/161003_wahid/samples/game.html)
- [CreateJS版](https://ics-creative.github.io/tutorial-createjs/samples/game_shooting.html)

フラクタル図形

- [wahid版](https://ics-creative.github.io/161003_wahid/samples/fractal.html)
- [CreateJS版](https://ics-creative.github.io/tutorial-createjs/samples/fractal_tree_animation.html)

## ファーストインプレッション

- パーティクルやフラクタル図形はコピペだけで動いたので驚きました。(`script`要素の`src`属性をCreateJSから、wahidに変更しただけで動きました)
- wahidはWebGLをベースとするため描画性能の向上を期待しましたが、今回の小規模なサンプルではそれは確認できませんでした。wahidに適した最適化方法があるかもしれないので、追って調べていきたいと思います。


## 気づいたこと

- 当たり判定周りのAPIが本家CreateJSと異なるようで、移植時に僅かに修正しました。
- フラクタル図形のサンプルで顕著ですが、グラフィック周りは見え方に異なりました。本家CreateJSはContext2Dで、wahidはWebGLをベースとするため内部的な違いがあるのかもしれません。