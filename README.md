# AI Learning Notes

## AI Engineering by Chip Huyen

Roadmap for navigating Generative AI. Adapting foundational models. 

What Makes a Good Prompt
* Clear task description
* Show examples of input and output
* Present input you want processed
* Models pay more attention to instructions at beginning and ending of prompt
* Tell LLM what format
* Break complex tasks into subtasks
* Experiment iteratively

Retrieval Augmented Generation (RAG)
* Rag tackles knowledge frozen in time and hallucations
* Documents, databases, websites, knowledge graphs
* Term-based methods use keyword searches
* Embedding-based methods use vectors (semantic/intent, not just keywords)
* Chunks- breaking docs into smaller pieces
* Indexing- organizing chunks

Data Quality
* High quality, well formatted data is essential
* Quality, coverage, then quantity
* More data isn't always better- noisy, inconsistent, irrelevant
* Relevant, consistent, and covers range of problems
* Prioritize data quality and relevance over quantity- focus that captures diversity of use cases and free of errors and inconsistencies

Fine-Tuning
* Foundational models are like powerful general purpose instruments, fine-tuning is like specializing for particular type of music
* Makes model more specialized, more aligned with specific task. Aligns behavior with human preferences. Refining without retraining from scratch.
* Supervised fine-tuning- show examples of what you want to do and it learns to do similar things, adjusts its weights
* Parameter efficient fine-tuning- PEFT- reduce memory footprint and computational cost of fine-tuning, fine-tune small number of parameters
* PEFT methods: Lora, adapters, prompt tuning- achieve performance close to full fine-tuning with much less resource usage
* For fine-tuning- needs data you specifically want the model to learn
* Use human generated content or AI generated instructions to create instruction data for supervised fine-tuning

Inference Optimization
* Make AI system more efficient- faster and cheaper
* Inference- feed data in, generate ouput
* Inference can be computational expensive, reduce latency (how long it takes model to respond)
* Model-level optimization- changing model itself to be more efficient (reduce precision of model weights using fewer bits to represent them)
* Model-level optimization method- Quantization, compression, attention mechanism modifications
* There can be slight, but minimal trade off in accuracy, gains in efficiency are significant
* Compression techniques: pruning and distillation reduce size of model by removing redundant or less important parts
* Distillation- train a big powerful model then distill its knowledge into a smaller, faster model
* Attention mechanism modifications- key to how transformers work
* Computational intensive, modifying them, making them more efficiently can significantly speed up inference
* Sparse attention or linear attention
* Service-level optimizations- how you deploy and serve the model
* Parallelism and caching are key
* Parallelism- running inference on mutlple requests using multiple GPUs or CPUS (multiple servers)
* Caching- storing results of previous computations so you don't have to re-compute if get same request
* Prompt caching- useful for LLMs (users ask similar questions repeatedly, reduce latency and cost)
* Speculative decoding- reduce latency- predict next words before generated, model speculates about next token

Evaluation Methodology
* How do you measure AI performance
* Define evaluation criteria
