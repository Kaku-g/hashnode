---
title: "AI-Pdf Summarizer"
datePublished: Sat May 20 2023 05:51:48 GMT+0000 (Coordinated Universal Time)
cuid: cli8qvui4000w08jp4bqs9eoc
slug: ai-pdf-summarizer
canonical: https://dev.to/kakug/ai-pdf-summarizer-2p56
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1685358013673/41621538-ca09-4edd-8375-18a811188345.png
tags: ai, github, python, tools, flask

---

#### About:

So, with AI tools spreading like a fire with the advent of Chat-GPT. I thought to make one app myself but ' without using OpenAI's api ' as it is not econmically feasible for longer tasks. So I decided to move forward with HuggingFace model which is open source and can be integrated easily with python.

#### Screenshots:

![Ai-pdf-summarizer web app image](https://cdn.hashnode.com/res/hashnode/image/upload/v1685358011345/478336f8-763a-4008-ba40-df9b2ba98001.png align="left")

#### Description

So lets talk about how to use the app or What else are we waiting for! . The app takes in PDF as an input from the user and produces the summary of the pdf in output as PDF. It is built using hugging face pre-trained model which is implemented using transformers. The web app is built using flask (a python framework) and various libraries for working with PDF. The app speed can be improved further by using the capabilities of GPU present in our system. So running the app on machines having GPU, speeds up the process.

How to install Locally? The app can be installed locally by following the instructions given in the github repo which can be found below.

#### Link to Source Code

The source code can be found on [Repo](https://github.com/Kaku-g/ai-pdf-summarizer)

The app is deployed on [Web](https://lionfish-app-r9d4y.ondigitalocean.app/) Can be setup locally by cloning the [repo](https://github.com/Kaku-g/ai-pdf-summarizer)

#### Permissive License

The repository/app comes under MIT License. For more information about the license you can visit [License](https://github.com/Kaku-g/ai-pdf-summarizer/blob/master/LICENSE)

#### Background story :)

So I had my exams and I needed to read the whole PDF, but due to the time constraint it was not feasible to cover whole document in one sitting so decided to make an app for summarizing the contents of PDF ;) .As most of the tools I found on the internet were paid and the results were not promising, so I thought to give it a try.

#### How I built it &lt;&gt;&lt;/&gt;

It was built using hugging face transformer model, so learned to implement it using python, also worked with PDF files using various libraries. Learned flask along the way as my primary working stack was MERN. Most of the things were new and I had to overcome many challenges, but it was worth it :). Overall it was an exciting and fun experience to work on such a project. The github actions was used to check all the requirements and the code by creating tests on every push. So continuous testing and integration was implemented using that. Codespaces was used to run the code on the cloud using ubuntu VM, and to test the required changes quickly wihtout going through the code editor again & again.

#### Additional Resources/Info

[Huggingface model for text summarization](https://huggingface.co/models?pipeline_tag=summarization)

[Github actions](https://github.com/features/actions)

[Github codespaces](https://github.com/features/codespaces)

PS- The app can still be improved a lot on design and performance basis, so feel free to create and raise the pull request. Keep coding.

This app is part of Dev X Github hackathon under the category " Wacky Wildcards "