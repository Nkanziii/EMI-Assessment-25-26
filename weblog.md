# EMI 2026 Final Project Weblog

You should have at least 10 dated entries in your weblog describing your iterative progress on your project. The clarity and completeness of your weblog is an integral part of your project and its marking.


<h2>Entry: 8 May 2026</h2> 
Brainstorming project ideas, I want to lean towards

<p align='center'>
  <img src="assets/research/brain-storm.jpg" width='400'/>
</p>

<h2>Entery: 12 May 2026</h2>
Diving deeper into my project idea, I didn't feel too emotionally drawn to the context of my previous idea, I wanted to add onto the theme of creating a machine leanering model that inputs peoples emotions via webcam and creating a visual generative video based on this. I felt as though this was quite boring and mundane there was no emotional attachment to this. Therefore, I have decided that I want to explore a more sensitive but emotionally compelling theme of using news data and headlines instead.

<h3>Project Concept: 'The news as a nervous System'</h3>
<p>Creating a Machine learning system trained on live news data (as input) that classifies the emotional state of the current world events, measuring fear, anger, sadness and hope.
Outputs a real time abstract visual in p5.js that responds to those emotional scores.</p>


<p align='center'>
  <img src='assets/research/brain.jpg' width='800'/>
</p>

<h4>The ML part:</h4>
<ul>
  <li>Input: News headlines from newsAPI.org</li>
  <li>Model: a sentiment/emotion classified</li>
  <li>Output: numerical scores per emotion category of my choosing</li>
  <li>The scores drive the p5.js visuals</li>
</ul>

<h3>Context</h3>
I wanted to make this project abit personal to me, as i often do with my projects, i feel like it relates more to an audience that also likes emotional attachment with artistic and technical pieces. I want to be attached to my pieces and create something i know alot of people will resonate with as well. My thought process actually came from how the current news and state of the world especially in the Middle East affected me and my family as well as many other people in the same situation. Coming from Iran watching the current state of the world is genuinely devestating, and with the rest of my family living with bombs dropping next to their houses, I feel bad that this is their reality and they cannot leave and we can not visit our motherland. I always knew that the news affects everyone differently and there is always negative emotions. However, for the first time i saw how it psychologically transformed one of my family members, making them relaps into psychosis and schitzophrenic episodes. She, disasociated with her reality and lost herself into a deep psychological parallel reality, because shes scared for the state of Iran and when can she go back to see her family. I was terrified of the hellucinations i was hearing about, and started to witness and understand a whole different level of psychological trauma about hearing unsettling news. Which is why I wanted to name this project 'The News as a Nervous System'. 

<h3>Artist references</h3>

<p align='center'>
  <img src='assets/research/refil.jpg' width='800'/> 
  <img src='assets/research/ryoji.jpg' width='800'/> 
</p>

<h2>Entery 2: 19 May 2026</h2>

So far in the project I have:

<ul>
  <li>Got news Api free key at newsApi.org</li>
  <li>Wrote python script to pull live headlines</li>
  <li>Tested a pre-trained emotion model from huggingFace</li>
</ul>

<p align='center'>
  <img src='assets/step-1/newsApi.png' />
</p>

This is the news api website where I got a personalised api key to include in my python code to grab current trending news data.

<p align='center'>
  <img src='assets/step-1/hugginFace.png' />
</p>

This is the huggingFace website where I found my pre-trained emotion model and attached this model to detect the emotional states of news headlines i got from the news Api.

<h4>current code</h4>

[news.ipynb](assets/code/news.ipynb)
