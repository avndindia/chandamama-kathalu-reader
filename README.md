# Chandamama Kathalu Reader

Static site for reading Chandamama Telugu magazine issues.

## Deploy on Cloudflare Pages
1. Connect this repo to Cloudflare Pages.
2. Build command: empty or `exit 0`
3. Output directory: `/`

## R2 Support
The catalog includes an `r2_url` field (currently null). After uploading PDFs to R2, update those fields and the viewer will prefer R2.

See `mirror_to_r2.py` for the upload script (coming).

Source: https://archive.org/details/chandamama_telugu_all
