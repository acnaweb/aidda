erDiagram

    CAPTURA_PROJETO {
    }

    SETOR {
        int codigo
        string nivel_1 "Taxonomia CT.xls[Setores]N1"
        string nivel_2 "Taxonomia CT.xls[Setores]N2"
        string nivel_3 "Taxonomia CT.xls[Setores]N3"
        string nivel_4 "Taxonomia CT.xls[Setores]N4"
    }

    PRODUTO {
        int codigo
        string especializacao "Taxonomia CT.xls[Produtos]N1"
        string pilar "Taxonomia CT.xls[Produtos]N2"
        string produto "Taxonomia CT.xls[Produtos]N3"
    }
    
    PROJETO {
        int codigo
        string nome_projeto
        int codigo_cliente
        int codigo_produto
        int codigo_checklist_alavanca
        boolean is_case "Define se o projeto é case"
    }

    DOCUMENTO {
        int codigo
        string nome
        string url "Sharepoint"
        enum tipo "CASE|PROPOSTA|POV|TESE|DOCUMENTO_PROJETO"
    }
    
    ESPECIALIZACAO {
        int codigo
        string nome "Especializacao na A&M"
    }
    FRENTE {
        int codigo
        string nome "Frente na A&M"
    }

    IMPACTO {
        int codigo
        string nome
    }

    ALAVANCA {
        int codigo
        string nome 
    }

    CARGO {
        int codigo
        string nome
    }

    IDIOMA {
        int codigo
        string nome
    }

    CONTROLE_ALAVANCA {
        int codigo
        int codigo_alavanca
        int codigo_especializacao
        int codigo_frente        
    }

    CHECKLIST_ALAVANCA {
        int int
        int codigo_projeto
        int codigo_impacto 
        int codigo_alavanca
        int codigo_frente
        int codigo_impacto
        enum implementado
        enum recorrente
        enum base
        string iniciativa "Descrição"       
    }

    CHECKLIST_ALAVANCA }o--|| IMPACTO: possui
    CHECKLIST_ALAVANCA }o--|| FRENTE: possui
    CHECKLIST_ALAVANCA }o--|| ALAVANCA: possui
    CONTROLE_ALAVANCA }o--|| ESPECIALIZACAO: possui
    CONTROLE_ALAVANCA }o--|| FRENTE: possui
    CONTROLE_ALAVANCA }o--|| ALAVANCA: possui

    PROPOSTA {
        int codigo
    }
    
    CLIENTE {
        int codigo PK
        int codigo_setor FK
        string pov "<<Dúvida>> Onde mapear?"
        string tese "<<Dúvida>> Onde mapear?"
    }

    PESSOA {
        int codigo PK
        string nome
        string email UK
        string historico_pessoal
        string autoavaliacao  
        int codigo_cargo 
        string url_linkedin 
        date data_entrada "Data de entrada na A&M"  
        boolean eh_habilitado_alocacao "<<Dúvida>>"
    }

    PESSOA_AUTOAVALIACAO_SETOR {
        int codigo PK
        int codigo_pessoa FK
        int codigo_setor FK
        date data
        percentual nota
    }

    PESSOA_AUTOAVALIACAO_PRODUTO {
        int codigo PK
        int codigo_pessoa FK
        int codigo_produto FK
        date data
        percentual nota
    }

    FORMACAO_ACADEMICA {
        int codigo PK
        string instituicao
        string curso
        date data_inicio
        date data_fim
    }

    EXPERIENCIA_PROFISSIONAL {
        int codigo PK
        string empresa
        int codigo_cargo
        date data_inicio
        date data_fim
        string descricao
    }


    CONTATO {
        int codigo PK
        string nome
        string cargo
        string empresa
    }

    ALOCACAO {        
        int codigo
        int codigo_pessoa
        int codigo_projeto
        date data_inicio
        date data_fim
    }

    PESSOA_IDIOMA {
        int codigo_pessoa
        int codigo_idioma
        dominio nivel "Básico/Intermediario/Fluente"
    }

    CERTIFICACAO {
        int codigo
        string nome
    }

    PESSOA_CERTIFICACAO {
        int codigo_pessoa
        int codigo_certificacao
        date data_obtencao
        date data_validade
    }

    HISTORICO_CARGO_PESSOA {
        date data_movimentacao
        int codigo_cargo
        int codigo_pessoa
    }

    CRM {
        int codigo
        string oportunidade
        int codigo_cliente FK
        dominio stage(status)
        string currency
        monetary fee
        int codigo_pessoa_originador_1 FK "<<Dúvida>> Criar automaticamente em Pessoa?"
        int codigo_pessoa_originador_2 FK "<<Dúvida>> Criar automaticamente em Pessoa?"
        int codigo_produto "Offering Name"
    }

    PROJETO }o--|{ PRODUTO: possui
    CLIENTE ||--o{ PROJETO : possui 
    PROJETO ||--o{ DOCUMENTO: possui
    SETOR ||--o{ DOCUMENTO: possui
    CLIENTE ||--o{ DOCUMENTO: possui
    PRODUTO }|--o{ DOCUMENTO: possui
    BRAIN |o--o{ PROJETO: possui 
    SETOR ||--o{ CLIENTE : pertence 
    BRAIN |o--o{ ALAVANCA: possui 
    PROPOSTA }|--o| PROJETO: possui
    ALOCACAO }o--|| PESSOA: possui
    ALOCACAO }o--|| PROJETO: possui
    CARGO }|--o| PESSOA: possui
    HISTORICO_CARGO_PESSOA }|--|| PESSOA: possui
    HISTORICO_CARGO_PESSOA }|--|| CARGO: possui
    PESSOA ||--o{ CONTATO: possui
    CRM ||--o{ CLIENTE: possui
    CRM ||--o{ PRODUTO: possui
    PESSOA ||--o{ FORMACAO_ACADEMICA: cursa
    PESSOA ||--o{ EXPERIENCIA_PROFISSIONAL: trabalha
    PESSOA_IDIOMA }|--|| PESSOA: fala
    PESSOA_IDIOMA }|--|| IDIOMA: eh_falado
    PESSOA_CERTIFICACAO }|--|| PESSOA: possui
    PESSOA_CERTIFICACAO }|--|| CERTIFICACAO: possui
    PESSOA_AUTOAVALIACAO_SETOR }|--|| PESSOA: possui
    PESSOA_AUTOAVALIACAO_SETOR }|--|| SETOR: possui
    PESSOA_AUTOAVALIACAO_PRODUTO }|--|| PESSOA: possui
    PESSOA_AUTOAVALIACAO_PRODUTO }|--|| PRODUTO: possui