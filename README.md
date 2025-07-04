# Enhanced Text Processing & Agentic System

An intelligent document analysis system that combines traditional NLP with modern AI to extract information, generate summaries, and answer questions about documents through an AI agent.

## 🚀 Quick Start

### Installation
```bash
# Clone the repo
git clone https://github.com/MuthukumaRrajendran26/TekSystems.git

# create a venv
python -m venv agent_ai

# Activate the venv
agent_ai/Scripts/activate

# Install dependencies
pip install -r requirements.txt

# Download language model
python -m spacy download en_core_web_sm

Run all cells in the demo.ipynb
```


## 📊 Dataset Source

**Primary Dataset: Reuters Corpus**
- **Source**: NLTK Reuters-21578 dataset
- **Content**: 21,578 news articles from Reuters newswire
- **Categories**: Financial, economic, and business news
- **Why chosen**: Standardized benchmark dataset with diverse document types and pre-labeled categories
- **Access**: Automatically downloaded via NLTK (`reuters.fileids()`)

**Sample Data**: When Reuters isn't available, the system uses realistic synthetic documents covering:
- Financial earnings reports
- Technology company news
- Economic policy updates
- Market analysis reports

## 🤖 Agentic Concept Explained

### What is an "Agent" in this system?

**Traditional Approach**: You search documents manually and read through results
```
User → Search Keywords → Get Documents → Read Everything → Extract Insights
```

**Agentic Approach**: An AI agent intelligently navigates documents to answer your questions
```
User → Ask Natural Question → Agent Reasons → Agent Uses Tools → Agent Provides Answer
```

### Core Agentic Capabilities

#### 1. **Multi-Tool Reasoning**
The agent doesn't just search - it combines multiple analysis tools:
- **Semantic Search**: Finds documents by meaning, not just keywords
- **Entity Extraction**: Identifies people, companies, dates, money
- **Sentiment Analysis**: Understands emotional context
- **Summarization**: Distills key points from multiple sources

#### 2. **Intelligent Planning**
When you ask: *"What are companies saying about AI investments?"*

The agent plans its approach:
1. "I need to find documents about companies AND AI investments"
2. "Let me search semantically for AI investment content"  
3. "Now extract company entities from relevant documents"
4. "Analyze sentiment of company statements"
5. "Synthesize findings into a coherent answer"

#### 3. **Reasoning Transparency**
Unlike a black box, the agent shows its thinking:
```
🧠 Reasoning Steps:
  - Analyzing question to determine search strategy...
  - Searching for documents with ORG entities...
  - Found 3 relevant documents
  - Synthesizing answer from multiple sources...
```

### Example: Research Agent in Action

**Scenario**: Financial Analyst researching quarterly earnings

```python
# Add multiple earnings reports
agent.add_document("apple_q1", "Apple reported $117B revenue...")
agent.add_document("microsoft_q1", "Microsoft announced $61B revenue...")
agent.add_document("tesla_q4", "Tesla delivered 484K vehicles...")

# Ask intelligent questions
response = agent.multi_modal_reasoning("Which companies exceeded analyst expectations?")

# Agent automatically:
# 1. Searches for expectation-related content
# 2. Extracts company performance metrics  
# 3. Compares actual vs expected results
# 4. Provides detailed answer with sources
```

**Agent Response**:
```
Answer: Based on analysis of earnings reports, Apple exceeded expectations 
with $117B revenue (vs $115B expected), while Tesla fell short with 484K 
deliveries (vs 500K expected). Microsoft met expectations at $61B revenue.

Confidence: 0.89
Sources: apple_q1, microsoft_q1, tesla_q4
```

## 🔧 Key Components

### 1. **Information Extraction**
- **Entities**: Companies, people, dates, locations
- **Financial Data**: Revenue, profits, percentages, currencies
- **Sentiment**: Positive/negative sentiment + emotions

### 2. **Document Summarization** 
- **Extractive**: Selects most important existing sentences
- **Abstractive**: Generates new summaries using AI models

### 3. **Research Agent (Agentic Core)**
- **Memory**: Stores and indexes all processed documents
- **Reasoning**: Plans multi-step analysis strategies
- **Tool Use**: Orchestrates extraction and summarization tools
- **Learning**: Improves from user feedback

## 📈 Use Cases

| Domain | What It Does | Example Question |
|--------|--------------|------------------|
| **Finance** | Analyze earnings, extract metrics | "What revenue growth rates are reported?" |
| **Research** | Process papers, synthesize findings | "What methodologies are most common?" |
| **Support** | Categorize tickets, track sentiment | "What are the main customer complaints?" |
| **Legal** | Extract clauses, identify obligations | "What are the key contract terms?" |
| **News** | Monitor trends, track developments | "What regulatory changes affect us?" |

## 🎯 Why This Matters

**Traditional text processing**: Manual keyword search + human reading
- ⏰ Time-consuming
- 🔍 Limited to exact keyword matches  
- 📚 Requires reading full documents
- 🧠 Relies on human synthesis

**Agentic text processing**: AI agent intelligently navigates documents
- ⚡ Fast automated analysis
- 🎯 Understands meaning and context
- 📝 Provides direct answers with reasoning
- 🔄 Learns and improves over time

**Result**: Transform hours of manual document analysis into seconds of intelligent AI-powered insights.

## 🛠️ System Architecture

```
User Question → Agent Planning → Tool Selection → Information Synthesis → Answer + Reasoning
                     ↓
                Multi-Tool Orchestra:
                - Semantic Search
                - Entity Extraction  
                - Sentiment Analysis
                - Document Summarization
                - Classification
```

The agent acts as an intelligent coordinator that knows when and how to use each tool to answer complex questions about document collections.

---

**Ready to start?** Run `demo.ipynb` and explore the intelligent document analysis capabilities!