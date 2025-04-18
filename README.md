# SOQ_Ml1
[Kaggle Dataset](https://www.kaggle.com/datasets/danofer/sarcasm) - here I wanted to do a fun project to adress the problem: </br>
LLMs mostly can't adress sarcasm and I'm furious! How many time have I wanted to troll deepseek or perplexity but they didn't understand </br>
me , so, i wanted to explore this little thing.
I don't really tabular data work, therefore, I've chosen the fun NLP task that i can still solve with easier models like linear regression and </br> easier ansumbles like forest.  </br>
My final point is to 'sell' to you this model : this is model that will help to find if a customer is chill, therefore, making a discount for him </br> Moreover, if he uses sarcasm - our LLM like 'oleg - helper' will answer with sarcasm too </br>

My plan for the project - try to detect whether message - sarcasm or not. </br> 
In order to do it i can go multiple ways:
1. Can just encodes certain "combos" to ensure that the most obvoius things are encoded 
2. Vectorize data - to make it computer compatible 
    - Also , I wanted to share cool insigts as sarcasm usually follows this tropes
        - certain words like 'bruh' or 'deez nuts'
        - caps like THAT
        - repetition of certain letter like - 'yeahhhhhh' and so much more
    - "This vectorization guy is pretty strong , vegeta , i don't think that we can beat him"
        - Vectorization of sklearn follows many complicated rules that i need to adress
            - Length of the 'combos' of words 
            - skip 'lower() ' altoteghter becaue 'YEAH' and 'yeah' is different
            - and so much more like
                - Regex breakdown:
                    1. \b\w+\b: Standard words.

                    2. !+/s: Explicit sarcasm marker (!/s).

                    3. \?{2,}: Multiple ??.

                    4. \S+: Catch-all for emojis/odd punctuation.
3. Try to fit the model with binaryzation - worst computational speed but exhaustive - as we can fit everything 
4. EDA - hard , will try to escape it as hard as possible , however, my specification of sarcasm and NLP combos is EDAnough , I suppose
    - Permutation importance - wll not be useful for NLP , maybe if we shuffle words? - no idea
    - SHAP - would definetely be just a list of the most useful words 
        - will use XGboost version of shap - it's built in
5. Use Optuna for full points and try to use Linear Regression , and Bagging(forest) and XGboost (small trees combined but they can be different height)
6. don't really understand different metrics of validation part 
* use prebuilt block system like vgg - faster and easier with dim like 64 and medium batch size
