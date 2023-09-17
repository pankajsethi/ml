# Scaling Instruction-Finetuned Language Models
## aka Flan paper
easily digestable blog: https://blog.research.google/2021/10/introducing-flan-more-generalizable.html


https://arxiv.org/pdf/2210.11416.pdf#page17

### key observation:
* very little math in this paper. more of "Did X and results are in graph Y". very accessible paper
* a lot of referneces are from the year 2020,2021 and 2022. speaks to how quickly the things are moving and everyone is building on top of each others work  without a lot if lag. 
* Newbie will need to dig into MMLU, BBH etc
* 1.8k fine tune tasks giving 10-15% improvement is significant 
* Does not achieve SOTA (State of the art) on specialized models
* instruction finetuning improves unseen tasks when the unseen tasks are in the same prompting paradigm as the finetuning tasks 
* """PaLM 540B, instruction finetuning requires only 0.2% of the pre-training compute but improves the normalized average across evaluation benchmarks by 9.4%.
