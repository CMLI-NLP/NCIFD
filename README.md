## NCIFD
NCIFD (National Culture Instruction-Following Dataset) is a national culture fine-tuning dataset for large models constructed by the National Language Resource Monitoring and Research Center for Minzu University of China.


Our dataset is stored in JSON format. Each data contains instructions (instruct), supplementary information (input) and answer results (ouput).

The specific examples are as follows:
    {
        "instruction": "藏族酥油花灯节的起源是什么时候和由谁创办的?",
        "input": "",
        "output": "藏族酥油花灯节的起源可追溯到1409年，由佛教格鲁派创始人宗喀巴创立，最初是在拉萨庆祝，以纪念释迦牟尼的成道日。"
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
