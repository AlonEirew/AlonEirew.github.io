---
layout: post
title:  "GitHub Copilot — The beginning of the future of software development"
date:   2022-10-01 09:00:00 +0000
categories: posts
image: /assets/img/posts/copilot_illus.webp
---

<figure>
  <img src="{{ page.image }}">
  <figcaption>Photo by <a href="https://unsplash.com/@ricaros?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Danial Igdery</a> 
    on <a href="https://unsplash.com/s/photos/programmer?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a></figcaption>
</figure>

At the end of June 2022 Microsoft, in a collaboration with [OpenAI](https://openai.com/) 
(the creator of cutting edge AI technologies such as [GPT-3](https://beta.openai.com/examples) and 
[DALL-E2](https://openai.com/dall-e-2/)), released a program synthesis tool called [GitHub Copilot](https://github.com/features/copilot). 
Program synthesis is the task of automatically ﬁnding a program in the underlying programming language 
that satisﬁes the user intent, as expressed in the form of some speciﬁcation. This task is long considered the holy grail of computer science, and recent advances in AI, particularly in natural language processing, have helped advance this important field considerably.

Copilot is an implementation of such an AI-based program synthesis tool. It offers autocomplete-style suggestions while coding. A suggestion might be a single line of code or a full function or class. Copilot can also offer suggestions following a natural language comment in the code.

My intent in this article is not to advocate nor critic GitHub Copilot itself, but rather to review and examine this preliminary technology from a software engineer point-of-view and ponder what the future of software development might look like.

It is worth mentioning that other similar/competitive tools either exist or are soon to be released 
(such as [Tabnine](https://www.tabnine.com/), [Kite](https://www.kite.com/), [CodeWhisperer](https://aws.amazon.com/codewhisperer/) 
and [IntelliCode](https://visualstudio.microsoft.com/services/intellicode/)), some of which might 
turn to be superior in some aspects to Copilot. However, Copilot is getting most of the attention, 
why? It is because Copilot provides unprecedented access to both applied tools and the 
[implementation details](https://arxiv.org/pdf/2107.03374.pdf). This gives researchers and developers alike a glimpse of how this technology was orchestrated and applied.

To that end, let’s begin by examining Copilot components. Copilot is composed of a client and a server. The client is installed on the user’s IDE as a plugin and is responsible for sending the relevant data to the server. The server is where Copilot does its magic analyzing the data and sending code suggestions back to the user’s IDE.

The data sent by the client, according to Copilot documentation, is the context in the file being edited along with some related files. However, it is not clear how much context or what related files are being sent each time. This might indicate that there is a mechanism in the client component responsible for code selection, a nontrivial task in a large code base.

The server, on the other hand, is where Copilot’s core-model, called Codex, is hosted. Codex, is a 
large language model with 12B parameters, based on OpenAI’s [GPT](https://arxiv.org/pdf/2005.14165.pdf) 
model architecture. Codex knowledge is acquired by training on vast amounts of code extracted from 
GitHub repositories, some of which are under strict copyrights. This raises [questions](https://www.zdnet.com/article/is-github-copilots-code-legal-ethically-right/) 
and [debate](https://www.reddit.com/r/linux/comments/vidjop/github_copilot_legally_stealingselling_licensed/) 
related to copyrights violations and the safety of using such AI code generation tool. It is therefore recommended to scan and track for code violations in the generated code.

Another aspect to be aware of is related to privacy. The Copilot engine, Codex, is a computationally demanding model, requiring hardware not available on client PC’s. Therefore, Codex is hosted on a dedicated machine in the cloud. This means the IDE is constantly sending what might be proprietary code to a 3rd-party server, where the code is then analyzed. This might be unnerving to some organizations and developers. Contrary to code violations which can be mitigated, overcoming this privacy issue will be more challenging due to the high computational costs of running the Copilot server (or Codex) on premise.

Now that we have briefly covered Copilot’s internal functioning, we can address the interesting part of hands-on user experience. Since there is a lot more to Copilot than can be covered in this short article, I’ve summarized its four biggest advantages (in my opinion):

1. There is no learning curve to using Copilot; it is as simple as writing code or describing the code you would like as you would normally do. This is ideally what we would like from advanced program synthesis tools, and Copilot meets the expectation.
2. To set the right user expectation, Copilot code generation is stated to perform best at producing boilerplate code (for example: I/O operations, data manipulation, etc.) and repetitive code patterns (such as predicting the code fragment that usually follows some code). To that end, I found Copilot to exceed my expectations.
3. One of the most interesting and challenging aspects of program synthesis is the ability to describe the desired functionality in natural language comments, a task referred to as “[Prompt Engineering](https://en.wikipedia.org/wiki/Prompt_engineering)”. Copilot can understand and suggest correct or close enough solutions to nontrivial functionality descriptions. Nonetheless, there is still much room for improvement. This, undoubtably, will take center stage in future competing solutions.
4. Finally, Copilot-generated suggestions can contain calls to classes, functions or packages that are not yet declared. In these cases, the IDE code completion and refactoring tools helped filling the gaps. I found these technologies to create a “symbiotic like relationship” helping me getting the job done faster.

On the downside, Copilot can be “over suggestive”, It takes a bit of time getting used to being prompted constantly, while fighting the urge to review all the proposed suggestions. This behavior might require a UX adjustment rather than a model change.

Conclusions: While the legal concerns and code privacy issues might prevent some organizations and developers from broadly using Copilot or a similar tool, this is a new production-ready AI-powered technology with very promising initial results. I, personally, will continue using Copilot as I feel it already brings me genuine value as a developer. Soon, we will probably see additional players releasing competing tools as well as improved versions of Copilot. This will further advance the technology.

Last, I look forward with anticipation at what might come out next. Program synthesis has opened the potential of combining several technologies together, 
in the pursuit of generating better and more refined code suggestions (such as; 
[code completion](https://en.wikipedia.org/wiki/Intelligent_code_completion), [code refactoring](https://en.wikipedia.org/wiki/Code_refactoring), 
[static code analysis](https://en.wikipedia.org/wiki/Static_program_analysis), tools for scanning 
for vulnerability, efficiency, and security gaps). This, has the potential to revolutionize the future of software development and accelerate development cycles.

## Acknowledgements
I would like to thank [Nagib Hakim](https://www.linkedin.com/in/nagib-hakim) for his review and feedback on earlier versions of this article.