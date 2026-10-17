# Chandamama Kathalu Reader

Static site for reading Chandamama Telugu magazine issues (1947–2002).

**Source:** [Internet Archive collection](https://archive.org/details/chandamama_telugu_all) (~646 PDFs, 6.2GB)

## Cloudflare (Paid Plan) Deployment

Your paid Cloudflare plan is ideal:

### 1. Pages (frontend)
1. Dashboard → Workers & Pages → Create application → Pages → Connect to Git
2. Select this repo (`chandamama-kathalu-reader`)
3. Production branch: `main`
4. Build command: (leave empty or `exit 0`)
5. Build output directory: `/`
6. Deploy. Add custom domain if desired (easy on paid).

### 2. R2 (PDF storage — "files in our database")
- Create bucket e.g. `chandamama-pdfs`
- Enable public access or attach custom domain / Worker
- Use the `mirror_to_r2.py` script (see below) to copy all PDFs from Archive.org
- Storage cost: ~$0.015/GB-month → ~$0.09/month for 6.2GB. Egress free.
- After upload, update `BASE_URL` in `viewer.html` to your R2 public URL.

### Catalog
`chandamama_catalog.json` drives the year/month browser. Expand it with full list as needed (naming pattern: `Chandamama-YYYY_MM.pdf` or `Chandamama-YYYY-MM.pdf`).

## Files
- `index.html` — Catalog browser
- `viewer.html` — PDF.js reader (supports IA or R2)
- `mirror_to_r2.py` — Bulk mirror script

## Legal
Archival/educational. Not affiliated with original publishers. Early issues likely public domain.
