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
- `13xforever.language-x86-64-assembly` – syntax highlighting, snippets e suporte à linguagem Assembly Intel x86-64 (NASM, YASM, GAS). Reconhece extensões `.asm`, `.inc`, `.S`, `.s`.
- `webfreak.debug` – debug visual com GDB/LLDB diretamente no VS Code. Permite breakpoints, watch de registradores e memória, e step-through do código assembly.
- `ms-vscode.hexeditor` – editor hexadecimal oficial da Microsoft para inspeção e edição de arquivos binários direto no VS Code.

## Extensões Opcionais

- `austin.code-gnu-global` – IntelliSense e navegação via GNU Global tags; útil se o projeto gerar tags para labels e símbolos.
- `ms-vscode.cpptools` – suporte oficial C/C++; pode ser útil se o projeto misturar código C com assembly inline.
- `yzhang.markdown-all-in-one` – útil para documentar notas de estudo, análise ou write-ups diretamente no repositório.

## Principais Settings

```json
{
  "files.associations": {
    "*.inc": "asm-intel-x64",
    "*.S": "asm-intel-x64",
    "*.s": "asm-intel-x64"
  },
  "terminal.integrated.defaultProfile.linux": "bash",
  "[asm-intel-x64]": {
    "editor.tabSize": 8,
    "editor.insertSpaces": false
  }
}
```

As associações de arquivo garantem que as extensões `.inc`, `.S` e `.s` sejam reconhecidas como Assembly Intel 64. A formatação com tabs (tamanho 8) segue a convenção clássica de escrita Assembly.

## Ferramentas Externas

- **NASM** (Netwide Assembler) – assembler recomendado para sintaxe Intel.
  ```bash
  sudo apt install nasm        # Ubuntu/Debian
  sudo dnf install nasm        # Fedora
  ```
- **YASM** – alternativa moderna ao NASM.
- **GNU Assembler (gas)** – assembler nativo do GNU Binutils, usa sintaxe AT&T por padrão mas aceita Intel com `.intel_syntax noprefix`.
- **GDB** (GNU Debugger) – debug do código assembly, visualização de registradores e memória.
  ```bash
  sudo apt install gdb          # Ubuntu/Debian
  sudo dnf install gdb          # Fedora
  ```
- **LD** (GNU Linker) ou **gold** – linkagem de objetos compilados.

### Fluxo de Trabalho Típico

```bash
# Montar (NASM)
nasm -f elf64 -o hello.o hello.asm

# Linkar
ld -o hello hello.o

# Executar
./hello

# Depurar com GDB
gdb ./hello
```

Ou, via GAS (GNU Assembler) com sintaxe Intel:

```bash
as --64 -o hello.o hello.s
ld -o hello hello.o
```

Para usar sintaxe Intel no GAS, inclua `.intel_syntax noprefix` no início do arquivo `.s`.

## Extensões de Arquivo Suportadas

| Extensão | Descrição |
|---|---|
| `.asm` | Arquivo Assembly (geralmente NASM ou YASM). |
| `.inc` | Include/header Assembly. |
| `.s` | Arquivo Assembly estilo GAS (GNU Assembler). |
| `.S` | Arquivo Assembly estilo GAS com pré-processador C. |
| `.bin` / `.o` / `.elf` | Binários inspecionáveis com Hex Editor. |
