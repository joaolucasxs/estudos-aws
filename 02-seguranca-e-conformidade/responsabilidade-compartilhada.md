# Modelo de Responsabilidade Compartilhada

## A ideia em uma frase
A AWS é responsável pela segurança **da** nuvem; o cliente é responsável pela segurança **na** nuvem.

## O que é responsabilidade da AWS
- Data centers físicos (acesso, energia, refrigeração)
- Hardware: servidores, storage, rede
- Software de virtualização (hypervisor)
- Serviços gerenciados por baixo (ex.: o sistema operacional do RDS)

## O que é responsabilidade do cliente
- Dados: classificação, criptografia, backup
- Gerenciamento de identidade e acesso (IAM): usuários, permissões, MFA
- Configuração do sistema operacional em EC2 (patches, firewall)
- Configuração de rede: Security Groups, NACLs
- Aplicação e o código dela

## Como a responsabilidade muda conforme o serviço
| Serviço | Quem cuida do SO e patches? | Quem cuida dos dados e acesso? |
|---|---|---|
| EC2 (IaaS) | Cliente | Cliente |
| RDS (serviço gerenciado) | AWS | Cliente |
| S3 / Lambda | AWS | Cliente |

Quanto mais gerenciado o serviço, mais a AWS assume — mas **dados e acesso são sempre do cliente**.

## Pegadinhas de prova
- "A AWS é responsável por criptografar meus dados" → **errado**, a AWS oferece a ferramenta (KMS, SSE-S3), o cliente decide usar.
- "A AWS aplica patches no meu EC2" → **errado**, EC2 é IaaS; patch é do cliente.
- Segurança **física** → sempre AWS.

## Fontes
- [AWS Shared Responsibility Model](https://aws.amazon.com/compliance/shared-responsibility-model/)
