# USD Hydra その1　

USDにはシーンとレンダラをつなぐHydra Frameworkが存在します。

今回は最終的に自作のレンダラーを自作のアプリでHydraを通して動かすことを目的として、学習を進めていこうと思います。

## Hydraについて

https://openusd.org/files/Siggraph2019_Hydra.pdf
を読んでみる。

```
Today, Hydra is an opensource framework to transport live scene graph data to renderers.
``` 

シーングラフをレンダラーに送ってくれるらしい

``` mermaid
classDiagram
    direction RL
    Hydra <|-- Scene1
    Hydra <|-- Scene2
    Renderer1 <|-- Hydra
    Renderer2 <|-- Hydra
```
```
Our goal is to support both, viewport and final frame.
```
ビューポートも最終レンダリングもサポートしたい。ということはどちらかというと映像向け。
高速な描画を目指しているというよりは、大規模なシーンを高速でレンダラーへ送ることが目的で、レンダラー様に気持ちよく働いてもらうためのフレームワークなのだとわかる。

シーンの中身はHydra primitivesとして処理されるらしい。

また、Scene DelegateとRender Delegateを通すことで、複数シーンを読み込むだけでなく、複数レンダラーでの描画も可能になるらしい。
需要はわからない。

デフォルトのUSDビルドでは、Hydra core、Scene DelegateとしてUsdImaging、Render DelegateとしてHdStorm(高速なOpenGLレンダラー)、HdPrman(Renderman)、HdEmbreeが提供される。
