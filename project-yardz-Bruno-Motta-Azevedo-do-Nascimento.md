# MongoDb - Projeto Final  
**Autor:** Bruno Motta Azevedo do Nascimento  
**Data** 1484314752170 //em timestamp  

## Para qual sistema você usaria o MogoDB (diferente desse)?
```
Usaria em um sistema de gestão de historico médico de pacientes.
Haveriam doenças pré-cadastradas e remédios.
Os médicos poderiam cadastrar o diagnostico do paciente. Colocar qual doença o paciente possiu e descrever o tratamento (podendo ou não colocar o remédio que foi receitado). Eles também poderiam cadastrar (upload) exames que serviram de apoio para diagnosticar a doença.  
  
Após isso, outros médicos podem ter acesso ao historico completo do paciente: doenças, tipo sanguineo, exames antigos, etc.  
  
De forma genérica eu utilizaria o MongoDB para sistemas que necessitem de alta velocidade de leitura e que de alguma forma garantam a integridade. Diferente de alguns outros No-Sql o MongoDB tende a garantir a integridade sobre a disponibilidade (o cassandra, por exemplo, garante a disponibilidade sobre a integridade). Portanto de certa forma os sistemas No-Sql devem ser tolerante a falhas.  
Outro ponto crítico é a modelagem, o mongo DB deve aumentar o numero de "documentos aninhados", portanto deve-se ser possível modelar os dados para ficarem aninhados.  
Por ultimo, é interessante que não haja muitas edições nos dados salvos, uma vez que a costuma-se ter dados redundantes as operações de escritas podem ser muito custosas. Pensando no exemplo de tags de um blog, ao editar uma tag, deve-se fazer alteração em todas as ocorrencias dentro de todos os posts.  

```

## Qual a modelagem da sua coleção de `users`?
```js

```

## Qual a modelagem da sua coleção de `projects`?
```js

```

## Qual a modelagem da sua coleção retirada de `projects`?
```js

```

A arquitetura dessa minha modelagem foi feita para a melhor forma da aplicação, ela pode armazenar um quantidade de dados.
Separadamente, a coleção de atividades foi feita para que devido ao grande numero de inserções que pode ocorrer em um unico projeto.
Retirei de `activities ` pelo motivo que pode aumentar o limite do arquivo.

## Create - cadastro

Primeiramente criei uma variável `names` com o valor dos 10 nomes dos usuários.

#### Cadastre 10 usuários diferentes.
```js

```

#### Cadastrando activities para os goals.
```js

```

#### Cadastrando projects e goals.
```js

```

## Retrieve - busca

#### Listar as informações dos membros de 1 projeto específico.
```js

```

#### Liste todos os projetos com a tag que você escolheu para os 3 projetos em comum.
```js

```

#### Liste apenas os nomes de todas as atividades para todos os projetos.
```js

```

#### Liste todos os projetos que não possuam uma tag.
```js

```

#### Liste todos os usuários que não fazem parte do primeiro projeto cadastrado.
```js

```

## Update - alteração
#### Adicione para todos os projetos o campo views: 0.
```js

```

#### Adicione 1 tag diferente para cada projeto.
```js

```

#### Adicione 2 membros diferentes para cada projeto.
```js

```

#### Adicione 1 comentário em cada atividade, deixe apenas 1 projeto sem.
```js

```

#### Adicione 1 projeto inteiro com UPSERT.
```js

```

## Delete - remoção
#### Apague todos os projetos que não possuam tags.
```js

```

#### Apague todos os projetos que não possuam comentários nas atividades.
```js

```

#### Apague todos os projetos que não possuam atividades.
```js

```

#### Escolha 2 usuários e apague todos os projetos em que os 2 fazem parte.
```js

```

#### Apague todos os projetos que possuam uma determinada tag em goal.
```js

```

## Gerenciamento de usuários
#### Crie um usuário com permissões APENAS de Leitura.
```js

```

#### Crie um usuário com permissões de Escrita e Leitura.
```js

```

#### Adicionar o papel grantRolesToUser e revokeRole para o usuário com Escrita e Leitura.
```js

```

#### Remover o papel grantRolesToUser para o usuário com Escrita e Leitura.
```js

```

#### Listar todos os usuários com seus papéis e ações.
```js

```

## Sharding
```js

```

## Replicas
```js

```

