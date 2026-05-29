# Spring Boot

Perfil para desenvolvimento de APIs e servicos Spring Boot no VS Code, combinando a base Java com ferramentas especificas de Spring.

## Indicado Para

- APIs REST em Spring Boot.
- Microservicos Java.
- Projetos com `application.yml`, `application.properties`, Maven ou Gradle.

## Extensoes Essenciais

- `icrawl.discord-vscode` - Discord Presence.
- `thang-nm.flow-icons` - tema de icones.
- `mechatroner.rainbow-csv` - leitura de CSV/TSV.
- `vscjava.vscode-java-pack` - base Java.
- `vscjava.vscode-java-dependency` - Project Manager for Java.
- `redhat.java` - linguagem Java, IntelliSense, navegacao e formatacao.
- `vscjava.vscode-java-debug` - debug de aplicacoes Java.
- `vscjava.vscode-java-test` - execucao e exploracao de testes.
- `vscjava.vscode-maven` - suporte a projetos Maven.
- `vscjava.vscode-gradle` - suporte a projetos Gradle.
- `vmware.vscode-boot-dev-pack` - Spring Boot Tools, Spring Initializr e Spring Boot Dashboard.
- `redhat.vscode-yaml` - suporte a YAML, comum em configuracoes Spring.

As extensoes Java aparecem explicitamente mesmo quando tambem sao cobertas pelo Java Extension Pack, para deixar o conteudo do perfil claro no preview de importacao.

## Extensoes Opcionais

- `humao.rest-client` - bom para versionar requests em arquivos `.http`.
- `rangav.vscode-thunder-client` - alternativa com UI para testar APIs sem sair do VS Code.
- `ms-azuretools.vscode-containers` - suporte a containers quando o projeto usa Docker/Compose.
- `SonarSource.sonarlint-vscode` - SonarQube for IDE, antigo SonarLint, para analise de qualidade e seguranca.
- `vscjava.vscode-lombok` - acoes auxiliares para projetos que usam Lombok.

Para APIs, a recomendacao padrao e documentar requests com `humao.rest-client` quando o time quer arquivos `.http` versionados. `rangav.vscode-thunder-client` faz mais sentido quando a equipe prefere uma interface visual.

## Principais Settings

```json
{
  "java.configuration.updateBuildConfiguration": "interactive",
  "java.compile.nullAnalysis.mode": "automatic",
  "java.saveActions.organizeImports": true,
  "spring-boot.ls.problem.application-properties.enabled": true,
  "yaml.format.enable": true,
  "[java]": {
    "editor.defaultFormatter": "redhat.java"
  },
  "[yaml]": {
    "editor.defaultFormatter": "redhat.vscode-yaml"
  }
}
```

## Ferramentas Externas

- JDK instalado.
- Maven ou Gradle conforme o projeto.
- Spring Boot definido no projeto.
- Docker ou ferramenta equivalente apenas se o projeto usar containers.
