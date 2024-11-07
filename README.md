## NCIFD
NCIFD (National Culture Instruction-Following Dataset) is a national culture fine-tuning dataset for large models constructed by the National Language Resource Monitoring and Research Center for Minzu University of China.


Our dataset is stored in JSON format. Each data contains instructions (instruct), supplementary information (input) and answer results (ouput).

The specific examples are as follows:
    {
      
        "instruction": "根据输入中给定的节日，介绍其在中国少数民族中的庆祝方式和意义。",
      
        "input": "春节",
      
        "output": "春节是中国最重要的传统节日，也被称为农历新年。在中国少数民族中，春节有着不同的庆祝方式和意义。\n- 在汉族中，春节通常会进行大型家庭聚餐，赏花灯、放烟火等活动，并且会贴对联和挂红包等来祈求幸运和财富。\n- 在藏族中，春节被称为“扎西德勒”，意为“吉祥如意”。他们会穿上盛装，跳起特殊的舞蹈，同时还会举行马术比赛和射箭比赛。\n- 在傣族中，春节被称为“水节”，他们会在河边放生小龙虾，同时还会举行划龙舟比赛和打水仗等活动。\n总的来说，春节在中国少数民族中都具有团圆、祈福和欢乐的意义，是一种传承千年的文化传统。"
   
    }

## Contributions

(1) We collected and sorted out 18 books related to ethnic culture, such as "Encyclopedia of Chinese Ethnic Groups" and "Chinese Costume Encyclopedia", and generated QA pairs by constructing prompts and using a large language model. We screened the quality of the generated QA pairs, evaluated the clarity of the questions, the completeness, accuracy and clarity of the answers, and the overall independence of the Q&A pairs, and rewrote the answers with poor content quality. Finally, we obtained the NCQA dataset.

(2) We used the sorted ethnic culture books to construct the NCSC (National Culture Seed Collection), which covers seven major areas such as food, etiquette, language, and customs. We used the guidance of the seeds to generate datasets using a large language model through the Self-Instruct framework, and screened the quality of the generated data. Finally, we obtained the NCSI dataset.

(3) We conducted fine-tuning experiments on mainstream open source models such as ChatGLM-6B and Llama-2-7B, and used Wenxin Yiyan 4.0 to evaluate the accuracy and fluency of the fine-tuned model responses. At the same time, we verified the reliability and authenticity of the large language model evaluation through manual evaluation.

## Experimental Result:

We selected NCSI, 30,000 NCQA, 150,000 NCQA, and a mixture of NCSI and NCQA. ChatGLM3-6B-Base, Llama2-7B, Baichuan2-7B-Base, and Qwen1.5-7B were used as fine-tuning base models, and the low-rank adaptation method was used for fine-tuning and their ROUGE-L scores were calculated.

<p align="center">Table 1: ROUGE-L Experimental Results.</p>
<p align="center"> <img src="https://github.com/CMLI-NLP/NCIFD/blob/main/images/30879812727bc4f4ce1fdcf7b7ac086.png" width="800" /></p>

At the same time, the Wenxinyiyan 4.0 large language model is used to extract the core content of the standard answers in the test set by writing prompts, and the accuracy is scored by semantic comparison with the replies of the experimental model. At the same time, the fluency is scored based on the logic and length of the reply sentences.

<p align="center">Table 2: Experimental results of Wenxinyiyan 4.0.</p>
<p align="center"> <img src="https://github.com/CMLI-NLP/NCIFD/blob/main/images/c01c52497cced511f303ece644a4368.png" width="800" /></p>

## Download

[Data Set](https://github.com/letsgoLakers/NCIFD/tree/main/NCFID%E6%95%B0%E6%8D%AE%E9%9B%86) 
