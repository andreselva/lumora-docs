# Instruções do projeto de documentação

## Sobre este projeto

- Este repositório é a documentação do Lumora, publicada com [Mintlify](https://mintlify.com).
- As páginas são arquivos MDX com frontmatter YAML. A configuração fica em `docs.json`.
- O código-fonte do produto fica no repositório `lumora`, normalmente em `../lumora`. Ele é a fonte de verdade técnica.
- Não altere o repositório `lumora` a partir de tarefas de documentação.
- Para conhecimento sobre o Mintlify (componentes, configuração), instale a skill: `npx skills add https://mintlify.com/docs`.

## Públicos

- `user/`: fotógrafos que usam o produto. Linguagem simples, sem detalhes de implementação.
- `developers/`: quem mantém o Lumora. Arquitetura, fluxos, decisões e operação.

## Terminologia

- Escreva em português.
- Mantenha em inglês, sem tradução, os identificadores do código: nomes de classes, enums, campos, rotas e serviços. Exemplo: "Uma foto permanece em `PENDING_UPLOAD` enquanto...".
- Use "evento", "galeria" e "foto" para os conceitos do produto. Use "fotógrafo" para o usuário do Studio e "cliente" para quem recebe a galeria.
- Use "Lumora Studio" para a área do fotógrafo.
- Use "original" para o arquivo enviado e "derivados" para miniatura e preview.
- Use "tentativa" para `processingAttemptId` e "lease" para `processingLeaseUntil`.

## Estilo

- Voz ativa. No guia do usuário, trate o leitor por "você".
- Frases curtas, uma ideia por frase.
- Títulos em caixa de frase.
- Negrito para elementos da interface: clique em **Salvar alterações**.
- Formatação de código para arquivos, comandos, caminhos e identificadores.
- Sem linguagem de marketing e sem frases vazias.
- Prefira explicar conceitos, garantias e cenários a listar classes e métodos.
- Não use números de linha em referências ao código.
- Use diagramas Mermaid quando ajudarem. Cada diagrama responde a uma pergunta.

## Limites de conteúdo

- Documente apenas o que está confirmado no código. Não transforme comentários, o `README.md` do `lumora` ou suposições em fatos.
- Separe o estado atual do planejado. Use "atualmente" e "hoje" para o que existe; "consideração futura" e "planejado" para o que não existe.
- No guia do usuário, não apresente como disponível uma funcionalidade incompleta. Não exponha conceitos internos como SQS, DynamoDB, Lambda, lease ou version ids.
- Quando algo não puder ser confirmado, diga isso na página ou não documente.
- Não registre segredos, tokens, credenciais, ids de conta AWS, ids de recursos reais nem dados pessoais. Exemplos de chaves e ids são sempre fictícios.
- Crie um ADR apenas para decisões confirmadas no código. Veja `developers/adr/index.mdx`.

## Validação

Antes de concluir uma alteração, execute `mint validate` e `mint broken-links`.
