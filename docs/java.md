# Java

Perfil para desenvolvimento Java puro no VS Code, com suporte a linguagem, debug, testes, Maven, Gradle e gerenciamento de projetos via Java Extension Pack.

Este perfil inclui a base compartilhada do [settings.json](../settings.json): tema nativo Dark 2026, icones Flow Deep, cursor fino, barras de rolagem discretas, painel lateral a direita e Tab manual com quatro espacos. Veja o [README](../README.md#base-compartilhada-settingsjson) para os demais ajustes comuns.

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
- `ms-azuretools.vscode-containers` - Container Tools: gerencia containers, imagens, logs e servicos Docker Compose.
- `vscjava.vscode-java-pack` - pacote oficial/consolidado com suporte a Java, debug, testes e build tools.
- `vscjava.vscode-java-dependency` - Project Manager for Java.
- `redhat.java` - linguagem Java, IntelliSense e navegacao; formatacao habilitada durante a edicao e desativada ao salvar.
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
  "editor.autoIndent": "full",
  "editor.detectIndentation": false,
  "editor.autoIndentOnPaste": false,
  "editor.formatOnSave": false,
  "editor.formatOnPaste": false,
  "editor.formatOnType": true,
  "editor.codeActionsOnSave": {
    "source.fixAll": "never",
    "source.organizeImports": "never"
  },
  "java.configuration.updateBuildConfiguration": "interactive",
  "java.compile.nullAnalysis.mode": "automatic",
  "java.saveActions.organizeImports": false,
  "java.format.enabled": true,
  "java.format.onType.enabled": true
}
```

O perfil habilita a indentacao automatica e a formatacao ao digitar, quando a linguagem oferece esse suporte. Enter dentro de blocos usa a indentacao da linguagem. A formatacao ao salvar e colar e as acoes de correcao/organizacao de imports ao salvar continuam desativadas; Ctrl+S nao executa o formatador.

## Ferramentas Externas

- JDK instalado.
- Maven e/ou Gradle conforme o projeto.
- Configuracoes de teste no projeto, como JUnit ou TestNG, quando aplicavel.
