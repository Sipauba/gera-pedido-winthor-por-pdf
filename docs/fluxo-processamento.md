# Fluxo de processamento

> **Status: Protótipo em desenvolvimento.**

Os nós atuais cobrem recebimento de evento, obtenção da mídia, conversão para arquivo, extração de PDF, interpretação com IA, separação de linhas, busca de catálogo, filtragem, validação da resposta e geração de Excel.

A extração tenta identificar número do pedido, cliente, data, item, código informado pelo cliente, descrição, quantidade, unidade, NCM, marca, modelo, produto-base, volume, peso, dimensões, concentração, cor, material, quantidade por embalagem e atributos adicionais. Esses valores dependem do documento e da interpretação do modelo. A IA não deve inventar informação ausente; campos desconhecidos devem permanecer ausentes ou ser sinalizados para revisão.

O caminho de mídia está implementado para PDF conforme os nós exportados. O suporte a imagem, foto e texto faz parte do objetivo mais amplo e requer validação/desenvolvimento antes de ser considerado disponível.
