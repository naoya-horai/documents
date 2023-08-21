# USDビルド環境について

USDのビルドは提供されているbuild_usd.pyで簡単にできます。また、先人の皆様がビルドに関してのたくさんの情報を残してくださっていますので、それらに関する文献は無数にあります。

しかし、ビルドにあたって、Pythonのバージョンなどが文献によってまちまちで、最新の環境を作る際には環境構築で躓いてしまいます。

今回は、USDビルドに際して必要なもののバージョンについて書いていきます。

## USD22.08から23.08までの環境について

現在最新のUSDリリースはバージョン23.08です。現在のUSDは、バージョン22.08から、CY2020環境に乗せる形で作られています。

## CY2020とは

CY2020とは、CY20XXの形で毎年リリースされている、VFX Reference Platformという、CG制作環境の標準を定義したものです。
VFX Reference Platformでは、Linux、macOS、Windowsの各種プラットフォームのCコンパイラ、Python、Boost、TBB、MKL、C++ API、Qt関連ライブラリ、NumPy、OpenEXRなど各種CG関連のライブラリのバージョンが定められています。

## 今後のリリースについて

今後のリリースでは、USDはCY2022環境に依存するようになります。

これにあたって、Visual Studioのバージョンを2019 v16.9以上とする、windows SDKをv10.0.19041とする、Pythonのバージョンを3.9.1から3.9の最新版とする、C++のAPIレベルをC++17以上とする、などの変更があり、USDのバージョンアップに伴い、手元の環境を変更する必要があるかもしれません。

## 参考文献など
https://fereria.github.io/reincarnation_tech/usd/install_usd

https://github.com/PixarAnimationStudios/OpenUSD/blob/release/CHANGELOG.md

https://vfxplatform.com/platform_history.html


最終更新日 2023-08-21