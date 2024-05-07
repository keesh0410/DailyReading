1.具体干了啥
our research provides a granular analysis of how data volume, parameter size, and data construction methods influence the development of each underlying ability of LLM, such as creative writing, code generation, and logical reasoning. 

// 学个新词不用difference, 用 discrepancies.
This research proposes a novel, human-curated Chinese dataset with over 40k instruction instances covering ten ability categories, enabling investigation of how the growth of LLM abilities is influenced by data volume, parameter size, and data construction methods during instruction tuning. We are the first to disentangle the effects of these factors by studying a comprehensive set of over 500 model checkpoints, ranging from 7b to 33b. We find that the effects of increasing data volume and model size vary across different abilities. Synthetic data, particularly from GPT-4 using Self-Instruct, is less effective than human-curated data. Adjustments in data construction based on these insights lead to performance improvements on public benchmarks.

他们做了一个数据集，然后分了十个不同的domain，在不同的domain上面做训练发现不同的能力其实增长的速度并不一致.
比如creative writing 就比较简单，但是Ethic的东西就比较难.
