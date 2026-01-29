# n8n Labs 🚀

A collection of powerful n8n automation workflows demonstrating various integration scenarios, from email processing to weather monitoring and quiz generation.

## 📋 About This Project

This repository contains a curated set of n8n workflow templates that showcase real-world automation use cases. Each workflow demonstrates different n8n nodes, API integrations, and automation patterns that can be used as learning resources or starting points for your own projects.

## 🔧 Workflows Overview

### 1. Gmail Email Filter (My first workflow)
**File:** `My first workflow.json`

An email automation workflow that filters Gmail messages and logs them to Google Sheets.

**Features:**
- Fetches Gmail messages
- Filters emails containing "n8n" in the subject
- Automatically appends matching emails to Google Sheets

**Nodes Used:**
- Manual Trigger
- Gmail (OAuth2)
- IF condition
- Google Sheets

---

### 2. European Countries Data Dashboard (My workflow 2)
**File:** `My workflow 2.json`

Fetches and processes data about European countries from the REST Countries API and stores it in Google Sheets.

**Features:**
- Retrieves country data (population, area, capital, languages, etc.)
- Filters countries by population (> 100,000)
- Calculates population density
- Formats currency and language information
- Stores data in a structured Google Sheets dashboard

**Nodes Used:**
- HTTP Request (REST Countries API)
- IF condition
- Edit Fields
- Code (JavaScript)
- Google Sheets

**API:** https://restcountries.com/v3.1/region/europe

---

### 3. European Weather & Air Quality Monitoring (My workflow 3)
**File:** `My workflow 3.json`

A comprehensive weather monitoring system that tracks weather conditions and air quality for major European cities.

**Features:**
- Monitors 5 European cities (Paris, Berlin, Madrid, Rome, Amsterdam)
- Fetches real-time weather data (temperature, wind, precipitation)
- Retrieves air quality index (AQI)
- Calculates risk scores based on multiple factors
- Generates color-coded alerts (GREEN, YELLOW, ORANGE, RED)
- Sends HTML email reports via Gmail
- Saves CSV reports to Google Drive
- Sends webhook alerts for red alert conditions

**Nodes Used:**
- Manual Trigger
- Code (JavaScript) - Multiple instances
- HTTP Request (Open-Meteo API)
- Loop Over Items
- Merge
- Gmail
- Google Drive
- IF condition

**APIs Used:**
- https://api.open-meteo.com/v1/forecast
- https://air-quality-api.open-meteo.com/v1/air-quality

---

### 4. Football Quiz Generator (My workflow 4)
**File:** `My workflow 4.json`

An AI-powered quiz generation system that creates football trivia questions using Google Gemini.

**Features:**
- Generates randomized football quiz questions using Google Gemini AI
- Creates multiple-choice questions with 3 options (A, B, C)
- Stores questions in Google Sheets with tracking fields
- Tracks quiz status, timestamps, and user responses

**Nodes Used:**
- Google Gemini (LangChain)
- Code (JavaScript) - JSON parsing and data preparation
- Google Sheets

**AI Model:** Gemini 2.5 Flash

---

### 5. CV Analysis System (My workflow 5)
**File:** `My workflow 5.json`

An intelligent CV processing system that extracts and analyzes resume information using AI.

**Features:**
- Web form to upload PDF CVs
- Extracts text from PDF files
- Uses Google Gemini to analyze and structure CV data
- Formats output for HR professionals
- Sends formatted CV analysis via Telegram

**Nodes Used:**
- Form Trigger
- Extract from File (PDF)
- Google Gemini (LangChain)
- Telegram

**AI Model:** Gemini Flash Latest

---

## 🚀 Getting Started

### Prerequisites

- [n8n](https://n8n.io/) installed (self-hosted or cloud)
- Required API credentials:
  - Gmail OAuth2
  - Google Sheets OAuth2
  - Google Drive OAuth2 (for workflow 3)
  - Google Gemini API key (for workflows 4 & 5)
  - Telegram Bot Token (for workflow 5)

### Installation

1. **Clone this repository:**
   ```bash
   git clone https://github.com/Younessboumlik/n8n_labs.git
   cd n8n_labs
   ```

2. **Import workflows into n8n:**
   - Open your n8n instance
   - Go to **Workflows** → **Import from File**
   - Select the desired `.json` workflow file
   - Click **Import**

3. **Configure credentials:**
   - Set up OAuth2 credentials for Gmail and Google Sheets
   - Add API keys for external services (Gemini, Telegram)
   - Update any hardcoded values (email addresses, sheet IDs, etc.)

4. **Activate the workflow:**
   - Open the imported workflow
   - Click **Active** toggle to enable automatic execution (for triggered workflows)
   - Or click **Execute Workflow** for manual execution

## 🔑 Required Credentials

| Service | Workflows | Authentication Type |
|---------|-----------|---------------------|
| Gmail | 1, 3 | OAuth2 |
| Google Sheets | 1, 2, 4 | OAuth2 |
| Google Drive | 3 | OAuth2 |
| Google Gemini (PaLM) | 4, 5 | API Key |
| Telegram | 5 | Bot Token |

## 📚 Learning Resources

- [n8n Documentation](https://docs.n8n.io/)
- [n8n Community Forum](https://community.n8n.io/)
- [n8n Academy](https://www.n8n.io/academy)
- [REST Countries API Documentation](https://restcountries.com/)
- [Open-Meteo API Documentation](https://open-meteo.com/)

## 🤝 Contributing

Contributions are welcome! If you have new workflow ideas or improvements:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-workflow`)
3. Commit your changes (`git commit -m 'Add amazing workflow'`)
4. Push to the branch (`git push origin feature/amazing-workflow`)
5. Open a Pull Request

### Workflow Contribution Guidelines

- Include descriptive names for all nodes
- Add comments in Code nodes to explain complex logic
- Remove any sensitive credentials or personal information
- Test the workflow thoroughly before submitting
- Include a brief description in your PR

## 📝 Documentation

Each workflow JSON file contains:
- Node configurations
- Connection mappings
- Credential references (IDs only, not actual credentials)
- Execution settings

### Customization Tips

- **Email addresses:** Update recipient emails in Gmail nodes
- **Sheet IDs:** Replace Google Sheets document IDs with your own
- **API endpoints:** Modify URLs if using different data sources
- **Scheduling:** Add Schedule Trigger nodes for automated execution
- **Error handling:** Add Error Trigger nodes for better reliability

## 🔒 Security Notes

⚠️ **Important Security Considerations:**

- Never commit actual API keys or OAuth tokens to the repository
- Credential IDs in workflow JSON files are environment-specific
- Review all webhook URLs before activating workflows
- Use environment variables for sensitive configuration
- Regularly rotate API keys and tokens
- Review n8n's [security best practices](https://docs.n8n.io/hosting/security/)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Youness Boumlik**

- GitHub: [@Younessboumlik](https://github.com/Younessboumlik)

## 🙏 Acknowledgments

- [n8n.io](https://n8n.io/) - The workflow automation platform
- REST Countries API - Free country data API
- Open-Meteo - Free weather and air quality API
- Google Gemini - AI model for intelligent automation

## 📞 Support

If you encounter any issues or have questions:

- Open an [issue](https://github.com/Younessboumlik/n8n_labs/issues)
- Check the [n8n Community Forum](https://community.n8n.io/)
- Review the [n8n Documentation](https://docs.n8n.io/)

---

⭐ **Star this repository if you find it helpful!**

*Built with ❤️ using n8n*
