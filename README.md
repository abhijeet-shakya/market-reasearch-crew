# Market Research Crew

A powerful AI-powered market research automation tool built with [CrewAI](https://www.crewai.com/) that conducts comprehensive market analysis for product ideas using specialized AI agents.

## 📋 Overview

Market Research Crew uses a multi-agent system to perform thorough market analysis for any product idea. It combines market research, competitive intelligence, customer insights, and business strategy to provide actionable recommendations for new product launches.

### ✨ Key Features

- **Automated Market Research**: Comprehensive analysis of market size, growth trends, industry dynamics, and technology adoption patterns
- **Competitive Intelligence**: Identifies and analyzes direct, indirect, and adjacent competitors
- **Customer Insights**: Develops deep understanding of target customer segments, pain points, and willingness to pay
- **Product Strategy**: Designs comprehensive product strategy, MVP features, and development roadmap
- **Business Analysis**: Synthesizes findings into actionable business reports with pricing and revenue models
- **Web Intelligence Tools**: Leverages web search and advanced scraping for real-time market data
- **Multi-Agent Collaboration**: Specialized AI agents work together to provide comprehensive analysis

## 🏗️ Architecture

The project uses a multi-agent crew with highly specialized roles that work collaboratively:

### 👥 Agents

1. **Market Research Specialist**
   - Conducts comprehensive market analysis
   - Calculates TAM/SAM/SOM (market sizing)
   - Analyzes growth trends and regulatory landscape
2. **Competitive Intelligence Analyst**
   - Identifies direct, indirect, and adjacent competitors
   - Analyzes competitor positioning and strategies
   - Uncovers competitive gaps and opportunities
3. **Customer Insights Researcher**
   - Develops detailed customer personas
   - Identifies pain points and customer needs
   - Analyzes customer acquisition channels
4. **Product Strategy Advisor**
   - Designs product strategy and positioning
   - Prioritizes MVP features
   - Creates technical feasibility assessment and roadmap
5. **Business Analyst**
   - Synthesizes all research findings
   - Develops pricing and revenue strategies
   - Provides go/no-go recommendations

### 🛠️ Tools

The crew has access to:

- **SerperDevTool** - Web search for current market data and insights
- **ScrapeWebsiteTool** - Website content extraction for analysis
- **SeleniumScrapingTool** - Advanced web scraping with browser automation

## 📁 Project Structure

```
market-research-crew/
├── README.md                          # Project documentation
├── pyproject.toml                     # Project configuration and dependencies
├── .env                               # Environment variables (create this)
├── knowledge/
│   └── user_preference.txt            # User preferences and settings
├── reports/
│   └── report.md                      # Generated market research reports
└── src/
    └── market_research_crew/
        ├── __init__.py                # Package initialization
        ├── main.py                    # Entry point and CLI commands
        ├── crew.py                    # Crew definition with agents and tasks
        ├── config/
        │   ├── agents.yaml            # Agent roles, goals, and backstories
        │   └── tasks.yaml             # Task descriptions and expected outputs
        └── tools/
            ├── __init__.py            # Tools package initialization
            └── custom_tool.py         # Custom tools for extended functionality
```

## 🔧 Prerequisites

- **Python 3.10 or higher**
- **pip** or your preferred package manager
- **API Keys**:
  - [OpenAI API](https://platform.openai.com/api-keys) (for LLM capabilities)
  - [Serper API](https://serper.dev/) (for web search functionality)

## 📦 Installation

### 1. Clone the Repository

```bash
git clone <repository-url>
cd market-research-crew
```

### 2. Create a Virtual Environment (Recommended)

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -e .
```

### 4. Set Up Environment Variables

Create a `.env` file in the root directory:

```env
OPENAI_API_KEY=your_openai_api_key_here
SERPER_API_KEY=your_serper_api_key_here
```

## 🚀 Usage

### Run Market Research Analysis

```bash
market_research_crew
```

Or using the alternative command:

```bash
run_crew
```

### Training Mode

Train the crew on previous experiences:

```bash
train
```

### Replay Mode

Replay a specific task execution:

```bash
replay
```

### Run Tests

Run tests for the crew:

```bash
test
```

### Run with Trigger

Execute the crew with a specific trigger:

```bash
run_with_trigger
```

## ⚙️ Configuration

### Customize the Product Idea

Edit the `product_idea` in [src/market_research_crew/main.py](src/market_research_crew/main.py):

```python
inputs = {
    "product_idea": "An AI powered tool that summarizes youtube videos on my channel and posts the summary on various social media platforms like LinkedIn, Instagram, Facebook, X, WhatsApp"
}
```

Change the `product_idea` value to analyze a different product concept.

### Modify Agent Behavior

Adjust agent roles, goals, and backstories in [src/market_research_crew/config/agents.yaml](src/market_research_crew/config/agents.yaml):

- **role**: The agent's position and title
- **goal**: What the agent aims to achieve
- **backstory**: The agent's background and expertise (influences behavior)

### Customize Tasks

Modify task descriptions and expected outputs in [src/market_research_crew/config/tasks.yaml](src/market_research_crew/config/tasks.yaml):

- **description**: What the task should accomplish
- **expected_output**: Format and content of the task output
- **agent**: Which agent executes the task

## 📊 Output

The crew generates comprehensive market research reports including:

- **Executive Summary** - High-level market opportunity overview
- **Market Sizing** - TAM (Total Addressable Market), SAM (Serviceable Addressable Market), SOM (Serviceable Obtainable Market)
- **Industry Trends** - Current and emerging trends with supporting data
- **Competitive Analysis** - Detailed competitor landscape and positioning
- **Customer Insights** - Target customer segments and personas
- **Product Strategy** - MVP features, differentiation, and roadmap
- **Business Analysis** - Pricing strategy, revenue models, financial projections
- **Risk Analysis** - Key risks and mitigation strategies
- **Recommendation** - Go/no-go decision for the product

Reports are saved in the `reports/` directory as markdown files.

## 📚 Dependencies

Core dependencies (see [pyproject.toml](pyproject.toml) for complete list):

- **crewai[tools]** (1.3.0) - Multi-agent framework
- **selenium** (>=4.39.0) - Web browser automation
- **webdriver-manager** (>=4.0.2) - WebDriver management
- **python-dotenv** - Environment variable management

## 🐛 Troubleshooting

### API Key Issues

- Verify `OPENAI_API_KEY` and `SERPER_API_KEY` are correctly set in `.env`
- Ensure API keys have appropriate permissions
- Check API usage limits and billing status

### Web Scraping Issues

- Some websites may block automated access (the crew uses alternative sources)
- Ensure stable internet connection
- Check Selenium WebDriver compatibility with your browser

### Performance

- Market research analysis may take several minutes (depending on product complexity)
- Consider simplifying task descriptions for faster analysis
- Monitor API usage and costs

### Module Import Errors

- Ensure virtual environment is activated
- Run `pip install -e .` again to reinstall package in development mode

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch
3. Submit a pull request with your improvements

## 📄 License

This project is licensed under the MIT License - see LICENSE file for details.

## 💬 Support

For issues, questions, or suggestions:

- Open an issue on the GitHub repository
- Check [CrewAI Documentation](https://docs.crewai.com)
- Visit the [CrewAI GitHub Repository](https://github.com/joaomdmoura/crewai)

## 🙏 Acknowledgments

- Built with [CrewAI](https://www.crewai.com/)
- Powered by [OpenAI](https://openai.com/)
- Web search enabled by [Serper](https://serper.dev/)

---

