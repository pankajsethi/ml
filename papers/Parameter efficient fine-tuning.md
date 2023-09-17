# Parameter Efficient Fine-tuning (PEFT)

* Paper of papers. defines taxonomy 
## Types of PEFT
!(httpsarxiv.orgpdf2303.15647.pdf#page15.png)
### Additive
adds extra layers or parameters and only trains them. 
* Adapters add a fully connected layer after transformer layers and trains those
* Soft Prompts: 
** commonly added to input embeddings that can be pretrained for specific taks
** these tensors dont have to reprenst words and can occupy any value in emdedding space
** can be used for any intermediate layer as well. 


