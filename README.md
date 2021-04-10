# GPT2 IndiaSpeaks
[![Open In Collab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1TPgsHyavUQ-wNqDDtncu-mKjAekT-1PD?usp=sharing)

Finetuning GPT2 to generate r/IndiaSpeaks self-posts using [huggingface/transformers](https://github.com/huggingface/transformers/).

## Pre-trained Models

### aarav1

Trained on ~100 unique posts repeated multiple times. No idea how it works but it's better than the newer one somehow.

* [Training Data](https://drive.google.com/drive/folders/1by-fwkDV7KXPUcuAvfSYEeX1N3rp6Vs_?usp=sharing)
* [Model](https://drive.google.com/drive/folders/1-zbiOL6-72ngvd30tMm-6q_rznezhnAh?usp=sharing)
* [Examples](https://drive.google.com/drive/folders/1TuhS9OTkKmcCw2qMxUZ1FWRpYCjksKDQ?usp=sharing)

### aarav2

**WIP**, trained on ~15k posts with best possible cleaning including removing posts in non-ASCII characters, HTML encoding and reddit markdown.

* [Training Data](https://drive.google.com/drive/folders/1ouhLpXZ-vn6h2R35PKHdt98tJHJVKEqq?usp=sharing)
* [Model](https://drive.google.com/drive/folders/1DavOFZej9fFVg-b6cyE8eEPY-UN7HblK?usp=sharing)
* [Examples](https://drive.google.com/drive/folders/1inQdAfJPwlSEPxJ4Bhck5SFDQIyw9Yed?usp=sharing)

These can be downloaded and used to generate text. For info about parameters refer to [this article](https://huggingface.co/blog/how-to-generate) and [this notebook](https://colab.research.google.com/gist/GeorgeDittmar/5c57a35332b2b5818e51618af7953351/lm-huggingface-finetune-gpt-2.ipynb).  
For Example: 
  
```py
from transformers import TFGPT2LMHeadModel
from transformers import GPT2Tokenizer

# Import the trained model
model = TFGPT2LMHeadModel.from_pretrained("path/to/model", from_pt=True)
tokenizer = GPT2Tokenizer.from_pretrained("gpt2")

# Generate new sequences from the trained model
generated_text_samples = model.generate(
    None, 
    max_length=300,  
    num_return_sequences=30,
    repetition_penalty=1.0,
    top_p=0.9,
    temperature=1.0,
    do_sample=True,
    top_k=50,
)

# Decode and display model output
for i, beam in enumerate(generated_text_samples):
  print("{}: {}".format(i,tokenizer.decode(beam, skip_special_tokens=True)))
  print()
```




## Finest Examples  
  
> Bollywood actor Anurag Kashyaps has called on Indian censor authorities to step up and give the right response when he makes a comment about Islam in a movie.
> 
> "I want all Muslims in the world to have the right to free speech. At this stage of the Islam in India debate, no one is talking about 'jizya' or 'takfiris'," Kashyaps tweeted.
> India's blasphemy laws are rife with examples where a Muslim extremist makes a comment that is distasteful to a non-Muslim audience, Kashyaps suggested. But unlike in the past, when an extremist makes a comment that threatens to kill a non-Muslim, such comments are not motivated by hatred, he suggested.In a rare public statement, Kashyaps defended his remarks saying they were not politically motivated.
> A copy of Kashyaps' written statement can be found here. Kashyaps did not respond to requests for comment from The Hindu. He did not respond to multiple phone and e-mails.In a follow-up message, an Indian citizen of Indian descent, Anupam Sinha, expressed her support for freedom of speech in the movie. "I want everyone to have the right to express themselves in a free and open culture. This movie needs to have diversity in its cast, its themes, and its themes are not political.`


> The first three paragraphs in my first essay, "Islam in India: Its Discontents and Implications", deal with two points. The first is that much of Indian thought in the 21st century has shifted to the right in three dimensions: politics, business and societal change. The Indian right has enjoyed strong political, cultural and social differentiation for centuries, but it has suffered from institutional racism, caste and religion. The left has also suffered from cultural and societal change, with most Muslims following a more moderate model of government. Islam in India has been marginalized, with many Hindus following a more fundamentalist interpretation. But it is also true that Muslims in India have also suffered societal and cultural changes, from colonialism to post-colonial rule. Religion of peace has long been a political issue in India, but it has also been linked to inequality, joblessness and caste divisions. It is difficult to reconcile these with Hinduism and Muslim communalism, which both claim an equal share of the world's Muslims. Muslims in India have long been marginalized, having historically enjoyed greater status in the world than their Christian and Muslim neighbours. But in the 19th Century, Islam was seen as a moderate alternative to both. And it has since been seen as a threat to established order. This is because Islam has been seen as a religion that is both universal and tolerant of all faiths. Moreover, it is also seen as a model of brotherhood among Muslims, which has brought it to the forefront in the world today.


> Moreover, the Hindu right is clearly winning in Kerala, with about 6% of the vote to 19.8% among Christians. Now, there are reservations about the BJP's organisational culture in Kerala, which is clearly distasteful to Hindus. But even so, the communal war in Assam is making a comeback in Kerala, with about 18% of the vote to 19.8%.  Kerala's Christians account for the majority of Muslims, which makes up about 6% of the state's total.  At this rate, the communal war could have a long-lasting effect on India's regional politics.  The RSS is also winning in Assam and Kerala, which account for about a third of the vote. In Kerala, where the BJP is winning about 6.5% of the vote to 19.8%, the Congress has suffered a humiliating humiliating washout in Assam, and its gains are eroding. In the three largest states, Indira, Fajr and Sangh Parivar, the Hindu right has been stoking communal feeling in the north and south. In Kerala, where the BJP is winning about 15.5% of the vote to 19%, the Congress is having its worst month in a while. This is because the communal war in Assam is deepening, with Muslims making up only 6.4% of the vote in Assamese state and 6% in Assamese south.

> I am sick and tired of defending Islam in our country. I don't agree with every bit of his statements, but I believe that he is pushing the very definition of Islam that defines us as a people. Islam is not a religion of peace; it is not a religion that expects you to follow the strict interpretation of sharia law, or even follow the sharia encyclopedic law that defines marriage between a man and a woman. Islam is not a religion that expects you to follow the sharia code; it is not a religion that expects you to follow the law of plural marriage. Muslims in India today believe that adultery is a sin against Allah, not a law against Muslims. I have long since removed these statements from my website, as I believe they are politically motivated lies masquerading as evidence to derail public debate. Even though I do not support all of these statements, I still support the right of all Muslims to practise their faith according to their own set of moral code. I want to make clear that I do not support or discourage any action that would instill in others the same belief or ideology that I do not support.Islam in India is not a religion of peace. The country is divided into three major camps. Islamic, Bollywood and Christian. I would like to see both camps demonize each other and try to distance Muslims from each other.
