# OSI参照モデルとは

## **どんなもの?**
&emsp; OSI参照モデルとは通信のプロトコルである. これは7つの層(上から順に, アプリケーション層, プレゼンテーション層, セッション層, トランスポート層, インターネット層, データリンク層, 物理層)から構成されている. TCP/IPに則った通信を構成することで, 異なる機器同士での通信が可能となる.

***
## **TCP/IPが考えられた背景**
&emsp; OSI参照モデルが考えられた背景は通信機器の規格の統一である. もし, 異なる会社が製造した通信機器同士に互換性がない場合, その通信機器同士において正しく情報を受信できなかったり, 通信した情報が文字化けするなどの障害が生じる. 

***
## **アプリケーション層**
&emsp; アプリケーション層では, 送信側は宛先と送信主の情報をメッセージのヘッダに追加して, これを送信している. 受信側は受信したメッセージを解析（宛先や送信主が誰なのか）を行う. また, 何らかの理由でメッセージを受信できなかった場合は, 送信側に対してエラーメッセージを送信する.

***
## **プレゼンテーション層**
&emsp; プレゼンテーション層では, 送信側はコンピュータ固有のデータ表示形式からネットワーク全体のデータ表示形式(UTF8やShift-Jisなど)に変換する. また, どのような表示形式を使用したかの情報を, 送信するメッセージのヘッダに追加する. 受信側では, 受信したメッセージのヘッダに書かれた表示形式に従って, ネットワーク全体の表示形式からコンピュータ固有のデータ表示形式に変換する. 

***
## **セッション層**
&emsp; セッション層では, コネクションの確立のタイミングと, データを送信するタイミングを決める. あくまでタイミングを決めるだけであるので, データの送信は行わない. 

***
## **トランスポート層**
&emsp; トランスポート層では, コネクションの確立と切断を行う. また, 受信側が, 送信側が送信したデータを完全に受信できなかった場合, 再度送信するように促す役割を持つ. 

***
## **ネットワーク層**
&emsp; ネットワーク層では, データの送信を行う. データを複数のパケットに分割し, トランスポート層で確立されたコネクションを通してデータの送信を行う. また, IPアドレスという端末の識別子を用いて, 特定の端末に対してデータを送信する. 

***
## **データリンク層, 物理層**
&emsp; 物理層では, 物理的にデータを送信する. データを0,1のビット列に変換し, LANケーブルなどを通してデータの送信を行う. データリンク層は, IPアドレスを用いて, 特定の端末に対してデータを送信する. IPアドレスを用いてデータを送信する点はネットワーク層と同じであるが, ネットワーク層は全区間のデータの伝送を行うのに対し, データリンク層は1区間のデータの伝送を行う.