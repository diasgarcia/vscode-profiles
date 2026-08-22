# Java

Perfil para desenvolvimento Java puro no VS Code, com suporte a linguagem, debug, testes, Maven, Gradle e gerenciamento de projetos via Java Extension Pack.

## Indicado Para

- Projetos Java sem Spring.
- Exercicios, bibliotecas, CLIs e aplicacoes Java tradicionais.
- Times que querem um perfil Java enxuto, sem ferramentas de backend web por padrao.

## Extensoes Essenciais

- `icrawl.discord-vscode` - Discord Presence.
- `thang-nm.flow-icons` - tema de icones.
- `mechatroner.rainbow-csv` - leitura de CSV/TSV.
- `cweijan.vscode-office` - visualizacao de documentos Office (Word, Excel e PDF) direto no editor.
- `ms-vscode-remote.remote-wsl` - abre projetos no ambiente Linux do WSL.
- `ms-vscode-remote.remote-containers` - abre projetos em dev containers com Docker.
- `tinkertrain.theme-panda` - tema de cores Panda Syntax.
- `vscjava.vscode-java-pack` - pacote oficial/consolidado com suporte a Java, debug, testes e build tools.
- `vscjava.vscode-java-dependency` - Project Manager for Java.
- `redhat.java` - linguagem Java, IntelliSense, navegacao e formatacao.
- `vscjava.vscode-java-debug` - debug de aplicacoes Java.
- `vscjava.vscode-java-test` - execucao e exploracao de testes.
- `vscjava.vscode-maven` - suporte a projetos Maven.
- `vscjava.vscode-gradle` - suporte a projetos Gradle.

Algumas dessas extensoes tambem fazem parte do Java Extension Pack, mas ficam listadas explicitamente para o preview do perfil mostrar claramente o suporte a linguagem, debug, testes e build.

## Extensoes Opcionais

- `SonarSource.sonarlint-vscode` - SonarQube for IDE, antigo SonarLint, para analise de qualidade e seguranca no editor.
- `redhat.vscode-yaml` - util quando o projeto Java usa muitos arquivos YAML.

## Principais Settings

```json
{
  "java.configuration.updateBuildConfiguration": "interactive",
  "java.compile.nullAnalysis.mode": "automatic",
  "java.saveActions.organizeImports": true,
  "[java]": {
    "editor.defaultFormatter": "redhat.java"
  }
}
```

## Ferramentas Externas

- JDK instalado.
- Maven e/ou Gradle conforme o projeto.
- Configuracoes de teste no projeto, como JUnit ou TestNG, quando aplicavel.
