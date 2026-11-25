# Matriz Interativa de Ameaças a Sistemas de Inteligência Artificial

[![Live Demo](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-5b3cf5.svg)](https://tavardt-brasil.github.io/ai-threat-matrix-br/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Matriz interativa de ameaças e guia de mitigação para aplicações com Modelos de Linguagem e IA generativa. Baseado em OWASP LLM e MITRE ATLAS.

Desenvolvido para organizações, pesquisadores e equipes de engenharia em **Brasil**, este repositório fornece uma matriz estruturada para avaliação de postura defensiva e blindagem técnica de aplicações com Modelos de Linguagem e agentes de Inteligência Artificial autônomos.

***

## Modos de Operação

### 1. Aplicação Web no Navegador (GitHub Pages)
Acesse a versão gráfica interativa diretamente pelo navegador:
- **Endereço Oficial**: [https://tavardt-brasil.github.io/ai-threat-matrix-br/](https://tavardt-brasil.github.io/ai-threat-matrix-br/)
- **Privacidade por Design**: Processamento 100% no motor JavaScript do seu navegador. Nenhum dado arquitetural ou resultado é transmitido para servidores remotos.

### 2. Utilitário de Linha de Comando (CLI)
Para validação automatizada em pipelines de CI/CD ou auditorias locais:

```bash
# Avaliação básica com perfil de arquitetura de agente autônomo
python threat_matrix_evaluator.py -arch agent

# Exportação de Blueprint de Blindagem em Markdown
python threat_matrix_evaluator.py -arch rag -export-blueprint hardening-blueprint.md

# Validação com arquivo de perfil de controles defensivos
python threat_matrix_evaluator.py -profile profile.json -strict

# Saída estruturada em JSON para automações
python threat_matrix_evaluator.py -arch agent -json
```

***

## 10 Vetores de Ameaça Mapeados (OWASP Top 10 for LLMs)

1. **Injeção de Prompts (Direta e Indireta)**: Manipulação do fluxo de instruções do LLM via entradas manipuladas ou dados de contexto externo.
2. **Divulgação de Informações Sensíveis**: Fuga involuntária de PII, chaves de API ou dados confidenciais nas respostas geradas.
3. **Vulnerabilidades na Cadeia de Suprimentos**: Riscos decorrentes de bibliotecas externas, plugins vulneráveis ou checkpoints de modelos adulterados.
4. **Envenenamento de Dados e Modelos**: Corrupção deliberada de dados de treinamento ou documentos de fine-tuning.
5. **Tratamento Inadequado de Saídas**: Execução direta de respostas do modelo por interpretadores ou bancos de dados sem higienização.
6. **Excessiva Concessão de Autonomia**: Agentes dotados de extensões e permissões de sistema sem supervisão ou barreiras de contenção.
7. **Vazamento do Prompt de Sistema**: Extração não autorizada de instruções de negócio ou personas fundamentais.
8. **Fraquezas em Embeddings e Vetores**: Manipulação da base vetorial do RAG via injeção de documentos maliciosos.
9. **Alucinação e Desinformação Crítica**: Geração de conclusões fáticas incorretas em fluxos críticos de tomada de decisão.
10. **Consumo Ilimitado de Recursos**: Esgotamento de capacidade computacional ou ataques de negação de carteira (Denial of Wallet).

***

## Integração em CI/CD (GitHub Actions)

Exemplo de pipeline para verificação contínua de postura de segurança:

```yaml
name: AI Threat Matrix Gate
on: [push, pull_request]

jobs:
  evaluate-ai-security:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.11'
      - name: Run AI Threat Matrix Assessment
        run: |
          python threat_matrix_evaluator.py -arch agent -strict
```

***

## Conformidade e Padrões Técnicos

- **Padrão Normativo**: OWASP Top 10 for LLM Applications e MITRE ATLAS

***

## Links Úteis

* **Portal Corporativo:** https://ag.tavardt.com/br/
* **Suíte de Diagnósticos:** https://tools.tavardt.com/br/
* **Contato Técnico:** https://ag.tavardt.com/br/contato/

***

### Licença
Distribuído sob a Licença MIT.

***

© 2026 TAVARDT. Todos os direitos reservados.
