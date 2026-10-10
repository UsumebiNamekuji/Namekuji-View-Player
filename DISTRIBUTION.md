# 配布・同梱コンポーネントについて

このリポジトリはNamekuji View Playerの配布案内用です。アプリの開発用ソースは公開していません。

v0.1.0の配布ファイルは、Windows 11 x64向けインストーラー `NamekujiViewPlayer-Setup-v0.1.0-x64.exe` の1本です。アプリ、.NETランタイム、再生エンジン、VR投影用シェーダーを含みます。

## 主な同梱コンポーネント

| コンポーネント | 版・構成 | ライセンス |
|---|---|---|
| mpv | 0.41.0、MSYS2 UCRT64のWindows x64ビルド。Direct3D 11、gpu-nextを使用 | mpvはGPL-2.0-or-later。GPLv3の依存を含む配布構成にはGPLv3の条件も適用 |
| FFmpeg | 実行時9.0.2、mpvのビルド時9.0.1。`--enable-gpl`・`--enable-version3`有効、`--enable-nonfree`無効 | GPL-3.0-or-laterおよび依存コンポーネントの各ライセンス |
| libplacebo | 7.360.1 | LGPL-2.1-or-later |
| .NET／Windows Desktop Runtime | 10.0.9、自己完結型Windows x64 | MITおよび同梱する第三者の各ライセンス |

mpvは独立したプロセスとして動作します。アプリのVR投影には、実行に必要な独自GLSLシェーダーを同梱しています。

依存ライブラリを含む詳しい版・配布元・ビルド構成は、インストール先の `third-party` フォルダー内に記載しています。ライセンス文書・著作権表示は `third-party/licenses` に収録しています。

## 対応ソースの提供

mpv、FFmpegと同梱依存ライブラリの対応ソースを、**同じインストーラー内の `third-party/sources` に収録**しています。版に対応するソースパッケージ、パッチ、ビルド用のPKGBUILDと必要な依存素材を含みます。上流へのリンクだけに依存する提供方法ではありません。

ソースの対応関係・ハッシュは `third-party/source-manifest.json` と `third-party/rust-source-manifest.json`、再ビルドの案内は `third-party/SOURCE-BUILD-INSTRUCTIONS.md` に収録しています。元のビルド情報は `third-party/build-metadata` に保存しています。

第三者コンポーネントの改変・再配布時は、それぞれのライセンスに従ってください。通常のアプリ利用にソースの展開や開発環境の導入は不要です。

これらの第三者ライセンスは、アプリ本体に新たなオープンソースライセンスを設定するものではありません。
