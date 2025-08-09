- alias::
  tags::
  url:: 
  rel-projects::
  see-also::
-
- # Multi-Platform Notes Publishing Workflow
- ## Overview
  
  This repository contains a sophisticated workflow for managing notes across three platforms:
  
  1. **Logseq** - For bullet-based, block-referenced note-taking
  2. **Obsidian** - For graph-based knowledge management
  3. **Quarto** - For publication-ready documents
  
  Each platform publishes to its own custom subdomain, preserving the unique features and formatting of each tool.
- ## Architecture
  
  ```
  ┌─────────────────┐     ┌──────────────────┐     ┌─────────────────┐
  │    Logseq       │────▶│   GitHub Repo    │◀────│    Obsidian     │
  │notes-logseq.com │     │  (Main Source)   │     │notes-obsidian.  │
  └─────────────────┘     └──────────────────┘     │     .com        │
         │                       ▲               └─────────────────┘
         │                       │                        │
         │              ┌────────┴────────┐               │
         └──────────────┤ Sync Scripts    ├───────────────┘
                        └────────┬────────┘
                                 │
                       ┌─────────▼──────────┐
                       │    Quarto          │
                       │notes-quarto.com    │
                       └────────────────────┘
  ```
- ## Key Features
- ### 1. Platform-Specific Formatting
- **Logseq**: Preserves bullet formatting, block references `((block-id))`, and page embeds
- **Obsidian**: Maintains wiki-links `[[page]]`, tags, and backlinks
- **Quarto**: Professional publication format with proper YAML frontmatter
- ### 2. Automated Synchronization
- Weekly scheduled sync every Sunday at 2 AM UTC
- Manual sync trigger available
- Intelligent source detection based on modification history
- Bidirectional sync preserving platform-specific features
- ### 3. Custom Publishing
- Each platform publishes to its own subdomain
- Logseq maintains its bullet-based UI
- Obsidian uses a Material theme for an Obsidian-like experience
- Quarto provides a professional publication site
- ## Quick Start
- ### 1. Initial Setup
  
  ```bash
  # Clone the repository
  git clone <your-repo-url>
  cd notes-repository
  
  # Run setup script with your domains
  python setup_repo.py \
  --logseq-domain=notes-logseq.yourdomain.com \
  --obsidian-domain=notes-obsidian.yourdomain.com \
  --quarto-domain=notes-quarto.yourdomain.com
  
  # Initialize and push to GitHub
  git add .
  git commit -m "Initial notes repository setup"
  git push -u origin main
  ```
- ### 2. DNS Configuration
  
  Add these CNAME records to your domain:
  
  ```
  notes-logseq    →  yourusername.github.io
  notes-obsidian  →  yourusername.github.io
  notes-quarto    →  yourusername.github.io
  ```
- ### 3. GitHub Pages Setup
  
  Configure three GitHub Pages deployments:
- `gh-pages-logseq` for Logseq
- `gh-pages-obsidian` for Obsidian
- `gh-pages-quarto` for Quarto
- ## Usage Workflows
- ### Writing Notes
- #### In Logseq
  ```markdown
  title:: My Note
  type:: note
  
  - This is a bullet point
  - ((block-reference)) to another block
  - {{embed [[Another Page]]}}
  ```
- #### In Obsidian
  ```markdown
  ---
  title: My Note
  tags: [example, obsidian]
  created: 2025-05-11
  ---
  
  # My Note
  
  This is standard markdown with [[wiki-links]] and backlinks.
  ```
- #### In Quarto
  ```markdown
  ---
  title: "My Note"
  format: html
  date: "2025-05-11"
  categories: [example, quarto]
  ---
  
  # My Note
  
  Professional publication format for web publishing.
  ```
- ### Synchronization
- #### Manual Sync
  ```bash
  # Sync from content to all platforms
  python scripts/notes_sync.py --source content --target all
  
  # Sync from specific platform to others
  python scripts/notes_sync.py --source logseq --target all
  ```
- #### Automated Sync
- Runs weekly on Sunday at 2 AM UTC
- Automatically detects the most active source
- Syncs changes across all platforms
- Triggers appropriate publishing workflows
- ## Directory Structure
  
  ```
  notes-repository/
  ├── content/                 # Core markdown content
  │   ├── notes/              # Your actual notes
  │   └── assets/             # Images and attachments
  ├── logseq/                 # Logseq-specific files
  │   ├── pages/              # Logseq pages
  │   ├── config.edn          # Logseq configuration
  │   └── CNAME               # Custom domain
  ├── obsidian/               # Obsidian vault
  │   ├── notes/              # Obsidian notes
  │   ├── .obsidian/          # Obsidian settings
  │   └── CNAME               # Custom domain
  ├── quarto/                 # Quarto project
  │   ├── posts/              # Quarto posts
  │   ├── _quarto.yml         # Quarto configuration
  │   └── CNAME               # Custom domain
  ├── scripts/                # Utility scripts
  │   ├── notes_sync.py       # Main sync script
  │   └── yaml_transformer.py # YAML format converter
  └── .github/workflows/      # GitHub Actions
    ├── sync-notes.yml      # Immediate sync on push
    ├── weekly-sync.yml     # Scheduled weekly sync
    ├── logseq_publish.yml  # Logseq publishing
    ├── obsidian_publish.yml# Obsidian publishing
    └── quarto_publish.yml  # Quarto publishing
  ```
- ## Advanced Features
- ### Block Reference Conversion
  
  The sync script automatically converts between platform-specific syntax:
- Logseq `((block-id))` → Obsidian `[[^block-id]]`
- Logseq `{{embed [[page]]}}` → Obsidian `![[page]]`
- Converts both to appropriate Quarto syntax
- ### YAML Frontmatter Adaptation
  
  Each platform has different metadata requirements:
  
  | Field      | Logseq      | Obsidian    | Quarto      |
  |------------|-------------|-------------|-------------|
  | Title      | `title::`   | `title:`    | `title:`    |
  | Type       | `type::`    | -           | -           |
  | Tags       | -           | `tags:`     | `categories:` |
  | Date       | -           | `created:`  | `date:`     |
  | Format     | -           | -           | `format:`   |
- ## Troubleshooting
- ### Common Issues
  
  1. **Sync Not Working**
	- Check GitHub Actions logs
	- Verify script dependencies are installed
	- Ensure proper Git configuration
	  
	  2. **Publishing Failures**
	- Verify DNS records are correctly set
	- Check GitHub Pages settings
	- Review workflow logs for errors
	  
	  3. **Format Conflicts**
	- Manually run YAML transformer
	- Check for unsupported syntax
	- Review conversion logs
- ### Debug Commands
  
  ```bash
  # Test sync with verbose output
  python scripts/notes_sync.py --source logseq --target obsidian -v
  
  # Validate YAML transformations
  python scripts/yaml_transformer.py --source logseq --target obsidian file.md
  
  # Check Git history
  git log --oneline --graph --all
  ```
- ## Contributing
  
  Feel free to customize this workflow for your needs:
  
  1. Modify sync frequency in `weekly-sync.yml`
  2. Adjust platform-specific configurations
  3. Add new platforms or publishing destinations
  4. Enhance the sync logic for your use case
- ## License
  
  This workflow template is provided as-is for personal use. Modify and adapt as needed for your note-taking workflow.