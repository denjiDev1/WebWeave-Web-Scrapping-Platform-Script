# 🕸️ WebWeave – Smart Web Info Extractor

WebWeave is a powerful, terminal-based and web-integrated application that intelligently crawls, scrapes, and extracts structured information from any target website. From company details and contact info to legal pages, portfolios, and upcoming events – WebWeave organizes it all, and stores the results in **MongoDB** with a unique SHA-256 hash key for retrieval.

---

## 🚀 Features

- 🔍 **Deep Website Crawling** via Selenium and BeautifulSoup
- 🧠 **Smart Extraction** of structured categories:
  - Company Overview
  - Services, Categories & Subcategories
  - Contact Info (Email, Phone)
  - News, Events, Team, Legal, Portfolio
- 🧱 **Data Storage** in MongoDB with unique SHA-256 keys
- 📦 **Dual Output Formats**: JSON and TXT
- 🧠 **Modular Design** for integration with web apps
- 📜 **Terminal Interface** (CLI-based usage)
- 🔑 **SHA-256 Key Generation** using (email + URL) for unique access
- 📤 **Web App Compatibility**: Can be deployed in a backend server setup

---

## 🛠️ Technologies Used

- **Language**: Python  
- **Libraries**: `selenium`, `beautifulsoup4`, `re`, `pymongo`, `hashlib`, `json`, `os`  
- **Database**: MongoDB Atlas (Cloud or Local)  
- **CLI Input**: `python main.py <email> <link>`

---

## 🧪 How It Works

1. Receives `email` and `link` via command-line or web app
2. Initializes a headless **Selenium** session and crawls all internal links
3. Extracts text, metadata, and identifies category-specific content using regex
4. Saves the structured data to:
   - `output_data/all_data.json`
   - `output_data/all_data.txt`
5. Uploads to **MongoDB** using a hash key derived from `email + link`
6. Returns a success message with the hash key as retrieval ID

---

## 📂 Folder Structure

```
webweave/
├── output_data/            # Stores all_data.json and all_data.txt
├── main.py                 # Main crawling & extraction script
├── utils/                  # SHA, normalization, link extractor
├── templates/              # (Optional) Web frontend
├── case_study.pdf          # 📘 Visual documentation & process report
├── README.md
```

---

## 🧪 Running the Script

```bash
python main.py your_email@example.com https://example.com
```

> 📝 This will start crawling, extract all structured data, and store it in MongoDB with a generated hash key.

---

## 📄 Output Example

```
output_data/
├── all_data.json    # Structured data dump
└── all_data.txt     # Readable format for manual inspection
```

MongoDB Entry:
```json
{
  "key": "9b3ef5c1a3a8d472...f49e01",
  "text_data": "All extracted information as a string"
}
```

---

## 🧩 Use Case Integration

WebWeave was designed as a module for a larger **Lead Generation + Intelligence Platform** where users submit a URL, and get clean structured insights about the business or product ecosystem of that site.

It can also be integrated into:
- Web Audit Tools
- B2B Data Enrichment Platforms
- SaaS Company Profiling Apps

---

## 📘 Case Study

📎 **`webweave_webscrapping.pdf`** — Included in the root directory.

The case study covers:
- Problem Statement & Objective
- System Architecture & Flowchart
- Sample Screenshots
- Technologies Used
- Challenges Faced
- Key Learnings & Future Scope

---

## 💡 Example Use Case

> "Given a startup's website, retrieve their mission, services, team members, news updates, contact channels, and upload all into a knowledge database."

---

## 🤝 Contributing

Feel free to fork this repo and submit improvements like:
- Multilingual scraping
- ML-based text classification
- Frontend Dashboard
- PDF/CSV Export Options

---

## 📜 License

MIT License © 2025 Botnist Devs

---
> 🕸️ *Weave through the web. Extract the essence.*
