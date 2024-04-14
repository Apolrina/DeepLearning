# DeepLearning
Обучение искусственного интеллекта для генерации сказок.

Предлагается задание - вырастить собственный искусственный интеллект.

Согласно данным Russian SuperGLUE https://russiansuperglue.com/leaderboard/2 , лучшими LLM для русского языка являются:

1. Mistral-7b-instruct https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.1 от стартапа Mistral.ai, затюненная Ильёй Гусевым на русских инструкционных датасетах https://huggingface.co/IlyaGusev/saiga_mistral_7b_lora (а сейчас Mistral.ai выпустил уже новую версию https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.2 );

2. FRED-T5-1.7B  от Сбера https://huggingface.co/ai-forever/FRED-T5-1.7B

Первый вариант - типичный представитель decoder only архитектуры, а второй - это классический seq2seq-трансформер.

Было сделано следущее:

1) Придумать интересную и забавную задачу для вашего искусственного интеллекта. Была выбрана генерация сказок про животных для детей.

2) Сформировать обучающий (на 80-100 примеров, не больше) и тестовый (примерно на 20-30 примеров) инструкционные датасеты в духе Dolly https://huggingface.co/datasets/databricks/databricks-dolly-15k , только гораздо меньше и для конкретно вашей задачи;

3) Дообучить одну из двух моделей (Mistral или FRED-T5 - на ваш выбор) с помощью LORA tuning https://arxiv.org/pdf/2106.09685.pdf или promp tuning https://arxiv.org/pdf/2104.08691.pdf средствами библиотеки PEFT https://huggingface.co/docs/peft/task_guides/clm-prompt-tuning

4) Оценить качество полученного искусственного интеллекта на тестовой части вашего инструкционного датасета с помощью BERT score https://github.com/Tiiiger/bert_score
