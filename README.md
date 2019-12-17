# Text Augmentation
[EDA: Easy Data Augmentation Techniques for Boosting Performance on Text Classification Tasks](https://arxiv.org/pdf/1901.11196.pdf)を参考にText Augmentationを行う。  
行うタスクは、類義語置換・単語削除・単語スワップ・類義語挿入の4つである。  
各タスクで用いる確率は論文のものを参考にしている。

## 類義語置換(Replace Synonym)
単語をランダムに類義語で置換するタスク。  
類義語の候補はwordnetで帰ってきた単語の上位３件を候補とし、ランダムに選択している。

```
(置換前)iPhoneには動画撮影機能が付いているがその機能を使って動画を撮影しそれを投稿してみんなで楽しんでしまおうというSNSがあるので紹介しよう
(置換後)iPhoneには絵撮影役立つが付いているがその役立つを使って絵を撮影しそれを投稿してみんなで楽しんでしまおうというSNSがあるので紹介しよう
```

## 単語削除(Random Deletion)
文中から単語をランダムに削除するタスク。  
単語が一つしかない場合は削除しない。  
単語を全て削除してしまった場合は、文章からランダムに一つの単語を返す。

```
(削除前)iPhoneには動画撮影機能が付いているがその機能を使って動画を撮影しそれを投稿してみんなで楽しんでしまおうというSNSがあるので紹介しよう
(削除後)iPhone動画撮影付いその機能使っ投稿みんな楽しんしまおうという紹介しよう"
```

## 単語スワップ(Random Swap)
文中の単語同士をランダムにスワップ(交換)するタスク。  
3回交換が行われなかった場合はそのまま返している。

```
(スワップ前)iPhoneには動画撮影機能が付いているがその機能を使って動画を撮影しそれを投稿してみんなで楽しんでしまおうというSNSがあるので紹介しよう
(スワップ後)iPhone機能撮影という付いその動画使っ動画撮影投稿みんな楽しんしまおう機能SNS紹介しよう
```

## 類義語挿入(Random Insertion)
文中にある単語の類義語をランダムな場所に挿入するタスク。  
類義語の候補はwordnetで帰ってきた単語の上位３件を候補とし、ランダムに選択している。
```
(挿入前)iPhoneには動画撮影機能が付いているがその機能を使って動画を撮影しそれを投稿してみんなで楽しんでしまおうというSNSがあるので紹介しよう
(挿入後)iPhone動画引き合す撮影作用機能取りいれる付い利く絵その降服映像機能写す使っ動画撮影画像投稿みんな楽しんしまお映画化う動くというSNS撮る撮る映像紹介動くしよ降服う
```