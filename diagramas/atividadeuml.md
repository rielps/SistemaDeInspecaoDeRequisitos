### Diagrama de Atividade

O Diagrama de atividade uml apresentas fluxo de atividades realizadas durante um processo, nesse caso, optamos por mostrar o fluxo da inspeção do artefato que vai para análise (principal fluxo do sistema).

```mermaid
flowchart TD

    inicio((Início))

    login["Usuário realiza login"]
    acessar["Acessa o sistema"]
    enviar["Submete o artefato<br>(HU ou CDU ou Diagrama)"]
    validar{"Artefato válido?"}

    corrigir["Usuário corrige<br>as informações"]

    preparar["Sistema prepara o artefato<br>e o contexto para análise (transformação em md e montagem de prompt)"]
    rag["Sistema recupera informações<br>relevantes da base de conhecimento (RAG)"]
    llm["Sistema envia os dados<br>para a API da LLM (o input)"]
    analisar["LLM realiza a inspeção<br>do artefato"]
    processar["Sistema processa<br>o resultado da análise com as correções"]
    exibir["Sistema apresenta<br>os resultados da análse ao usuário"]

    consultar["Usuário consulta<br>os resultados"]

    fim((Fim))

    inicio --> login
    login --> acessar
    acessar --> enviar
    enviar --> validar

    validar -- "Não" --> corrigir
    corrigir --> enviar

    validar -- "Sim" --> preparar
    preparar --> rag
    rag --> llm
    llm --> analisar
    analisar --> processar
    processar --> exibir
    exibir --> consultar
    consultar --> fim