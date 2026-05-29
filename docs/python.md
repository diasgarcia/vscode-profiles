# Python

Perfil para desenvolvimento Python moderno no VS Code, com foco em autocomplete, type checking basico, debug e padronizacao de lint/formatacao com Ruff.

## Indicado Para

- APIs e scripts Python.
- Projetos com `pyproject.toml`.
- Times que querem um setup leve, sem misturar notebook/data science por padrao.

## Extensoes Essenciais

- `icrawl.discord-vscode` - Discord Presence.
- `thang-nm.flow-icons` - tema de icones.
- `mechatroner.rainbow-csv` - leitura de CSV/TSV.
- `ms-python.python` - suporte oficial a Python.
- `ms-python.vscode-pylance` - IntelliSense e type checking com Pyright/Pylance.
- `ms-python.debugpy` - debug de codigo Python.
- `charliermarsh.ruff` - lint, formatacao e organizacao de imports.

## Extensoes Opcionais

- `ms-toolsai.jupyter` - notebooks, celulas interativas e fluxos de dados.
- `ms-python.vscode-python-envs` - gerenciamento visual de ambientes Python. Em versoes atuais, pode ser instalado como parte do ecossistema da extensao Python, mas nao e o foco principal deste perfil.

## Principais Settings

```json
{
  "python.analysis.typeCheckingMode": "basic",
  "python.analysis.autoImportCompletions": true,
  "[python]": {
    "editor.defaultFormatter": "charliermarsh.ruff",
    "editor.codeActionsOnSave": {
      "source.fixAll.ruff": "explicit",
      "source.organizeImports.ruff": "explicit"
    }
  }
}
```

## Ferramentas Externas

- Python instalado na maquina.
- Um gerenciador de ambiente, como `venv`, `pyenv`, `conda`, `poetry` ou equivalente.
- Ruff pode ser instalado no projeto para alinhar VS Code, terminal e CI.
- Opcionalmente, Jupyter instalado no ambiente quando o projeto usar notebooks.
