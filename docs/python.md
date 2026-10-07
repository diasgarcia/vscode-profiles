# Python

Perfil para desenvolvimento Python moderno no VS Code, com foco em autocomplete, type checking basico e debug.

Este perfil inclui a base compartilhada do [settings.json](../settings.json): tema nativo Dark 2026, icones Flow Deep, cursor fino, barras de rolagem discretas, painel lateral a direita e Tab manual com quatro espacos. Veja o [README](../README.md#base-compartilhada-settingsjson) para os demais ajustes comuns.

## Indicado Para

- APIs e scripts Python.
- Projetos com `pyproject.toml`.
- Times que querem um setup leve, sem misturar notebook/data science por padrao.

## Extensoes Essenciais

- `icrawl.discord-vscode` - Discord Presence.
- `thang-nm.flow-icons` - tema de icones.
- `mechatroner.rainbow-csv` - leitura de CSV/TSV.
- `cweijan.vscode-office` - visualizacao de documentos Office (Word, Excel e PDF) direto no editor.
- `ms-vscode-remote.remote-wsl` - abre projetos no ambiente Linux do WSL.
- `ms-vscode-remote.remote-containers` - abre projetos em dev containers com Docker.
- `ms-azuretools.vscode-containers` - Container Tools: gerencia containers, imagens, logs e servicos Docker Compose.
- `ms-python.python` - suporte oficial a Python.
- `ms-python.vscode-pylance` - IntelliSense e type checking com Pyright/Pylance.
- `ms-python.debugpy` - debug de codigo Python.

## Extensoes Opcionais

- `ms-toolsai.jupyter` - notebooks, celulas interativas e fluxos de dados.
- `ms-python.vscode-python-envs` - gerenciamento visual de ambientes Python. Em versoes atuais, pode ser instalado como parte do ecossistema da extensao Python, mas nao e o foco principal deste perfil.

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
  "python.analysis.typeCheckingMode": "basic",
  "python.analysis.autoImportCompletions": true
}
```

O perfil desativa a indentacao automatica, a formatacao ao salvar, colar ou digitar e as acoes de correcao/organizacao de imports ao salvar. Tab e espacos continuam disponiveis para indentacao manual.

## Ferramentas Externas

- Python instalado na maquina.
- Um gerenciador de ambiente, como `venv`, `pyenv`, `conda`, `poetry` ou equivalente.
- Ruff e opcional no projeto para lint/formatacao pelo terminal ou CI; sua extensao nao esta incluida no perfil.
- Opcionalmente, Jupyter instalado no ambiente quando o projeto usar notebooks.
