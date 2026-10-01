# Documentação do Lumora

Documentação oficial do Lumora, publicada com [Mintlify](https://mintlify.com). O código-fonte do produto fica no repositório `lumora`.

A documentação tem dois públicos, em duas abas separadas:

| Aba | Pasta | Público | Conteúdo |
| --- | --- | --- | --- |
| Guia do usuário | `user/` | Fotógrafos | Como usar o produto. Só funcionalidades disponíveis, sem detalhes internos. |
| Desenvolvedores | `developers/` | Quem mantém o Lumora | Arquitetura, fluxos, modelo de dados, ADRs, operação e limitações. |

## Estrutura

```
docs.json                 navegação e identidade visual
user/                     guia do usuário
developers/
├── index.mdx             ponto de partida
├── limitations.mdx       limitações, pontos futuros e divergências do README
├── architecture/         visão geral, frontend, backend, infraestrutura, modelo de dados
├── flows/                autenticação, perfil, eventos e galerias, upload, processamento
├── adr/                  decisões arquiteturais
└── operations/           desenvolvimento local, implantação, observabilidade, problemas
```

## Princípios

- O **código** explica como algo foi implementado. A **documentação** explica como o sistema funciona. O **ADR** explica por que uma decisão foi tomada.
- O repositório `lumora` é a fonte de verdade. Em caso de divergência, o código prevalece e a página deve ser corrigida.
- Documente o sistema atual. O que é planejado fica identificado como planejado, em `developers/limitations.mdx`.
- Não registre segredos, tokens, ids de conta AWS, ids de recursos reais nem dados de usuários.

As regras de escrita estão em `AGENTS.md`.

## Pré-visualizar

Instale a CLI do Mintlify e execute na raiz do repositório:

```bash
npm i -g mint
mint dev
```

A pré-visualização fica em `http://localhost:3000`.

## Validar

```bash
mint validate
mint broken-links
```

Execute os dois comandos antes de abrir um pull request.

## Adicionar uma página

1. Crie o arquivo `.mdx` na pasta correspondente, com `title` e `description` no frontmatter.
2. Adicione o caminho ao grupo adequado em `docs.json`.
3. Para um ADR, siga as instruções de `developers/adr/index.mdx`.
