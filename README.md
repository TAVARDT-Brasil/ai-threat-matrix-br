# Matriz Interativa de Ameaças a Sistemas de Inteligência Artificial

[![Live Demo](https://img.shields.io/badge/GitHub%20Pages-Live%20Demo-38bdf8?style=for-the-badge)](https://tavardt-brasil.github.io/ai-threat-matrix-br/)
[![Standard](https://img.shields.io/badge/Standard-OWASP%20LLM%20%26%20MITRE-3b82f6?style=for-the-badge)](https://tavardt-brasil.github.io/ai-threat-matrix-br/)
[![Privacy](https://img.shields.io/badge/Privacy-100%25%20Client-Side-10b981?style=for-the-badge)](https://tavardt-brasil.github.io/ai-threat-matrix-br/)
[![License](https://img.shields.io/badge/License-MIT-slate?style=for-the-badge)](LICENSE)

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

### Licença
Distribuído sob a Licença MIT. Consulte o arquivo [LICENSE](LICENSE) para mais detalhes.

***

## Governança e Soberania

* **Unidade Soberana**: [TAVARDT Brasil](https://ag.tavardt.com/br/) (`TAVARDT-Brasil`)
* **Normas Centrais**: [00-core Governança](https://github.com/TAVARDT-Brasil/00-core)
* **Central de Diagnósticos**: [Central de Ferramentas TAVARDT](https://tools.tavardt.com/br/)
* **Segurança Corporativa**: [TAVARDT Cibersegurança](https://ag.tavardt.com/br/ciberseguranca/)

***

### Licença
Distribuído sob a Licença MIT. Consulte o arquivo [LICENSE](LICENSE) para obter detalhes completos.

***

© 2026 TAVARDT. Todos os direitos reservados.
