# NestJS

Perfil para desenvolvimento de APIs e servicos com NestJS no VS Code, com TypeScript, debug e imports relativos conforme a convencao do Nest CLI.

Este perfil inclui a base compartilhada do [settings.json](../settings.json): tema nativo Dark 2026, icones Flow Deep, cursor fino, barras de rolagem discretas, painel lateral a direita e Tab manual com quatro espacos. Veja o [README](../README.md#base-compartilhada-settingsjson) para os demais ajustes comuns.

## Indicado Para

- APIs REST e GraphQL com NestJS.
- Microservicos e workers Nest.
- Projetos gerados com Nest CLI usando TypeScript.

## Extensoes Essenciais

- `icrawl.discord-vscode` - Discord Presence.
- `thang-nm.flow-icons` - tema de icones.
- `mechatroner.rainbow-csv` - leitura de CSV/TSV.
- `cweijan.vscode-office` - visualizacao de documentos Office (Word, Excel e PDF) direto no editor.
- `ms-vscode-remote.remote-wsl` - abre projetos no ambiente Linux do WSL.
- `ms-vscode-remote.remote-containers` - abre projetos em dev containers com Docker.
- `ms-azuretools.vscode-containers` - Container Tools: gerencia containers, imagens, logs e servicos Docker Compose.

O VS Code ja inclui suporte nativo forte a TypeScript, npm scripts e debug de Node. Por isso, o perfil nao instala packs de snippets de terceiros para NestJS, que tendem a ficar desatualizados em relacao as versoes novas do framework.

## Extensoes Opcionais

- `Prisma.prisma` - suporte ao schema Prisma quando o projeto usa Prisma como ORM.
- `orta.vscode-jest` - suporte a Jest quando o projeto usa esse runner.
- `vitest.explorer` - suporte a Vitest quando o projeto usa esse runner.
- `yoavbls.pretty-ts-errors` - leitura mais clara de erros TypeScript.
- `humao.rest-client` - bom para versionar requests em arquivos `.http`.
- `rangav.vscode-thunder-client` - alternativa com UI para testar APIs sem sair do VS Code.
- `redhat.vscode-yaml` - util para projetos com muitos arquivos YAML, como docker-compose e pipelines.

Para APIs Nest, `humao.rest-client` e a escolha mais leve quando os requests devem ficar no repositorio. `rangav.vscode-thunder-client` faz mais sentido quando a equipe prefere uma interface visual.

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
  "javascript.updateImportsOnFileMove.enabled": "always",
  "typescript.preferences.importModuleSpecifier": "relative",
  "javascript.preferences.importModuleSpecifier": "relative",
  "debug.javascript.autoAttachFilter": "smart"
}
```

O perfil desativa a indentacao automatica, a formatacao ao salvar, colar ou digitar e as acoes de correcao/organizacao de imports ao salvar. Tab e espacos continuam disponiveis para indentacao manual.

O `importModuleSpecifier` em `relative` segue a convencao do Nest CLI, que gera imports relativos nos modulos, controllers e services. Se o projeto usar paths absolutos via `tsconfig.json`, ajuste para `shortest` ou `non-relative`.

## Ferramentas Externas

- Node.js instalado.
- Nest CLI (`@nestjs/cli`) para gerar projetos, modulos, controllers e services.
- Um gerenciador de pacotes, como `npm`, `pnpm` ou `yarn`.
- ESLint e Prettier sao opcionais no projeto para uso pelo terminal ou CI; o perfil nao inclui suas extensoes.
- Jest (padrao do Nest CLI) configurado no projeto para execucao de testes.
