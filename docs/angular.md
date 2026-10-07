# Angular

Perfil para desenvolvimento Angular com TypeScript e suporte a templates, sem indentacao ou formatacao automatica.

Este perfil inclui a base compartilhada do [settings.json](../settings.json): tema nativo Dark 2026, icones Flow Deep, cursor fino, barras de rolagem discretas, painel lateral a direita e Tab manual com quatro espacos. Veja o [README](../README.md#base-compartilhada-settingsjson) para os demais ajustes comuns.

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
- `ms-azuretools.vscode-containers` - Container Tools: gerencia containers, imagens, logs e servicos Docker Compose.
- `angular.ng-template` - Angular Language Service.

## Extensoes Opcionais

- `bradlc.vscode-tailwindcss` - util quando o projeto Angular usa Tailwind CSS.
- `nrwl.angular-console` - util para workspaces Nx e monorepos gerenciados com Nx.

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
- Angular CLI, normalmente via `npm`, `pnpm` ou `yarn`.
- Opcionalmente, `eslint`, `prettier` e pacotes `@angular-eslint/*` para lint/formatacao pelo terminal ou CI; o perfil nao inclui suas extensoes.
