# Playwright / QA

Perfil para automacao de testes com Playwright, JavaScript e TypeScript, com execucao, debug e inspecao de testes.

Este perfil inclui a base compartilhada do [settings.json](../settings.json): tema nativo Dark 2026, icones Flow Deep, cursor fino, barras de rolagem discretas, painel lateral a direita e Tab manual com quatro espacos. Veja o [README](../README.md#base-compartilhada-settingsjson) para os demais ajustes comuns.

## Indicado Para

- Testes end-to-end com Playwright.
- Projetos QA com TypeScript ou JavaScript.
- Suites de testes que rodam localmente e em CI.

## Extensoes Essenciais

- `icrawl.discord-vscode` - Discord Presence.
- `thang-nm.flow-icons` - tema de icones.
- `mechatroner.rainbow-csv` - leitura de CSV/TSV e massa de dados.
- `cweijan.vscode-office` - visualizacao de documentos Office (Word, Excel e PDF) direto no editor.
- `ms-vscode-remote.remote-wsl` - abre projetos no ambiente Linux do WSL.
- `ms-vscode-remote.remote-containers` - abre projetos em dev containers com Docker.
- `ms-azuretools.vscode-containers` - Container Tools: gerencia containers, imagens, logs e servicos Docker Compose.
- `ms-playwright.playwright` - execucao, debug e inspecao de testes Playwright.

## Extensoes Opcionais

- `eamodio.gitlens` - historico e autoria de codigo, util em investigacao de falhas.
- `humao.rest-client` - recomendado quando os requests devem ficar versionados em `.http`.
- `rangav.vscode-thunder-client` - alternativa com UI para quem prefere uma experiencia visual parecida com Postman.

Para suites de QA, `humao.rest-client` e a escolha mais leve quando os requests precisam morar no repositorio. `rangav.vscode-thunder-client` e melhor quando a equipe prefere colecoes visuais dentro do editor.

## Principais Settings

```json
{
  "editor.autoIndent": "none",
  "editor.detectIndentation": false,
  "editor.autoIndentOnPaste": false,
  "editor.formatOnSave": false,
  "editor.formatOnPaste": false,
  "editor.formatOnType": false,
  "editor.codeActionsOnSave": {
    "source.fixAll": "never",
    "source.organizeImports": "never"
  },
  "typescript.updateImportsOnFileMove.enabled": "always",
  "javascript.updateImportsOnFileMove.enabled": "always"
}
```

O perfil desativa a indentacao automatica, a formatacao ao salvar, colar ou digitar e as acoes de correcao/organizacao de imports ao salvar. Tab e espacos continuam disponiveis para indentacao manual.

## Ferramentas Externas

- Node.js instalado.
- Playwright instalado no projeto, normalmente com `npm init playwright` ou equivalente.
- Browsers do Playwright instalados com `npx playwright install`.
- ESLint e Prettier sao opcionais no projeto para uso pelo terminal ou CI; o perfil nao inclui suas extensoes.
