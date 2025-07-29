# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS


```sh
Data: 01/09/2025
Empresa: Abstergo Industries
Responsável: Evany Silvestre
```


## Introdução
Este relatório apresenta o processo de implementação de ferramentas na empresa Abstergo Industries realizado por Evany Silvestre. O objetivo do projeto foi elencar 3 serviços AWS, com a finalidade de realizar diminuição de custos imediatos.


## Descrição do Projeto
O projeto de implementação de ferramentas foi dividido em 3 etapas, cada uma com seus objetivos específicos. A seguir, serão descritas as etapas do projeto:


### Etapa 1:
**Amazon S3 (Simple Storage Service)** - Armazenamento de Dados Econômico e Escalável


#### Foco da Ferramenta
Permitir o armazenamento centralizado de documentos fiscais, históricos de pedidos, catálogos e backups automatizados, resultando em agilidade, segurança dos dados e menos preocupação com espaço.


#### Implementação - Caso de uso
- **Criação de Buckets**: Configurar buckets no S3 para organizar os diferentes tipos de arquivos (ex: `documentos-fiscais`, `backups-erp`).


- **Integrar Aplicações**: Utilizar SDKs AWS diretamente no código das aplicações (ERP, portal de pedidos) para que elas salvem e recuperem arquivos automaticamente no S3.


- **Configurar Acesso e Ciclo de Vida**: Definir permissões granulares com AWS IAM e criar políticas de ciclo de vida para mover dados pouco acessados para armazenamento mais barato (Glacier) ou excluí-los, para otimizar custos.




### Etapa 2:
**Amazon EC2 (Elastic Compute Cloud)** - Poder Computacional Flexível e Sob Demanda


#### Foco da Ferramenta
Sistemas de gestão (ERP/WMS), portal de pedidos e sistemas de roteirização funcionando com alto desempenho, mesmo em picos de demanda, pagando apenas pelo uso.


#### Implementação - Caso de uso
- **Lançar Instâncias**: Escolher a imagem do sistema operacional (AMI) e o tipo de instância EC2 (poder de processamento) adequados.


- **Configurar a Rede**: Criar uma VPC (Virtual Private Cloud) e Security Groups para isolar e proteger as instâncias, controlando quem pode acessá-las (ex: apenas equipe de TI ou o portal web).


- **Instalar e Configurar Softwares**: Após lançar a instância, conectar a ela (via SSH ou RDP) para instalar o ERP/WMS, servidores web e quaisquer outras aplicações da distribuidora, configurando-as para se comunicar com o banco de dados (RDS).


- **Monitorar**: Usar o Amazon CloudWatch para acompanhar o desempenho e identificar necessidades de escalonamento.


### Etapa 3:
**Amazon RDS (Relational Database Service)** - Gerenciamento de Banco de Dados Simplificado e Confiável


#### Foco da Ferramenta
Dados críticos (clientes, produtos, pedidos) sempre seguros, disponíveis e com alta performance, liberando a equipe de TI da gestão do banco de dados.


#### Implementação - Caso de uso
- **Criar a Instância DB**: Selecionar o motor de banco de dados (MySQL, PostgreSQL, SQL Server, etc.) que o ERP/WMS utiliza e o tipo de instância RDS.


- **Garantir a Segurança**: Colocar o RDS em uma subnet privada da nossa VPC, acessível apenas pelas nossas instâncias EC2, e configurar Security Groups para permitir essa comunicação.


- **Habilitar Alta Disponibilidade e Backups**: Ativar o Multi-AZ para ter uma réplica automática em outra região e configurar backups diários com período de retenção.


- **Migrar os Dados**: Transferir os dados do banco de dados atual para o RDS, seja via backup/restauração ou usando o AWS DMS (Database Migration Service) para migrações mais complexas.


- **Conectar as Aplicações**: Atualizar as configurações das suas aplicações (no EC2) para apontar para o endpoint do RDS.


## Conclusão
A implementação de ferramentas como **Amazon S3, Amazon EC2 e Amazon RDS** na empresa **Abstergo Industries** tem como esperado **redução significativa de custos** *- estima-se uma redução entre 20% e 50% nos custos de TI -* , **maior escalabilidade para suportar o crescimento das operações e das lojas clientes, alta disponibilidade dos sistemas e dados, e otimização da eficiência operacional**, o que aumentará a eficiência e a produtividade da empresa. Recomenda-se a continuidade da utilização das ferramentas implementadas e a busca por novas tecnologias que possam melhorar ainda mais os processos da empresa.


## Anexos


- [Documentação Amazon S3](https://docs.aws.amazon.com/s3/);
- [Documentação Amazon EC2](https://docs.aws.amazon.com/ec2/);
- [Documentação Amazon RDS](https://docs.aws.amazon.com/rds/);
- [Calculadora de Preços da AWS](https://calculator.aws/) - Para estimar custos;
- [AWS Free Tier](https://aws.amazon.com/pt/free/) - Para experimentar os serviços gratuitamente;



**Assinatura do Responsável pelo Projeto**:
Evany Silvestre de Lima

