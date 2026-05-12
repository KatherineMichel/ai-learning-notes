# AI Learning Notes

## AI Engineering by Chip Huyen

Goes beyond tools and trends to give timeless understanding. 

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

Inference Optimization- Model-level
* Model-level optimization- changing model itself to be more efficient (reduce precision of model weights using fewer bits to represent them)
* Model-level optimization method- Quantization, compression, attention mechanism modifications
* There can be slight, but minimal trade off in accuracy, gains in efficiency are significant
* Compression techniques: pruning and distillation reduce size of model by removing redundant or less important parts
* Distillation- train a big powerful model then distill its knowledge into a smaller, faster model
* Attention mechanism modifications- key to how transformers work
* Computational intensive, modifying them, making them more efficiently can significantly speed up inference
* Sparse attention or linear attention

Inference Optimization- Service-level
* Service-level optimizations- how you deploy and serve the model
* Parallelism and caching are key
* Parallelism- running inference on multiple requests using multiple GPUs or CPUS (multiple servers)
* Caching- storing results of previous computations so you don't have to re-compute if get same request
* Prompt caching- useful for LLMs (users ask similar questions repeatedly, reduce latency and cost)
* Speculative decoding- reduce latency- predict next words before generated, model speculates about next token

Evaluation Methodology
* How do you measure AI performance
* Define evaluation criteria, select metrics, create scoring rubrics
* Aspects of performance to evaluate- accuracy, fluency, factual consistency- depends on application
* Metrics- numerical to quantify, BLU score for translation, accuracy for classification, BLEU, Rouge, acuracy, precision, recall
* Select metrics relevant to evaluation criteria and application goals
* Scoring rubrics- guidelines for human evaluators- different performance levels with examples (especially subjective)
* Automated (BLEU score) and AI as judge (use another AI model to evaluate output of system, scalable)
* You need humans to define criteria, create rubrics, and validate that AI judge is evaluating what you want it to evaluate.
* Factual consistency, instruction-following capability (does it do what asked to do), cost metrics- consider
* Slide data for fine-grain understanding to avoid biases
* Don't look at overall, average performance. Slice by different demographics, use cases, input types- identify biases and understand where system is performing well/struggling
* Reveal hidden biases, performance disparities

User-feedback for Continuous Improvement
* Most crucial for longterm success
* User are ultimate judges of whether AI system is useful/helpful in real world
* Explicit feedback- direct (ratings, reviews, comments, thumbs, stars, text feedback forms)
* Implicit- how users interact with system- click-through-rate, dwell time, task completion rates, error rates, usage patterns
* Things you can't rack without users explicitly telling you anything
* Click on feature a lot, correcting output, abandoning tasks
* Preventing users from exploiting the model
* AI systems can be vulnerable to mis-use- harmful content, bypass safety filters, exploit vulnerabilities
* Preventative measures, monitor user behaviors for positive and negative signals
* Ongoing cycle of feedback, analysis, improvement
* Close loop- build, evaluate, get feedback, improve, repeat, user feedback is fuel
