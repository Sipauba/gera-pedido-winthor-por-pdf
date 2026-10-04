# Validações e estados

> **Status: Protótipo em desenvolvimento.** Os critérios abaixo são provisórios.

O nó “Validar compatibilidade dos candidatos” busca incompatibilidades objetivas antes da avaliação por IA. “Preparar candidatos para IA” e “Tem candidatos para IA?” controlam quais opções seguem. “Avaliar candidatos com IA” recebe apenas a lista aprovada pelas etapas anteriores; “Validar decisão da IA” verifica se a resposta está dentro das regras e dos códigos disponíveis.

Estados identificados no workflow:

- **APROVADO** — candidato considerado suficientemente compatível segundo os critérios atuais; ainda pode exigir conferência.
- **REVISAR** — há candidato provável, mas atributos não confirmados, confiança insuficiente ou necessidade de conferência humana.
- **SEM_CORRESPONDENCIA** — nenhum candidato adequado permaneceu disponível.
- **ERRO_IA** — resposta não validada ou em desacordo com o formato/regras esperados.

Esses rótulos não equivalem a aprovação comercial nem substituem a conferência humana.
