# virtualbox

## download

- [Oracle VM VirtualBox \- ダウンロード \| Oracle 日本](https://www.oracle.com/jp/virtualization/technologies/vm/downloads/virtualbox-downloads.html)
- ubuntu
  - LTS: [Download Ubuntu Desktop \| Download \| Ubuntu](https://ubuntu.com/download/desktop)
  - 18.04.6: [Ubuntu 18\.04\.6 LTS \(Bionic Beaver\)](https://releases.ubuntu.com/18.04/)

## ubuntu

- インストール時のポイント
  - 基本構成はEnglishにしておく
  - キーボードは日本語(自分の利用するものに合わせる)
- クリップボード、ドラッグアンドドロップの有効化
  1. "Gest Additions CD" で機能のインストール: メニュー > デバイス > Guest Additions CD
  2. メニュー > デバイスの設定
- about folder share:
  1. we need "Guest Additions" writen befer.
  2. アクセスしたときにパーミッション宣言を出さない方法
    - `sudo usermod -a -G vboxsf "$USER"`
  3. マウントポイントを設定しないこと
    - 自動マウント, 永続化するにチェックを入れる

## ubuntu に dotnet をインストールする

インストール方法はこちら。ただし6.0しか書いてない

- [Install \.NET on Ubuntu \- \.NET \| Microsoft Docs](https://docs.microsoft.com/en-us/dotnet/core/install/linux-ubuntu)

5.0をインストールしたい場合は、20.04 のdepを一回インストールして、`apt update` する

- パッケージリポジトリの削除方法: `sudo apt-get remove packages-microsoft-prod`
- .netのパッケージリポジトリファイルダウロード: `wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb`
  - 22.4: `wget https://packages.microsoft.com/config/ubuntu/22.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb`
- リポジトリインストール: `sudo dpkg -i packages-microsoft-prod.deb`
  - バージョンが上なら上書き可能っぽい
- リポジトリ更新: `sudo apt update` リポジトリインストールとセットで
- .net インストール `sudo apt-get install -y dotnet-sdk-5.0`, `sudo apt-get install -y dotnet-sdk-6.0`
