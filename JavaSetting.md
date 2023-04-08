# 環境構築
## 実行環境
___
<br>

* OS
    * Windows 11 Home
* JDK
    * version "17.0.6" 2023-01-17 LTS
* Visual Studio Code

<br>

コードエディタは他のものでも問題ありません<br>
今回はVSCode向けに環境構築を行います

<br>

## 各ツールインストール<p>
___
<br>

[JDK ダウンロード](https://www.oracle.com/java/technologies/downloads/)<br>
(インストール先をコピーしておくとPATHの設定がスムーズになります)<br>

[VSCode ダウンロード](https://code.visualstudio.com/)<br>

<br>

## PATHの設定<p>
___
<br>

### JAVA_HOMEの新規追加
___
<br>

システム環境変数の編集->環境変数->システム環境変数->新規
<br>

変数名：JAVA_HOME<br>
変数値：インストール先のパスを指定する<br>

#### 変数値の例：C:\Program Files\Java\jdk-17

### Pathの追加
___
<br>

次にシステム環境変数内にあるPathを選択->編集->新規
から以下を追加
<br>

    %JAVA_HOME%¥bin

追加したものを「上へ」を選択し、一番上に移動させる

### Pathの確認
___
<br>

コマンドプロンプトもしくパワーシェルを起動し、パスが通っていることを確認する<br>

    java -version
    javac -version

<br>
パスが存在していない場合、以下の原因が考えられる
* JAVA_HOMEの設定ミス 

    以下のコマンドを利用して、正しく設定されているか確認できる

        set JAVA_HOME

* Pathの設定ミス

    システム環境変数から確認
    
Javaのバージョンが正しく設定されている場合は、Javaのバージョン情報が出力される

<br>

## VSCodeの設定<p>
___
<br>

VSCodeを起動してExtensions(Ctrl+Shift+X)から

Extension Pack for Java をインストール

<br>
Settings(Shift+,)画面にJAVA HOMEを入力し<p>

    Java>Jdt>Ls>Java:Home

の欄から Edit in setting.json をクリックして以下を追加<br>
※　“　”内は自分のPathで

    "java.jdt.ls.java.home": "C:\Program Files\Java\jdk-17"

Ctrl + Shift + p で Java:Create Java project で作成