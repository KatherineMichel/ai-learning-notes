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
* Makes model more specialized, more aligned with specific task. Aligns behavior with human preferences. Without retraining from scratch. 
