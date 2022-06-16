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
  2. `sudo usermod -a -G vboxsf "$USER"`
 