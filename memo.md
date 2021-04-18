# 実装するにあたってのメモ


## Reflective Shadow Mapsについて
### 参考文献  
[Reflective Shadow Maps](https://ericpolman.com/2016/03/17/reflective-shadow-maps/)  
[穴空間 実装例](http://kagamin.net/hole/rsm/index.htm)  
[元の論文](https://users.soe.ucsc.edu/~pang/160/s13/proposal/mijallen/proposal/media/p203-dachsbacher.pdf)  

この参考文献にあるようなGI計算に使うのではなく、これらのマップの情報を使ってフォトンを飛ばすのに使う  
ライトに対するレイトレ用GBufferみたいな感じ  

また、フォトンを飛ばすにあたり各ピクセルから飛ばすのではなく重要度サンプリングする  
内容としては、このRSMのdirectional falloffとアルベド情報に対しミップマップをかけ2 * 2画像を用意し、この情報をもとに重要度サンプリングを行う  

###  その他試してみたいこと
- s_uの計算がライトへの方向を使って計算しているが、考え方としてはむしろそこでサンプリングされた際のレイの方向をもらってきた方がいいのではないかと思った  
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTU2NDMwODYsLTEwMDg1MzEwNSw0MDE4Nz
A0ODksMTY5MzI1NzQwNSwtMzU2NTg4MzI5XX0=
-->