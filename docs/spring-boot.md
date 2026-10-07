# Spring Boot

Perfil para desenvolvimento de APIs e servicos Spring Boot no VS Code, combinando a base Java com ferramentas especificas de Spring.

Este perfil inclui a base compartilhada do [settings.json](../settings.json): tema nativo Dark 2026, icones Flow Deep, cursor fino, barras de rolagem discretas, painel lateral a direita e Tab manual com quatro espacos. Veja o [README](../README.md#base-compartilhada-settingsjson) para os demais ajustes comuns.

## Indicado Para

- APIs REST em Spring Boot.
- Microservicos Java.
- Projetos com `application.yml`, `application.properties`, Maven ou Gradle.

## Extensoes Essenciais

- `icrawl.discord-vscode` - Discord Presence.
- `thang-nm.flow-icons` - tema de icones.
- `mechatroner.rainbow-csv` - leitura de CSV/TSV.
- `cweijan.vscode-office` - visualizacao de documentos Office (Word, Excel e PDF) direto no editor.
- `ms-vscode-remote.remote-wsl` - abre projetos no ambiente Linux do WSL.
- `ms-vscode-remote.remote-containers` - abre projetos em dev containers com Docker.
- `ms-azuretools.vscode-containers` - Container Tools: gerencia containers, imagens, logs e servicos Docker Compose.
- `vscjava.vscode-java-pack` - base Java.
- `vscjava.vscode-java-dependency` - Project Manager for Java.
- `redhat.java` - linguagem Java, IntelliSense e navegacao; formatacao desativada neste perfil.
- `vscjava.vscode-java-debug` - debug de aplicacoes Java.
- `vscjava.vscode-java-test` - execucao e exploracao de testes.
- `vscjava.vscode-maven` - suporte a projetos Maven.
- `vscjava.vscode-gradle` - suporte a projetos Gradle.
- `vmware.vscode-boot-dev-pack` - Spring Boot Tools, Spring Initializr e Spring Boot Dashboard.
- `vscjava.vscode-spring-boot-dashboard` - painel para acompanhar aplicacoes Spring Boot em execucao, instalado explicitamente alem do pack.
- `vscjava.vscode-spring-initializr` - gera projetos Spring Boot pelo Spring Initializr direto no VS Code, instalado explicitamente alem do pack.
- `redhat.vscode-yaml` - suporte a YAML, comum em configuracoes Spring.

As extensoes Java aparecem explicitamente mesmo quando tambem sao cobertas pelo Java Extension Pack, para deixar o conteudo do perfil claro no preview de importacao.

## Extensoes Opcionais

- `humao.rest-client` - bom para versionar requests em arquivos `.http`.
- `rangav.vscode-thunder-client` - alternativa com UI para testar APIs sem sair do VS Code.
- `SonarSource.sonarlint-vscode` - SonarQube for IDE, antigo SonarLint, para analise de qualidade e seguranca.
- `vscjava.vscode-lombok` - acoes auxiliares para projetos que usam Lombok.

Para APIs, a recomendacao padrao e documentar requests com `humao.rest-client` quando o time quer arquivos `.http` versionados. `rangav.vscode-thunder-client` faz mais sentido quando a equipe prefere uma interface visual.

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
  "java.configuration.updateBuildConfiguration": "interactive",
  "java.compile.nullAnalysis.mode": "automatic",
  "java.saveActions.organizeImports": false,
  "spring-boot.ls.problem.application-properties.enabled": true,
  "yaml.format.enable": false,
  "java.format.enabled": false,
  "java.format.onType.enabled": false
}
```

O perfil desativa a indentacao automatica, a formatacao ao salvar, colar ou digitar e as acoes de correcao/organizacao de imports ao salvar. Tab e espacos continuam disponiveis para indentacao manual.

## Ferramentas Externas

- JDK instalado.
- Maven ou Gradle conforme o projeto.
- Spring Boot definido no projeto.
- Docker ou ferramenta equivalente apenas se o projeto usar containers.
