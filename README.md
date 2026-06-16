# Career Compass AI

**Career Compass AI** is an intelligent career guidance platform built with Streamlit. It empowers students, early-career professionals, and career changers to discover meaningful roles, identify skill gaps, and follow a clear, personalized roadmap toward their dream career.

## 🚀 Features

- **Personalized Career Analysis**: Input your skills, interests, experience, and dream role to receive a tailored career profile
- **AI-Powered Role Recommendations**: Get 5 curated role suggestions based on your career category and interests
- **Interactive Roadmap**: View structured action plans for the next 30 days, 3 months, 6 months, and 1 year
- **Career Fit Scoring**: Receive a calculated fit score based on skills, interests, and alignment with your dream role
- **Curated Learning Resources**: Get category-specific recommendations for courses, certifications, and learning platforms
- **Salary Insights**: View realistic salary ranges (in LPA) for target roles in the Indian market
- **Optional AI Narrative**: Generate personalized, in-depth career advice using OpenAI or Google Generative AI
- **Work Style Preferences**: Choose from Collaborative, Independent, Fast-paced, Structured, or Flexible work environments
- **Responsive UI**: Clean, professional Streamlit interface with multi-column layout for easy reading

## 🔧 Tech Stack

- **Framework**: Streamlit (web UI)
- **Language**: Python 3.10+
- **Core Dependencies**:
  - `streamlit` - Interactive web framework
  - `python-dotenv` - Environment configuration
  - `openai` - OpenAI API integration (optional)
  - `google-generativeai` - Google Generative AI SDK (optional)

## ✅ Getting Started

### Prerequisites
- Python 3.10 or higher
- pip (Python package manager)
- Git

### Installation

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd "career compass ai/career-compass-ai"
   ```

2. **Create and activate a virtual environment**:
   ```bash
   # On Linux/macOS
   python -m venv .venv
   source .venv/bin/activate

   # On Windows
   python -m venv .venv
   .venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables** (Optional - only if using AI features):
   ```bash
   cp .env.example .env
   ```

5. **Add your API keys** (Optional - for AI generation):
   Edit `.env` and add:
   ```env
   OPENAI_API_KEY=your_openai_api_key_here
   GOOGLE_API_KEY=your_google_api_key_here
   ```

6. **Run the application**:
   ```bash
   streamlit run app.py
   ```

   The app will open in your default browser at `http://localhost:8501`

## 📖 How to Use

1. **Enter Your Profile**: Fill in the form with:
   - Your name and current role
   - Years of professional experience
   - Your skills (comma or semicolon-separated)
   - Your interests (comma or semicolon-separated)
   - Your dream career role
   - Your preferred work style

2. **Generate Report**: Click "Generate Career Report" to create your personalized analysis

3. **View Results**:
   - **Career Fit Summary**: See recommended roles, strengths, and opportunity areas
   - **Career Roadmap**: Follow structured action plans across 4 time horizons (30 days, 3 months, 6 months, 1 year)
   - **Learning Resources**: Access curated courses and certifications for your career path
   - **Salary Outlook**: Check realistic compensation ranges for target roles
   - **Profile Summary**: Review your skills, interests, and work style preferences

4. **AI Enhancement** (Optional):
   - Toggle "Use AI generation" in the sidebar
   - Select your preferred AI provider (OpenAI or Google)
   - Provide an API key if needed
   - The AI will generate a personalized, in-depth narrative based on your profile

## ✅ Getting started

1. Clone the repository:

```bash
git clone <repository-url>
cd "career compass ai/career-compass-ai"
```

2. Create and activate a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

4. Copy the example environment file:

```bash
cp .env.example .env
```

5. Add your API keys to `.env` if you want AI generation:

```env
OPENAI_API_KEY=your_openai_api_key_here
GOOGLE_API_KEY=your_google_api_key_here
```

## 🧩 Project Structure

```
career-compass-ai/
├── app.py                    # Main Streamlit application
├── requirements.txt          # Python dependencies
├── .env.example              # Example environment variables
├── README.md                 # Project documentation
├── .gitignore                # Git ignore rules
└── utils/
    ├── __init__.py           # Package initialization
    ├── ai_client.py          # AI provider integration (OpenAI, Google)
    └── career_engine.py      # Career analysis and report generation logic
```

### Module Descriptions

**`app.py`**:
- Streamlit UI configuration and page layout
- Form handling for user input (name, role, skills, interests, dream career, work style)
- Report generation workflow and result visualization
- Optional AI narrative generation

**`utils/ai_client.py`**:
- `AIClient` class for multi-provider AI support
- Providers: OpenAI (GPT-3.5-turbo) and Google Generative AI
- Graceful fallback if provider not available or API not configured
- System prompt for professional career coaching tone

**`utils/career_engine.py`**:
- `generate_local_report()`: Core analysis engine
- Career categorization based on keywords
- Role recommendation and roadmap generation
- Career fit scoring algorithm
- Resource and salary data management
- Support for 6+ career categories with specialized guidance

## 🧩 Project structure

```text
career-compass-ai/
├── app.py
├── requirements.txt
├── .env.example
├── README.md
├── .gitignore
└── utils/
    ├── __init__.py
    ├── ai_client.py
    └── career_engine.py
```


## 💡 How It Works

### Core Architecture

**Career Compass AI** processes your career input through intelligent analysis and generation:

1. **User Input Processing**:
   - Parses skills, interests, and experience using regex-based tokenization
   - Categorizes dream career into one of 6 categories: AI, Software, Product, Cloud, Business, or Design

2. **Career Analysis Engine** (`utils/career_engine.py`):
   - **Dream Career Categorization**: Maps your dream role to a career category using keyword matching
   - **Role Recommendation**: Generates 5 tailored role suggestions based on your category
   - **Roadmap Generation**: Creates time-bound action plans (30 days, 3 months, 6 months, 1 year) with category-specific guidance
   - **Career Fit Scoring**: Calculates a 0-100 score based on skill count, interests, and goal clarity
   - **Resource Selection**: Recommends courses, certifications, and learning paths for your category
   - **Salary Lookup**: Provides current market salary ranges (in LPA) for recommended roles

3. **AI Enhancement** (Optional - `utils/ai_client.py`):
   - Supports **OpenAI** (GPT-3.5-turbo) and **Google Generative AI**
   - Generates personalized, detailed career narratives using system prompt guidance
   - Gracefully falls back to local analysis if no API is configured

4. **Report Generation**:
   - Compiles all analysis into a structured report object
   - Renders visually in the Streamlit UI with metrics, columns, and markdown formatting

### Career Categories & Keywords

The system recognizes these career paths:
- **AI**: Machine Learning, Data Science, Deep Learning
- **Software**: Backend/Frontend/Full Stack Development, Web Development
- **Product**: Product Management, UX/UI Design, Strategy
- **Cloud**: DevOps, Infrastructure, AWS/GCP/Azure
- **Business**: Strategy, Consulting, Sales, Marketing
- **Design**: Graphic Design, Creative, UX/Visual Design

## 💡 How it works

1. Enter your name, current role, years of experience, skills, interests, and dream career.
2. Choose whether to generate an enhanced AI narrative.
3. The app produces:
   - recommended roles
   - growth opportunities
   - a personalized learning roadmap
   - suggested resources
   - salary outlook and career fit score


## ⚙️ Configuration

### Environment Variables

Create a `.env` file in the project root with the following (optional):

```env
# OpenAI Configuration
OPENAI_API_KEY=sk-...  # Your OpenAI API key

# Google Generative AI Configuration
GOOGLE_API_KEY=...     # Your Google Generative AI API key
```

### AI Provider Selection

In the Streamlit sidebar:
- **Provider**: Choose between `local`, `openai`, or `google`
- **API Key**: Paste your API key (or leave blank if using local mode)
- **Use AI Generation**: Toggle to enable/disable AI narrative generation

If no valid API key is provided, the app automatically uses local analysis (no AI enhancement).

## 🔮 Future Enhancements

- 🎓 **Resume Review & Feedback**: Upload and get AI-powered resume analysis
- 📊 **Skill Gap Scoring**: Real-time skill gap identification with market job data
- 🗺️ **Curated Learning Paths**: AI-generated study schedules and milestone tracking
- 🎤 **Mock Interview Assistant**: Practice technical and behavioral interview questions
- 💼 **Job Opportunity Discovery**: Integration with job boards for role matching
- 📈 **Progress Tracking**: Track your career progress over time with periodic re-assessments
- 🌍 **Multi-Country Support**: Localized salary data and job markets (US, UK, EU, APAC)

## 📝 Notes

- **AI is Optional**: The app provides robust built-in career analysis even without API keys. AI generation is purely optional for enhanced narratives.
- **Data Privacy**: No user data is stored or persisted. All analysis happens in real-time on your machine.
- **Salary Data**: Salary ranges are based on Indian market (LPA = Lakh Per Annum). Update `SALARY_RANGES` in `utils/career_engine.py` for other markets.
- **Extensible Design**: Easy to add new career categories or customize learning resources in `career_engine.py`.

## 🚀 Performance & Deployment

### Local Development
```bash
streamlit run app.py
```
The app will be available at `http://localhost:8501`

### Production Deployment

**Streamlit Cloud** (Recommended - Free):
1. Push your repository to GitHub
2. Go to [Streamlit Cloud](https://streamlit.io/cloud)
3. Click "New App" and connect your GitHub repo
4. Add your API keys in the Secrets management panel

**Docker Deployment**:
```dockerfile
FROM python:3.10-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
EXPOSE 8501
CMD ["streamlit", "run", "app.py"]
```

## 🤝 Contributing

We welcome contributions! Here's how to contribute:

1. **Fork the repository** on GitHub
2. **Create a feature branch**: `git checkout -b feature/your-feature-name`
3. **Make your changes** and test locally
4. **Commit your changes**: `git commit -m "Add your feature description"`
5. **Push to your fork**: `git push origin feature/your-feature-name`
6. **Open a Pull Request** with a clear description of your changes

### Areas for Contribution:
- New career categories and role recommendations
- Additional learning resources for specific fields
- Enhanced career scoring algorithms
- Localization and multi-language support
- UI/UX improvements
- Bug fixes and optimizations

## 📄 License

This project is open source and available under the MIT License.

## 🌟 Acknowledgments

- Built with [Streamlit](https://streamlit.io) for fast, interactive web apps
- AI integration with [OpenAI](https://openai.com) and [Google Generative AI](https://ai.google.dev)
- Inspired by career guidance best practices and professional development frameworks

---

**Career Compass AI**: Empowering career transitions with intelligence, structure, and confidence. Navigate your next move with data-driven insights and actionable guidance.

**Questions? Issues? Ideas?** Open an issue on GitHub or reach out to the maintainers.
