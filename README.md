# Trabalho de Prompt Engineering – Revisão Automática de Pull Requests (IaC)

**Aluno:** Felipe Piffer
**Curso:** MBA em Cloud Computing e DevOps
**Cloud:** AWS

---

## Objetivo do Trabalho

Demonstrar domínio de *Prompt Engineering* por meio da criação de três versões evolutivas de um prompt (v1, v2 e v3) para análise automática de Pull Requests (PRs) de Infraestrutura como Código (IaC), simulando o papel de um engenheiro DevOps responsável por revisar mudanças antes de produção.

Cada versão do prompt busca melhorar a anterior em termos de:

* Clareza de instruções
* Consistência das respostas
* Estrutura da saída
* Robustez contra erros e ataques de *prompt injection*

---

## Contexto Simulado

O cenário assume um engenheiro responsável por revisar dezenas de PRs de IaC diariamente, avaliando mudanças em Terraform e CloudFormation na AWS, com foco em:

* Segurança
* Custo
* Compliance
* Boas práticas

A IA é utilizada como apoio à decisão, não como aprovadora final.

---

## Raciocínio de Criação dos Prompts

### Versão v1 – Baseline

A versão v1 representa um prompt inicial e simplificado, semelhante ao que um usuário iniciante criaria. Ele fornece pouco contexto, não define formato de saída e não impõe restrições claras sobre como a IA deve interpretar o conteúdo do PR.

Objetivo desta versão:

* Demonstrar respostas inconsistentes
* Evidenciar falta de padronização
* Mostrar vulnerabilidade a instruções maliciosas embutidas no PR

Essa versão serve como ponto de comparação para as melhorias posteriores.

---

### Versão v2 – Structured

A versão v2 introduz estrutura explícita ao prompt. Nela, são definidos critérios claros de análise (segurança, custo, compliance e boas práticas), além de solicitações diretas para classificação de risco, decisão e ações recomendadas.

Melhorias em relação à v1:

* Maior previsibilidade das respostas
* Organização por tópicos
* Melhor alinhamento com práticas reais de revisão de PRs

Apesar da evolução, esta versão ainda pode ser influenciada por textos maliciosos incluídos no PR.

---

### Versão v3 – Schema + Anti Prompt Injection

A versão v3 é a mais completa e robusta, simulando um prompt pronto para uso profissional. Ela define regras explícitas de comportamento para a IA, incluindo a obrigatoriedade de ignorar qualquer instrução contida no conteúdo do PR.

Principais melhorias:

* Proteção explícita contra *prompt injection*
* Saída padronizada em formato fixo (schema)
* Separação clara entre dados de entrada e regras de análise
* Maior consistência e confiabilidade nos resultados

Esta versão se mostrou resiliente mesmo diante de PRs contendo tentativas diretas de manipulação da IA.

---

## Testes Realizados

Cada versão do prompt foi aplicada aos mesmos Pull Requests de teste fornecidos na especificação do trabalho, incluindo:

* Criação de recursos AWS
* Alterações com impacto em segurança
* Mudanças com alto impacto de custo
* Melhorias de governança
* Tentativas explícitas de *prompt injection*

Os resultados de cada execução foram registrados por meio de capturas de tela e organizados na pasta `resultados/`, conforme solicitado.

---

## Conclusão

A evolução entre as versões evidencia a importância do *Prompt Engineering* para uso seguro e confiável de IA em ambientes de produção. Um prompt bem estruturado reduz ambiguidades, aumenta a qualidade das respostas e protege contra usos maliciosos, tornando a IA uma ferramenta efetiva de apoio ao trabalho de engenharia.
