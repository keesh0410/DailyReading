
# 摘要
(1) IT fails to enhance knowledge or skills in LLMs. LoRA fine-tuning is limited to learning response initiation and style tokens, and full-parameter finetuning leads to knowledge degradation. 
(2) Copying response patterns from IT datasets derived from knowledgeable sources leads to a decline in response quality. 
(3) Full-parameter fine-tuning increases hallucination by inaccurately borrowing tokens from conceptually similar instances in the IT dataset for generating responses. 
(4) Popular methods to improve IT do not lead to performance improvements over a simple LoRA fine-tuned model.

# 摘要翻译:
指令微调没办法增加知识到LLMs.
Lora微调只会学习到回复的格式，全量微调则会导致知识退化.
微调之后模型回复的质量会下降. 全量微调会增加模型的幻觉现象，因为模型在微调之后会抄袭一些微调数据集里面的一些词语.
目前微调的改进方案跟lora相比没什么优势.

ps: IT 是Instruction Tuning 的意思

接下来学习一下人家具体是怎么做实验分析的.

1. IT is not a knowledge enhancer.
2. IT 会抄袭风格,这会损害性能.
3. 从微调数据集学习到的词语会导致幻觉.


复杂的知识训练与构建，这种连接感觉只能在全量微调中进行连接.
SVD low rank学习到的内容到底和全量的有什么区别？

# 实验设置
LLMs: 5种 Llama2 7B 13B 70B ; Mistral-7B Phi-1.5 1.3B
Datasets: Alpaca(52k)、MedInstruct(52k)、LIMA(1k)、TuLu-V2-Mix(326k)
Base Model Evaluation 和 finetune之后的Evaluation 不太一样。
Tuned Evaluation使用了GPT4进行评估.

Key Findings:

关于tokens distribution shrift： 
1. Fine-tuning using Lora results in a minimal shift.
2. 在1的基础上, Scaling the IT dataset size has a negligible effect.
3. 全量微调的导致的distribution shift 明显大于 Lora
4. Model Size 可以减少这个distribution Shift的情况.


关于模型具体学了啥
LFT 其实只是一个模型回复的初始化，
对于Lora而言，学习不到什么新的知识, 

论文结构.
1 Introduction 
2 Experimental Setting 
3 IT is (currently) Not a Knowledge Enhancer
4 Pattern Copying (often) Hurts Performance
5 Causal Analysis of Hallucinations
6 Methods to Improve IT are Ineffective
7 Related Work
8 Conclusion, Limitations and Future Work
