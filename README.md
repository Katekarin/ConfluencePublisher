# Confluence Publisher

Publishes a Markdown file to a Confluence page, uploads referenced images, and converts Mermaid blocks to images.

## Requirements
- .NET SDK
- Mermaid CLI (`mmdc`) available on PATH, or pass `--mermaid-cli` with its full path

## Credentials
Create a `credentials.json` file:

```json
{
  "baseUrl": "https://your-domain.atlassian.net/wiki",
  "username": "your-email@example.com",
  "apiToken": "your-api-token"
}
```

Use `--save-credentials` to write credentials from the command line to the file.

## Usage

```bash
dotnet run --project ConfluencePublisher -- \
  --markdown docs/example.md \
  --space SPACEKEY \
  --title "Page Title" \
  --parent-id 123456 \
  --credentials-file credentials.json
```

Optional arguments:
- `--page-id` use a specific page ID
- `--base-url` override Confluence base URL
- `--username` override username
- `--api-token` override API token
- `--log-file` write logs to a specific path
- `--mermaid-cli` path to `mmdc`
- `--save-credentials` save current credentials to the file
