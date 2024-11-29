erDiagram
    
    PROJETO {
        string codigo
        string nome_projeto
        int codigo_cliente
        int codigo_produto
        boolean is_case "Define se o projeto é case"

    }
    
    BRAIN {
        int codigo
        int codigo_projeto "Case de projeto encerrado"
        int codigo_alavanca
        string impacto "Descrição do impacto do resultado no cliente"
        string resultado "<<Confirmar>> Resultado do projeto "
    }

    ALAVANCA {
        int codigo
        string descricao
    }

    PROPOSTA {
        int codigo
    }
    
    CLIENTE {
        int codigo
        int codigo_setor 
        string pov "<<Dúvida>> Onde mapear?"
        string tese "<<Dúvida>> Onde mapear?"
    }

    SETOR {
        int codigo
        string nome_setor
    }

    PRODUTO {
        int codigo
        string nome_produto
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

    CARGO {
        int codigo
        string nome_cargo
    }

    IDIOMA {
        int codigo
        string idioma
    }

    PESSOA_IDIOMA {
        int codigo_pessoa
        int codigo_idioma
        dominio nivel "Básico/Intermediario/Fluente"
    }

    CERTIFICACAO {
        int codigo
        string certificacao
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

    CLIENTE ||--o{ PROJETO : possui 
    SETOR ||--o{ CLIENTE : pertence 
    PROJETO ||--|| PRODUTO: possui
    BRAIN |o--o{ PROJETO: possui 
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