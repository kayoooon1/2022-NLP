# WordNet   
* Previously commonest NLP solution   
* 동의어, 관계의 집합   
* 문제점 존재 :innocent:
    + Missing nuance, new meanings of words...etc   

# Representing Words   
1. 단어들은 one-hot vectors로 표현될 수 있음   
2. Vector dimension = # of words in vocabs   
3. 문제점 존재   
    + one-hot vectors에서 **유사성(similarity)** 를 찾을 수가 없는 것   
    :gem: Solution : Learn to encode similarity in the vectors themselves!   

   
# Distributional semantics (분포 의미론)   
    * 위의 문제점을 해결하기 위한 representing words **by their context**
    * 언어 데이터의 큰 샘플에서 분포 특성을 기반으로 언어 항목 간의 의미 론적 유사성을 정량화하고 분류   
    * 단어 w가 text에 존재할 때, context는 fixed-size window와 함께 그 주변에 나타나는 set of words다.   
    * Word vectors는 각 단어의 dense vector로 **dot product** 를 통해 유사성을 측정한다. Word Embeddings, Word Representation 이라고도 불린다.   
    * Vector space는 각 vector들의 배치를 2D 공간에 투영한 것으로 정확히 투영되지는 않지만 유사한 단어가 유사한 위치에 있음을 확인 가능   



#  Word2vec   
## 1. Overview   
* Word vectors를 학습하기 위한 프레임워크   
* 말뭉치(corpus) : a long list of words   
* 모든 단어는 벡터로서 표현   
* 각 텍스트의 t 포지션에서 센터 단어 c와 그 밖의 언어 o가 있음   
* 주어진 c에서 o가 나올 확률을 계산하기 위해 c와 o의 유사성을 사용, 확률을 극대화 하기 위해 벡터들을 적응시킴   
* 단어 벡터간의 유사도를 이용해 맥락에서 특정 단어가 나타날 확률을 계산   
* 모든 단어 (t)에 대해 fixed-size window(m)의 단어(j)만큼 주변 단어의 확률을 곱하면 됨

## 2. Objective function   
* word vector 𝜽(parameter)가 주어졌을 때, window 내의 context word가 해당 위치에 나타날 확률의 곱   
* negative log likelihood 를 거쳐 objective function을 만든 후, 이를 최소화 하는 𝜽(parameter)를 구하기   



[추가 참고자료 1](https://godcode.tistory.com/26)   
[추가 참고자료 2](https://velog.io/@tobigs-text1314/CS224n-Lecture-1-Introduction-and-Word-Vector)   