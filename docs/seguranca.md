# Segurança e dados

> **Status: Protótipo em desenvolvimento.** Esta documentação não substitui a revisão de segurança do ambiente que o executar.

Pedidos podem conter dados comerciais, identificação de clientes e informações pessoais. Não versione documentos reais, arquivos PDF recebidos, planilhas Excel geradas ou payloads de produção. Exemplos devem ser inteiramente fictícios.

- Mantenha credenciais no gerenciador do n8n ou em mecanismo seguro do ambiente.
- Não inclua API keys, tokens, senhas ou credenciais Oracle no workflow, no Git ou em logs.
- Sanitize toda exportação n8n antes de publicá-la: URLs, IDs de webhook/instância, referências de credenciais, metadados e Sticky Notes.
- A cópia pública generaliza a URL da API de mídia e mascara webhook ID e `instanceId`; o Sticky Note que continha cópia do workflow foi reduzido a uma nota curta.
- Use `.env.example` apenas como lista de nomes; mantenha valores reais fora do repositório.
- PDFs e XLSX estão ignorados pelo Git para reduzir publicação acidental de pedidos e resultados.

Recomenda-se executar [gitleaks](https://github.com/gitleaks/gitleaks) antes de publicar e revisar os valores encontrados manualmente, pois scanners podem não detectar identificadores e dados comerciais contextuais.
