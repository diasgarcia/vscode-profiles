# Node.js

Perfil para desenvolvimento Node.js moderno no VS Code, com foco em JavaScript, TypeScript e debug de processos Node.

Este perfil inclui a base compartilhada do [settings.json](../settings.json): tema nativo Dark 2026, icones Flow Deep, cursor fino, barras de rolagem discretas, painel lateral a direita e Tab manual com quatro espacos. Veja o [README](../README.md#base-compartilhada-settingsjson) para os demais ajustes comuns.

## Indicado Para

- APIs, CLIs, workers e bibliotecas em Node.js.
- Projetos JavaScript ou TypeScript.
- Times que querem um setup base sem amarrar o perfil a React, Next.js, NestJS ou outro framework especifico.

## Extensoes Essenciais

- `icrawl.discord-vscode` - Discord Presence.
- `thang-nm.flow-icons` - tema de icones.
- `mechatroner.rainbow-csv` - leitura de CSV/TSV.
- `cweijan.vscode-office` - visualizacao de documentos Office (Word, Excel e PDF) direto no editor.
- `ms-vscode-remote.remote-wsl` - abre projetos no ambiente Linux do WSL.
- `ms-vscode-remote.remote-containers` - abre projetos em dev containers com Docker.
- `yoavbls.pretty-ts-errors` - leitura mais clara de erros TypeScript.

O VS Code ja inclui suporte nativo forte a JavaScript, TypeScript, npm scripts e debug de Node. Por isso, o perfil nao instala extensoes extras para funcionalidades que ja existem no editor.

## Extensoes Opcionais

- `christian-kohler.npm-intellisense` - autocomplete de pacotes npm em imports; util, mas nao essencial.
- `orta.vscode-jest` - suporte a Jest quando o projeto usa esse runner.
- `vitest.explorer` - suporte a Vitest quando o projeto usa esse runner.
- `ms-vscode.vscode-typescript-next` - JavaScript and TypeScript Nightly, apenas quando o projeto precisa testar a versao mais nova do TypeScript.
- `Prisma.prisma` - suporte a schema Prisma.
- `bradlc.vscode-tailwindcss` - util quando o projeto usa Tailwind CSS.
- `redhat.vscode-yaml` - util para projetos com muitos arquivos YAML.
- `ms-azuretools.vscode-containers` - suporte a containers quando o projeto usa Docker/Compose.
- `humao.rest-client` - bom para versionar requests em arquivos `.http`.
- `rangav.vscode-thunder-client` - alternativa com UI para testar APIs sem sair do VS Code.

Para APIs Node, `humao.rest-client` e a escolha mais leve quando os requests precisam morar no repositorio. `rangav.vscode-thunder-client` faz mais sentido quando a equipe prefere uma interface visual.

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
  "typescript.preferences.importModuleSpecifier": "shortest",
  "javascript.preferences.importModuleSpecifier": "shortest",
  "debug.javascript.autoAttachFilter": "smart"
}
```

O perfil desativa a indentacao automatica, a formatacao ao salvar, colar ou digitar e as acoes de correcao/organizacao de imports ao salvar. Tab e espacos continuam disponiveis para indentacao manual.

## Ferramentas Externas

- Node.js instalado.
- Um gerenciador de pacotes, como `npm`, `pnpm` ou `yarn`.
- ESLint e Prettier sao opcionais no projeto para uso pelo terminal ou CI; o perfil nao inclui suas extensoes.
- TypeScript instalado no projeto quando o codigo for TypeScript.
- Um runner de testes, como Jest, Vitest ou Node Test Runner, conforme a stack do projeto.
