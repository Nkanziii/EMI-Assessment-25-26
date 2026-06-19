# EMI-Assessment-25-26


# The news as a Nervous system

[Weblog Link](weblog.md) 

Link to video: [link](http://arts.ac.uk)

# Introduction

 This project explores how news cycles shape a collective emotional and political state. Especially for ethnic minority groups in the western society. As someone who has dual nationality and is originally from Iran, with the current state of the world I have seen how the news has such a big emotionaly impact on my family and other Iranian British citizens. Especially when we still have family and people we love in our home country that are living under bomb strikes and terror, with out the peace of mind that their government is protecting them, or with a route to escape.

 The objective was to builf a pipeline that makes that emotional undercurrent visible, turing live headlines into an abstract visual signal, interpreted completly by the model dependent on the prompts i give for each emotion. 
 Using ML to interrogate/expose a process, not just automate a task.


# Related technical and/or creative work

**Refik Anadol:** Data-driven, large-scale generative visualization of collective/environmental data.

**Ryoji Ikeda:** Abstraction of data into a preceptual/sensory experience.

**Adam Cole, Kiss/Crash:** A project where A trained ai model, reflects human intamacy and kisses, after a car crash.

**Caramiaux & Fdili Alaoui(2022):** theoretical anchor: categorizing how artists use AI (critically vs. instrumentally).

# Summary of design and development process

In the beginning, the design process was very simple and surface level, the main emotions being: fear, anger, sadness, surprised, joy, disgust and fear, and each emotion has a score level based on the emotion model API i grabbed from hugging face. Based on the prompt recieved associated with each emotion the model will generate an image. In the beginning the image generated very dull, abstract colours in gray scale, which contributed to the theme of neutral, meaning the AI model viewed every headline as neutral. I then changed this narrative so it takes, 3 different top emotions and creates an image based on that, which in the beginning I associated anger disgust and fear and rotting fruit and the colour red. 
After this I created a moodboard based on each emotion, and created detailed prompts for the ai model to generate the image. And with the prompt the model became more and more specific and showing faces, bit distorted and creapy.

# Summary of final version

The final version of my project is a trained Ai model, that generates images, grabbed from News apis the top headlines of today, and with detailed prompting, picks the top 3 emotions with the highest score resonating to the headlines and what emotions they evoke and generates images based on this. This was a trial and error as in the beginning getting it to escape that neutral safe space was difficult to do.

# Evaluation

Has your project accomplished your objectives? How do you know? E.g., you might wish to employ some critical reflection with some illustrative examples, provide some plots or tables arising from quantitative evaluation, provide a description of some qualitative engagements with pilot audiences or users, etc. 

Your evaluation may be described already in your weblog; if so, give us a high-level description along with key links to your weblog entries.

# Reflection and conclusion

How do you feel about your final project, in the end? What might you do differently, or how might you continue to work on it? Etc.

# Repository structure and instructions for running

 
## Repository structure
 
```
final-project/
├── step-1/
│   └── news.ipynb        # [main pipeline — This is the jupyter notebook where everything is tested]
├── research/              # [brainstorm image]
├── week-2/                 # [research and setting up apis and tokens]
├── step-3/                  # [images from the image generation]
├── step-4/                  # [more images]
├── assets/                   # [all the images and assets i used inside the weblog]
├── README.md
└── weblog.md
```
 
[1-2 sentences: which file is the actual deliverable, which folders are supporting/process documentation]
 
## Pipeline overview
 
[Your own sentence(s) covering, in order:]
1. Install dependencies — `transformers==4.30.0`, `diffusers==0.21.0`, `huggingface_hub==0.16.4`, `torch`
2. Fetch headlines — NewsAPI, query: `[your actual query terms]`
3. Classify — each headline scored for emotion
4. Average — scores combined into one collective state across all headlines
5. Generate prompt — dominant emotion mapped to visual language
6. Generate image — Stable Diffusion (`runwayml/stable-diffusion-v1-5`), saved to `output.png`
## How to run
 
**Environment:**
- [conda/EMI kernel, Python version]
- Install dependencies: `[your actual pip/conda command(s)]`
**API key:**
- Requires your own NewsAPI key
- [describe how you're handling it now — env variable / .env file / etc., matching what you actually did]
**Running the notebook:**
- Open `news.ipynb` in [Jupyter / VS Code], select the `[kernel name]` kernel
- [Run All / run top to bottom] — note: [your own note about the prompt-must-be-defined-before-Stable-Diffusion-cell dependency, if still relevant]
## Current scope
 
[Your own 2-3 sentences: what works end-to-end, what's out of scope — e.g. single image per run, no batch/video output, prompt mapping is hand-designed rather than learned]


# Statement on use of AI tools (draft — review and edit to match your actual usage before submitting)
 
I used Claude (Anthropic) throughout the development of this project's code, primarily as a guided problem-solving aid rather than a code-generation tool. Specific uses included:
 
- Debugging Python/library version conflicts between `transformers` and the EMI kernel's pinned `torch` version, which I resolved by pinning `transformers==4.30.0`.
- Working through logic for averaging emotion classifier outputs across multiple headlines into a single collective score, where Claude asked guiding questions about my looping approach rather than supplying the solution directly.
- Troubleshooting notebook execution order issues (e.g. a Stable Diffusion cell failing because an upstream `prompt` variable hadn't been defined yet), and identifying that my `get_prompt()` function was defined but never called.
- Adjusting Stable Diffusion generation parameters (adding a `negative_prompt` and increasing `guidance_scale`) to resolve an issue where outputs defaulted to greyscale/monochrome.
- General planning support: breaking the project into a weekly schedule with milestones, and discussing how to frame the project's critical use of AI in relation to Caramiaux & Fdili Alaoui's (2022) framework.
- CV/LinkedIn wording support for describing this project professionally (not part of the academic submission itself).
I did not use Claude or any other AI tool to write the weblog entries or this readme document; those were written by me. Where I asked Claude for help structuring this readme, I used bullet-point prompts and wrote the prose myself.
 
---

# References

Anadol, R. (n.d.) *Refik Anadol Studio*. Available at: https://refikanadol.com/ (Accessed: [add date]).
 
Caramiaux, B. and Fdili Alaoui, S. (2022) '"Explorers of Unknown Planets": Practices and Politics of Artificial Intelligence in Visual Arts', in *Proceedings of the 2022 ACM Designing Interactive Systems Conference*. New York: ACM, pp. [add page numbers].
 
Cole, A. (n.d.) *Kiss/Crash*. Available at: [add URL] (Accessed: [add date]).
 
HuggingFace (n.d.) *bhadresh-savani/distilbert-base-uncased-emotion*. Available at: https://huggingface.co/bhadresh-savani/distilbert-base-uncased-emotion (Accessed: 15.05.2026).
 
Ikeda, R. (n.d.) *Ryoji Ikeda*. Available at: https://www.ryojiikeda.com/ (Accessed: [add date]).
 
NewsAPI (n.d.) *NewsAPI.org*. Available at: https://newsapi.org/ (Accessed: 18.05.2026).



