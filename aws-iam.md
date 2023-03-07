# AWS Identity and Access Management (IAM)
Permite o gerenciamento seguro dos serviços e recursos da AWS através de criação de usuários, grupos de usuários e permissões.

## Termos e conceitos
- `Identity:` fornece acesso a uma conta na AWS;
- `IAM Users:` representa uma pessoa ou serviço que utiliza serviços da AWS;
- `IAM Groups:` coleção de usuários IAM;
- `IAM Roles:` conjunto de permissões que definem o nível de acesso de uma identidade aos serviços AWS;
- `IAM Policies:`define permissões de acesso a serviços AWS;
  - Inline policy: permissão atrelada diretamente a uma identidade, não reaproveitáveis;
  - Managed policy: permissões disponíveis para várias identidades.
- `IAM Permissions:` nível mais baixo da hierarquia, determina se uma identidade pode ou não tomar uma acão sobre determinado recurso (Allow/Deny);

![image](https://user-images.githubusercontent.com/15961779/223550459-33baa9a9-0cae-4d35-947c-ec535a58d42d.png)

## Boas práticas
- Não utilizar conta raiz para desenvolvimento;
- Criar usuários individuais;
- Privilégios mínimos;
- Utilizar grupos de usuários com permissões;
- Ativar o AWS CloudTrail para auditoria;
- Usar senhas fortes;
- Ativar o MFA para usuários privilegiados.
