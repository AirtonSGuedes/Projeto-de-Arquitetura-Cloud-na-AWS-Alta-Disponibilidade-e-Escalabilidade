# Projeto-de-Arquitetura-Cloud-na-AWS-Alta-Disponibilidade-e-Escalabilidade
Projeto prático de arquitetura web escalável na AWS, utilizando VPC customizada, subnets públicas em múltiplas AZs, EC2, Application Load Balancer, Auto Scaling e CloudWatch. O foco foi alta disponibilidade, escalabilidade e monitoramento, com recursos criados via AWS Console.
# Arquitetura Web Escalável na AWS

## 📌 Visão Geral
Este projeto demonstra a criação de uma arquitetura web escalável e altamente disponível na AWS, utilizando serviços essenciais como VPC, EC2, Application Load Balancer (ALB), Auto Scaling e CloudWatch.

Todos os recursos foram criados manualmente através do AWS Management Console, com foco no entendimento dos fundamentos de computação em nuvem.

---

## 🏗️ Serviços Utilizados
- Amazon VPC (customizada)
- Subnets públicas em múltiplas Availability Zones
- Internet Gateway
- Tabelas de Rotas
- Security Groups
- Amazon EC2
- Application Load Balancer (ALB)
- Target Group
- Auto Scaling Group
- Amazon CloudWatch

---

## 🌐 Rede e VPC

### Criação da VPC
Foi criada uma VPC customizada utilizando o bloco CIDR `10.0.0.0/16`.

![Criação da VPC](screenshots/vpc-create.png)
![Detalhes da VPC](screenshots/vpc-details.png)
 
### Subnets
Foram criadas duas subnets públicas em diferentes zonas de disponibilidade, garantindo alta disponibilidade.

![Subnets](screenshots/subnets.png)

### Internet Gateway e Roteamento
Um Internet Gateway foi associado à VPC e uma tabela de rotas foi configurada com a rota `0.0.0.0/0` apontando para o gateway.

![Internet Gateway](screenshots/internet-gateway.png)
![Tabela de Rotas](screenshots/route-table.png)

---

## 🔐 Segurança
Foi criado um Security Group permitindo:
- Acesso HTTP (porta 80) a partir de qualquer origem
- Acesso SSH (porta 22) restrito a um IP específico

![Security Group](screenshots/security-group.png)

---

## 🖥️ Computação (EC2)
Uma instância EC2 foi criada utilizando Amazon Linux 2023 e o tipo de instância `t3.micro`.

![Criação da EC2](screenshots/ec2-launch.png)
![Instância em execução](screenshots/ec2-running.png)

---

## ⚖️ Balanceamento de Carga
Foi criado um Application Load Balancer (internet-facing) para distribuir o tráfego entre as instâncias.

![Lista de Load Balancers](screenshots/load-balancer-list.png)
![Detalhes do Load Balancer](screenshots/load-balancer-details.png)

---

## 🎯 Grupo de Destino
A instância EC2 foi registrada em um Target Group com verificações de integridade configuradas.

![Target Group](screenshots/target-group.png)

---

## 📈 Auto Scaling
Foi configurado um Auto Scaling Group com:
- Capacidade mínima: 1
- Capacidade máxima: 3
- Distribuição em múltiplas Availability Zones

![Auto Scaling Group](screenshots/auto-scaling-group.png)
![Detalhes do Auto Scaling](screenshots/auto-scaling-details.png)

---

## 📊 Monitoramento
Foi criado um alarme no CloudWatch para monitorar a utilização de CPU acima de 70%.

![Lista de Alarmes](screenshots/cloudwatch-alarm-list.png)
![Detalhes do Alarme](screenshots/cloudwatch-alarm-details.png)

---

## 🎯 Aprendizados
- Fundamentos de rede na AWS (VPC, Subnets e Roteamento)
- Alta disponibilidade utilizando múltiplas AZs
- Balanceamento de carga com ALB
- Escalabilidade automática com Auto Scaling
- Monitoramento e alertas com CloudWatch

---

## 🚀 Próximos Passos
- Implementar HTTPS com AWS Certificate Manager (ACM)
- Criar subnets privadas com NAT Gateway
- Automatizar a infraestrutura com Terraform ou CloudFormation

---

## 👤 Autor
**Airton da Silva Guedes**  
Estudante de Cloud Computing e Análise de Dados  
