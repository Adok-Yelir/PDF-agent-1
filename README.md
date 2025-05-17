<details> <summary>Click to copy the full README markup</summary>
markdown
Copy
Edit
# PDF Manager v2

This repo contains the docker-compose stack and n8n workflow for an automated
PDF intake pipeline: ingest ➜ convert ➜ OCR ➜ GPT extract ➜ rename ➜ file.

## Quick start

1. Create a `.env` next to `docker-compose.yml` with  
OPENAI_API_KEY=<your-openai-key>
AZURE_CV_KEY=<your-azure-vision-key>
AZURE_CV_ENDPOINT=https://<region>.api.cognitive.microsoft.com/
N8N_USER=admin
N8N_PASSWORD=strongpass
POSTGRES_PASSWORD=n8npass
markdown
Copy
Edit
2. `docker compose up -d`  
3. Browse to **http://localhost:5678** (login = `admin` / `strongpass`).  
4. Import `n8n_graph_credentials.json` and `workflow-pdf-manager-v2.json`.

### Scaling workers
```bash
docker compose up -d --scale n8n-worker=3
