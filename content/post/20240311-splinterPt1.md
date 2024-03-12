+++
title = 'Ressuscitando velhos projetos (Splinter #1)'
date = 2024-03-11T19:46:17-03:00
draft = false
+++
Hoje eu decidi fuçar em velhos projetos. O Splinter é um projeto antigo de faculdade, a ideia é básica,
eu queria criar um sistema pra quebrar o ENEM, ou qualquer outro tipo de prova semelhante. Para executar
esse projeto macabro eu queria criar um plataforma online, com as questões edições passadas das provas,
e os usuários iriam submeter tutoriais de como chegar a resposta correta das questões. Até aí tudo certo,
acredito que já existam plataformas semelhantes, mas para conseguir alcançar meu objetivo eu iria
adicionar um sistema de ranking entre as soluções, baseado nas avaliações dos usuários, dessa forma
eu conseguiria, teoricamente, os melhores métodos para responder as questões do ENEM. Na época
conseguimos entregar uma versão beta, mas ainda não tinha sistema de ranking. Então vou reescrever
ele do zero e documentar o processo de desenvolvimento aqui. 

Pra começar eu criei um novo projeto Laravel utilizando a ferramena Sail. Não sei se essa ferramenta
é muito utilizada pela comunidade, mas eu costumo usar ela para criar novos projetos, pois já cria o
esqueleto do projeto com docker, o que me economiza um tempo.

Com o esqueleto de Laravel pronto, vamos para a primeira modificação do projeto original, adicionar
um banco de dados NoSQL. Originalmente eu achava que devia seguir com apenas um banco de dados (SQL 
ou NoSQL), e sei que o banco relacional seria o ideal para a maioria dos sistemas, porém eu acredito
que o NoSQL pode me quebrar um galho facilitando a abstração dos conteúdos de questões e tutoriais de
usuários. Acredito que o formato desses conteúdos pode variar bastante e criar uma estrutura SQL para
suportar esses dados pode demorar muito tempo de análise e testes. Fora esses dois, acredito que o
restante dos dados da plataforma pode ser armazenado de forma estruturada e com isso terei o melhor
dos dois tipos de bancos de dados. Para isso vou usar os bancos MySQL e MongoDB.

O MySQL já vem configurado por padrão em projetos Laravel criados com o Sail. Porém o MongoDB tive
de adicionar após, seguindo um [tutorial](https://www.mongodb.com/developer/languages/php/laravel-mongodb-tutorial/)
da internet tive meu primeiro probleminha. O composer se recusava a instalar o pacote
**mongodb/laravel-mongodb**. Para esse pacote o composer necessita que um plugin do PHP seja
instalado na máquina de hospedagem, como o Sail criou o projeto com uma estrutura docker padrão,
tive de copiar o arquivo Dockerfile original do Sail, adicionar no projeto, e dentro do Dockerfile
adicionar o pacote *php8.3-mongodb*. Após isso o composer instalou a dependência normalmente,
e pude testar a conexão com o banco de dados.

Hoje vou parando por aqui, mas ainda tenho a intenção de adicionar o mongodb no docker-compose,
assim não vou depender da hospedagem para o desenvolvimento. Eu gravei alguns passos desse processo,
então acho que posso postar esse vídeo junto com esse texto.