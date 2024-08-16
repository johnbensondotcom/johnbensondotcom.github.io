---
layout: single
author: John Benson
title: "Prompting Techniques"
excerpt: "An interactive exploration of the ethical risks and benefits of AI under the ABA model rules"
permalink: /ai/prompt-strategy/
classes: wide
previous_next_links: false
header:
  teaser: "/assets/images/explorer_teaser.jpg"
---

<style>
.prompting-techniques {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1em;
}
.prompting-techniques .notice--info {
  background-color: #f9f9f9 !important;
  border-left: 3px solid #8B0000 !important;
  padding: 1em !important;
  margin-bottom: 2em !important;
  font-size: .9em !important;
  line-height: 1.6 !important;
  color: #000 !important;
}
.prompting-techniques .search-container {
  margin-bottom: 2em;
  width: 100%;
}
.prompting-techniques .search-input {
  width: 100%;
  padding: 0.5em;
  font-size: 1em;
  border: 1px solid #e0e0e0;
  border-radius: 4px;
  box-shadow: 0 1px 3px rgba(0,0,0,0.1);
}
.prompting-techniques .grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2em;
}
  .prompting-techniques .card {
    background-color: #fff;
    border: 1px solid #f2f3f3;
    border-radius: 4px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    overflow: hidden;
    display: flex;
    flex-direction: column;
    transition: box-shadow 0.3s ease;
  }
  .prompting-techniques .card:hover {
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
  }
  .prompting-techniques .card h3 {
    font-size: 1.4em;
    margin: 0;
    padding: 0.75em 0.5em 0.5em;
    color: #8B0000;
  }
  .prompting-techniques .card p {
    padding: 0 0.75em 0.75em;
    margin: 0;
    flex-grow: 1;
  }
  .prompting-techniques .card button {
    background: none;
    border: none;
    color: #8B0000;
    cursor: pointer;
    padding: 0.5em 0.75em;
    font: inherit;
    text-align: left;
    transition: color 0.3s ease;
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
  }
  .prompting-techniques .card button:hover {
    color: #5a0000;
  }
  .prompting-techniques .card button::after {
    content: '›';
    font-size: 1.2em;
    transform: rotate(90deg);
    transition: transform 0.3s ease;
  }
  .prompting-techniques .card button.expanded::after {
    transform: rotate(-90deg);
  }
  .prompting-techniques .expanded-content {
    display: none;
    padding: 0.75em;
    border-top: 1px solid #f2f3f3;
  }
  .prompting-techniques .expanded-content h4 {
    font-size: 1.1em;
    margin: 0.75em 0 0.5em;
    color: #8B0000;
  }
  .prompting-techniques .expanded-content ul {
    margin: 0;
    padding-left: 20px;
  }
</style>

<div class="prompting-techniques">
  <p class="notice--info">
    Prompting techniques are strategies used to effectively communicate with and guide AI language models. 
    These methods help in obtaining more accurate, relevant, and insightful responses from AI, 
    enhancing the quality and usefulness of AI-generated content across various applications.
  </p>

  <div class="search-container">
    <input type="text" id="search-input" class="search-input" placeholder="Search techniques...">
  </div>

  <div class="grid" id="techniques-grid"></div>
</div>

<script>
  const techniques = [
    {
      technique: "Role Prompting",
      description: "Instruct the LLM to assume a specific role or persona",
      whenToUse: "To elicit responses from a particular viewpoint or when seeking expert-like answers in specific domains",
      examplePrompt: "You are a seasoned climate scientist with 20 years of experience in studying global warming. Explain the potential long-term effects of rising sea levels on coastal cities.",
      keyBenefits: [
        "Focuses responses on specific areas of expertise",
        "Leads to more nuanced or specialized answers"
      ]
    },
    {
      technique: "Few Shot Prompting",
      description: "Provide examples of desired input-output pattern",
      whenToUse: "When you want to guide the model's output format or style or for tasks requiring specific patterns or structures in the response",
      examplePrompt: "Classify the sentiment of the following tweets as positive, negative, or neutral: [Examples provided]",
      keyBenefits: [
        "Improves model performance on specific tasks",
        "Allows for quick adaptation without fine-tuning"
      ]
    },
    {
      technique: "Chain of Thought (CoT)",
      description: "LLM breaks down complex problems into step-by-step reasoning processes",
      whenToUse: "Complex mathematical or logical problems, multi-step reasoning tasks, or when transparency in AI decision-making is crucial",
      examplePrompt: "Let's approach this step-by-step: What is the sum of the first 10 prime numbers? Explain your reasoning at each step.",
      keyBenefits: [
        "Improves accuracy on complex tasks",
        "Enhances explainability of AI decisions"
      ]
    },
    {
      technique: "Least-to-Most Prompting",
      description: "Break down complex problems into simpler sub-problems",
      whenToUse: "For multi-step problems where intermediate results build towards the final solution or when dealing with complex reasoning tasks",
      examplePrompt: "Let's solve this word problem step by step: [Problem statement followed by step-by-step instructions]",
      keyBenefits: [
        "Improves LLM performance on complex tasks",
        "Provides more transparent and explainable solutions"
      ]
    },
    {
      technique: "Self Reflection",
      description: "LLM analyzes its own reasoning and output during the generation process, then revises",
      whenToUse: "Complex or nuanced topics, addressing potential biases, improving comprehensiveness",
      examplePrompt: "Describe the impacts of social media on society. Reflect on your initial response, identifying any biases or omissions, then provide an improved explanation.",
      keyBenefits: [
        "More balanced and thorough responses",
        "Real-time bias correction"
      ]
    },
    {
      technique: "Step by Step Rationalization (STaR)",
      description: "Guides the model through a logical, sequential thought process with explicit reasoning at each stage",
      whenToUse: "For tasks requiring clear, logical reasoning, when transparency in the decision-making process is crucial, or to improve the quality and reliability of AI-generated solutions",
      examplePrompt: "Let's approach this ethical dilemma step by step: [Scenario description] Step 1: Identify key ethical principles. Step 2: Consider potential consequences. [Additional steps...] Please provide your reasoning for each step, then give your final ethical assessment.",
      keyBenefits: [
        "Enhances quality and depth of AI-generated reasoning",
        "Provides clear, traceable logic for complex decisions",
        "Improves user trust through transparency",
        "Facilitates easier human review and validation"
      ]
    },
    {
      technique: "Tree of Thoughts (ToT)",
      description: "LLM explores multiple reasoning paths simultaneously",
      whenToUse: "Complex problem-solving with multiple possible approaches or tasks requiring creative or innovative solutions",
      examplePrompt: "Design a sustainable urban transportation system. Generate three initial approaches, explore two potential developments for each, evaluate their promise, expand on the most promising ideas, backtrack if necessary, and synthesize the best elements into a final solution.",
      keyBenefits: [
        "Enables comprehensive problem exploration",
        "Increases likelihood of finding optimal solutions"
      ]
    },
    {
      technique: "Self Evaluation",
      description: "LLM rates its own performance on a given task using a predefined scale",
      whenToUse: "Assessing output quality, gauging model confidence, or comparing performance across tasks",
      examplePrompt: "Explain quantum computing in simple terms. Then rate your explanation on a scale of 1-10 for clarity and accuracy, justifying your score.",
      keyBenefits: [
        "Immediate feedback on output quality",
        "Identifies areas of low confidence"
      ]
    }
  ];

  function createCard(technique) {
    const card = document.createElement('div');
    card.className = 'card';
    card.innerHTML = `
      <h3>${technique.technique}</h3>
      <p>${technique.description}</p>
      <button onclick="toggleExpand(this)">Show more</button>
      <div class="expanded-content">
        <h4>When to Use:</h4>
        <p>${technique.whenToUse}</p>
        <h4>Example Prompt:</h4>
        <p><em>"${technique.examplePrompt}"</em></p>
        <h4>Key Benefits:</h4>
        <ul>
          ${technique.keyBenefits.map(benefit => `<li>${benefit}</li>`).join('')}
        </ul>
      </div>
    `;
    return card;
  }

  function toggleExpand(button) {
    const expandedContent = button.nextElementSibling;
    const isExpanded = expandedContent.style.display === 'block';
    expandedContent.style.display = isExpanded ? 'none' : 'block';
    button.textContent = isExpanded ? 'Show more' : 'Show less';
    button.classList.toggle('expanded', !isExpanded);
  }

  function renderTechniques(techniquesToRender) {
    const container = document.getElementById('techniques-grid');
    container.innerHTML = '';
    techniquesToRender.forEach(technique => {
      container.appendChild(createCard(technique));
    });
  }

  function filterTechniques() {
    const searchTerm = document.getElementById('search-input').value.toLowerCase();
    const filteredTechniques = techniques.filter(technique => 
      technique.technique.toLowerCase().includes(searchTerm) ||
      technique.description.toLowerCase().includes(searchTerm) ||
      technique.whenToUse.toLowerCase().includes(searchTerm)
    );
    renderTechniques(filteredTechniques);
  }

  document.addEventListener('DOMContentLoaded', function() {
    document.getElementById('search-input').addEventListener('input', filterTechniques);
    renderTechniques(techniques);
  });
</script>
