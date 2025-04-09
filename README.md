# Desafio-Arquitetura-de-Solucoes-em-Infraestrutura-Verx

### 🔹  Dimensionamento de Recursos (CPU, Memória, Escalabilidade)
O dimensionamento de recursos depende das necessidades específicas do sistema legado e dos requisitos de carga. Antes de migrar, é essencial analisar o uso atual de recursos no sistema legado (CPU, memória, armazenamento). Isso pode ser feito através de ferramentas de monitoramento como **Zabbix** ou **PRTG** para identificar picos de carga e padrões de uso. Com isso utilizando as instâncias **EC2** da **AWS** para suportar as cargars de trabalhos, configurado juntamente com o **Auto Scaling** para prover novas instâncias automaticamente, caso a carga de trabalho solicite maiores recursos, baseado nos parâmetros configurados.Se o sistema for adaptado para contêineres, podemos utilizar **Kubernetes** para orquestrar a escalabilidade, com recursos ajustáveis conforme a demanda.

Passando para a metodologia de **FinOps** afim de Otimizar de Custos podemos usar as Instâncias sob Demanda e Reservadas sendo elas as instâncias sob demanda para cargas variáveis, e as instâncias reservadas para cargas previsíveis, garantindo um equilíbrio entre flexibilidade e cust, monitorando os recursos, desligando automaticamente os recursos que estão ociosos na estrutura. Além das instâncias, podemos otimizar a utilização dos níveis de armazenamento, escolhendo o melhor nível de armazenamento afim de reduzir custos.

É Sempre bom utilizar as ferramentas de monitormento de custos, para avaliar os custos em tempo real e ajustar a Infraestrutura para a melhor utilização com o melhor custo.

---

#  Diagrama da Topologia da Solução
<img width="773" alt="Desenho1" src="https://github.com/user-attachments/assets/e1a84ea0-32c2-4946-acae-7df773c7e9f3" />

---

#  Justificativa das Escolhas Tecnológicas
### 🔹 Nuvem AWS
A escolha de **AWS**, é justificada pela flexibilidade, escalabilidade e suporte a múltiplos tipos de instâncias e diversos serviços oferecidos pela CLoud da AWS.

---

#  Automação via IaC (Terraform, Ansible)
### 🔹 Terraform
Define a infraestrutura na nuvem (_instâncias, redes, balanceadores de carga, VPCs_).

### 🔹 Ansible
Gerencia a configuração do software (_implantação de aplicativos, configuração de servidores_).

Obs.: Como já feito em laboratórios que podem ser acessados pelo link abaixo:
### 🔹
https://medium.com/@alexandre.barbosavr/implementa%C3%A7%C3%A3o-de-um-sistema-de-e-commerce-na-aws-de-forma-automatizada-usando-terraform-e-ansible-4653488b987e

---

#  Plano de Disaster Recovery
### 🔹 Recursos que podem ser utilizados:
Podemos implementar backups automatizados com o serviço AWS RDS Automated Backups, em conjunto podemos utilizar um ambiente **Multi-AZ**, executando a replicação para um ambiente de receupeção, para garantir a continuidade da operação, utilizando multiplas zonas e regiões, e acima de tudo realizando testes regulares para garantir a efetividade da recuperação. 

---

#  Monitoramento
### 🔹Ferramentas que podem ser utilizadas
Podemos utilizar ferramentas como **Prometheus**, **Grafana**, **CloudWatch** (_AWS_), **PRTG**, **Wazuh** para monitoramento contínuo.

---

#  Modelo OSI Aplicado
Se levando em conta a integraão por VPN do ambiente On-premise para a CLoud, é importante se atentar a configuração dos protocolos de roteamento, configuração das sub-redes e vpns contidos na camada de rede do modelo OSI, sejam respeitados, para uma melhor utilização dos serviços oferecidos pela solução proposta.

---

#  Conclusão
A migração para um modelo híbrido exige uma abordagem equilibrada entre **otimização de custos, escalabilidade e segurança**. Tecnologias de nuvem, contêineres e **automação por IaC** são essenciais para garantir eficiência e robustez. **Monitoramento contínuo e um plano de Disaster Recovery** são fundamentais para garantir a continuidade dos negócios.
```
