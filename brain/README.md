# BrAIn

## 1. Figma

https://www.figma.com/design/aSipzYouIAbM2nRsv8vVU0/paginas-aidda

## 2. Mapeamento de Operações em Entidades

### Entidade Read Only (somente importação)

- PRODUTO (Taxonomia CT.xls)
- SETOR (Taxonomia CT.xls)
- CONTROLE_ALAVANCA (Checklist_Controle Alavancas)
- CHECKLIST_ALAVANCA (Checklist Alavancas)
- ESPECIALIZACAO
- PROJETO (Prime)
- CLIENTE
- CRM
- PROPOSTA 
- BRAIN 
- IMPACTO
- PESSOA 
- CARGO 
- CONTATO 
- HISTORICO_CARGO_PESSOA 
- IDIOMA 

### Entidade Read Write (somente edição)

- PESSOA_IDIOMA 
- ALOCACAO
- PESSOA_AUTOAVALIACAO_SETOR
- PESSOA_AUTOAVALIACAO_PRODUTO 
- FORMACAO_ACADEMICA 
- EXPERIENCIA_PROFISSIONAL
- CERTIFICACAO 
- PESSOA_CERTIFICACAO

### Entidade Merge (edição + importação)

>> Qual é a prioridade para prevalecer sem update?

## 2. Planilhas de importação 

>> Nota: Incorporar 1 ou + entidades por planilha

- PROJETO 
- CLIENTE
- SETOR
- CRM
- PROPOSTA 
- BRAIN 
- ALAVANCA 
- PESSOA 
- CONTATO 
- PRODUTO
- HISTORICO_CARGO_PESSOA 
- IDIOMA 
- CARGO 

## To Do

- Validação de atributos
- Mapeamento de Planilhas  
- Infra
- DDL 
- Rede de contato - analisar UI com dados de grafos
    - Empresas com Relacionamento - manual flag (cliente)
    - Entidades iguais com nomes diferentes
- DML Carga inicial
    - Produto padrão 1
    - Setor padrão 1
    - Cliente padrão 1
    - Projeto padrão 1

## Issues

- Historico de Cargo
- Integração: Linkedin - 
- Importação de CV (pdf Linkedin)
- Edição de CV (não desejável)
    - Adicionar entidades (clientes dinamicamente) - Grafos (pensar)
- Mapear clientes com as entidades profissionais vindo de historico
- Feature: [Extrair dados detalhados] Exportar planilha
- Especialistas: algoritmo classificação/inferencia por junior/pleno/sr/especialização a partir de regra
- Total de Pessoas: (somente especialistas por setor, produto)
- Total de Pessoas: (somente alocadas)
- Garantir que pessoas se avaliam especialistas no SETOR.
- Pessoas Alocadas -> são especista do setor
- Pessoas/Bio -> gerar por GenAI (Arttur/Caio)
- Nova alocação para cliente não existente - 
    - Selecionar cliente '_Temporário'
    - Abrir cadastro para cadastro de Projeto Descritivo
    - Selecionar o gestor
    - Input txt informar projeto (salvar na alocação)
    - Notificar o gestões por email
    Impacto: 
        - sem estatística
        - sem link entre Projeto Descricao x Projeto Real
- Notificar Líderes que existe "Projeto Temporário"
- Criar tela de conversão de "Projeto Temporário" para o "Projeto Específico"
- Data de Fim (Prevista) - 
- Nota autoatribuída - Setores/Produtos

Temas para quarta:
 
Histórico profissional e de cargos
Aidda: é uma integração. Quais as sugestões?
 
Empresas com relacionamento
Aidda: sugeriu que fosse controlado. Quais sugestões?
 
Jornada: primeiro login e caminho
 
Rede de contato
 
Cadastro de cliente
Aidda: controle de entidades pode ser dificil (exemplo anaconda)
 
Periodicidade de atualização das planilhas

