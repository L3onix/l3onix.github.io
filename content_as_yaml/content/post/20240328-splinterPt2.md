---
date: '2024-03-28T00:50:10-03:00'
draft: false
title: 'Primeiras rotas (Splinter #2)'
---
Continuando a saga de desenvolvimento do Splinter, hoje vou continuar seguinte aquele mesmo
[tutorial](https://www.mongodb.com/developer/languages/php/laravel-mongodb-tutorial/) da semana passada.
Após a configuração do MongoDB eu posso criar a primeira rota. Como comentei no post passado
vou utlizar o NoSQL para armazenar as questões de provas, pra isso eu crio o *model*
QuestionMongoDB (os models que vão utilizar o MongoDB vão ter esse padrão de nome). Aqui já
tem algumas alterações pra serem feitas, partindo do padrão criado pelo artisan, eu mudo
a classe *model* (para a classe específica da biblioteca **laravel-mogodb**), e crio o variável
*connection*, ela serve pra selecionar explicitamente qual conexão com o banco de dados deve
ser utilizado nesse *model* (não detalhei isso no post anterior, mas no arquivo de configurações
de bancos de dados do laravel eu adicionei a opção para o mongodb), também adicionei a variável
*fillable* para definir os campos do "tabela" de questões, por enquanto estou carregando uma
apenas uma estrutura básica, futuramente o esse model vai passar por um revisão baseada em
questões reais.

O restante dos arquivos, controller e api.php, seguem da mesma forma que o
implementações com bancos de dados SQL, claro que existem algumas particularidades nas funções
do model. Fiz uns testes básicos, apenas para verificar se o código funcionava e os dados
eram salvos no banco de dados. No final deu tudo certo.

Por esse post é só isso. Acho que no próximo post vou focar na estrutura json em que as questões
serão armazenadas, com isso eu vou poder criar o form request das rotas de Question, e também
vou poder definir o arquivo de resources para rotas. 


