# EMI-Assessment-25-26


# The news as a Nervous system

[Weblog Link](weblog.md) 

Link to video: [link](https://youtu.be/PBWDdoYrHhE)

# Introduction

 This project explores how news cycles shape a collective emotional and political state. Especially for ethnic minority groups in the western society. As someone who has dual nationality and is originally from Iran, with the current state of the world I have seen how the news has such a big emotionally impact on my family and other Iranian British citizens. Especially when we still have family and people we love in our home country that are living under bomb strikes and terror, with out the peace of mind that their government is protecting them, or with a route to escape.

 The objective was to build a pipeline that makes that emotional undercurrent visible, turning live headlines into an abstract visual signal, interpreted completely by the model dependent on the prompts i give for each emotion. 
 Using ML to interrogate/expose a process, not just automate a task.


# Related technical and/or creative work

**Refik Anadol:** Data-driven, large-scale generative visualization of collective/environmental data.

**Ryoji Ikeda:** Abstraction of data into a perceptual/sensory experience.

**Adam Cole, Kiss/Crash:** A project where a trained ai model reflects human intimacy and kisses, after a car crash.

**Caramiaux & Fdili Alaoui (2022):** theoretical anchor: categorizing how artists use AI (critically vs. instrumentally).

# Summary of design and development process

In the beginning, the design process was very simple and surface level, the main emotions being: fear, anger, sadness, surprised, joy, disgust and fear, and each emotion has a score level based on the emotion model API i grabbed from hugging face. Based on the prompt received associated with each emotion the model will generate an image. In the beginning the image generated very dull, abstract colours in gray scale, which contributed to the theme of neutral, meaning the AI model viewed every headline as neutral. I then changed this narrative so it takes, 3 different top emotions and creates an image based on that, which in the beginning I associated anger disgust and fear and rotting fruit and the colour red. 
After this I created a moodboard based on each emotion, and created detailed prompts for the ai model to generate the image. And with the prompt the model became more and more specific and showing faces, bit distorted and creepy.

# Summary of final version

The final version of my project is a pipeline using pretrained Ai models, that generates images, grabbed from News apis the top headlines of today, and with detailed prompting, picks the top 3 emotions with the highest score resonating to the headlines and what emotions they evoke and generates images based on this. This was a trial and error as in the beginning getting it to escape that neutral safe space was difficult to do.

# Evaluation

My project has mostly worked, and hit the target I wanted it to so far, the pipeline did translate live headlines into images that felt emotionally tied to the source material, not random/generic images, it felt intentionally and meaningful.
The best evidence is the Iran/conflict headlines run -> image with red/black, decaying, distorted face, this was genuinely striking to me it evoked fear and anger, and the colours associated with it very well. 
Compared to my early failure with the grey-scale "neutral" outputs when the model played it safe and not indulging, even after so many tries even removing neutral as a option for emotion it was still giving me a hard time, so the growth and the colourful striking images it generated after was honestly so relieving to see. 
Recalling back to Caramiaux, the unpredictability of what the model produced (faces, distortion, not literal illustrations of headlines), was itself evidence the model is interpreting rather than decorating, it portrayed a visual replica of the top 3 emotions fused together, distorted, uncanny, uncomfortable, and thats what I wanted, I wanted it to produce something by itself something striking.

The limitation I guess would be that it generates one image at a time, it would be cooler if it generated a animation perhaps morphing images together, this could  be something I can experiment with further, as I found this project to be really fun and rewarding to make.


# Reflection and conclusion

As previously mentioned, I am proud of the project I made, I am proud of overcoming the hurdle of getting the model to generate self made striking colour uncanny images to reflect the uncomfortableness that watching and reading the news headlines makes us feel. The surprising part I would sad is the first image produced after the constant neutral grayscale ones, how the model started straying away from the safe zone and opening up abit more with how it evoked and interpreted each prompt. Something new I want to try is, it would be cool if it could make a animation or a video montage of the emotions, morphing images together this is definitely something I want to evolve. 
Something that taught me specifically about using AI critically is that AI even if trained with a certain criteria, even if you wanted to make something completely new, it is still biased it doesnt bend to your will, with the data it gathers from APIs it still gives the illusion that your not fully in control of it. 


# Repository structure and instructions for running

 
## Repository structure
 
```
final-project/
├── step-1/
│   └── news.ipynb        # main pipeline — This is the jupyter notebook where everything is tested
├── research/              # brainstorm image
├── week-2/                 # research and setting up apis and tokens
├── step-3/                  # images from the image generation
├── step-4/                  # more images
├── assets/                   # all the images and assets i used inside the weblog
├── README.md
└── weblog.md
```
 
Step-1 is where the actual code resides thats the main pipeline, and step 3 is the Image generations.
 
## Pipeline overview
 
1. Install dependencies — `transformers==4.30.0`, `diffusers==0.21.0`, `huggingface_hub==0.16.4`, `torch`
2. Fetch headlines — NewsAPI, query: `"Iran OR protest OR conflict OR war"`
3. Classify — each headline scored for emotion
4. Average — scores combined into one collective state across all headlines
5. Generate prompt — top 3 dominant emotions mapped to visual language
6. Generate image — Stable Diffusion (`runwayml/stable-diffusion-v1-5`), saved to `output.png`

## How to run
 
**Environment:**
- EMI conda kernel, Python 3.10
- Install dependencies:
  ```
  pip install transformers==4.30.0 diffusers==0.21.0 huggingface_hub==0.16.4
  pip install --upgrade torch
  ```

**API key:**
- Requires your own NewsAPI key
- The notebook ships with `API_KEY = ""` as an empty placeholder — paste your own NewsAPI key into this string before running the headline-fetch cell

**Running the notebook:**
- Open `news.ipynb` in Jupyter or VS Code, select the `emi` kernel
- Run All — note that the `get_prompt()` function must actually be called (not just defined) before the Stable Diffusion cell runs, or the `prompt` variable will be undefined and the cell will fail

# Use of other third-party resources

The Stable Diffusion integration in this project was adapted from the UAL EMI course notebook `03_StableDiffusion_animations.ipynb`. The model loading and pipeline setup (loading `runwayml/stable-diffusion-v1-5` via the `diffusers` library) follows the structure of that course notebook. The prompt-construction logic — mapping the top 3 dominant emotions from the headline analysis to specific visual language — is my own work, built on top of that base setup.

 

# Statement on use of AI tools
 
I used Claude (Anthropic) throughout the development of this project's code, primarily as a guided problem-solving aid rather than a code-generation tool. Specific uses included:
 
- Debugging Python/library version conflicts between `transformers` and the EMI kernel's pinned `torch` version, which I resolved by pinning `transformers==4.30.0`.
- Working through logic for averaging emotion classifier outputs across multiple headlines into a single collective score, where Claude asked guiding questions about my looping approach rather than supplying the solution directly.
- Troubleshooting notebook execution order issues (e.g. a Stable Diffusion cell failing because an upstream `prompt` variable hadn't been defined yet), and identifying that my `get_prompt()` function was defined but never called.
- Adjusting Stable Diffusion generation parameters (adding a `negative_prompt` and increasing `guidance_scale`) to resolve an issue where outputs defaulted to greyscale/monochrome.
- General planning support: breaking the project into a weekly schedule with milestones, and discussing how to frame the project's critical use of AI in relation to Caramiaux & Fdili Alaoui's (2022) framework.
- CV/LinkedIn wording support for describing this project professionally (not part of the academic submission itself).
- Structuring this readme: I described what had actually happened in my project, and Claude turned that into section headings and bullet points covering the right factual details (e.g. dependency versions, file structure, run order). I then wrote the final sentences and all reflective/evaluative content (Introduction, Evaluation, Reflection and conclusion) myself.
I did not use Claude or any other AI tool to write the weblog entries; those were written entirely by me.
 
---

# References

Anadol, R. (n.d.) *Refik Anadol Studio*. Available at: https://refikanadol.com/ (Accessed: 12.05.2026).
 
Caramiaux, B. and Fdili Alaoui, S. (2022) '"Explorers of Unknown Planets": Practices and Politics of Artificial Intelligence in Visual Arts', in *Proceedings of the 2022 ACM Designing Interactive Systems Conference*. New York: ACM.
 
Cole, A. (2026) *Kiss/Crash*. [Lecture]. Engaged Machine Learning, University of the Arts London.
 
HuggingFace (n.d.) *tabularisai/multilingual-emotion-classification*. Available at: https://huggingface.co/tabularisai/multilingual-emotion-classification (Accessed: 12.05.2026).
 
Ikeda, R. (n.d.) *Ryoji Ikeda*. Available at: https://www.ryojiikeda.com/ (Accessed: 12.05.2026).
 
NewsAPI (n.d.) *NewsAPI.org*. Available at: https://newsapi.org/ (Accessed: 18.05.2026).
 
University of the Arts London (2026) *03_StableDiffusion_animations.ipynb*. [Course notebook]. Engaged Machine Learning, University of the Arts London.



