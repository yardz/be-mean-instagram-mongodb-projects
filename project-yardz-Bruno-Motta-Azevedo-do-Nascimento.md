# MongoDb - Projeto Final  
**Autor:** Bruno Motta Azevedo do Nascimento  
**Data** 1484314752170  

## Para qual sistema você usaria o MogoDB (diferente desse)?
```
Usaria em um sistema de gestão de historico médico de pacientes.
Haveriam doenças pré-cadastradas e remédios.
Os médicos poderiam cadastrar o diagnostico do paciente. Colocar qual doença o paciente possiu e descrever o tratamento (podendo ou não colocar o remédio que foi receitado). Eles também poderiam cadastrar (upload) exames que serviram de apoio para diagnosticar a doença.  
  
Após isso, outros médicos podem ter acesso ao historico completo do paciente: doenças, tipo sanguineo, exames antigos, etc.  
```

## Qual a modelagem da sua coleção de `users`?
```js
users{
    name:String,
    bio:String,
    date_register: Date,
    avatar_path : String,
    settings_system:{
        background_path:String
    },
    auth:{
        username : String,
        email : String,
        password : String,
        last_access : Date,
        online : Boolean,
        disabled : Boolean,
        hash_token : String
    }
}
```

## Qual a modelagem da sua coleção de `projects`?
```js
projects{
    name: String,
    description: String,
    date_begin: Date,
    date_dream: Date,
    date_end: Date,
    visible: Boolean,
    realocate: Boolean,
    expired: Boolean,
    visualizable_mod: String
    tags:[],
    members:[
        {
            type_name: String,
            user: ObjectID, //users _id
            notify:String,
            //Repetindo estes campos pois são campos que se fazem necessários com maior frequência. Dessa forma é possível evitar novas buscas no banco para estes dados que serão amplamente utilizados.  
            user_name: String,
            avatar_path : String
        }
    ],
    goals:[
        {
            name: String,
            description: String,
            data_begin: Date,
            data_dream: Date,
            data_end: Date,
            data_realocate: Date,
            realocate: Boolean,
            expired: Boolean,
            tags: [],
            date_realocate:[],
            activitys:[
                {
                    members:[
                        {
                            //Repetindo o mesmo "members dentro de projetos". Essa repetição existe pois nem todo membro do projeto está dentro do "goal"  
                            type_name: String,
                            user: ObjectID, //users _id
                            notify:String,
                            user_name: String,
                            avatar_path : String
                        }
                    ],
                    name: String,
                    description: String,
                    date_begin: Date,
                    date_dream: Date,
                    date_end: Date,
                    realocate: Boolean,
                    expired: Boolean,
                }
            ],
            activity_historic:[],
            comments:[
                {
                    text: String,
                    date_comment: Date,
                    members:[
                        {
                            //Repetindo o mesmo "members dentro de projetos". Essa repetição existe pois nem todo membro do projeto está dentro do "goal"  
                            type_name: String,
                            user: ObjectID, //users _id
                            notify:String,
                            user_name: String,
                            avatar_path : String
                        }
                    ],
                    files:[
                        {
                            path: String,
                            weight: Number,
                            name: String
                        }
                    ]
                }
            ]
        }
    ]
}

A única grande modificação que eu colocaria são os "members" de forma mais redundante. Colocaria as informações mais utilizadas dos usuários nos dentro do members para que não sejam necessárias outras buscas para adiquirir essas informações.  
Caso a coleção torne-se muito grande, seria interessante separa as atividades ou goals em outra coleção, e deixar a collection "projetos" menor. A meu ver essa decisão depende muito da quantidade de goals e de atividades dentro de cada projeto, pois caso o número seja pequeno pode não fazer sentido separa-las.
```

## Create - cadastro
```js
```

## Retrieve - busca
```js
```

## Update - alteração
```js
```

## Delete - remoção
```js
```

## Sharding
```js
// coloque aqui todos os comandos que você executou

```

## Replica
```js
// coloque aqui todos os comandos que você executou

```

