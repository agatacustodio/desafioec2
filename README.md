# Desafio - Instâncias EC2

Repositório para armazenar os conhecimentos adquiridos em Gerenciamento de Instâncias EC2 na AWS, no Bootcamp Code Girls 2025 da [DIO](https://www.dio.me/en) 

## 📚 Documentação
- [Gerenciando Instâncias EC2](https://docs.aws.amazon.com/pt_br/toolkit-for-visual-studio/latest/user-guide/tkv-ec2-ami.html)

## 💻 Resumos das Aulas

## Elastic Compute Cloud - EC2

São as máquinas virtuais na AWS. As instâncias são agrupadas em famílias, com base nos diferentes recursos de computação, como memória e armazenamento.

Tipos de locação: instâncias compartilhadas, instâncias dedicadas e hosts dedicados.

Tipos de carga de trabalho: uso constante, pico de tráfego diário, pico de tráfego semanal e pico de tráfego mensal.

| Tipos de Instância | Vantagens | Desvantagens |
| ------------ | ----------- | ---------------|
| On demand Instances | Flexibilidade total | Maior custo|
| Spot Instances| Menor custo | Pode ser interrompida pela AWS |
|Reserved Instances | Mais acessível | Pouca flexibilidade |
|Convertible Reserved Instances| Adaptabilidade | Acessível, porém menos do que as RIs  |

### Convenção do nome dos tipos de instância

#### c7gn.xlarge

| Representação | Significado |
| -- | ----------------|
| c | Instance family |
| 7 | Instance generation| 
| g | Processor family |
| n | Additional capability |
| xlarge | Instance size |

### Otimização de Recursos

Desligar instâncias não utilizadas.

Remover recursos ociosos/não utilizados.

Escalar recursos para processar workloads em momentos específicos.

- Verticalmente: acrescentar ou reduzir capacidade de um recurso.

- Horizontalmente: aumento do números de recursos.
