# Diagrama de Contexto

Diagrama de contexto c4 que apresenta uma visão geral do sistema, mostrando quem interage (usuário) e qual sistema externo está relacionado.

```mermaid
flowchart TD

    usuario["<b>Usuário do sistema</b><br>Leigos, clientes, desenvolvedores e estudantes de TI"]

    sistema["<b>Sistema de Inspeção de Requisitos</b><br>Permite submeter, inspecionar e consultar artefatos de Engenharia de Requisitos"]

    llm["<b>API externa de LLM</b><br>Serviço de LLM utilizado para realizar a inspeção dos artefatos"]

    usuario -->|"Submete artefatos e consulta resultados"| sistema
    sistema -->|"Envia artefatos e contexto; recebe resultado da inspeção"| llm