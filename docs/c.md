# C

Perfil para desenvolvimento em C no VS Code usando WSL, com foco em aprender e trabalhar com a toolchain real do Linux: terminal, GCC/Clang, GDB, Make e CMake quando fizer sentido.

Este perfil inclui a base compartilhada do [settings.json](../settings.json): tema nativo Dark 2026, icones Flow Deep, cursor fino, barras de rolagem discretas, painel lateral a direita e Tab manual com quatro espacos. Veja o [README](../README.md#base-compartilhada-settingsjson) para os demais ajustes comuns.

## Indicado Para

- Estudos de linguagem C no Windows usando WSL.
- Projetos pequenos compilados pelo terminal com `gcc` ou `clang`.
- Projetos C com `Makefile` ou, mais adiante, `CMakeLists.txt`.
- Quem quer evitar atalhos que escondem o processo de compilacao.

## Extensoes Essenciais

- `icrawl.discord-vscode` - Discord Presence.
- `thang-nm.flow-icons` - tema de icones.
- `mechatroner.rainbow-csv` - leitura de CSV/TSV.
- `cweijan.vscode-office` - visualizacao de documentos Office (Word, Excel e PDF) direto no editor.
- `ms-vscode-remote.remote-wsl` - permite abrir pastas, terminal, debug e extensoes dentro do ambiente Linux do WSL.
- `ms-vscode-remote.remote-containers` - abre projetos em dev containers com Docker.
- `ms-azuretools.vscode-containers` - Container Tools: gerencia containers, imagens, logs e servicos Docker Compose.
- `ms-vscode.cpptools` - suporte oficial da Microsoft para C/C++, IntelliSense, navegacao e debug; formatacao desativada neste perfil.

A combinacao de `ms-vscode-remote.remote-wsl` e `ms-vscode.cpptools` permite manter o VS Code no Windows e executar o projeto e a toolchain de C no Linux do WSL.

## Extensoes Opcionais

- `ms-vscode.makefile-tools` - util quando o projeto usa `Makefile`.
- `ms-vscode.cmake-tools` - util quando o projeto usa `CMakeLists.txt`.
- `ms-vscode.cpptools-extension-pack` - pacote mais completo de C/C++; bom para quem quer instalar tudo de uma vez, mas nao entra no perfil por padrao para evitar excesso.
- `usernamehw.errorlens` - mostra diagnosticos direto na linha; ajuda bastante em estudo, mas e uma escolha mais visual/pessoal.

O perfil nao inclui Code Runner de proposito. Para C, especialmente estudando no WSL, e melhor compilar e executar pelo terminal para entender o fluxo real:

```bash
gcc main.c -o main
./main
```

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
  "C_Cpp.default.compilerPath": "/usr/bin/gcc",
  "C_Cpp.default.intelliSenseMode": "linux-gcc-x64",
  "C_Cpp.default.cStandard": "c17",
  "C_Cpp.errorSquiggles": "enabled",
  "C_Cpp.formatting": "disabled"
}
```

O perfil desativa a indentacao automatica, a formatacao ao salvar, colar ou digitar e as acoes de correcao/organizacao de imports ao salvar. Tab e espacos continuam disponiveis para indentacao manual.

Esses settings assumem uso dentro do WSL. Se o projeto for aberto fora do WSL, o `compilerPath` `/usr/bin/gcc` provavelmente nao existe no Windows e deve ser ajustado.

## Ferramentas Externas

- WSL instalado.
- Uma distribuicao Linux no WSL, como Ubuntu.
- Toolchain de C no WSL, por exemplo `build-essential`.
- `gcc` ou `clang`.
- `gdb` para debug.
- `make` para projetos com `Makefile`.
- `cmake` apenas quando o projeto usar CMake.
- `clang-format` e opcional para formatacao pelo terminal; a formatacao de C/C++ esta desativada no perfil.
