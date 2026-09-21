# Diagrama de Casos de Uso

Diagrama de casos de uso que apresenta as principais funcionalidades do Sistema de Inspeção de Requisitos, os atores que interagem com o sistema e as relações entre os casos de uso.

```mermaid
flowchart LR
    U["👤 Usuário"]
    LLM["👤 Serviço de LLM"]

    subgraph SYS["Sistema de Inspeção de Requisitos"]
        direction TB

        subgraph CONTA["Conta e acesso"]
            direction TB
            CAD([Cadastrar-se])
            AUT([Autenticar-se])
            PERF([Gerenciar perfil])
            SAIR([Encerrar sessão])
        end

        subgraph ART["Gerenciamento de artefatos"]
            direction TB
            GER([Gerenciar artefatos])
            VISART([Visualizar artefato])
            CADART([Cadastrar artefato])
            EDITART([Editar artefato])
            EXCART([Excluir artefato])
            ASSOC([Associar diagrama])

            VISART -. generalização .-> GER
            CADART -. generalização .-> GER
            EDITART -. generalização .-> GER
            EXCART -. generalização .-> GER
            ASSOC -. generalização .-> GER
        end

        subgraph INSP["Inspeção"]
            direction TB
            SOL([Solicitar inspeção])
            REL([Inspecionar artefatos relacionados])
            PREP([Preparar contexto])
            RAG([Recuperar informações via RAG])
            ENV([Enviar artefatos para LLM])
            REC([Receber resultado da LLM])

            REL -. "«extend»" .-> SOL
            SOL -. "«include»" .-> PREP
            PREP -. "«include»" .-> RAG
            SOL -. "«include»" .-> ENV
            SOL -. "«include»" .-> REC
        end

        subgraph RES["Resultados e histórico"]
            direction TB
            GERDOC([Gerar documento da inspeção])
            VISRES([Visualizar resultado da inspeção])
            HIST([Consultar histórico de inspeções])
            VISANT([Visualizar inspeção anterior])
            EXCHIST([Excluir inspeção do histórico])

            GERDOC -. "«extend»" .-> VISRES
            VISANT -. "«extend»" .-> HIST
            EXCHIST -. "«extend»" .-> HIST
        end
    end

    U --- CAD
    U --- AUT
    U --- PERF
    U --- GER
    U --- SOL
    U --- GERDOC
    U --- VISRES
    U --- HIST
    U --- SAIR

    ENV --- LLM
    REC --- LLM