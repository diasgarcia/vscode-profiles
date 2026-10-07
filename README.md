# VS Code Profiles by Stack

Perfis limpos e reutilizaveis do Visual Studio Code, organizados por stack e prontos para importacao como arquivos `.code-profile`.

Este projeto mantem a ideia de compartilhar configuracoes produtivas do VS Code, mas evita tratar o perfil como backup pessoal. Os perfis incluem extensoes essenciais, uma base comum de settings e ajustes por stack, com `globalState` minimo e vazio para compatibilidade de importacao, sem historico, layout antigo, views fixadas ou estado visual desnecessario.

## Perfis Disponiveis

| Perfil | Arquivo | Quando usar |
| --- | --- | --- |
| Python | `profiles/python.code-profile` | Projetos Python com autocomplete, type checking e debug. |
| Node.js | `profiles/node.code-profile` | Projetos Node.js com JavaScript/TypeScript e debug. |
| NestJS | `profiles/nest.code-profile` | APIs Node.js com NestJS, TypeScript e imports relativos. |
| Go | `profiles/go.code-profile` | Projetos Go com suporte oficial, gopls, debug e testes. |
| C | `profiles/c.code-profile` | Projetos C no WSL com WSL, C/C++, GCC, GDB e terminal Linux. |
| Assembly | `profiles/assembly.code-profile` | Desenvolvimento Assembly Intel 64 (x86-64) com NASM/YASM/GAS, debug nativo via GDB e editor hexadecimal. |
| Angular | `profiles/angular.code-profile` | Aplicacoes Angular com TypeScript e suporte a templates. |
| Java | `profiles/java.code-profile` | Projetos Java puros, com debug, testes e build tools comuns. |
| Spring Boot | `profiles/spring-boot.code-profile` | APIs e servicos Spring Boot com ferramentas Java e Spring. |
| Playwright / QA | `profiles/playwright-qa.code-profile` | Automacao de testes end-to-end com Playwright, JavaScript e TypeScript. |

Todos os perfis incluem como base:

- `icrawl.discord-vscode`
- `thang-nm.flow-icons`
- `mechatroner.rainbow-csv`
- `cweijan.vscode-office`
- `ms-vscode-remote.remote-wsl`
- `ms-vscode-remote.remote-containers`

Todos os perfis incluem as configuracoes do [settings.json](settings.json), com o mesmo visual e comportamento de edicao. As configuracoes especificas de cada stack sao adicionadas a essa base. Entre os ajustes compartilhados estao:

- `workbench.iconTheme: flow-deep`
- `workbench.colorTheme: Dark 2026`
- `workbench.startupEditor: none`
- `chat.disableAIFeatures: false` para manter o Chat com estrelinha visivel
- `chat.agent.enabled: false`
- `chat.titleBar.openInAgentsWindow.enabled: false`
- `chat.titleBar.signIn.enabled: false`
- `github.copilot.enable`: `{ "*": false }` para desativar sugestoes inline
- `github.copilot.nextEditSuggestions.enabled: false`
- `editor.fontSize: 16`
- `editor.tabSize: 4` em todos os perfis, incluindo Assembly e NestJS
- `editor.insertSpaces: true`
- `editor.cursorStyle: line` e `editor.cursorBlinking: blink`
- `editor.fontLigatures: true` e `editor.lineHeight: 1.2`
- `editor.linkedEditing: true`
- barras de rolagem automaticas com indicador de cinco pixels
- `window.zoomLevel: 0.3`
- barra lateral a direita, barra de atividades embaixo e barra de status oculta
- controles de layout visiveis e repositorios Git sempre disponiveis
- telemetria desativada
- `editor.matchBrackets: near`
- `files.encoding: utf8`
- `editor.autoIndent: none`
- `editor.detectIndentation: false`
- `editor.autoIndentOnPaste: false`
- `editor.formatOnSave: false`
- `editor.formatOnPaste: false`
- `editor.formatOnType: false`
- `editor.codeActionsOnSave`: `source.fixAll` e `source.organizeImports` como `never`
- `files.insertFinalNewline: true`
- `files.trimTrailingWhitespace: true`

Os perfis nao incluem Prettier, EditorConfig, ESLint ou Ruff. As extensoes de linguagem de C/C++, Go, Java e YAML continuam presentes para autocomplete, navegacao, diagnosticos e debug quando disponiveis, com a formatacao automatica desativada. Tab e espacos continuam funcionando para indentacao manual, com quatro espacos em todos os perfis. A limpeza de espacos no fim das linhas e a insercao de uma quebra de linha final continuam habilitadas.

Os arquivos seguem o formato exportado pelo VS Code: `name`, `settings`, `extensions` e `globalState`. O campo `globalState` fica presente apenas por compatibilidade, com `storage` vazio.

## Como Importar

1. Abra o VS Code.
2. Acesse `File > Preferences > Profiles`.
3. No menu de `New Profile`, escolha `Import Profile...` e selecione um arquivo `.code-profile` dentro de `profiles/`.
4. Revise o conteudo do perfil.
5. Clique em `Create` para importar.

Tambem e possivel abrir a Command Palette e executar `Profiles: Import Profile...`.

## Base Compartilhada (`settings.json`)

O [settings.json](settings.json) na raiz do repositorio e a referencia legivel das preferencias de interface, editor e terminal incorporadas nos dez arquivos `.code-profile`. Ao importar um perfil, essa base ja vem incluida. O arquivo tambem pode ser aplicado manualmente a um perfil existente. Estar na raiz do repositorio nao faz o VS Code aplica-lo automaticamente.

O arquivo configura:

- **Editor:** fonte de tamanho 16, ligaturas, altura de linha de 1.2, cursor fino e piscando, Tab manual com quatro espacos e minimapa oculto. Desativa a indentacao e a formatacao automaticas, oculta breadcrumbs e o destaque da linha atual. As barras de rolagem aparecem quando necessario, com o indicador de cinco pixels; `horizontalSliderSize` e `verticalSliderSize` sao opcoes internas e podem aparecer como desconhecidas no editor de settings.
- **Interface:** zoom de 0.3, barra lateral principal a direita, barra de atividades embaixo e barra de status oculta. Os botoes de layout continuam visiveis; o Command Center e os controles de navegacao ficam ocultos.
- **Git:** a secao `Repositories` fica sempre disponivel no painel de Source Control. O nome da branch nesse painel continua clicavel mesmo com a barra de status escondida.
- **Edicao e abas:** `editor.linkedEditing` sincroniza edicoes relacionadas, como tags HTML de abertura e fechamento; `workbench.editor.revealIfOpen` leva para a aba existente ao abrir um arquivo que ja esta aberto.
- **Terminal:** ligaturas e altura de linha de 1.2. As ligaturas do editor e do terminal dependem de uma fonte que as suporte.
- **Tema de cores:** seleciona o tema nativo `Dark 2026`, sem extensao adicional.
- **Icones:** seleciona o tema `Flow Deep` (`flow-deep`). A extensao `thang-nm.flow-icons` precisa estar instalada e habilitada no perfil ativo.
- **Chat e telemetria:** mantem o Chat com estrelinha e todos os controles de layout visiveis. Desativa o modo agente, as sugestoes inline e de proxima edicao do Copilot, o acesso a servidores MCP pelo chat e a telemetria do VS Code. Oculta os botoes `Open in Agents` e de login do Copilot na barra de titulo.
- **Zen Mode:** ao ativar esse modo, evita entrar em tela cheia e centralizar o layout. Essas opcoes nao ativam o Zen Mode automaticamente.

### Como Aplicar Manualmente a um Perfil Existente

1. Deixe ativo no VS Code o perfil que voce quer ajustar. Se voce acabou de importar um dos perfis deste repositorio, a base ja esta incluida; basta substituir a chave de licenca conforme o passo 5.
2. Pressione `Ctrl + Shift + P` e execute `Preferences: Open User Settings (JSON)`.
3. Guarde uma copia das configuracoes atuais para poder restaurar depois.
4. Copie as propriedades do `settings.json` deste repositorio para dentro do objeto existente. Atualize as propriedades repetidas e mantenha as configuracoes especificas da stack; o arquivo final deve ter apenas um objeto `{ ... }`.
5. O valor `FLOW-KEY` em `flow-icons.licenseKey` e um placeholder. Substitua-o pela sua chave apenas nas configuracoes locais do VS Code, sem colocar a chave real no arquivo versionado. A chave de licenca e a selecao do tema (`workbench.iconTheme`) sao configuracoes separadas.
6. Salve com `Ctrl + S`.

Para acessar a branch na lateral direita, execute `Source Control: Focus on Repositories View` pela Command Palette e clique no nome da branch no painel.

Os dez perfis ja incluem essas preferencias. Configuracoes do workspace e blocos de linguagem, como `[python]` ou `[go]`, podem ter prioridade sobre os ajustes gerais do editor.

O Chat fica visivel porque `chat.disableAIFeatures` esta como `false`; usar `true` oculta tambem esse botao. Para manter o Chat e ocultar Agents, deixe `chat.agent.enabled`, `chat.titleBar.openInAgentsWindow.enabled` e `chat.titleBar.signIn.enabled` como `false`. As sugestoes automaticas sao desativadas separadamente por `github.copilot.enable` e `github.copilot.nextEditSuggestions.enabled`. Se um perfil instalado mostrar um comportamento diferente, confira os User Settings do perfil e os ajustes do workspace, depois execute `Developer: Reload Window`. Veja a [referencia oficial das configuracoes de IA](https://code.visualstudio.com/docs/agents/reference/ai-settings).

O arquivo desativa a indentacao e a formatacao automaticas e as acoes de correcao/organizacao de imports ao salvar. Ele nao instala ou remove extensoes. Os `.code-profile` contem uma copia dessa base: alterar `settings.json` futuramente exige atualizar os perfis tambem, pois nao ha geracao automatica. Para usar os perfis revisados em uma instalacao existente, importe-os novamente; editar os arquivos deste repositorio nao desinstala extensoes do VS Code.

Para desfazer o teste, restaure a copia das configuracoes anteriores. Mais detalhes na documentacao oficial de [configuracoes do VS Code](https://code.visualstudio.com/docs/configure/settings) e [repositorios Git](https://code.visualstudio.com/docs/sourcecontrol/repos-remotes).

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
