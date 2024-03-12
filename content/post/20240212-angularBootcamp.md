+++
title = 'Bootcamp Angular'
date = 2024-01-29T02:09:29-03:00
draft = true
+++
Esse final de ano, eu resolvi participar de um bootcamp, para fortalecer meus
conhecimentos sobre frontend, que confesso, não é a parte em que mais gosto em
desenvolvimento de software, mas também concordo que **devo** ter conhecimento
no assunto.

Então desde dezembro de 2023 venho fazendo os módulos do curso, no meu ritmo,
e percebi que as gravações dos módulos foram feitas a alguns anos atrás, prova
disso que os vídeos estão utilizando o Angular v14 para as aulas, e na data desse
post, já está disponível o Angular v17. Eu achei que por sei um bootcamp o
conteúdo seria mais atualizado, mas não sei se isso é uma prática comum ou não.
Por conta dessa desatualização comecei a ler mais a documentação do Angular
mais recente, e fiz meus exercícios com essa versão mais atual.

Acho que o conteúdo do bootcamp não é ruim por esse fato, descrevi essa situação para
contextualizar a ideia que quero compartilhar agora. Muitas vezes as bibliotecas
ou frameworks fazer anos de atualizações, porém continuam funcionando da mesma forma,
na prática o programador vai continuar trabalhando como antes. No caso do Angular, e
durante essa minha experiência, consegui perceber que o Angular mudou em um ponto que
parecia ser algo chave na metodologia de desenvolvimento (não acho isso alarmante, só
considero uma mudança relevante para ser comentada). Na versão 14 do Angular eles
disponibilizaram o recurso ***standalone components***, que, se não me engano, é
um comportamento padrão do React, onde um component pode ser importado por outro
sem passar por um injetor de dependências. No caso do Angular, até a versão 14, era
necessário que um component ou página tivesse uma classe de módulo (NgModule), que injetaria
as dependências daquele component.

Ainda na versão 14 esse novo tipo de component não era "incentivado" pelo Angular,
e os projetos ainda eram carregados de arquivos de módulos. Não sei em que versão
isso mudou, mas agora na versão 17 os módulos estão sendo apagados pelo Angular.
Tutoriais, documentação, e geradores de código, todos incentivam que o desenvolvedor
utilize o standalone component.