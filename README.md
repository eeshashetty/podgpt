# podgpt
This is a fake podcast generated using GPT2, created for my [Art and ML Class](https://sites.google.com/view/artml23s) at CMU! <br><br>
You can view the demo [here](https://youtu.be/mWk2NMHxeDU).

## Notebooks
### podgpt.ipynb
---
This has all the code for creating a dataset for finetuning, and the actual finetuning process

#### Creating the Dataset
- Podcast transcripts for the Freakonomics podcast are taken from https://www.happyscribe.com/
- These are scraped using BeautifulSoup and cleaned up to add `<|startoftext|>` and `<|endoftext|>` tokens around each epsiode to guide finetuning

#### Fine-Tuning GPT2
I followed [this](https://minimaxir.com/2019/09/howto-gpt2/) nifty article on finetuning GPT2 with a very simple package. Then just use generate functions to create scripts, you can leave the prefix prompt blank or provide a starting prompt for the model to generate from.

### podgpt tortoise-tts
---
This notebook is directly picked up from Tortoise TTS' [official documentation](https://github.com/neonbjb/tortoise-tts), and altered bit to fix versioning issues, and fit on my generated transcript
- Tortoise only takes in a small amount of text, so I had to break up the transcript into smaller chunks and then add all the files together with [PyDub](https://pypi.org/project/pydub/)
- I also used PyDub to overlay background music to give it a better feel.

## Future Tasks
- [ ] Get more freedom to finetune rather than using a direct package
- [ ] Find better ways to split text to avoid breaks in audio
