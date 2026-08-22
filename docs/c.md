# C

Perfil para desenvolvimento em C no VS Code usando WSL, com foco em aprender e trabalhar com a toolchain real do Linux: terminal, GCC/Clang, GDB, Make e CMake quando fizer sentido.

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
- `tinkertrain.theme-panda` - tema de cores Panda Syntax.
- `ms-vscode.cpptools` - suporte oficial da Microsoft para C/C++, IntelliSense, navegacao, formatacao e debug.

Para o seu caso, faz sentido deixar `ms-vscode-remote.remote-wsl` e `ms-vscode.cpptools` como obrigatorias. O VS Code fica no Windows, mas o projeto roda no Linux do WSL, que e onde a toolchain de C deve viver.

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
  "C_Cpp.default.compilerPath": "/usr/bin/gcc",
  "C_Cpp.default.intelliSenseMode": "linux-gcc-x64",
  "C_Cpp.default.cStandard": "c17",
  "C_Cpp.errorSquiggles": "enabled",
  "C_Cpp.formatting": "clangFormat",
  "C_Cpp.clang_format_fallbackStyle": "LLVM",
  "[c]": {
    "editor.defaultFormatter": "ms-vscode.cpptools",
    "editor.formatOnSave": true
  }
}
```

Esses settings assumem uso dentro do WSL. Se o projeto for aberto fora do WSL, o `compilerPath` `/usr/bin/gcc` provavelmente nao existe no Windows e deve ser ajustado.

## Ferramentas Externas

- WSL instalado.
- Uma distribuicao Linux no WSL, como Ubuntu.
- Toolchain de C no WSL, por exemplo `build-essential`.
- `gcc` ou `clang`.
- `gdb` para debug.
- `make` para projetos com `Makefile`.
- `cmake` apenas quando o projeto usar CMake.
- `clang-format` se quiser formatacao consistente pelo terminal e pelo VS Code.
