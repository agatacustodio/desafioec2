# Desafio - Instâncias EC2

Repositório sobre Gerenciamento de Instâncias EC2 na AWS, para armazenar os conhecimentos adquiridos no Bootcamp Code Girls da [DIO](https://www.dio.me/en).

## 📚 Documentação
- [Gerenciando Instâncias EC2](https://docs.aws.amazon.com/pt_br/toolkit-for-visual-studio/latest/user-guide/tkv-ec2-ami.html)

## 💻 Resumos das Aulas 

### Entendendo as Instâncias EC2 e a Otimização de Recursos na AWS

#### **Elastic Compute Cloud (EC2)**

São as máquinas virtuais na AWS. As instâncias são agrupadas em famílias, com base nos diferentes recursos de computação, como memória, CPU, rede e armazenamento.

- **Tipos de locação:** instâncias compartilhadas, instâncias dedicadas e hosts dedicados.

- **Tipos de carga de trabalho:** uso constante, pico de tráfego diário, pico de tráfego semanal e pico de tráfego mensal.

- **Tipos de Conteiner:** on demand, spot, reserved e convertible reserved.

| Categoria | Vantagens | Desvantagens |
| ------------ | ----------- | ---------------|
| On demand Instances | Flexibilidade total | Maior custo|
| Spot Instances| Menor custo | Pode ser interrompida pela AWS |
|Reserved Instances | Mais acessível | Pouca flexibilidade |
|Convertible Reserved Instances| Adaptabilidade | Acessível, porém menos do que as RIs  |

#### **Entendendo o Nome dos Tipos de Instância**

**Exemplo:** c7gn.xlarge

| Representação | Significado |
| -- | ----------------|
| c | Instance family |
| 7 | Instance generation| 
| g | Processor family |
| n | Additional capability |
| xlarge | Instance size |


### Otimização de Recursos


- Desligar instâncias não utilizadas.

- Remover recursos ociosos/não utilizados.

- Escalar recursos verticalmente (acrescentar ou reduzir capacidade de um recurso) ou horizontalmente (aumentar o números de recursos).


### Armazenamento na Nuvem com Amazon EBS e S3

#### **Amazon Elastic Block Store (EBS)**

O EBS permite expandir a capacidade de armazenamento de uma instância, como uma espécie de HD externo.

- **99.999%** de disponibilidade.

#### **Amazon Simple Storage Service (S3)**

É um serviço escalável e de armazenamento de objetos em nuvem. Ideal para armazenar, organizar e recuperar grandes volumes de forma segura e escalável.

- **99.999999999%** de disponibilidade.

- **Classes de Armazenamento:** S3 Standard, S3 Standard IA, S3 One Zone - IA, S3 Glacier.

*IA = Infrequent Access*

Os objetos não passam automaticamente de uma classe para outra. Essa transição é possível por meio da configuração de uma Lifecycle Rule (Regra de ciclo de vida). Também é possível programar a exclusão do objeto.

Por padrão, os objetos ficam no S3 Standard até serem excluídos ou regras se aplicarem.

**Exemplo:** criar uma regra que define que os objetos serão movidos do S3 Standard para o S3 Standard IA após 90 dias e, após 1 ano, para o S3 Glacier.

#### **Amazon Machine Image (AMI)**

É uma imagem da máquina virtual pré-configurada que inclui as informações necessárias para iniciar uma instância (sistema operacional, servidor de aplicações e as aplicações).

- **Criação e uso de imagens AMI** 

As AMIs podem ser criadas à partir de instâncias em execução ou paradas, o que permite capturar um instântaneo do ambiente configurado.

A AWS fornece uma variedade de AMIs públicas, e também é possível criar e usar AMIs privadas. É possível personalizar uma instância e criar um AMI à partir dela.

A AMI fornece as informações necessárias para executar instâncias no EC2, como o volume do dispositivo raiz e as permissões de inicialização. Essa base fornevcida permite a criação de ambientes consistentes e reproduzíveis na nuvem.

- **Tipos de AMI**: Amazon Linux, Windows, etc.

Escolhe-se uma AMI com base nos requisitos da aplicação e do sistema operacional.

#### **Snapshots EBS**

É um serviço de backup nativo da AWS. O backup dos volumes do EBS é realizado em um determinado momento, e a frequencia dos snapshots ("fotos") é configurável.

Para fins de recuperação de desastres (DR), os instantâneos do EBS podem ser armazenados em uma região remota.

- **Imagem vs Snapshot**

Uma imagem (AMI) faz o backup de um servidor inteiro, incluindo todos os volumes EBS anexados. Já um snapshot é uma cópia pontual de um determinado volume.


## 🔎 Referências
- [Exemplo](https://docs.aws.amazon.com/pt_br/toolkit-for-visual-studio/latest/user-guide/tkv-ec2-ami.html)
