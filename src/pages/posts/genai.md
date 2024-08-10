---
layout: ../../layouts/post.astro
title: "Understanding Generative AI"
pubDate: 2024-08-10
description: "Our project for Buildathon 2024"
author: "Pranav"
excerpt: "Generative AI is transforming creativity by generating new content like text, images, and code from existing data. While it's powerful, it raises concerns about creativity, job displacement, and data security. Balancing its benefits with mindful use is key to harnessing its full potential."
image:
  src:
  alt:
tags: ["GenAI", "AIML","LLM"]
---
---
If you've been keeping up with tech news lately, you've probably heard about this buzzing topic that's taking the AI space by storm. But what exactly is Generative AI ? and why is everyone talking about it? Well, think of it as that one friend who’s incredibly creative and can whip up anything with just a bit of inspiration. But instead of a human, it’s a machine doing all the creative heavy lifting.

It’s like it popped out of nowhere on a random Tuesday afternoon. Some say it's the future, some say it’s the end of creativity, and others fear it’ll steal our jobs. As with most things, the truth lies somewhere in between
> Spoiler alert: I agree with all of these views—but only partially. Let’s explore why.

### What is GenAI
Generative AI (GenAI) is a branch of artificial intelligence that focuses on creating new content. The magic behind Generative AI lies in its ability to use **existing data** to create something entirely new, something that looks, sounds, or feels real.
In simple terms, Generative AI can create content—like text, images, music, or even code—on its own. It’s not like the AI we’re used to, which just follows instructions or analyses data;
 
 Is GenAI a boon or a bane to us? People often think GenAI was suddenly dropped on us, fully formed, but it’s been in development for years. It’s an amazing technology—one that can help us write, look up stuff, generate content (like code, blogs, or even art). But, every wave of technology comes with trade-offs.

- Take calculators, for example. They made math easier to an exponential level but started the decline of simple mental arithmetic like knowing multiplication tables or knowing shortcuts for calculations or what we popularly call *vedic math*. 
- Then came spreadsheets—great for managing data, they  reduced our reliance on traditional bookkeeping skills. 
- Phones evolved too; we can call anyone, anywhere, but now we barely remember phone numbers because our contacts app handles it. 
- Now phones are developed where they can practically substitute lower end laptops, but what we need ask ourselves is "how dependent are we on the autocorrects of our phones and how well we know our spellings?"

Now, GenAI is the **latest wave**. It’s doing the creative heavy lifting—autogenerating content, art, and ideas—but we risk losing our unique creativity and critical thinking if we rely on it too much.

For example: All through my school years, I had to dig through textbooks and presentations, understand concepts, and use tools like Wikipedia or YouTube to reinforce what I learned. It was a multi-step process that helped me really grasp the material. Now, I can just ask an AI to explain a topic. While that’s convenient, it means I’m spending less time deeply understanding and more time skimming through.

Lets address the elephant in the room now **Will GenAI take away jobs?**
Not all of them. Sure, it’ll automate some tasks, but it still needs human direction. The prompt *"create an image of a cat"* gives you one result, but *"create an image of a black cat with green eyes jumping from a grey cement wall onto the street"* requires more detailed input—and that’s where human creativity and specificity come in. As mentioned before, GenAI lacks the true skill to innovate something novel, it wont generate code to build some product the world has never seen;  it generates content based on what it’s seen before. We can think of GenAI as a glorified search engine where you don't have to go through multiple website to collect information, it does your work for you and puts it in one place. So, while GenAI is powerful, it’s not about to replace human ingenuity. Our jobs aren’t going anywhere, and there’s no imminent threat of AI taking over the world like aliens.

### **The W-H Questions of GenAI**


##### **What is GenAI?** 
Generative AI, or GenAI, is a branch of AI that focuses on creating new content. Unlike traditional AI models that analyse or predict based on existing data, GenAI uses machine learning techniques to generate new outputs that mimic the patterns and structures it has learned from **its training data**. Large Language Models (LLMs), like GPT, are a subset of GenAI focused on generating human-like text.

##### **When Should We Use LLMs?** 
LLMs are incredibly useful when you need to generate text quickly, brainstorm ideas, or automate content creation. They’re great for drafting emails, writing code snippets, or even creating fictional stories. However, they’re not a replacement for deep, nuanced thinking, and they shouldn’t be relied upon for tasks requiring precise judgment or highly specialised knowledge.

##### **How Do We Effectively Use LLMs?**  
To get the most out of LLMs, use them as a starting point or a tool to enhance your work. Provide clear, detailed prompts, and always review and refine the output. Remember, while LLMs can generate text, the creativity and critical thinking behind that text are still very much human responsibilities.

##### **Where to Use LLMs?** 
LLMs are widely used in content creation platforms, coding environments, and even customer service bots. For those interested in experimenting with LLMs, open-source models are available, which can be fine-tuned for specific applications. 


### **The Dark Side of GenAI**
- **Hallucinations:** LLMs sometimes unknowingly generate content that is factually incorrect, misleading or it can generate false positives.

- **Bias:** AI models can perpetuate biases present in their training data, at the end they generate output based on its training data, so if the model is trained to avoid certain topics it will, if it has been trained to respond to certain question in limited ways. We truly don't know if there's an agenda behind it. 
	  - An incident that does justice to the statement is Google's LLM avoiding the topic of US politics, this proves that people's opinion can be swayed just because a model was trained in a particular way
	
- **Data Security:** 
	- Concerns over where training data comes from
	- What are it's sources, how credible are they?
	- How it’s used
	- How your data is stored
	- Where is your data stored
  Recent incidents have highlighted the risks of using GenAI models hosted by big tech companies. For instance, Gemini, a model developed by Google, was found to be accessing people’s Google Drive and Gmail data. While this access is meant to improve the AI’s performance, it raises serious questions about privacy and data security. We don’t really know what information is being stored or how it’s being used, which makes it hard to trust these platforms completely.
  
- **Intellectual Property Issues:** Ownership of AI-generated content is a legal gray area.

- **Deepfakes:** Misuse of GenAI to create realistic but fake media.

- **Cross-Chat Memory:** Risk of retaining information across sessions, leading to privacy concerns.


## **How do I safely use GenAI**
 I rely on my own model, which is private. By running it locally, I manage exactly what gets processed, ensuring there's no scraping of my data from services like Google Drive or Gmail. I found my model on Ollama, a website that’s lists all the free models we can use, say-github for open-source models. The best part? I don't even need the internet to use it. With enough RAM and CPU power, you can also run a model like Llama 3.1 locally on your laptop, giving you complete control over your AI interactions.

I took it a step further by asking a friend to help me write a zsh script that allows me to run all the necessary commands with just one line. This makes firing up my model even more efficient and streamlined. With a single command, I can quickly get my Llama 3.1 model up and running, all while keeping my data secure and private.
