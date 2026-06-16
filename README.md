# Projeto: Estudo do OWASP Top 10 com NotebookLM

## 1. Contexto e Objetivos
O objetivo deste projeto é utilizar o NotebookLM para realizar uma curadoria técnica sobre o OWASP Top 10, focando em entender as vulnerabilidades mais críticas da web e suas mitigações para ambientes de desenvolvimento.

## 2. Curadoria de Fontes
- Fonte: [OWASP Top 10:2021 PDF](https://owasp.org/www-project-top-ten/)

## 3. Engenharia de Prompts e "Cicatrizes" (Troubleshooting)
Durante a execução do projeto, o principal desafio foi transitar de uma abordagem teórica para uma prática. Inicialmente, as respostas da IA eram muito conceituais. Para resolver isso, apliquei técnicas de *Prompt Engineering*:
* **Refinamento de Contexto:** Adicionei a instrução "Atue como um mentor de cibersegurança" para forçar a IA a priorizar a aplicabilidade técnica.
* **Troubleshooting:** Ao notar que a IA omitia detalhes sobre controle de acesso, refinei o prompt para exigir especificamente "mitigações para desenvolvedores".
* **Raciocínio Técnico:** A dificuldade em extrair recomendações práticas me forçou a estruturar os prompts para que a IA organizasse as informações em tabelas comparativas.

## 4. Miniguia de Estudo

### Resumo e Tabela de Riscos
Este documento detalha as principais vulnerabilidades de segurança cibernética, focando em práticas de DevOps. A maioria dos riscos surge durante o design e desenvolvimento, reforçando que a cooperação entre desenvolvedores e operadores reduz drasticamente as brechas.

| Vulnerabilidade | Risco Associado | Recomendação de Mitigação |
| :--- | :--- | :--- |
| **A01: Broken Access Control** | Violação do privilégio mínimo. | Adotar "negar por padrão", verificar propriedade. |
| **A02: Security Misconfiguration** | Senhas padrão e erros expostos. | Hardening repetível e remover recursos inúteis. |
| **A03: Supply Chain Failures** | Uso de bibliotecas vulneráveis. | Inventário de versões e fontes oficiais. |
| **A04: Cryptographic Failures** | Algoritmos fracos/dados claros. | Criptografar dados e usar hashing moderno. |
| **A05: Injection** | Entrada não sanitizada. | Consultas parametrizadas e validação rigorosa. |

### Glossário
- **Controle de Acesso Quebrado (Broken Access Control):** Falha onde restrições de usuários autenticados não são aplicadas, permitindo elevação de privilégios ou acesso a dados alheios.
- **Injeção (Injection):** Ocorre quando dados não validados são inseridos em comandos, permitindo que atacantes executem código malicioso.
- **Configuração Incorreta de Segurança (Security Misconfiguration):** Falha no *hardening* do sistema, como uso de credenciais padrão ou exposição de mensagens de erro técnicas.
- **Falhas Criptográficas (Cryptographic Failures):** Falha em proteger dados sensíveis, seja por uso de algoritmos obsoletos (MD5/SHA1) ou transmissão em texto claro.
- **Falhas na Cadeia de Suprimentos de Software (Software Supply Chain Failures):** Risco associado ao uso de dependências de terceiros vulneráveis ou não confiáveis.

### Prompts Reutilizáveis
1. "Atue como um Especialista em Segurança. Liste as 3 principais técnicas de ataque para esta vulnerabilidade e como posso detectá-las nos logs do sistema."
2. "Crie um checklist de testes unitários para garantir que esta vulnerabilidade não seja inserida no meu código durante o desenvolvimento."
3. "Compare esta vulnerabilidade com o framework MITRE ATT&CK e me indique qual técnica de defesa é mais eficaz contra ela em um ambiente de produção."
