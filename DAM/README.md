[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

# __Deep Attention Matching Network__

This is the source code of Deep Attention Matching network (DAM), that is proposed for multi-turn response selection in the retrieval-based chatbot.

DAM is a neural matching network that entirely based on attention mechanism. The motivation of DAM is to capture those semantic dependencies, among dialogue elements at different level of granularities, in multi-turn conversation as matching evidences, in order to better match response candidate with its multi-turn context. DAM will appear on ACL-2018, please find our paper at: http://acl2018.org/conference/accepted-papers/.

## __Paddle Version__

DAM is originally implemented with Tensorflow, we highly recommend using the paddle version as Paddle supports parallely training with very large corpus.

You can find the paddle version at: https://github.com/PaddlePaddle/models/tree/develop/fluid .

## __Network__

DAM is inspired by Transformer in Machine Translation (Vaswani et al., 2017), and we extend the key attention mechanism of Transformer in two perspectives and introduce those two kinds of attention in one uniform neural network.

- **self-attention** To gradually capture semantic representations in different granularities by stacking attention from word-level embeddings. Those multi-grained semantic representations would facilitate exploring segmental dependencies between context and response.

- **cross-attention** Attention across context and response can generally capture the relevance in dependency between segment pairs, which could provide complementary information to textual relevance for matching response with multi-turn context.

<div align=center>
<img src="appendix/Figure1.png" width=800>
</div>

## __Results__

We test DAM on two large-scale multi-turn response selection tasks, i.e., the Ubuntu Corpus v1 and Douban Conversation Corpus, experimental results are bellow:

<img src="appendix/Figure2.png">

## __Usage__

First, please download [data](https://pan.baidu.com/s/1hakfuuwdS8xl7NyxlWzRiQ "data") and unzip it:
```
cd data
unzip data.zip
```

If you want use well trained models directly, please download [models](https://pan.baidu.com/s/1pl4d63MBxihgrEWWfdAz0w "models") and unzip it:
```
cd output
unzip output.zip
```

Train and test the model by:
```
sh run.sh
```

## __Dependencies__

- Python >= 2.7.3
- Tensorflow == 1.2.1

## __Citation__

The following article describe the DAM in detail. We recommend citing this article as default.

```
@inproceedings{ ,
  title={Multi-Turn Response Selection for Chatbots with Deep Attention Matching Network},
  author={Xiangyang Zhou, Lu Li, Daxiang Dong, Yi Liu, Ying Chen, Wayne Xin Zhao, Dianhai Yu and Hua Wu},
  booktitle={Proceedings of the 56th Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers)},
  volume={1},
  pages={  --  },
  year={2018}
}
```


