# 📣 Social Media AI Studio

### RAG-Powered Social Media Marketing & Content Generation

An AI-powered web application that generates original, business-focused social media posts using **Retrieval-Augmented Generation (RAG), advanced prompt engineering, OpenAI, ChromaDB, and Streamlit**.

The application uses knowledge retrieved from an uploaded social media marketing reference book to create content tailored to different businesses, audiences, and social media platforms.

## 🚀 Features

- 📚 **PDF Knowledge Base:** Upload a social media marketing book or other PDF reference material.
- 🧠 **Retrieval-Augmented Generation:** Retrieve relevant passages before generating content.
- ✍️ **AI Content Generation:** Generate LinkedIn, Instagram, Facebook, and X posts.
- 🎯 **Audience Targeting:** Customize content for a specific target audience.
- 🎨 **Tone Selection:** Choose professional, educational, storytelling, or friendly writing.
- 🔍 **Source Transparency:** View retrieved book passages and their PDF page numbers.
- 📥 **Download Content:** Export generated content as a text file.
- ☁️ **Cloud Deployment:** Deploy through Streamlit Community Cloud.

## 🏗️ Application Architecture

```text
                USER
                 |
                 v
        Streamlit Web Interface
                 |
                 v
          Upload PDF Book
                 |
                 v
        PDF Text Extraction
                 |
                 v
           Text Chunking
                 |
                 v
         OpenAI Embeddings
                 |
                 v
        ChromaDB Vector Store
                 |
                 v
         Semantic Retrieval
                 |
                 v
       Advanced Prompt Template
                 |
                 v
           OpenAI LLM
                 |
                 v
       Generated Social Media Post
                 |
                 v
        Review and Download
```

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| Python | Application programming language |
| Streamlit | Interactive web interface |
| OpenAI API | Embeddings and content generation |
| ChromaDB | Vector database for semantic search |
| PyPDF | PDF text extraction |
| RAG | Grounding generated content in retrieved knowledge |

**Models used:**

- Embeddings: `text-embedding-3-small`
- Content generation: `gpt-4.1-mini`

## 📁 Project Structure

```text
social-media-ai-studio/
│
├── app.py
├── requirements.txt
├── README.md
├── .gitignore
│
├── .streamlit/
│   └── secrets.toml   # Local only, do not commit
│
└── .venv/             # Local only, do not commit
```

## 💻 Local Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/social-media-ai-studio.git
cd social-media-ai-studio
```

Replace `YOUR_USERNAME` with your GitHub username.

### Step 2: Create a Virtual Environment

On macOS or Linux:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

On Windows:

```powershell
python -m venv .venv
.venv\Scripts\activate
```

### Step 3: Install Dependencies

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

The `requirements.txt` file should contain:

```text
streamlit>=1.40,<2
openai>=1.60,<3
chromadb>=1.0,<2
pypdf>=5,<7
```

### Step 4: Configure OpenAI API Key

Create a `.streamlit` folder and a `secrets.toml` file inside it.

```toml
OPENAI_API_KEY = "your-openai-api-key"
```

Never commit this file to GitHub.

### Step 5: Start the Application

```bash
python -m streamlit run app.py
```

Open the local application:

**http://localhost:8501**

To stop the application, press `Control + C` in Terminal.

## 📖 How to Use

1. Launch the Streamlit application.
2. Upload a PDF containing social media marketing knowledge.
3. Click **Process Book** to create the searchable knowledge base.
4. Enter a social media post topic.
5. Choose the social media platform.
6. Specify the target audience and writing tone.
7. Click **Generate Post**.
8. Review the AI-generated content and its retrieved source passages.
9. Edit the content and download it as a text file.

## 🧪 Example Use Case

**Business:** Online AI Training Academy

**Target Audience:** Working professionals and students

**Platform:** LinkedIn

**Topic:** How AI skills can help professionals prepare for future career opportunities

**Tone:** Educational

**Expected output:**

An original LinkedIn post featuring a compelling opening, relevant educational insights, an actionable recommendation, a call to action, and suitable hashtags.

The application also displays relevant retrieved passages from the uploaded reference document.

## 🧠 Advanced Prompt Engineering

This project demonstrates several important prompting concepts:

**Role Prompting:** Assigns the AI the role of an experienced social media strategist.

**Context Grounding:** Supplies relevant passages retrieved from the knowledge base.

**Audience Conditioning:** Adapts the response to the intended audience and platform.

**Constraint-Based Prompting:** Instructs the model to avoid unsupported statistics, lengthy copied passages, and outdated platform claims.

**Structured Output Prompting:** Requests a hook, main post, call to action, hashtags, and supporting page references.

**Source Verification:** Allows users to inspect retrieved passages and review generated claims before publication.

## ☁️ Deployment on Streamlit Community Cloud

1. Push `app.py`, `requirements.txt`, `README.md`, and `.gitignore` to GitHub.
2. Visit https://share.streamlit.io/.
3. Sign in with GitHub.
4. Select the repository containing the project.
5. Choose the `main` branch.
6. Set the main application file to `app.py`.
7. Add the following in the deployment's Secrets settings:

```toml
OPENAI_API_KEY = "your-openai-api-key"
```

8. Deploy the application.
9. Open the deployed URL and test the PDF indexing and post generation workflow.

The application requires a working OpenAI API account with available usage credits.

## 🔒 Security, Privacy & Limitations

- Never expose API keys in source code or public repositories.
- Do not upload confidential documents to a publicly accessible demonstration application.
- Uploaded PDF content is sent to the configured embedding API for processing.
- The current application uses an in-memory ChromaDB collection; indexed knowledge is not guaranteed to persist across sessions or server restarts.
- Scanned PDFs without extractable text require OCR, which is not included in this version.
- AI-generated content may contain inaccuracies and should be reviewed before publication.
- API requests incur usage costs.
- This classroom MVP does not include authentication, user quotas, billing, or persistent customer storage.

### Copyright and Reference Material

The sample knowledge source is *The Social Media Marketing Book* by Dan Zarrella, published by O'Reilly Media in 2010.

The book is copyrighted. Do not publicly redistribute its PDF or substantial extracted content without appropriate permission.

Because the book is historical, platform-specific information may be outdated. Use its foundational marketing concepts as reference material and independently verify current platform features, policies, and statistics.

## 🔮 Future Enhancements

- Business profile management
- Persistent multi-user knowledge bases
- Seven-day and 30-day content calendars
- Multiple post variations
- Brand voice templates
- Content evaluation and quality scoring
- User authentication and subscription plans
- Marketing analytics integrations
- Approval workflows before publishing
- Direct social media publishing through authorized platform APIs

## 🎓 Educational Objectives

This project demonstrates how to combine:

- Retrieval-Augmented Generation
- Embeddings and vector databases
- Semantic search
- Advanced prompt engineering
- Large language models
- Web application development
- Cloud deployment

It is designed as a practical learning project for students studying Generative AI, Prompt Engineering, and Agentic AI.

---

**Built with Python, Streamlit, OpenAI, and ChromaDB.**

*Social Media AI Studio — Turning marketing knowledge into actionable content.*
