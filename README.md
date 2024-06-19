# Site instruction and context for LLM 

Welcome to the Site instruction and context for LLM! This repository provides guidelines and resources for leveraging Large Language Models (LLMs) to interact with and automate tasks on websites, particularly with many features e.g. Salesforce, Hubspot, LinkedIn and etc. This can be site guide for llm to how to use the sites.

## Table of Contents
- [Introduction](#introduction)
- [Repository Structure](#repository-structure)
- [Files Explained](#files-explained)
- [Use Cases](#use-cases)
- [Getting Started](#getting-started)
- [Using with Web Crawlers or Browser Automation Tools](#using-with-web-crawlers-or-browser-automation-tools)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This repository contains JSON files that describe how to use LLMs to perform specific actions on different parts of a website. For instance, it includes instructions for reading and responding to messages, or searching for people on LinkedIn. This enables the automation of various workflows using LLMs.

## Repository Structure

```
/
├── com/
│   └── linkedin/
│       └── www/
│           ├── pages.json
│           └── use-cases.json
└── README.md
```

## Files Explained

### `pages.json`

This file lists web pages and the specific tools or instructions that can be applied to each page. Each entry includes a path and an associated instruction.

Example:
```json
[
    {"path": "messages/", "instruction": "read message and respond"},
    {"path": "people/", "instruction": "search people"}
]
```

### `use-cases.json`

This file outlines various use cases that combine the tools and instructions from `pages.json` to perform more complex tasks.

Example:
```json
[
    "sending message to a user after searching for the user from the people section",
    "researching a company by searching for the company and then looking up their people"
]
```

## Use Cases

Here are a few examples of what you can do with this repository:

1. **Send a Message After Searching for a User:**
   - **Step 1:** Use the instruction for the `people/` path to search for a user.
   - **Step 2:** Use the instruction for the `messages/` path to send a message to the user.

2. **Research a Company:**
   - **Step 1:** Search for a company using the relevant path.
   - **Step 2:** Look up people associated with that company using the `people/` path.

## Getting Started

To get started, follow these steps:

1. **Fork and Clone the repository:**

2. **Review the `pages.json` file :**
   - For the site you want to update, review and write
   - Understand the paths and instructions provided.
   - Modify or extend the instructions to suit your needs.

3. **Explore the `use-cases.json` file:**
   - Look at the provided use cases.
   - Create your own use cases by combining different instructions.

4. **Implement Your Automation:**
   - Use the paths and instructions to guide your LLM-based automation scripts.
   - read the repo from your code and add the guide to prompt

## Using with Web Crawlers or Browser Automation Tools

To utilize this repository directly with web crawlers or browser automation tools, follow these guidelines:

1. **Choose a Web Crawler or Browser Automation Tool:**
   - Popular tools include Selenium, Puppeteer, and Beautiful Soup.

2. **Integrate LLMs with Your Automation Scripts:**
   - Use an LLM API (such as OpenAI's GPT-4) to process the instructions from `pages.json` or `use-cases.json`.
   - Example: Use Selenium to navigate to LinkedIn and then use the LLM to interpret and execute the instructions.

3. **Adapt Instructions to Your Needs:**
   - Customize the JSON files and your automation scripts based on your specific use cases.
   - Leverage the flexibility of LLMs to enhance the automation tasks.

## Contributing

We welcome contributions from the community! If you have suggestions for new instructions or use cases, feel free to fork the repository and submit a pull request.

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a pull request.

## License

This project is licensed under the Apache v2 License. See the [LICENSE](LICENSE) file for more details.

---

Feel free to reach out if you have any questions or need further assistance. Happy automating!