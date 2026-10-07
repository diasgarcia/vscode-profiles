# Go

Perfil para desenvolvimento Go moderno no VS Code, com foco em suporte oficial da linguagem, gopls, debug e testes.

Este perfil inclui a base compartilhada do [settings.json](../settings.json): tema nativo Dark 2026, icones Flow Deep, cursor fino, barras de rolagem discretas, painel lateral a direita e Tab manual com quatro espacos. Veja o [README](../README.md#base-compartilhada-settingsjson) para os demais ajustes comuns.

## Indicado Para

- APIs, CLIs, workers e bibliotecas em Go.
- Projetos Go modules.
- Times que querem suporte de linguagem enxuto, com WSL e Dev Containers na base compartilhada.

## Extensoes Essenciais

- `icrawl.discord-vscode` - Discord Presence.
- `thang-nm.flow-icons` - tema de icones.
- `mechatroner.rainbow-csv` - leitura de CSV/TSV.
- `cweijan.vscode-office` - visualizacao de documentos Office (Word, Excel e PDF) direto no editor.
- `ms-vscode-remote.remote-wsl` - abre projetos no ambiente Linux do WSL.
- `ms-vscode-remote.remote-containers` - abre projetos em dev containers com Docker.
- `ms-azuretools.vscode-containers` - Container Tools: gerencia containers, imagens, logs e servicos Docker Compose.
- `golang.go` - extensao oficial de Go, mantida pelo Go Team at Google, com suporte a linguagem, `gopls`, debug, testes e ferramentas da stack Go; formatacao automatica desativada neste perfil.

A extensao oficial cobre o que normalmente seria dividido em varias extensoes: IntelliSense, navegacao, diagnosticos, testes, debug com Delve e integracao com ferramentas como `gofmt`, `goimports` e `gopls`.

## Extensoes Opcionais

- `redhat.vscode-yaml` - util para projetos com muitos arquivos YAML, como manifests, pipelines e configuracoes de deploy.
- `humao.rest-client` - bom para versionar requests em arquivos `.http`.
- `rangav.vscode-thunder-client` - alternativa com UI para testar APIs sem sair do VS Code.

Para APIs Go, `humao.rest-client` e a escolha mais leve quando os requests devem ficar no repositorio. `rangav.vscode-thunder-client` faz mais sentido quando a equipe prefere uma interface visual.

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
  "go.useLanguageServer": true,
  "go.toolsManagement.autoUpdate": true,
  "[go]": {
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
    "editor.tabSize": 4,
    "editor.insertSpaces": true
  }
}
```

O perfil desativa a indentacao automatica, a formatacao ao salvar, colar ou digitar e as acoes de correcao/organizacao de imports ao salvar. Tab e espacos continuam disponiveis para indentacao manual.

## Ferramentas Externas

- Go instalado.
- `gopls` para linguagem, autocomplete e diagnosticos; a extensao oficial pode gerenciar a instalacao.
- Delve (`dlv`) para debug; a extensao oficial pode instalar quando necessario.
- `go test` configurado no projeto para execucao de testes.
- `go vet`, `staticcheck` ou linters equivalentes quando o projeto exigir analise adicional no terminal ou CI.
