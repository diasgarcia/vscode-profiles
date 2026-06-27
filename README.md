# VS Code Profiles by Stack

Perfis limpos e reutilizaveis do Visual Studio Code, organizados por stack e prontos para importacao como arquivos `.code-profile`.

Este projeto mantem a ideia de compartilhar configuracoes produtivas do VS Code, mas evita tratar o perfil como backup pessoal. Os perfis incluem apenas extensoes essenciais e settings pequenos, com `globalState` minimo e vazio para compatibilidade de importacao, sem historico, layout antigo, views fixadas ou estado visual desnecessario.

## Perfis Disponiveis

| Perfil | Arquivo | Quando usar |
| --- | --- | --- |
| Python | `profiles/python.code-profile` | Projetos Python modernos com lint e formatacao via Ruff. |
| Node.js | `profiles/node.code-profile` | Projetos Node.js com JavaScript/TypeScript, ESLint e Prettier. |
| Go | `profiles/go.code-profile` | Projetos Go com suporte oficial, gopls, debug, testes e formatacao padrao. |
| C | `profiles/c.code-profile` | Projetos C no WSL com WSL, C/C++, GCC, GDB e terminal Linux. |
| Assembly | `profiles/assembly.code-profile` | Desenvolvimento Assembly Intel 64 (x86-64) com NASM/YASM/GAS, debug nativo via GDB e editor hexadecimal. |
| Angular | `profiles/angular.code-profile` | Aplicacoes Angular com TypeScript, templates, ESLint e Prettier. |
| Java | `profiles/java.code-profile` | Projetos Java puros, com debug, testes e build tools comuns. |
| Spring Boot | `profiles/spring-boot.code-profile` | APIs e servicos Spring Boot com ferramentas Java e Spring. |
| Playwright / QA | `profiles/playwright-qa.code-profile` | Automacao de testes end-to-end com Playwright, JavaScript e TypeScript. |

Todos os perfis incluem como base:

- `icrawl.discord-vscode`
- `thang-nm.flow-icons`
- `mechatroner.rainbow-csv`

Os arquivos seguem o formato exportado pelo VS Code: `name`, `settings`, `extensions` e `globalState`. O campo `globalState` fica presente apenas por compatibilidade, com `storage` vazio.

## Como Importar

1. Abra o VS Code.
2. Acesse `File > Preferences > Profiles > Import Profile...`.
3. Selecione um arquivo `.code-profile` dentro de `profiles/`.
4. Revise o conteudo do perfil.
5. Clique em `Create` para importar.

Tambem e possivel abrir a Command Palette e executar `Profiles: Import Profile...`.

## Documentacao

Cada perfil tem uma pagina propria em `docs/` com:

- descricao do perfil;
- publico indicado;
- extensoes essenciais;
- extensoes opcionais;
- principais settings;
- ferramentas externas necessarias.

## Como Contribuir

Para adicionar ou atualizar um perfil:

1. Mantenha o arquivo principal em `profiles/<stack>.code-profile`.
2. Documente o perfil em `docs/<stack>.md`.
3. Separe extensoes essenciais de opcionais.
4. Prefira extensoes oficiais ou amplamente consolidadas.
5. Evite duplicar ferramentas com a mesma funcao.
6. Nao exporte estado de interface do seu VS Code pessoal; mantenha `globalState` vazio ou minimo.
7. Valide os IDs das extensoes no Marketplace antes de publicar.

## Nota Sobre Extensoes

Extensoes do VS Code mudam com o tempo: publishers podem renomear produtos, extensoes podem ser descontinuadas e novas ferramentas podem substituir fluxos antigos. Revise periodicamente os IDs, manutencao e relevancia de cada perfil.

Os IDs e UUIDs dos perfis atuais foram conferidos no Visual Studio Marketplace durante a revisao inicial do projeto.
