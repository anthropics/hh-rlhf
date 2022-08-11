## Overview

This repository provides access to:
1. Human preference data about helpfulness and harmlessness
2. Human generated red teaming data

Each of these datasets are described further below. 

**Disclaimer**: The data contain content that may be offensive or upsetting. Topics include, but are not limited to, discriminatory language and discussions of abuse, violence, self-harm, exploitation, and other potentially upsetting subject matter. Please only engage with the data in accordance with your own personal risk tolerance. The data are intended for research purposes, especially research that can make models *less* harmful. The views expressed in the data do not necessarily reflect the views of Anthropic or any of its employees.

## Human preference data about helpfulness and harmlessness

The data are described in the paper: [Training a Helpful and Harmless Assistant with Reinforcement Learning from Human Feedback](https://arxiv.org/abs/2204.05862). If you find the data useful, please cite the paper. The data format is very simple -- each line of the jsonl files contains a pair of texts, one "chosen" and one "rejected".

For **helpfulness**, the data are grouped into train/test splits in three tranches: from our base models (context-distilled 52B language models), via rejection sampling (mostly with best-of-16 sampling) against an early preference model, and a dataset sampled during our iterated "online" process. 

For **harmlessness**, the data are only collected for our base models, but otherwise formatted in the same way.

Details about the data collection process and crowdworker population can be found in the paper, specifically in section 2 and appendix D. 

## Red teaming data

The data are described in the paper: [Red Teaming Language Models](https://arxiv.org). If you find the data useful, please cite the paper.

Details about the data and data collection procedures can be found in the Datasheet in the appendix of the paper. 

Each line of the jsonl file contains a dictionary with the following fields:
- `transcript` a text transcript of a conversation between a human adversary (red team member) and an AI assistant
- `min_harmlessness_score_transcript` a real value score of the harmlessness of the AI assistant (lower is more harmful) as obtained from a preference model
- `num_params` number of parameters in the language model powering the AI assistant
- `model_type` type of model powering the AI assistant
- `rating` the red team member's rating of how successful they were at breaking the AI assistant (Likert scale, higher is more successful)  
- `task_description` a short text description written by the red team member about how they tried to red team the AI assistant
- `task_descripton_harmlessness_score` a real value score of the harmlessness of the task description (lower is more harmful) as obtained from a preference model
- `red_team_member_id` an arbitary identifier of the red team member. one red team member can generate multiple red team attacks
- `is_upworker` a binary indicator that is true if the red team member was from the crowd platform Upwork or false if they were from MTurk
- `tags` a list of up to 6 tags per transcript. tags are short descriptions of the red team attempts generated by crowdworkers who reviewed red team data post-hoc

## Contact
You can submit inquiries to: redteam@anthropic.com
