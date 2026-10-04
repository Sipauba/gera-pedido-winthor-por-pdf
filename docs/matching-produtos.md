# Correspondência de produtos

> **Status: Protótipo em desenvolvimento.** Regras e critérios podem mudar.

O nó “Normalizar produto solicitado” remove acentos, converte texto para maiúsculas, ajusta espaços e unidades e identifica medidas e atributos como volume, peso, dimensões, concentração, material, marca, modelo e quantidade por embalagem. Os termos preparados são usados para recuperar produtos possíveis.

“Buscar candidatos no Oracle” combina termos principais/técnicos e descrição normalizada, busca textual (`LIKE`), pontuação por presença de termos e `UTL_MATCH.JARO_WINKLER_SIMILARITY`. A similaridade é uma etapa de recuperação/ranking; sozinha não prova que dois itens sejam equivalentes.

Antes da IA, “Validar compatibilidade dos candidatos” tenta rejeitar divergências objetivas, incluindo volume, peso, dimensões, concentração, voltagem, quantidade/embalagem, tipo e características técnicas. A cobertura depende dos dados disponíveis no pedido e no cadastro.

Candidatos que passam as regras são preparados para avaliação semântica. A IA deve escolher somente entre os códigos fornecidos e não deve inventar, alterar ou criar códigos ou produtos. A saída é validada pelo fluxo; inconsistências podem resultar em erro ou revisão.
