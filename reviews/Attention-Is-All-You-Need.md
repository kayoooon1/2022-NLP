# Attention Is All You Need   
* Reviewer : 김가윤   
* 작성일 : 2022-05-25   

## Model Architecture   
* Neural sequence transduction models = Encoder-Decoder 구조   
* 인코더는 maps an input sequence -> continuous representation z로 변환   
* z를 받은 디코더는 output sequence를 생성   
* 이전의 것을 받아 다음의 것을 생성   
* Transformer 또한 이러한 구조를 따름   
<br>   
    ### 1. Encoder and Decoder Stacks   
    * 인코더는 6개의 identical layers, each layer은 2개의 sub layers 가지고 있다.