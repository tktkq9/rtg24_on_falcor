# 実装するにあたってのメモ


## Reflective Shadow Maps
### 参考文献  
[Reflective Shadow Maps](https://ericpolman.com/2016/03/17/reflective-shadow-maps/)  
[穴空間 実装例](http://kagamin.net/hole/rsm/index.htm)  
[元の論文](https://users.soe.ucsc.edu/~pang/160/s13/proposal/mijallen/proposal/media/p203-dachsbacher.pdf)  

この参考文献の内容を使うのではなく、これらのマップの情報を使ってフォトンを飛ばす用に使う  
ライトに対するレイトレ用GBufferみたいな感じ  

このRSMミップマップをかけ2 * 2画像を用意し、この
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTA2MzY2NjIzNCwtMzU2NTg4MzI5XX0=
-->