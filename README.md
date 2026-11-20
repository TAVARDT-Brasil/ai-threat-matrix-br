# Matriz Interativa de Ameacas a Sistemas de Inteligencia Artificial

[![Live Demo](https://img.shields.io/badge/GitHub%20Pages-Live%20Demo-38bdf8?style=for-the-badge)](https://tavardt-brasil.github.io/ai-threat-matrix-br/)
[![Standard](https://img.shields.io/badge/Standard-OWASP%20LLM%20%26%20MITRE-3b82f6?style=for-the-badge)](https://tavardt-brasil.github.io/ai-threat-matrix-br/)
[![Privacy](https://img.shields.io/badge/Privacy-100%25%20Client--Side-10b981?style=for-the-badge)](https://tavardt-brasil.github.io/ai-threat-matrix-br/)
[![License](https://img.shields.io/badge/License-MIT-slate?style=for-the-badge)](LICENSE)

Matriz interativa de ameacas e guia de mitigacao para aplicacoes com Modelos de Linguagem e IA generativa. Baseado em OWASP LLM e MITRE ATLAS.

Desenvolvido para organizacoes, pesquisadores e equipes de engenharia em **Brasil**, este repositorio fornece uma matriz estruturada para avaliacao de postura defensiva e blindagem tecnica de aplicacoes com Modelos de Linguagem e agentes de Inteligencia Artificial autonomos.

---

## Modos de Operacao

### 1. Aplicacao Web no Navegador (GitHub Pages)
Acesse a versao grafica interativa diretamente pelo navegador:
- **Endereco Oficial**: [https://tavardt-brasil.github.io/ai-threat-matrix-br/](https://tavardt-brasil.github.io/ai-threat-matrix-br/)
- **Privacidade por Design**: Processamento 100% no motor JavaScript do seu navegador. Nenhum dado arquitetural ou resultado e transmitido para servidores remotos.

### 2. Utilitario de Linha de Comando (CLI)
Para validacao automatizada em pipelines de CI/CD ou auditorias locais:

```bash
# Avaliacao basica com perfil de arquitetura de agente autonomo
python threat_matrix_evaluator.py --arch agent

# Exportacao de Blueprint de Blindagem em Markdown
python threat_matrix_evaluator.py --arch rag --export-blueprint hardening-blueprint.md

# Validacao com arquivo de perfil de controles defensivos
python threat_matrix_evaluator.py --profile profile.json --strict

# Saida estruturada em JSON para automacoes
python threat_matrix_evaluator.py --arch agent --json
```

---

## 10 Vetores de Ameaca Mapeados (OWASP Top 10 for LLMs)

1. **Injecao de Prompts (Direta e Indireta)**: Manipulacao do fluxo de instrucoes do LLM via entradas manipuladas ou dados de contexto externo.
2. **Divulgacao de Informacoes Sensiveis**: Fuga involuntaria de PII, chaves de API ou dados confidenciais nas respostas geradas.
3. **Vulnerabilidades na Cadeia de Suprimentos**: Riscos decorrentes de bibliotecas externas, plugins vulneraveis ou checkpoints de modelos adulterados.
4. **Envenenamento de Dados e Modelos**: Corrupcao deliberada de dados de treinamento ou documentos de fine-tuning.
5. **Tratamento Inadequado de Saidas**: Execucao direta de respostas do modelo por interpretadores ou bancos de dados sem higienizacao.
6. **Excessiva Concessao de Autonomia**: Agentes dotados de extensoes e permissoes de sistema sem supervisao ou barreiras de contencao.
7. **Vazamento do Prompt de Sistema**: Extracao nao autorizada de instrucoes de negocio ou personas fundamentais.
8. **Fraquezas em Embeddings e Vetores**: Envenenamento de bases de RAG para desviar o raciocinio do modelo.
9. **Alucinacao e Desinformacao Critica**: Producao de afirmacoes inveridicas em caminhos operacionais criticos.
10. **Consumo Ilimitado de Recursos**: Esgotamento de infraestrutura computacional ou custos abusivos de tokens (Denial of Wallet).

---

## Exemplo de Integracao com GitHub Actions

```yaml
name: AI Threat Matrix Gate
on: [push, pull_request]

jobs:
  evaluate-ai-security:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Configurar Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.11'
      - name: Executar Avaliacao da Matriz de Ameacas
        run: |
          python threat_matrix_evaluator.py --arch agent --strict
```

---

## Padroes Institucionais e Conformidade

- **Jurisdicao**: Brasil
- **Referencial Tecnico**: OWASP Top 10 for LLM Applications e MITRE ATLAS
- **Organizacao Mantenedora**: [TAVARDT-Brasil](https://github.com/TAVARDT-Brasil)

## Ecossistema e Portais TAVARDT

- **Portal Institucional**: [https://ag.tavardt.com/br/](https://ag.tavardt.com/br/)
- **Central de Ferramentas de Ciberseguranca**: [https://tools.tavardt.com/br/](https://tools.tavardt.com/br/)
- **Canal de Atendimento e Suporte Tecnico**: [https://ag.tavardt.com/br/contato/](https://ag.tavardt.com/br/contato/)

---

### Licenca
Distribuido sob os termos da licenca MIT. Consulte o arquivo [LICENSE](LICENSE) para maiores informacoes.
