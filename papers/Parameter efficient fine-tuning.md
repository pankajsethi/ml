# Parameter Efficient Fine-tuning (PEFT)

* Paper of papers. defines taxonomy 
## Types of PEFT
![here](https://github.com/pankajsethi/ml/blob/main/papers/images/peft-types.png)
### Additive - Adapters
adds extra layers or parameters and only trains them. 

> > for every byte of trainable parameter, one extra byte is needed for its gradient, and two more bytes are needed to store the optimizer state: the first and second moments of the gradient. In practice, depending on the setup, training a model requires 12-20 times more GPU memory than the model weights.

#### Adapters:
 * add fully-connected networks after attention and FFN layers in Transformer.
#### AdaMix:
 > utilizing multiple adapters in a mixture-of-experts (MoE) fashion
 >  After training, the adapter weights are averaged across the experts which makes inference more memoryefficient.
### Additive -  Soft Prompts: 

####  Prompt Tuning
 * commonly added a trainable tensor to input embeddings.
 * These  tensors can be pre-trained on specific taks
 * these tensors dont have to reprenst words and can occupy any value in emdedding space
 > Overall, soft prompts are incredibly parameter-efficient at the cost of inference
overhead and more applicable to larger models.

#### Prefix Tuning
Like Prompt tuning but trainable tensors are added to hidden state of all layers and not just input.

#### Intrinsic Prompt Tuning
* Like  prompt tuning but use an autoencoder to "compress" the soft prompt and train on the compressed soft prompt.


### Selective
* Selective methods fine-tune a subset of the existing parameters of the model. It could be a layer depth-based selection, layer type-based lection, or even individual parameter selection
* Overall approach at this time underperforms other approaches (Adapter or LoRA)

#### Bitfit
* Only fine tunes biases
* Significantly underfperforms full fine-tuning and other PEFT

#### Diff Pruning
* Achives results compared to full fine-tuning by just updating .5% of parameters
* Requires more memory

#### Freeze and Reconfigure (FAR)


### Reparametrization based  
* Creates a low-rank represenation of parameters to reduce the number of training parameters

#### LoRA
* Probably the most commonly used and easiest to understand.
> Parameter update for a weight matrix in LoRa is decomposed into a product of two low-rank matricies
* no inference overhead
> The method outperforms BitFit and Adapters and has been evaluated on the models up to 175B parameters.

Paper talks about many approaches but I stopped here since I want to read the LoRA paper next.

