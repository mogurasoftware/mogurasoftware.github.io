---
layout: layout
title: CKEditorをソースコードからビルドする
---

# CKEditorをソースコードからビルドする

## 環境

  - Linux
  - JDK (java.1.8)
  - git

## ソースコードを入手

[https://github.com/ckeditor/](https://github.com/ckeditor/)からダウンロードする

最新のリリースバージョン(2016/2/13時点では4.5.7)を入手したい場合、ckeditor-dev -> 10 branches -> release/4.5.xとたどって行き、
[https://github.com/ckeditor/ckeditor-dev/tree/release/4.5.x](https://github.com/ckeditor/ckeditor-dev/tree/release/4.5.x)から、Download ZIPボタンをクリックすると、ckeditor-dev-release-4.5.x.zipを入手できる

## ソースコードを展開

unzip ckeditor-dev-release-4.5.x.zipで展開

## buildする  

cd ckeditor-dev-release-4.5.x/dev/builder  
./build.sh  
でbuildできる

## その他

build.shを実行したときNot a git repositoryなどとエラーが出る場合は、build.shで  
REVISION=$(git rev-parse --verrify --short HEAD)の行を  
REVISION=0  
のように書き換える  
同様に、  
TAG=$(git symbolic-ref -q --short HEAD ...)の行も  
TAG=0  
のように書き換えてから、build.shを実行する  
