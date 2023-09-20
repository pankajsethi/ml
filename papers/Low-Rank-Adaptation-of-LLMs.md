# LORA: LOW-RANK ADAPTATION OF LARGE LANGUAGE MODELS

[Paper Link](https://arxiv.org/pdf/2106.09685.pdf)

* Really effective approach given how simple it is. If you have to learn one approach for fine tuning, this might be it.


> LoRA possesses several key advantages.
> * A pre-trained model can be shared and used to build many small LoRA modules for different tasks. We can freeze the shared model and efficiently switch tasks by replacing the
matrices A and B in Figure 1, reducing the storage requirement and task-switching overhead significantly.
> * LoRA makes training more efficient and lowers the hardware barrier to entry by up to 3
times when using adaptive optimizers since we do not need to calculate the gradients or
maintain the optimizer states for most parameters. Instead, we only optimize the injected,
much smaller low-rank matrices.
> * Our simple linear design allows us to merge the trainable matrices with the frozen weights
when deployed, introducing no inference latency compared to a fully fine-tuned model, by
construction.
> * LoRA is orthogonal to many prior methods and can be combined with many of them, such
as prefix-tuning. We provide an example in Appendix E.


From [Hugging Face](https://huggingface.co/docs/diffusers/training/lora)
> * Previous pretrained weights are kept frozen so the model is not as prone to catastrophic forgetting.
> * LoRA matrices are generally added to the attention layers of the original model. LoRA is not only limited to attention layers. The authors found that amending the attention layers of a language model is sufficient to obtain good downstream performance with great efficiency. This is why it’s common to just add the LoRA weights to the attention layers of a model. 

* In the appendix, paper mentions that LoRA can be combined with prefix tuning and get better results. These two approaches seem to be orthogonal and results are additive