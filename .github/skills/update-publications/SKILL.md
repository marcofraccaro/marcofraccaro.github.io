---
name: update-publications
description: "Use when: updating Marco's publications list from Google Scholar. Helps fetch new publications, download PDFs, organize BibTeX entries, and update the website."
---

# Update Publications Skill

This skill guides you through the process of updating the publications list on marcofraccaro.github.io from your Google Scholar profile.

## Overview

The publications update workflow involves six main steps:
1. **Identify publications** from Google Scholar or provide publication details
2. **Select publications** you want to add
3. **Download or obtain PDFs** for selected publications
4. **Create/manage BibTeX entries** 
5. **Update publications.md** with new entries in chronological order
6. **Verify all files** are properly organized and linked

## Step 1: Fetch Publications from Google Scholar

Navigate to your Google Scholar profile:
- URL: https://scholar.google.com/citations?hl=en&user=s52eLC4AAAAJ&view_op=list_works&sortby=pubdate
- Review the list sorted by publication date (most recent first)
- Identify new publications that aren't in `publications.md`

**Important:** Google Scholar has dynamic content that cannot be automatically scraped. You will need to manually review the page and provide publication details.

**Tips:**
- Note the publication title, authors, venue, year, and publication date
- Check if the publication already exists in publications.md to avoid duplicates
- Gather DOI, arXiv link, or conference/journal URL if available
- Copy/paste titles and details directly from Google Scholar when prompted

## Step 2: Provide Publication Details

Provide the agent with publication information found on Google Scholar:

**For each publication provide:**
- Full title
- All authors (in order)
- Venue/Journal name
- Publication year
- Publication date (if available)
- DOI, arXiv link, or publisher URL

**Format:** You can copy/paste directly from Google Scholar or type out a structured list.

**Your role:**
- Review the Google Scholar list for new publications
- Provide details for publications you want to add
- Specify placement (optional):
  - **Highlighted publications**: Major papers, PhD/Master theses, top-tier conferences (NeurIPS, ICML, Nature, Science, etc.)
  - **Other publications**: Journal articles, workshop papers, conference papers from other venues

**Reasons to skip a publication:**
- Already listed in publications.md
- Work in progress or preprint you want to exclude
- Paper published somewhere you don't want highlighted
- Contributions you prefer not to list publicly
- Duplicate or superseded by a newer version

## Step 3: Download or Obtain PDFs for Selected Publications

For each publication, obtain the PDF:

**Common sources:**
- Publisher website (DOI link)
- arXiv (for preprints): https://arxiv.org/
- ResearchGate or author's personal website
- Google Scholar's "PDF" link

**Automatic downloads:** Many publisher websites block automated downloads (MDPI, ACM, etc.). If automated downloads fail:
- Manually download from the publisher/source website
- Save with the correct filename in `/download/publications/`

**File naming convention:**
- Use kebab-case (lowercase, hyphens): `paper-title-shortened.pdf`
- Match the BibTeX filename (see Step 4)
- Store in `/download/publications/`
- No spaces in filenames

**Example:**
```
generative-temporal-models-with-spatial-memory_icml2018.pdf
```**Note:** PDFs can be added manually even if the agent cannot auto-download them. The BibTeX entries and publications.md can be updated first, and PDFs added later.

## Step 4: Create/Manage BibTeX Entries

For each publication you selected, create a `.bib` file:

**Option A: Generate from Google Scholar**
1. Find the publication on Google Scholar
2. Click the quote icon ("") at the bottom
3. Select "BibTeX" format
4. Copy the BibTeX entry

**Option B: Generate from CrossRef**
1. Search the publication on https://www.crossref.org/
2. Copy the BibTeX format

**Option C: Manually create a BibTeX entry**
If automated sources aren't easily accessible, create manually using the publication details:

```bibtex
@article{fraccaro2025,
  title={Full Publication Title},
  author={Author1, A. and Author2, B. and Author3, C.},
  journal={Journal Name},
  volume={6},
  number={2},
  pages={37},
  year={2025},
  publisher={Publisher Name},
  doi={10.xxxx/xxxxx},
  url={https://example.com}
}
```

**File naming convention:**
- Use same name as PDF: `paper-title-shortened.bib`
- Store in `/download/bibtex/`
- No spaces in filenames

**Ensure:**
- The `@type` (article, inproceedings, phdthesis, etc.) is correct
- All author names are included in full
- Year is set correctly
- DOI or URL is present
- Volume, pages, and publisher info included when available

## Step 5: Update publications.md

Add new publication entries to `publications.md` in chronological order (newest first).

**Location:**
- "Highlighted publications" section (for major papers, theses, top-tier venues)
- "Other publications" section (for all other publications)

**Insertion point:** 
- Add new publications at the **top** of their respective section
- This maintains reverse-chronological order (most recent first)

**HTML entry template:**
```html
<li> 
<b> Full Publication Title. </b> <font color="red"> [optional badge] </font> <br>
Author1, Author2, Author3. <br>
<i>Venue Name, Year. </i> <br>
<a href="url">[venue-link]</a>
<a href="/download/publications/filename.pdf">[pdf]</a>
<a href="/download/bibtex/filename.bib">[bibtex]</a>
</li>
```

**Typical links to include:**
- Publisher/conference page: `[ICML]`, `[NeurIPS]`, `[Diagnostics]`, `[ACM]`
- PDF on website: `[pdf]`
- ArXiv version (if available): `[arXiv]`
- GitHub repo (if available): `[code]`
- BibTeX entry: `[bibtex]`

**Badge examples:**
- `[long talk]`, `[oral presentation]`, `[spotlight presentation]`
- Leave badge empty if not applicable (keep the `<font color="red"> </font>` placeholder)

## Step 6: Verify All Files and Links

Ensure proper file organization and link integrity:

**Directory structure:**
```
download/
├── publications/
│   ├── filename.pdf
│   ├── filename_supplementary.zip (if applicable)
│   └── ...
└── bibtex/
    ├── filename.bib
    └── ...
```

**Final verification checklist:**
- [ ] All selected publications added to `publications.md`
- [ ] PDFs exist in `/download/publications/` (or noted as manual download needed)
- [ ] BibTeX files exist in `/download/bibtex/`
- [ ] Filenames match between PDF and BibTeX (except extension)
- [ ] Filenames match the links in `publications.md`
- [ ] No spaces in filenames (use hyphens)
- [ ] All HTML links in publications.md point to correct files
- [ ] File naming is consistent (kebab-case, lowercase)
- [ ] BibTeX entries are properly formatted with all required fields
- [ ] No duplicate publications (check against existing entries)
- [ ] Entries are in correct chronological order (most recent first within each section)
- [ ] Author names are complete and properly formatted in BibTeX

## Workflow Summary

1. **Open Google Scholar profile** and manually identify new publications (2024+)
2. **Provide publication details** to the agent (copy/paste from Google Scholar)
3. **Create BibTeX entries** (auto-generate or manually create)
4. **Download PDFs** (manually or auto-download if available)
5. **Update publications.md** with new entries at top of appropriate section
6. **Verify all files** are properly organized and linked

For most workflows, Steps 3, 4, and 5 can happen in parallel or immediately without waiting for PDFs.

## Highlighted vs Other Publications

**publications.md has two main sections:**

1. **Highlighted publications**
   - PhD/Master theses
   - Top-tier conference papers (NeurIPS, ICML, ICCV, CVPR, etc.)
   - Top-tier journals (Nature, Science, JMLR, etc.)
   - Papers with presentation honors (oral, spotlight, long talk)

2. **Other publications**
   - Journal articles
   - Workshop papers
   - Conference papers from other venues
   - Technical reports

**Ordering within sections:** Reverse-chronological (newest first)

## Key Differences from Manual Updates

**This skill optimizes the update process by:**
- Acknowledging Google Scholar's dynamic content limitations
- Requiring manual publication detail entry instead of auto-scraping
- Supporting parallel workflows (don't need all PDFs before publishing entry)
- Providing fallback options when automated downloads fail
- Including comprehensive BibTeX creation guidance

## Tools & Resources

**Publication Sources:**
- **Google Scholar**: https://scholar.google.com/citations?hl=en&user=s52eLC4AAAAJ&view_op=list_works&sortby=pubdate
- **arXiv**: https://arxiv.org/ (for preprints and PDFs)
- **CrossRef**: https://www.crossref.org/ (find BibTeX citations)

**BibTeX Tools:**
- **BibDesk**: https://www.bibdesk.org/ (desktop editor)
- **BibTeX Tidy**: https://truben.no/bibtex/ (online editor)
- **Google Scholar Citation Export**: Click quote icon → BibTeX

**Validation & Preview:**
- **VS Code Markdown Preview**: Check links as you update publications.md
- **Local Jekyll Build**: `bundle exec jekyll serve` to verify site rendering

## Common Issues & Solutions

**Issue**: PDF link broken in publications.md  
**Solution**: Verify the filename in download/publications/ matches exactly (case-sensitive on GitHub Pages)

**Issue**: BibTeX file not loading  
**Solution**: Check for typos in filename and ensure .bib extension is lowercase

**Issue**: Publication already exists  
**Solution**: Search publications.md for the title or authors before adding

**Issue**: Can't find PDF  
**Solution**: Check arXiv, ResearchGate, or contact the authors for the paper

---

**Last updated:** March 2026  
**Site**: marcofraccaro.github.io
