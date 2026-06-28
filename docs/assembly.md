# Assembly Intel 64

Perfil para desenvolvimento em Assembly Intel 64 (x86-64) no VS Code, com syntax highlighting dedicado, debug visual com GDB e editor hexadecimal para inspeção binária.

## Indicado Para

- Estudos de Assembly, engenharia reversa e análise de binários.
- Desenvolvimento com NASM, YASM ou GNU Assembler (gas) na arquitetura x86-64.
- Quem quer um setup completo para escrever, compilar, depurar e inspecionar código de baixo nível no VS Code.
- Correções e patches binários com editor hexadecimal integrado.

## Extensões Essenciais

- `icrawl.discord-vscode` – Discord Presence.
- `thang-nm.flow-icons` – tema de ícones.
- `mechatroner.rainbow-csv` – leitura de CSV/TSV.
- `13xforever.language-x86-64-assembly` – syntax highlighting, snippets e suporte à linguagem Assembly Intel x86-64.
- `webfreak.debug` – debug visual com GDB/LLDB diretamente no VS Code.
- `ms-vscode.hexeditor` – editor hexadecimal oficial da Microsoft para inspeção e edição de arquivos binários.

## Extensões Opcionais

- `austin.code-gnu-global` – IntelliSense e navegação via GNU Global tags; útil se o projeto gerar tags para labels e símbolos.
- `ms-vscode.cpptools` – suporte oficial C/C++; pode ser útil se o projeto misturar código C com assembly inline.
- `yzhang.markdown-all-in-one` – útil para documentar notas de estudo, análise ou write-ups diretamente no repositório.

## Ferramentas Externas

No Ubuntu/WSL:

```bash
sudo apt update
sudo apt install nasm binutils gdb
```

Ferramentas usadas:

- **NASM** – assembler recomendado para sintaxe Intel.
- **LD** – linker usado para gerar o executável Linux.
- **GDB** – debugger usado pela extensão Native Debug.
- **Binutils** – pacote que fornece ferramentas de linkedição e inspeção binária.

## Configuração `.vscode/`

Este perfil também pode incluir uma configuração de projeto em `.vscode/` para compilar e depurar o arquivo Assembly aberto no momento.

Estrutura esperada:

```text
.vscode/
├── launch.json
├── settings.json
└── tasks.json
```

Essa configuração funciona bem para projetos simples de estudo, onde cada exercício tem um arquivo `.asm` independente.

## `.vscode/launch.json`

```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug ASM atual",
      "type": "gdb",
      "request": "launch",
      "target": "${workspaceFolder}/build/${fileBasenameNoExtension}",
      "cwd": "${fileDirname}",
      "preLaunchTask": "Build ASM atual",
      "valuesFormatting": "parseText"
    }
  ]
}
```

Essa configuração inicia o GDB usando o executável gerado em `build/`, com o mesmo nome do arquivo `.asm` aberto.

Exemplo:

```text
capitulo02/hello.asm
```

Ao rodar o debug, será gerado:

```text
build/hello.o
build/hello
```

## `.vscode/tasks.json`

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "Build ASM atual",
      "type": "shell",
      "command": "mkdir -p \"${workspaceFolder}/build\" && nasm -f elf64 -g -F dwarf \"${file}\" -o \"${workspaceFolder}/build/${fileBasenameNoExtension}.o\" && ld \"${workspaceFolder}/build/${fileBasenameNoExtension}.o\" -o \"${workspaceFolder}/build/${fileBasenameNoExtension}\"",
      "group": {
        "kind": "build",
        "isDefault": true
      },
      "problemMatcher": []
    }
  ]
}
```

Essa task compila o arquivo `.asm` aberto no VS Code com NASM e gera o executável dentro de `build/`.

O comando usado é:

```bash
nasm -f elf64 -g -F dwarf arquivo.asm -o build/arquivo.o
ld build/arquivo.o -o build/arquivo
```

## `.vscode/settings.json`

```json
{
  "editor.glyphMargin": true,
  "debug.allowBreakpointsEverywhere": true,
  "files.associations": {
    "*.asm": "asm-intel-x86-generic",
    "*.inc": "asm-intel-x86-generic",
    "*.s": "asm-intel-x86-generic",
    "*.S": "asm-intel-x86-generic"
  },
  "[asm-intel-x86-generic]": {
    "editor.formatOnSave": false,
    "editor.formatOnPaste": false,
    "editor.formatOnType": false,
    "editor.detectIndentation": false,
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  }
}
```

O identificador `asm-intel-x86-generic` é usado pela extensão `13xforever.language-x86-64-assembly` para syntax highlighting.

A arquitetura real do binário não vem desse identificador. Ela vem do comando:

```bash
nasm -f elf64
```

Ou seja:

- `asm-intel-x86-generic` define apenas o modo de linguagem no VS Code.
- `nasm -f elf64` define a geração de objeto Linux x86-64.
- `ld` gera o executável final.

## Partes Que Podem Precisar Mudar em Cada Projeto

### 1. Nome da task

Se mudar o nome da task em `tasks.json`:

```json
"label": "Build ASM atual"
```

também precisa mudar o `preLaunchTask` em `launch.json`:

```json
"preLaunchTask": "Build ASM atual"
```

Os dois nomes precisam ser iguais.

### 2. Caminho do executável gerado

A configuração atual espera que o executável fique em:

```json
"target": "${workspaceFolder}/build/${fileBasenameNoExtension}"
```

Isso depende da task gerar o binário no mesmo lugar:

```json
"command": "mkdir -p \"${workspaceFolder}/build\" && nasm -f elf64 -g -F dwarf \"${file}\" -o \"${workspaceFolder}/build/${fileBasenameNoExtension}.o\" && ld \"${workspaceFolder}/build/${fileBasenameNoExtension}.o\" -o \"${workspaceFolder}/build/${fileBasenameNoExtension}\""
```

Se o projeto gerar executáveis em outro diretório, os dois pontos precisam ser ajustados.

### 3. Tipo de Assembly

A task atual usa NASM com objeto ELF 64-bit:

```bash
nasm -f elf64
```

Isso é adequado para Linux x86-64.

Se o projeto usar outro formato, precisa mudar essa parte.

Exemplos:

```bash
nasm -f elf32
nasm -f bin
nasm -f win64
```

### 4. Linkedição

A task atual usa `ld` diretamente:

```bash
ld arquivo.o -o arquivo
```

Isso funciona para exemplos simples com `_start` e syscalls Linux.

Se o código usar `main`, libc ou integração com C, provavelmente será melhor linkar com `gcc`, por exemplo:

```bash
gcc arquivo.o -o arquivo
```

Nesse caso, a task precisa ser ajustada.

### 5. Projetos com múltiplos arquivos

A configuração atual foi feita para um arquivo `.asm` por exercício.

Ela funciona bem para casos como:

```text
hello.asm
stack.asm
print_rax.asm
```

Mas se o projeto tiver vários arquivos Assembly que precisam ser linkados juntos, por exemplo:

```text
main.asm
utils.asm
print.asm
```

a task atual não é suficiente.

Nesse caso, o ideal é criar um `Makefile` e mudar o `tasks.json` para chamar:

```bash
make
```

### 6. WSL/Linux

Essa configuração foi pensada para Ubuntu/WSL ou Linux.

Ela usa:

```bash
mkdir -p
nasm -f elf64
ld
gdb
```

Em Windows puro, sem WSL, essa configuração não deve funcionar sem adaptações.

## Fluxo de Trabalho

Para rodar/debugar um exercício:

1. Abra o arquivo `.asm` desejado.
2. Coloque um breakpoint, se quiser.
3. Aperte `F5`.
4. O VS Code executa a task `Build ASM atual`.
5. O executável é criado em `build/`.
6. O GDB inicia o debug pelo Native Debug.

Também é possível compilar manualmente:

```bash
mkdir -p build
nasm -f elf64 -g -F dwarf capitulo02/hello.asm -o build/hello.o
ld build/hello.o -o build/hello
./build/hello
```

## Exemplo de Código

```asm
global _start

section .data
message:     db 'hello, world!', 10
message_len: equ $ - message

section .text
_start:
    mov     rax, 1              ; syscall write
    mov     rdi, 1              ; stdout
    mov     rsi, message        ; endereço da mensagem
    mov     rdx, message_len    ; tamanho da mensagem
    syscall

    mov     rax, 60             ; syscall exit
    xor     rdi, rdi            ; código 0
    syscall
```

## `.gitignore` Recomendado

Como os binários e objetos são gerados em `build/`, esse diretório deve ser ignorado:

```gitignore
# Build gerado pelo VS Code/tasks
build/
out/
dist/

# Objetos e binários gerados por Assembly/C
*.o
*.obj
*.out
*.elf
*.bin
*.exe
*.dll
*.so
*.a
*.lib

# Executáveis comuns sem extensão
a.out
stack

# Arquivos auxiliares de assembler/linker/debug
*.lst
*.map
*.dump
*.dis
*.sym
*.dSYM/
*.debug

# Core dumps
core
core.*

# GDB
.gdb_history
.gdbinit.local

# Logs e temporários
*.log
*.tmp
*.temp
*.bak
*.swp
*.swo
*~

# Sistema operacional
.DS_Store
Thumbs.db
desktop.ini
```

A pasta `.vscode/` não precisa ser ignorada neste tipo de projeto, porque ela contém a configuração compartilhável de build e debug.

## Extensões de Arquivo Suportadas

| Extensão | Descrição |
|---|---|
| `.asm` | Arquivo Assembly, geralmente NASM ou YASM. |
| `.inc` | Include/header Assembly. |
| `.s` | Arquivo Assembly estilo GAS. |
| `.S` | Arquivo Assembly estilo GAS com pré-processador C. |
| `.bin` | Binário puro. |
| `.o` | Arquivo objeto. |
| `.elf` | Executável ou objeto no formato ELF. |
