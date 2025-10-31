# 🚀 Desafio DIO: Primeira Stack com AWS CloudFormation

## 🧠 Entendendo o Desafio
Este projeto faz parte do bootcamp **Santander 2025 - Fundamentos de IA para Devs**, em parceria com a **DIO (Digital Innovation One)**.  
O objetivo deste laboratório é colocar em prática os conhecimentos adquiridos sobre **infraestrutura como código (IaC)** utilizando o **AWS CloudFormation**, criando a sua **primeira Stack** na AWS e documentando todo o processo.

---

## 🎯 Objetivo do Desafio
- Aplicar os conceitos aprendidos em um ambiente prático;
- Documentar processos técnicos de forma clara e estruturada;
- Utilizar o **GitHub** como ferramenta para compartilhar documentação técnica e aprendizado.

---

## 🧰 Tecnologias Utilizadas
- **AWS CloudFormation** – Automação da infraestrutura como código  
- **AWS Management Console** – Interface de gerenciamento  
- **YAML** – Linguagem utilizada para o template da stack  
- **Git e GitHub** – Controle de versão e hospedagem da documentação  

---

## 🪜 Etapas Realizadas
​
## 🔹 Dica: Se você quiser criar em uma VPC real, substitua vpc-12345678 pelo ID correto da sua VPC.

### 1️⃣ Acesso ao Console AWS
Acessei o **AWS Management Console** e procurei pelo serviço **CloudFormation**.

### 2️⃣ Criação da Stack
1. Cliquei em **Create stack → With new resources (standard)**;  
2. Fiz o upload do arquivo **template.yaml** contendo a definição dos recursos;  
3. Defini o nome da stack (ex: `MinhaPrimeiraStackDIO`);  
4. Ajustei as permissões e parâmetros necessários;  
5. Concluí a criação acompanhando o status até aparecer **“CREATE_COMPLETE”**.

### 3️⃣ Criando o template da Stack (Exemplo Prático)

Vamos criar uma Stack de Firewall com Security Group que você poderá usar no laboratório.

```bash
AWSTemplateFormatVersion: '2010-09-09'
Description: Stack de Firewall para prática do bootcamp DIO

Resources:
  MeuSecurityGroup:
    Type: AWS::EC2::SecurityGroup
    Properties:
      GroupName: firewall-leticia
      GroupDescription: Security Group para acesso SSH e HTTP
      VpcId: vpc-12345678   # Substitua pelo ID da sua VPC
      SecurityGroupIngress:
        - IpProtocol: tcp
          FromPort: 22
          ToPort: 22
          CidrIp: 0.0.0.0/0  # Apenas para teste
        - IpProtocol: tcp
          FromPort: 80
          ToPort: 80
          CidrIp: 0.0.0.0/0  # HTTP público
      SecurityGroupEgress:
        - IpProtocol: -1
          CidrIp: 0.0.0.0/0  # Saída para qualquer destino

```

### 4️⃣ Validação da Criação
Após o provisionamento, verifiquei os **recursos criados automaticamente**, como VPCs, Security Groups, e instâncias EC2 (dependendo do template utilizado).

### 5️⃣ Registro de Evidências
Durante todo o processo, realizei capturas de tela e salvei na pasta `/images`, demonstrando:
- Criação da stack;
- Template utilizado;
- Status de execução;
- Recursos criados.

---

## 📸 Evidências
As imagens principais estão armazenadas na pasta `/images`:
- `01-criacao-stack.png`
- `02-template.png`
- `03-status-complete.png`
- `04-recursos-criados.png`

---

## 🧩 Estrutura do Repositório

```bash
📁 dio-desafio-cloudformation
┗ 📄 README.md

```

---

## 💡 Insights e Aprendizados

Durante a prática, compreendi de forma mais clara:
- A importância da **Infraestrutura como Código (IaC)** na automação de ambientes;  
- Como o **CloudFormation** facilita a criação, atualização e versionamento de recursos AWS;  
- A vantagem de usar templates **YAML** para manter a infraestrutura padronizada e replicável;  
- O poder de utilizar o **GitHub** como portfólio técnico e vitrine de aprendizado contínuo.  

---

## 🏁 Conclusão

Este desafio foi essencial para consolidar os conhecimentos sobre **AWS CloudFormation** e **DevOps na nuvem**.  
A partir desta experiência, me sinto mais preparada para implementar, versionar e automatizar recursos em ambientes reais utilizando boas práticas de IaC.  

---

## ✨ Autora

**Leticia Bacellar**  
👩‍💻 Bootcamp Santander 2025  
📚 Projeto desenvolvido na plataforma **Digital Innovation One (DIO)**  
🔗 [https://www.dio.me](https://www.dio.me)
