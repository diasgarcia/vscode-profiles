# Angular

Perfil para desenvolvimento Angular com TypeScript, templates, ESLint, Prettier e EditorConfig.

## Indicado Para

- Aplicacoes Angular modernas.
- Projetos com Angular CLI.
- Times que querem evitar extensoes antigas de snippets ou packs grandes demais.

## Extensoes Essenciais

- `icrawl.discord-vscode` - Discord Presence.
- `thang-nm.flow-icons` - tema de icones.
- `mechatroner.rainbow-csv` - leitura de CSV/TSV.
- `cweijan.vscode-office` - visualizacao de documentos Office (Word, Excel e PDF) direto no editor.
- `ms-vscode-remote.remote-wsl` - abre projetos no ambiente Linux do WSL.
- `ms-vscode-remote.remote-containers` - abre projetos em dev containers com Docker.
- `tinkertrain.theme-panda` - tema de cores Panda Syntax.
- `angular.ng-template` - Angular Language Service.
- `dbaeumer.vscode-eslint` - integracao com ESLint.
- `esbenp.prettier-vscode` - formatacao com Prettier.
- `editorconfig.editorconfig` - respeito ao `.editorconfig` do projeto.

## Extensoes Opcionais

- `bradlc.vscode-tailwindcss` - util quando o projeto Angular usa Tailwind CSS.
- `nrwl.angular-console` - util para workspaces Nx e monorepos gerenciados com Nx.

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
    "typescriptreact",
    "html"
  ],
  "[typescript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[html]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  }
}
```

## Ferramentas Externas

- Node.js instalado.
- Angular CLI, normalmente via `npm`, `pnpm` ou `yarn`.
- Dependencias do projeto: `eslint`, `prettier` e pacotes `@angular-eslint/*` quando o projeto usar ESLint em templates Angular.
- Nx Console deve ser instalado apenas em projetos que realmente usam Nx.
