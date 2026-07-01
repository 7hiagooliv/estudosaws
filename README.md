# estudosaws
# ☁️ AWS Cloud Fundamentals & EC2 Management

Este repositório foi criado para consolidar os conhecimentos adquiridos durante os módulos de introdução à AWS e computação em nuvem. Ele serve como um guia prático de consulta sobre conceitos essenciais de infraestrutura, segurança, custos e o gerenciamento prático de instâncias EC2, volumes EBS e armazenamento S3.

## 1. Introdução à AWS e Conceitos Básicos

### O que é Computação em Nuvem?
É a entrega de recursos de TI sob demanda por meio da internet, com definição de preços de pagamento conforme o uso. Em vez de comprar e manter servidores físicos, o acesso a tecnologias como poder de computação, armazenamento e bancos de dados é feito conforme a necessidade.

### Estrutura Global e Segurança
* **Regiões:** Locais geográficos físicos ao redor do mundo onde a AWS agrupa seus data centers.
* **Zonas de Disponibilidade (AZs):** Locais isolados (data centers individuais) dentro de uma Região AWS para garantir alta disponibilidade e tolerância a falhas.
* **Segurança (IAM):** Princípio do menor privilégio. Configuração de MFA (Autenticação de Múltiplos Fatores) obrigatoriamente na conta Root e criação de usuários específicos para tarefas diárias.
* **Controle de Custos:** Uso de ferramentas como *AWS Budgets* e *Cost Explorer* logo nos primeiros passos para evitar surpresas no faturamento (Free Tier).


## 2. Prática com Computação na Nuvem (EC2)

O **Amazon EC2 (Elastic Compute Cloud)** fornece capacidade de computação escalável na nuvem AWS. 

### Ciclo de Vida e Estados da Instância
* **Pending (Pendente):** A instância está se preparando para iniciar.
* **Running (Executando):** A instância está ativa e funcional. Cobrança ativa.
* **Stopping / Stopped (Interrompendo/Interrompida):** A instância é desligada. Não há cobrança pelo poder de processamento, mas o armazenamento (EBS) continua sendo cobrado.
* **Terminated (Encerrada):** A instância é permanentemente excluída e seus recursos são liberados.

### Tipos de Instâncias (Famílias)
As instâncias são otimizadas para diferentes casos de uso:
* Uso Geral (General Purpose): Equilíbrio de computação, memória e rede (Ex: famílias `t2`, `t3`). Excelente para testes e pequenos servidores web.
* Otimizadas para Computação (Compute Optimized): Foco em processadores de alta performance (Família `C`).
* Otimizadas para Memória (Memory Optimized): Para grandes bancos de dados e processamento em tempo real (Família `R`).

---

## 3. Armazenamento na Nuvem (EBS vs S3)

Durante a prática, diferenciamos os dois principais tipos de armazenamento conectados ao ecossistema EC2:

| Característica | Amazon EBS (Elastic Block Store) | Amazon S3 (Simple Storage Service) |

| Tipo de Armazenamento | Armazenamento em Bloco (como um SSD/HD virtual). | Armazenamento de Objetos (arquivos, imagens, vídeos). |
| Uso Principal | Disco rígido principal para o sistema operacional da EC2. | Backup, data lakes, hospedagem de arquivos estáticos. |
| Persistência | Pode ser configurado para persistir ou ser deletado junto com a EC2. | Totalmente independente de instâncias de computação. |
| Acesso | Mutuamente exclusivo (geralmente preso a uma única instância). | Acessível via web (URLs) ou SDKs de qualquer lugar. |

---

## 4. Insights e Melhores Práticas

> Principais aprendizados do laboratório:
> 1. **Segurança em Primeiro Lugar:** Nunca exponha portas desnecessárias nos *Security Groups*. Se o acesso é via SSH (porta 22), restrinja o IP de origem em vez de permitir `0.0.0.0/0`.
> 2. **Automação de Custos:** Configurar alertas de custo logo no primeiro dia evita gastos indesejados caso uma instância EC2 seja esquecida no estado *Running*.
> 3. **Otimização de Recursos:** Escolher o tamanho correto da instância (*Right-sizing*) baseado na carga de trabalho real economiza recursos consideráveis da empresa.
