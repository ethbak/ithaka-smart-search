<div align="center">

<img src="https://raw.githubusercontent.com/ethbak/ithaka-smart-search/main/images/ithaka-mvp-banner.png" alt="ithaka_banner" width="650"/>

<hr style="border: none; height: 2px; background-color: purple; width: 100%;">

![Static Badge](https://img.shields.io/badge/Ithaka-AI-purple)
![Static Badge](https://img.shields.io/badge/Smart-Search-red)
![Static Badge](https://img.shields.io/badge/Browser-Extension-lightblue)
![Static Badge](https://img.shields.io/badge/Author-Ethan_Baker-green)
![Static Badge](https://img.shields.io/badge/August-2025-orange)

</div>

# 🔎 Ithaka Smart Search [WIP]

Ithaka Smart Search provides an intuitive way to classify user queries in real time and route them to the most relevant backend—traditional search engines, AI search platforms, or large language models.

At its core, Ithaka compiles a small decision model (≈3M parameters) into WebAssembly, enabling inference directly inside the browser extension environment. The model achieves sub-90 ms latency on consumer hardware by combining TensorFlow graph execution with quantization and pruning. This ensures that Ithaka introduces almost no additional delay compared to native Google or Perplexity search, while offering adaptive query routing that optimizes for relevance and cost.

Ithaka aims to provide native AI integration into users' existing workflows, allowing better access in the age of information without requiring additional effort or knowledge.

<div align="center">
<img src="https://github.com/ethbak/ithaka-smart-search/blob/main/images/ithaka-workflow.png?raw=true" alt="flow diagram" width="750"/>
  <hr style="border: none; height: 1px; background-color: white; width: 100%;">
</div>

# ✨ Functionality

## Decision Model

Ithaka routes non-URL queries through a lightweight decision model that runs entirely on the user’s browser or desktop. The model was compressed from a larger general-purpose transformer via pruning and quantization to be optimized for low latency, delivering inference in under 90 ms without noticeable impact on user experience.

Each query is classified into one of three categories: web search, AI search, or generative AI, with routing handled accordingly. Expansion to additional categories such as image generation and domain-specific models is on the roadmap.

Planned features also include a feedback-driven retraining loop, allowing user corrections to be logged and incorporated into fine-tuned versions of the model, steadily improving routing accuracy over time.

## Browser Integration

<div align="left">
  <img src="https://github.com/ethbak/ithaka-smart-search/blob/main/images/ithaka-chrome.png?raw=true" alt="browser integration" width="550"/>
    <hr style="border: none; height: 1px; background-color: purple; width: 100%;">
</div>

Ithaka’s browser extension integrates with Chrome and Firefox to capture queries directly from the search bar or context menus. The decision model runs locally, classifying each query and instantly routing it to the most relevant destination.

Queries are transparently redirected to Google, Perplexity, or an LLM interface, with no extra steps required from the user. This design keeps search seamless while adding AI-powered routing behind the scenes.

The extension embeds into the search bar like a standard search engine, with controls to enable or disable routing and submit feedback on incorrect decisions.

## [Future] Raycast Integration

<div align="left">
  <img src="https://github.com/ethbak/ithaka-smart-search/blob/main/images/ithaka-raycast.png?raw=true" alt="browser integration" width="550"/>
    <hr style="border: none; height: 1px; background-color: purple; width: 100%;">
</div>

Ease of use is a core tenet of Ithaka's design model. To improve this in the future, Ithaka will provide Raycast support to expose the tool as a global command on macOS. Other media of integration will also be explored.

## [Future] User Customization

Ithaka aims to provide users with significant functionality for customization and integration with other AI tools, making use of Retrieval Augmented Generation (RAG) to allow custom routing instructions and Model Context Protocol (MCP) to facilitate connection to additional AI models. 

# 📀 Technologies / Dependencies

![Static Badge](https://img.shields.io/badge/TYPESCRIPT-darkblue?style=for-the-badge)
![Static Badge](https://img.shields.io/badge/TensorFlow-green?style=for-the-badge)
![Static Badge](https://img.shields.io/badge/OpenAI_API-gold?style=for-the-badge)
![Static Badge](https://img.shields.io/badge/HUGGING_FACE_TRANSFORMERS-purple?style=for-the-badge)
![Static Badge](https://img.shields.io/badge/HTML/CSS-blue?style=for-the-badge)
![Static Badge](https://img.shields.io/badge/MODEL_CONTEXT_PROTOCOL-orange?style=for-the-badge)

# 🏎️ Performance

### Latency

Ithaka provides _sub-90 ms_ routing time (time from user input to decision) for non-URL queries. This represents only a moderate increase in latency for Google searches and a negligible effect on AI search engines' and general LLMs' time-to-first-token.

| Tool | Latency | Ithaka Routing Percentage|
|------|----------|------|
|Ithaka Smart Search|0.09s|100%|
|Google Search|0.25s|36%|
|Perplexity|2.5s|3.6%|
|ChatGPT-5 Auto|1s|9%|
|ChatGPT-5 Thinking|60s|0.15%|  
  
### Accuracy

Decision model accuracy was measured with an LLM reward judge using a modified implementation of Gemp et al.'s [Steering Language Models with Game-Theoretic Solvers](https://arxiv.org/pdf/2402.01704) on a large data set of real, English-language web search and AI queries. 

**Decision accuracy:** `96.3%`

# ❓ Where's the code?

Ithaka, including its browser extension, Raycast extension, decision model, and other code, is proprietary technology and therefore not available for public use. 

This README file simply serves to provide a detailed depiction of my contribution and experience gained from the project.

# ❓ When will the extension be published?

I'm currently balancing a few different priorities... More info soon!

# 👨‍💻 Contributors

### [Ethan Baker](https://www.ebaker.us) - Founding Engineer
