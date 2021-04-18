# 実装するにあたってのメモ

1. シーンからAnalitic光源を読み込みRSMを生成するパス作成  
2. RSMに対しミップ作成をし、フォトンをサンプリングするｐ

## Reflective Shadow Mapsについて
### 参考文献  
[Reflective Shadow Maps](https://ericpolman.com/2016/03/17/reflective-shadow-maps/)  
[穴空間 実装例](http://kagamin.net/hole/rsm/index.htm)  
[元の論文](https://users.soe.ucsc.edu/~pang/160/s13/proposal/mijallen/proposal/media/p203-dachsbacher.pdf)  

この参考文献にあるようなGI計算に使うのではなく、これらのマップの情報を使ってフォトンを飛ばすのに使う  
ライトに対するレイトレ用GBufferみたいな感じ  

また、フォトンを飛ばすにあたり各ピクセルから飛ばすのではなく重要度サンプリングする  
内容としては、このRSMのdirectional falloffとアルベド情報に対しミップマップをかけ2 * 2画像を用意し、この情報をもとに重要度サンプリングを行う  

###  その他
- s_uの計算がライトへの方向を使って計算しているが、考え方としてはむしろそこでサンプリングされた時のレイの方向をもらってきた方がいいのではないか  
と思ったが実装の方ではちゃんとそうやっていた  

<!--stackedit_data:
eyJoaXN0b3J5IjpbODI1OTczODA1LDEzMTM2MzU4MCwtMTY3Nj
M4MDc4MywtMTAwODUzMTA1LDQwMTg3MDQ4OSwxNjkzMjU3NDA1
LC0zNTY1ODgzMjldfQ==
-->