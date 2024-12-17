# BrAIn

## 1. Figma

https://www.figma.com/design/aSipzYouIAbM2nRsv8vVU0/paginas-aidda

## 2. Mapeamento de Operações em Entidades

### Entidade Read Only (somente importação)

### Entidade Read Write (somente edição)

### Entidade Merge (edição + importação)

## Riscos

- Homônimos
- Problemas de Match
    - Typo
    - Acentuação
- Fluxo de dados não controlado pelo processo
- Dados faltantes
- Planilhas sem saneamento
- Planilhas em padrão definido
- Onde está url para Sharepoint?
- Onde está a base de usuários? Tiago Nascimento
- Planilhas com linhas e colunas sobrando: pode gerar 
- Aidda: controle de entidades pode ser dificil (exemplo anaconda)

## To Do

---------------------------------------------------------
- DDL 
---------------------------------------------------------
- Validação de atributos
---------------------------------------------------------
- Mapeamento de Planilhas  
---------------------------------------------------------
- Tabelas de Histórico Profissional
---------------------------------------------------------
- Infra
---------------------------------------------------------    
- DML Carga inicial
    - Produto padrão 1
    - Setor padrão 1
    - Cliente padrão 1
    - Projeto padrão 1

---------------------------------------------------------
Use Case do ETL

- Upload dos dados de origem (aprox. 10 planilhas) 
- Ingestão com Pandas -> Cloud SQL
- Transformação -> MER
---------------------------------------------------------
Rede de Contatos
 
- Tem importação? Não
- Edição: sim
- UI: revisar
	- Pesquisar em lista de clientes
	- Adicionar cliente quando não encontrar
	- Atributos (nome, nome_contato, cargo)
Modelagem:	
	- CLIENTE }o--o{ PESSOA
	- CLIENTE_PESSOA 
CLIENTE 10 - Anaconda
PESSOA 1 - AC
 
CLIENTE_PESSOA(10, 1, nome_pessoa='Eduardo', cargo <livre> 'Diretor')

---------------------------------------------------------
Empresas não cadastradas
(Clientes não cadastrados)
 
- Tem importação? Não
- Edição: sim
- UI: revisar
	- Pesquisar em lista de clientes
	- Adicionar cliente quando não encontrar
	- Adicionar site
Modelagem
	CLIENTE (site)

---------------------------------------------------------
- Nova alocação para cliente não existente - 
    - Selecionar cliente '_Temporário'
    - Abrir cadastro para cadastro de Projeto Descritivo
    - Selecionar o gestor/líder
    - Input txt informar projeto (salvar na alocação)
    - Notificar o gestores por email   

---------------------------------------------------------
- Mapear importação de Pessoa no modelo de User (ver com Diego)

---------------------------------------------------------
- Importar dados de usuários adm
    - e-mail
---------------------------------------------------------
- UC  Projetos sem Oportunidades (Dados de Sistema)
    - Notificar time de usuários adm
    - Emitir relatório após a ingestão da carga histórica

---------------------------------------------------------
- Ingestão de dados
    - Match com caixa baixa
    - Salvar com Pascal Case
    - Regex para remover acentos

-------------------------------------------
- Match
    2_Biblioteca de propostas POVs e teses_final <> 2_Contribuição_propostas, pov e teses_intermediária
    (Título) % Não encontramos da Biblioteca para Contribuição
    Proposta: mudar o processo


## Issues

- Historico de Cargo
- Integração: Linkedin
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
- Notificar Líderes que existe "Projeto Temporário"
- Criar tela de conversão de "Projeto Temporário" para o "Projeto Específico"
- Data de Fim (Prevista) - 
- Nota autoatribuída - Setores/Produtos

