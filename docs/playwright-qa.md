# Playwright / QA

Perfil para automacao de testes com Playwright, JavaScript e TypeScript, mantendo lint e formatacao consistentes.

## Indicado Para

- Testes end-to-end com Playwright.
- Projetos QA com TypeScript ou JavaScript.
- Suites de testes que rodam localmente e em CI.

## Extensoes Essenciais

- `icrawl.discord-vscode` - Discord Presence.
- `thang-nm.flow-icons` - tema de icones.
- `mechatroner.rainbow-csv` - leitura de CSV/TSV e massa de dados.
- `ms-playwright.playwright` - execucao, debug e inspecao de testes Playwright.
- `dbaeumer.vscode-eslint` - lint para JavaScript/TypeScript.
- `esbenp.prettier-vscode` - formatacao.
- `editorconfig.editorconfig` - respeito ao `.editorconfig` do projeto.

## Extensoes Opcionais

- `eamodio.gitlens` - historico e autoria de codigo, util em investigacao de falhas.
- `humao.rest-client` - recomendado quando os requests devem ficar versionados em `.http`.
- `rangav.vscode-thunder-client` - alternativa com UI para quem prefere uma experiencia visual parecida com Postman.

Para suites de QA, `humao.rest-client` e a escolha mais leve quando os requests precisam morar no repositorio. `rangav.vscode-thunder-client` e melhor quando a equipe prefere colecoes visuais dentro do editor.

## Principais Settings

```json
{
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": "explicit"
  },
  "eslint.validate": [
    "javascript",
    "javascriptreact",
    "typescript",
    "typescriptreact"
  ],
  "[typescript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  }
}
```

## Ferramentas Externas

- Node.js instalado.
- Playwright instalado no projeto, normalmente com `npm init playwright` ou equivalente.
- Browsers do Playwright instalados com `npx playwright install`.
- ESLint e Prettier instalados no projeto para alinhar editor e CI.
