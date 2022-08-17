This repository provides access to human preference data used in the paper [Training a Helpful and Harmless Assistant with Reinforcement Learning from Human Feedback](https://arxiv.org/abs/2204.05862).

The "helpfulness" datasets are available now, and the "harmlessness" or red teaming data will be made available later this year. The data is grouped into train/test splits in three tranches: from our base models (context-distilled 52B language models), via rejection sampling (mostly with best-of-16 sampling) against an early preference model, and a dataset sampled during our iterated "online" process. Details about the data collection process and crowdworker population can be found in the paper, specifically in section 2 and appendix D. The data format is very simple -- each line of the jsonl files contains a pair of texts, one "chosen" and one "rejected".

This data is only intended for research purposes. If you find it useful, please cite our paper.
