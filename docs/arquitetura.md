# Arquitetura

> **Status: Protótipo em desenvolvimento.** A arquitetura descrita reflete a exportação disponível e pode mudar.

O fluxo no n8n recebe um evento por webhook, recupera a mídia por uma API HTTP, converte o conteúdo para arquivo e extrai texto de PDF. Em seguida, OpenAI interpreta o pedido; nós JavaScript separam itens, normalizam atributos e preparam a busca. O Oracle retorna candidatos. Regras determinísticas filtram incompatibilidades antes de uma possível avaliação semântica com IA. A decisão é validada e consolidada em um Excel para conferência.

```mermaid
flowchart TD
    A[Documento / pedido] --> B[Webhook n8n]
    B --> C[Recuperação de mídia via HTTP]
    C --> D[Conversão Base64 / arquivo]
    D --> E[Extração de texto de PDF]
    E --> F[Extração estruturada com IA]
    F --> G[Separação de itens]
    G --> H[Normalização e termos]
    H --> I[Consulta Oracle]
    I --> J[Ranking e candidatos]
    J --> K[Validação determinística]
    K --> L{Candidatos elegíveis?}
    L -- Sim --> M[Avaliação semântica com IA]
    L -- Não --> N[Registrar ausência]
    M --> O[Validar decisão]
    N --> P[Consolidar]
    O --> P
    P --> Q[Excel para revisão humana]
```

A intenção futura é aceitar imagem, PDF, foto ou texto e preparar um orçamento no Winthor. Essa integração de ponta a ponta não deve ser presumida como existente: o workflow presente termina na planilha de conferência e não mostra gravação do orçamento no Winthor.
