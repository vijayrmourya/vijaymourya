# Vijay Mourya - Portfolio Website

Personal portfolio website for Vijay Mourya - Senior DevOps & Infrastructure Reliability Engineer

**Live Site:** [vijayrmourya.github.io](https://vijayrmourya.github.io)

---

## Features

- 📚 **Dynamic Medium Posts** - Automatically fetched from Medium RSS feed
- 🎓 **Course Certificates** - Auto-generated from PDF files
- 🎨 **Modern UI** - Dark theme with responsive design
- ⚡ **Static Site** - Fast loading with client-side rendering

---

## Tech Stack

- HTML, CSS, JavaScript (Vanilla)
- Python 3.11 (automation scripts)
- GitHub Actions (CI/CD)
- GitHub Pages (hosting)

---

## Local Development

```bash
# Clone repository
git clone https://github.com/vijayrmourya/vijaymourya-master.git
cd vijaymourya-master

# Start local server
python3 -m http.server 8000

# Open browser at http://localhost:8000
```

---

## 🛠️ Automation Tools

All content is managed through YAML files + Python automation:

### 📛 Badge Certifications (Professional Certs)

```bash
# Interactive add
python3 tools/add_badge_certification.py

# Or edit YAML directly
vim tools/badge_certifications.yaml
python3 tools/generate_badge_certifications.py
```

**Add badge images:** Download from Credly/Coursera and save to `assets/badges/`

### 📜 Course Certificates (PDF-based)

```bash
# Interactive add
python3 tools/add_certificate.py

# Or edit YAML directly
vim tools/certificates.yaml
python3 tools/generate_certificates_from_yaml.py
```

**Add PDFs:** Place PDFs in `assets/certificates/{Category}/`

### 💼 Work Experience

```bash
# Interactive add
python3 tools/add_experience.py

# Or edit YAML directly
vim tools/experience.yaml
python3 tools/generate_experience.py
```

### 📝 Medium Posts

```bash
python3 tools/fetch_medium.py
```

---

## 🤖 GitHub Actions Workflows

**Automated Workflows** for content management:

1. **Update Badge Certifications** - Triggered on push
   - Runs when: `badge_certifications.yaml`, generator script, or badges change
   - Generates: `assets/badge_certifications.json`
   - Manual trigger: Available

2. **Update Course Certificates** - Triggered on push
   - Runs when: `certificates.yaml`, generator script, or certificates change
   - Generates: `assets/certificates.json`
   - Manual trigger: Available

3. **Update Experience** - Triggered on push
   - Runs when: `experience.yaml` or generator script changes
   - Generates: `experience.html`
   - Manual trigger: Available

4. **Fetch Medium Posts** - Scheduled daily
   - Runs: Daily at 6:00 AM UTC
   - Fetches: Latest posts from Medium RSS feed
   - Updates: `assets/medium_posts.json`
   - Manual trigger: Available

**Benefits:**
- Path-specific triggers (efficient resource usage)
- Immediate updates on content changes
- Clean commit messages with item counts
- `[skip ci]` prevents workflow loops

---

## 📁 Project Structure

```
vijaymourya-master/
├── *.html                        # Website pages
├── scripts.js                    # Dynamic content rendering
├── styles.css                    # Global styling
├── assets/
│   ├── badges/                   # Certification badge images
│   ├── certificates/             # PDF certificates by category
│   ├── badge_certifications.json # Auto-generated
│   ├── certificates.json         # Auto-generated
│   └── medium_posts.json         # Auto-generated
├── tools/
│   ├── badge_certifications.yaml # Badge certs config
│   ├── certificates.yaml         # Course certs config
│   ├── experience.yaml           # Experience config
│   ├── generate_*.py             # Generator scripts
│   ├── add_*.py                  # Interactive helpers
│   └── fetch_medium.py           # Medium RSS fetcher
└── .github/workflows/            # CI/CD automation
```

---

## ⚙️ Configuration

**Medium Username:** Edit `.github/workflows/fetch_medium.yml`
```yaml
env:
  MEDIUM_USERNAME: vjmourya
  MAX_POSTS: '6'
```

**Certification Categories:** Edit YAML files in `tools/`

---

## License

© 2025 Vijay Mourya. All rights reserved.

---

**Built with HTML, CSS, JavaScript, Python & GitHub Actions**

