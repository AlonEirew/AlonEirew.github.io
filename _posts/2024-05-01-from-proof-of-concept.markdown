---
layout: post
title:  "From Proof of Concept to Product: Key Considerations for Building with Chatbots"
date:   2024-05-01 09:00:00 +0000
categories: posts
image: /assets/img/posts/poc_illus.webp
image1: /assets/img/posts/poc_illus.webp
image2: /assets/img/posts/venturebeat.webp
---

Recently, I’ve been introduced to a huge industry that I was previously unaware of — The Print-on-Demand (PoD) industry, and the story behind its growth serves as a compelling testament to human ingenuity and the transformative power of technology.

<figure>
  <img src="{{ page.image1 }}">
</figure>

By now, we have all grown accustomed to the rapid pace of large generative AI model releases, also referred to as generative Large Language Models (LLMs) or chatbots (such as ChatGPT). Chatbots are undoubtedly exceptional in their capabilities. Given an instruction, they can engage in natural conversations, answer questions, perform text summarization and paraphrasing, write code, plan vacations, provide medical or legal consultations, and much more. In some areas, they even surpass human experts.

The adoption of AI and chatbots by both the industry and the general public is remarkable, clearly demonstrating the interest and practicality of this relatively new technology. For instance, as a non-native English speaker writing this blog, I used ChatGPT to help me correct grammar, enhance spelling, and improve phrasing, and I used DALL-E to generate the blog image. This potential has captured the imagination of product managers, software engineers, industry leaders, and entrepreneurs inspiring them to explore how they might leverage this untapped technology to develop exciting products.

If you are one of those individuals, you’re in the right place. This article is aimed at non-AI experts who would like to gain insights into leveraging generative AI and chatbot technologies to accelerate product development. Understand the benefits and challenges you might encounter along the way, and make informed decisions to help enhance your product’s success.

The chatbot landscape has been constantly expanding over the last year, with new names emerging on a regular basis. Some of the current most well-known chatbots include GPT-4o (OpenAI), Gemini (Google), Claude (Anthropic), Perplexity, Llama (Meta), Mistral, Copilot (Microsoft), and the recent Command-R (Cohere), to name just a few. For details, comparisons, and to keep up with the pace of new releases, check HuggingFace’s chatbot arena leaderboard and Artificial-Analysis.

<figure>
<img src="{{ page.image2 }}">
  <figcaption>Chatbot Landscape 2023 for companies with ChatGPT-like models (source:<a href="venturebeat.com">venturebeat.com</a>)</figcaption>
</figure>

Another recent development in this chatbot landscape has been the introduction of “open” chatbot models. The more well-known models, such as GPT-4o, Gemini, Perplexity and Copilot, are “closed” models and can only be accessed through their commercial cloud API’s. In contrast, “open” models, such as Llama, Mistral, Phi, and Command-R, can be downloaded (via HuggingFace models), further fine-tuned, and deployed locally. In other words, an open model means the user can own a version of the chatbot and “calibrate” it for a specific use-case. Additionally, the once clear advantages of closed models is no longer definitive. However, this openness should be taken with a grain of salt, as fine-tuning or running a chatbot in-house is expensive, and in some cases even more expensive than using a cloud service of a closed one.

Most chatbot providers (both the “closed” and “open”) offer a straightforward cloud service to access their chatbots. These services come with thorough documentation, step-by-step guides, YouTube videos, and code examples designed to help beginners effectively use the interface and learn effective prompting techniques. This makes them easy to access and experiment with for both experts and non-experts alike.

The ease of adopting chatbot services makes them the default choice for building a product Proof of Concept (POC), and for good reason. Utilizing AI services can be fast, affordable, and straightforward. Additionally, demonstrating that your product idea can be effectively realized using such a service can strengthen your case and confirm the product’s viability. Key considerations when choosing a chatbot service for a POC include the cost of the service, performance on your specific task, speed, and token limits.

However, as we advance to the next phase of building a product, you might need to consider if, when and how to transition away from the chatbot cloud service. The top reason for considering this is usually related to Data Privacy, Confidentiality and fear of Intellectual Property (IP) leakage: This is critical when we cannot or choose not to share data with a 3rd party service due to legal, confidentiality, or proprietary concerns. Though we might manage with fabricated or obfuscated data samples during the POC phase, we cannot progress further without controlling the data pipeline. Of course, other reasons might arise to motivate to detach from the chatbot service.

Transitioning to an open chatbot model, such as one downloaded from HuggingFace and run in-house, offers control and the opportunity to fine-tune (i.e., adjust/calibrate) it for your specific task and data, potentially significantly enhancing performance. However, this option also introduces its own set of challenges, including high operational costs, maintenance requirements, and the need for expertise.

Alternatively, consider whether your product requires a complex, general solution like a chatbot in the first place. While chatbots have attracted most of the attention, the AI field has also rapidly advanced in less publicized areas such as task-specific models (those that excel in a specific task but cannot perform others). Although chatbots are often considered the Swiss Army knife of AI tools and the default choice for developing new products. Often, smaller models trained or fine-tuned for specific domain knowledge and task, can perform as well as, or in some cases even better than, general-purpose models like chatbots.

To investigate this, check the latest advances in task-specific models for your particular task. First you will need to define what you are trying to solve. Most likely your task has already been defined in research literature. Identifying the research field your task falls under will help you explore state-of-the-art solutions and potentially expose you to resources such as datasets, tutorials, and even open-source implementations. A good starting point can be to ask a chatbot service like ChatGPT what your task is, given the task expected input, output, description and objectives. Based on the response, you can explore resources such as NLP-Progress to get started.

However, you may discover that in your specific task, chatbots significantly outperform any alternative. Most chatbots come in various sizes, denoted by their parameter count, ranging from a few billion to hundreds of billions. This model size has major implications for the required hardware infrastructure and its cost. When assessing the performance gap between different model sizes, you might consider accepting some decline in performance for a smaller and more cost-effective in-house solution, or even find that you can achieve the same performance using a smaller chatbot model.

When considering an in-house alternative (whether an open chatbot or a task specific model) it does not mean pausing your product development. Whether your code already utilizes a chatbot service or not, maintaining a service-oriented architecture between your model component and business logic is a good practice. This approach ensures complete separation between the two components, which allows the development of both components in parallel.

To sum it up, if you have an idea for a project, product, or startup, experimenting with chatbot services can significantly accelerate your path to realization and secure investment. As you transition from a POC to a product, start considering the feasibility of replacing the chatbot service with an open chatbot or model more tailored to your specific needs. Explore solutions that are closely aligned with your task or data, delve into domain-specific research, and consult with experts. These activities can run in parallel to your main development efforts and could eventually help reduce costs, increase performance and give you full control over your product and IP.

Good luck! :)