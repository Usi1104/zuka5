## zuka5
# 演習１
``` mermaid
stateDiagram-v2
direction TB
s1 : 登録受付中
s2 : 登録処理
s3 : 抽選待ち状態
s4 : 履修修正状態
s5 : 削除処理

state sc <<choice>>
state s4 <<choice>>
state s5 <<choice>>

[*] --> s1
s1 --> s2 : 受講登録
s2 --> s1
s1 --> sc : 履修登録期間終了
sc --> s3 : [定員超過]
sc --> s4 : [定員内]

s3 --> s4 : 抽選

s4 --> s5 : 削除依頼
s5 --> s4
s4 --> [*]
```
# 演習２
``` mermaid
stateDiagram-v2
direction TB
s1 : 登録受付中
s2 : 登録処理
s3 : 抽選待ち状態
s4 : 履修修正状態
s5 : 削除処理
s6 : 余裕のある科目に登録

state sc <<choice>>
state s4 <<choice>>
state s5 <<choice>>

[*] --> s1
s1 --> s2 : 受講登録
s2 --> s1
s1 --> sc : 履修登録期間終了
sc --> s3 : [定員超過]
sc --> s4 : [定員内]

s3 --> s4 : 抽選

s4 --> s5 : 削除依頼
s5 --> s4

s4 --> s6
s6 --> sc

s4 --> [*]
```
# 課題
``` mermaid
stateDiagram-v2
direction TB
s1 : 登録受付中
s2 : 登録処理
s3 : 抽選待ち状態
s4 : 履修修正状態
s5 : 削除処理
s6 : 登録処理

state sc <<choice>>
state s4 <<choice>>
state s5 <<choice>>
state s7 <<choice>>
[*] --> s1
s1 --> s2 : 受講登録
s2 --> s1
s1 --> sc : 履修登録期間終了
sc --> s7 : [定員超過]
s7 --> s3 : [そのままの教室で講義]
s7 --> s4 : [さらに大きな教室で講義]
sc --> s4 : [定員内]

s3 --> s4 : 抽選

s4 --> s5 : 削除依頼
s5 --> s4

s4 --> s6 :[履修登録]
s6 --> s4

s4 --> [*]
```
