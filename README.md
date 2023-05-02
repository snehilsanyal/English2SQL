# English2SQL: Converting English Language commands to optimized AI-generated SQL Queries

## Initial Research

Why English to SQL??

- SQL is used for querying relational databases.
- Query and Analyzing data is a must to gain insights.
- At the user end, any beginner would like to know about the insights, but might not be fully aware of the query language. Also, the syntax should be correct for queries. This restricts common users to "have a conversation" with the database.

## Questions

1. What is the current state of tech where english to sql query generators are ? (Literature)
    - [ ]  Benchmark datasets (links, gyst, availability, paper), papers (models, implementations)
    - [ ]  Comparative table of benchmark models on different datasets
    - [ ]  Available Open source implementations / HF Spaces
    - [ ]  Available online tools, licenses and pricing(for reference), use them and look for loopholes and features from user’s perspective
    - [ ]  Review of architectures with parameters (comparative, use paperswithcode)
    
    ****************Benchmark Datasets and Papers:****************
    
    1. **Spider:** [https://yale-lily.github.io/spider](https://yale-lily.github.io/spider)
    
    ******************************Dataset Paper:****************************** [https://aclanthology.org/D18-1425.pdf](https://aclanthology.org/D18-1425.pdf) ****
    
    **************************Benchmark: SyntaxSQLNet: Syntax Tree Networks for Complex and Cross Domain Text-to-SQL Task************************** https://github.com/taoyds/syntaxsql ****[https://arxiv.org/pdf/1810.05237v2.pdf](https://arxiv.org/pdf/1810.05237v2.pdf) ****
    
    **SOTA:** DIN-SQL (uses GPT4) [https://arxiv.org/pdf/2304.11015.pdf](https://arxiv.org/pdf/2304.11015.pdf)  
    
    Code: https://github.com/MohammadrezaPourreza/Few-shot-NL2SQL-with-prompting
    
    Spider is a large-scale *[complex and cross-domain](https://medium.com/@tao.yu/spider-one-more-step-towards-natural-language-interfaces-to-databases-62298dc6df3c)* semantic parsing and text-to-SQL dataset annotated by 11 Yale students. The goal of the Spider challenge is to develop natural language interfaces to cross-domain databases. It consists of 10,181 questions and 5,693 unique complex SQL queries on 200 databases with multiple tables covering 138 different domains. In Spider 1.0, different complex SQL queries and databases appear in train and test sets. To do well on it, systems must *generalize well to not only new SQL queries but also new database schemas*.
    
    Another Model: Graphix-T5 Paper: [https://arxiv.org/pdf/2301.07507v1.pdf](https://arxiv.org/pdf/2301.07507v1.pdf) 
    
    **Code**: [https://github.com/AlibabaResearch/DAMO-ConvAI/tree/main](https://github.com/AlibabaResearch/DAMO-ConvAI/tree/main)  (Very Important by Alibaba Research, and many papers are related to this)
    
    2. **Stack Exchange Data Explorer (SEDE):** 
    Most available semantic parsing datasets, comprising of pairs of natural utterances and logical forms, were collected solely for the purpose of training and evaluation of natural language understanding systems. As a result, they do not contain any of the richness and variety of natural-occurring utterances, where humans ask about data they need or are curious about. In this work, we release SEDE, a dataset with 12,023 pairs of utterances and SQL queries collected from real usage on the Stack Exchange website. We show that these pairs contain a variety of real-world challenges which were rarely reflected so far in any other semantic parsing dataset, propose an evaluation metric based on comparison of partial query clauses that is more suitable for real-world queries, and conduct experiments with strong baselines, showing a large gap between the performance on SEDE compared to other common datasets.
    
    SEDE is a dataset comprised of 12,023 complex and diverse SQL queries and their natural language titles and descriptions, written by real users of the Stack Exchange Data Explorer out of a natural interaction. These pairs contain a variety of real-world challenges which were rarely reflected so far in any other semantic parsing dataset. The goal of this dataset is to take a significant step towards evaluation of Text-to-SQL models in a real-world setting. Compared to other Text-to-SQL datasets, SEDE contains at least 10 times more SQL queries templates (queries after canonization and anonymization of values) than other datasets, and has the most diverse set of utterances and SQL queries (in terms of 3-grams) out of all single-domain datasets. SEDE introduces real-world challenges, such as under-specification, usage of parameters in queries, dates manipulation and more. [Homepage](https://github.com/hirupert/sede)
    
    GitHub: https://github.com/hirupert/sede 
    
    [https://huggingface.co/datasets/sede](https://huggingface.co/datasets/sede) 
    
    Paper: [https://aclanthology.org/2021.nlp4prog-1.9.pdf](https://aclanthology.org/2021.nlp4prog-1.9.pdf)
    
    Model T5 Paper:  [https://arxiv.org/pdf/1910.10683.pdf](https://arxiv.org/pdf/1910.10683.pdf) Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer
    
    3. **KaggleDBQA**  
    
    Paper: KaggleDBQA: Realistic Evaluation of Text-to-SQL Parsers [https://arxiv.org/pdf/2106.11455v1.pdf](https://arxiv.org/pdf/2106.11455v1.pdf) 
    
    Data and Repo: https://github.com/chiahsuan156/KaggleDBQA 
    
    4. ****SParC (Semantic Parsing in Context)****
    
    **Dataset Paper:** SParC: Cross-Domain Semantic Parsing in Context [https://arxiv.org/pdf/1906.02285v1.pdf](https://arxiv.org/pdf/1906.02285v1.pdf)
    
    **[RASAT+PICARD](https://paperswithcode.com/paper/rasat-integrating-relational-structures-into) RASAT: Integrating Relational Structures into Pretrained Seq2Seq Model for Text-to-SQL (EMNLP2022)** [https://arxiv.org/pdf/2205.06983v2.pdf](https://arxiv.org/pdf/2205.06983v2.pdf)  https://github.com/lumia-group/rasat 
    
    5. ******************WikiSQL 
   
    ******************Paper:****************** [https://arxiv.org/pdf/1709.00103.pdf](https://arxiv.org/pdf/1709.00103.pdf) 
        
        ******************Repo:****************** https://github.com/salesforce/WikiSQL 
        
        ******************Model: T5 Base Fine Tuned on WikiSQL:****************** [https://huggingface.co/mrm8488/t5-base-finetuned-wikiSQL](https://huggingface.co/mrm8488/t5-base-finetuned-wikiSQL) 
        
        ****************************************************Project based on WikiSQL:**************************************************** https://github.com/tiwarikajal/Seq2SQL--Natural-Language-sentences-to-SQL-Queries (for reproducing)
        
    
    **************Papers**************
    
    ChatGPT-SQL https://github.com/thu-bpm/chatgpt-sql The prediction results of ChatGPT on various datasets of Text-to-SQL [https://arxiv.org/pdf/2303.13547.pdf](https://arxiv.org/pdf/2303.13547.pdf) 
    
    LEVER: Learning to Verify Language-to-Code Generation with Execution [https://arxiv.org/pdf/2302.08468v1.pdf](https://arxiv.org/pdf/2302.08468v1.pdf)
    
    ****RESDSQL: Decoupling Schema Linking and Skeleton Parsing for Text-to-SQL**** https://github.com/ruckbreasoning/resdsql 
    
    ****EHRSQL: A Practical Text-to-SQL Benchmark for Electronic Health Records**** https://github.com/glee4810/EHRSQL 
    
    **Paper Code Collection (MSRA DKI Group), MultiSpider** https://github.com/microsoft/ContextualSP 
    
    The dataset and source code for our paper: "Did You Ask a Good Question? A Cross-Domain Question IntentionClassification Benchmark for Text-to-SQL” https://github.com/chatc/TriageSQL 
    
    AI SQL (Is in GO) [https://github.com/HarryVolek/aisql/tree/main](https://github.com/HarryVolek/aisql/tree/main) 
    
    SyntaxSQLNet https://github.com/raffle-interns/SyntaxSQLNet 
    
    **************************************************************************************************Available Open source repos / Hugging Face Spaces**************************************************************************************************
    
    T5 English to SQL Generator: [https://huggingface.co/shashanksingh944/t5-english-to-sql-generator](https://huggingface.co/shashanksingh944/t5-english-to-sql-generator) 
    
    Text2SQL (Convert natural language query to appropriate SQL, make ERPs cool again.) https://github.com/yashbonde/text2sql 
    
    Text2SQL https://github.com/lokeshlal/TextToSql (For reproducing)
    
    TableQA (AI Tool for querying natural language on tabular data.) [https://github.com/abhijithneilabraham/tableQA](https://github.com/abhijithneilabraham/tableQA)
    
    RAT-SQL (A relation-aware semantic parsing model from English to SQL) https://github.com/microsoft/rat-sql Paper: [https://arxiv.org/pdf/1911.04942.pdf](https://arxiv.org/pdf/1911.04942.pdf) 
    Table2Ans (Table2answer: Read the database and answer without SQL [https://arxiv.org/abs/1902.04260](https://arxiv.org/abs/1902.04260))
    
    GAR: A Generate-and-Rank Approach for Natural Language to SQL Translation [https://github.com/Kaimary/GAR](https://github.com/Kaimary/GAR) 
    
    Cool Speech2Txt2SQL https://github.com/iGSRi/SpeechToTextToSQL
    
    **Available online tools, licenses and pricing:** 
    
    [Text2SQL Alternatives 2023, ProductHunt](https://www.producthunt.com/products/text2sql-ai/alternatives) 
    
    [AI2SQL](https://www.ai2sql.io/)
    [Text2SQL](https://www.text2sql.ai/)
    
    Nichness Tools ****SQL - Sentence to SQL Query (Beta) Generator**** [Nichness Sentence2SQL](https://nichesss.com/tools/sql-sentence-to-sql-query-beta-generator-k8mrJOQVG) 
    
    [SQL Query Generator, LogicLoop](https://www.logicloop.com/ai-sql-query-generator) 
    
    [GPT3Demo on Eng2SQL](https://gpt3demo.com/apps/simple-english-to-sql) 
    
    [Default SQL Transalate, OpenAI](https://platform.openai.com/examples/default-sql-translate) (Just for reference, won't use, never use)
    
    **********************************************Main architectures to be used********************************************** 
    
2. How do we imagine this entire system would look like, in terms of architecture and components used?
    - [ ]  Check other proposals
    - [ ]  Inputs, Outputs Deliverables, mention open-source tech (feasibility)
    - [ ]  Overall Tech pipeline using visuals (Add Miro/other visualization)
    - [ ]  Reproduce:
        - [ ]  specific pre-trained text-to-SQL model? Run a HF Space?
        - [ ]  Custom-trained text-to-SQL model
    Input Text --> Normalization (Stemming, Lemmatization) --> Tokenization --> POS Tagging (required?) --> NER (required?) -->Handling Stop Words (required?) --> Parsing (required?)
    
3. What all open-source technologies we have at our disposal to use in this system ?
    - [ ]  Open Source libraries I would be using
   
4. How do we imagine that the system is not only translating English to sql, but also how it is ensuring its writing the fastest query possible for that task ?
    - [ ]  Complete Step 2 (Reproduce)
    - [ ]  Ascendeum Database access and exploration
    - [ ]  Possible workaround? Returns list of queries (time evaluation), or maybe from a script which already has info about fastest way?
5. How do we imagine feedback loop looking for on the fly optimization of these AI-generated queries ?

### Usecases, other comments

