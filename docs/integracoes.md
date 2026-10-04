# Integrações

> **Status: Protótipo em desenvolvimento.** A configuração varia por instalação.

O workflow exportado contém nós para webhook n8n, API HTTP de recuperação de mídia, extração de arquivo/PDF, OpenAI e Oracle Database. A URL privada da API de mídia foi substituída por placeholder; configure um endpoint autorizado no ambiente local/n8n. Referências de credenciais devem ser configuradas na instância de destino, nunca inseridas como segredos no JSON público.

O SQL consulta um catálogo Oracle para recuperar candidatos e usa busca textual e `UTL_MATCH.JARO_WINKLER_SIMILARITY`. Usuário, senha, host, porta, service name, banco e ambiente devem ser fornecidos apenas na configuração privada. Nenhum orçamento é gravado no Winthor pelo fluxo atual; essa integração pertence ao objetivo futuro e precisa ser projetada e validada.

Variáveis com nomes genéricos estão em `.env.example`; o n8n pode exigir configurar credenciais pelo seu próprio gerenciador.
