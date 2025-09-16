# Desafio - Instâncias EC2

Repositório sobre Gerenciamento de Instâncias EC2 na AWS, para armazenar os conhecimentos adquiridos no Bootcamp Code Girls da [DIO](https://www.dio.me/en).

## 📚 Documentação
- [Gerenciando Instâncias EC2](https://docs.aws.amazon.com/pt_br/toolkit-for-visual-studio/latest/user-guide/tkv-ec2-ami.html)

## 💻 Resumos das Aulas 

### Entendendo as Instâncias EC2 e a Otimização de Recursos na AWS

#### **Elastic Compute Cloud (EC2)**

- São as máquinas virtuais da AWS.
- As instâncias são agrupadas em famílias, com base nos diferentes recursos de computação, como memória, CPU, rede e armazenamento.

**Tipos de locação:**

- Shared Instances → compartilham hardware com outros clientes.
- Dedicated Instances → instâncias isoladas em hardware dedicado.
- Dedicated Hosts → servidor físico dedicado, com controle sobre o hardware.

**Tipos de carga de trabalho:**
- Uso constante.
- Picos de tráfego (diário, semanal ou mensal).

**Tipos de Compra:**

- On-demand → flexibilidade total, paga apenas pelo uso.
- Spot → menor custo, mas pode ser interrompida pela AWS.
- Reserved → preço mais acessível, exige compromisso de longo prazo.
- Convertible Reserved → permite alterar tipo de instância mantendo parte do desconto.


#### **Nomeação das Instâncias**

**Exemplo:** c7gn.xlarge

| Representação | Significado |
| -- | ----------------|
| c | Família da instância |
| 7 | Geração da instância | 
| g | Tipo de processador |
| n | Capacidade adicional |
| xlarge | Tamanho da instância |


#### **Otimização de Recursos**


- Desligar instâncias não utilizadas.
- Remover recursos ociosos.
- Escalar recursos:
    -  Verticalmente → aumentar/reduzir capacidade de um recurso.
    -  Horizontalmente → aumentar/reduzir número de recursos.


### Armazenamento na Nuvem com Amazon EBS e S3

#### **Amazon Elastic Block Store (EBS)**

- Funciona como um HD/SSD externo para EC2.
- Alta disponibilidade (**99,999%**).
- Permite snapshots (cópias de backup).

#### **Amazon Simple Storage Service (S3)**

- Armazenamento de objetos altamente escalável.
- Alta durabilidade (**99,999999999%**).
- Classes de armazenamento:
    - S3 Standard
    - S3 Standard-IA (Infrequent Access)
    - S3 One Zone-IA
    - S3 Glacier (arquivamento)

*IA = Infrequent Access*

Os objetos não passam automaticamente de uma classe para outra. Essa transição é possível por meio da configuração de uma Lifecycle Rule (Regra de ciclo de vida). Também é possível programar a exclusão do objeto.

**Exemplo:** mover objetos do S3 Standard para o S3 IA após 90 dias e para o Glacier após 1 ano.

#### **Amazon Machine Image (AMI)**

É uma imagem da máquina virtual pré-configurada que inclui as informações necessárias para iniciar uma instância (sistema operacional, aplicativos e configurações).

- **Criação e uso de imagens AMI** 

As AMIs podem ser criadas a partir de instâncias em execução ou paradas, o que permite capturar um instantâneo do ambiente configurado.

A AWS fornece uma variedade de AMIs públicas, e também é possível criar e usar AMIs privadas. É possível personalizar uma instância e criar um AMI a partir dela.

✅ Permite criar ambientes consistentes e reproduzíveis.

**Tipos de AMI:** Amazon Linux, Windows, Ubuntu, etc.

Escolhe-se uma AMI com base nos requisitos da aplicação e do sistema operacional.

#### **Snapshots EBS**

É um serviço de backup incremental de volumes EBS em um ponto no tempo.

- A frequência dos snapshots ("fotos") é configurável.

- Para fins de recuperação de desastres (DR), os instantâneos do EBS podem ser armazenados em uma região remota.

📸 **AMI vs Snapshot**

Uma imagem (AMI) faz o backup de um servidor inteiro, incluindo todos os volumes EBS anexados. Já um snapshot é uma cópia pontual de um determinado volume.
