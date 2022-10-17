# Terraform - Challenge

### Requirements
- AWS CLI [https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html]
- tfenv [https://github.com/tfutils/tfenv]
- Conta AWS utilizada para testes

## ```Challenge Number 1```

- Criar VPC e demais dependências via console (Não precisa criar subnets privadas para ter o gasto com NAT GW)

- Autenticar via AWS CLI na conta de provisionamento dos recursos

- Criar módulo com a estrutura básica(main.tf, variable.tf, outputs.tf) para Amazon EC2, deixar o mais agnóstico e reutilizável possível

- Todos os "resources" que suportar TAGs o bloco deve ser incluído
```
tags = {
    Terraform   = "true"
  }
```

- Utilizar "locals" para injetar TAGs em todos os "resources" [https://www.terraform.io/language/values/locals]

- Criar algum tipo de condicional sem quebra do módulo, exemplo: Ter a possibilidade de utilizar um Key Pair gerado no momento de execução ou um já existente no console [https://www.terraform.io/language/expressions/conditionals]

- Chamar o módulo passando variáveis pertinentes ao ambiente
```
module "NAME_OF_MODULE" {
  source = "SOURCE_OF_MODULE"

  ### Input variables below ###
}
```

- Utilizar "Data Source" na chamada do módulo para aquisição de algum recurso já existente no ambiente [https://www.terraform.io/language/data-sources]

- Criar um Security Group personalizado fora do módulo (Na chamada do módulo) e vincular diretamente ao código da chamada

- Utilizar como backend um bucket do S3 [https://www.terraform.io/language/settings/backends/s3]

- Utilizar tabela do DynamoDB como lock table (Não permitir concorrência de execuções do Terraform) [https://quileswest.medium.com/how-to-lock-terraform-state-with-s3-bucket-in-dynamodb-3ba7c4e637]

## Validation

- Reaplicar o Terraform sem efetuar alterações no código e garantir a idempotência (No Changes)
- Reaplicar o Terraform alterando algo no código e validar a alteração no console
- Executar o Terraform Destroy

## ```Challenge Number 2```

- Developing...