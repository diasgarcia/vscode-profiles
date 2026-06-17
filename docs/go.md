# Go

Perfil para desenvolvimento Go moderno no VS Code, com foco em suporte oficial da linguagem, `gopls`, debug, testes e formatacao padrao da toolchain Go.

## Indicado Para

- APIs, CLIs, workers e bibliotecas em Go.
- Projetos Go modules.
- Times que querem um perfil enxuto, sem misturar ferramentas de backend, cloud ou containers por padrao.

## Extensoes Essenciais

- `icrawl.discord-vscode` - Discord Presence.
- `thang-nm.flow-icons` - tema de icones.
- `mechatroner.rainbow-csv` - leitura de CSV/TSV.
- `golang.go` - extensao oficial de Go, mantida pelo Go Team at Google, com suporte a linguagem, `gopls`, debug, testes, formatacao e ferramentas da stack Go.

A extensao oficial cobre o que normalmente seria dividido em varias extensoes: IntelliSense, navegacao, diagnosticos, testes, debug com Delve e integracao com ferramentas como `gofmt`, `goimports` e `gopls`.

## Extensoes Opcionais

- `editorconfig.editorconfig` - util quando o time padroniza indentacao e finais de linha via `.editorconfig`.
- `redhat.vscode-yaml` - util para projetos com muitos arquivos YAML, como manifests, pipelines e configuracoes de deploy.
- `ms-azuretools.vscode-containers` - suporte a containers quando o projeto usa Docker/Compose.
- `humao.rest-client` - bom para versionar requests em arquivos `.http`.
- `rangav.vscode-thunder-client` - alternativa com UI para testar APIs sem sair do VS Code.

Para APIs Go, `humao.rest-client` e a escolha mais leve quando os requests devem ficar no repositorio. `rangav.vscode-thunder-client` faz mais sentido quando a equipe prefere uma interface visual.

## Principais Settings

```json
{
  "go.useLanguageServer": true,
  "go.toolsManagement.autoUpdate": true,
  "[go]": {
    "editor.defaultFormatter": "golang.go",
    "editor.formatOnSave": true,
    "editor.codeActionsOnSave": {
      "source.organizeImports": "explicit"
    }
  }
}
```

## Ferramentas Externas

- Go instalado.
- `gopls` para linguagem, autocomplete e diagnosticos; a extensao oficial pode gerenciar a instalacao.
- Delve (`dlv`) para debug; a extensao oficial pode instalar quando necessario.
- `go test` configurado no projeto para execucao de testes.
- `go vet`, `staticcheck` ou linters equivalentes quando o projeto exigir analise adicional no terminal ou CI.
