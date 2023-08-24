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

シーンの中身はHydra primitivesとして処理されるらしい。

デフォルトのUSDビルドでは、Hydra core、Scene DelegateとしてUsdImaging、Render DelegateとしてHdStorm(高速なOpenGLレンダラー)、HdPrman(Renderman)、HdEmbreeが提供される。
