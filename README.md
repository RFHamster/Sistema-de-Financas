# Sistema-de-Financas

Um sistema de gerenciamento de finanças feito em Java, com JavaFX e Hibernate
Esse sistema foi feito para o Trabalho Final de POO2 e foi utilizado diversos padrões de projeto como Facade, Adapter e Factory.

O projeto foi feito em trio, sendo este eu, Gabriel Gama e Waldemar Silva. Fiquei com a parte do backend do projeto, Waldemar com o Front-ent e o Gama com os testes unitários.

A proposta do projeto era a seguinte: Sistema para organização de finanças pessoais permitindo o registro e anotações sobrereceitas, despesas, empréstimos e aplicações. O Sistema deverá permitir fazer o registro das informações e acompanhamentoda situação financeira, permitindo relatórios diários, semanais, mensais e anuais.

Dessa maneira já comecei primeiramente criando os tipos de registro e suas particularidades, configurando os mesmos também para funcionar no Hibernate (mapeando). Com isto pronto, uma fábrica de relatórios foi criada, para que cada um dos tipos de relatório acima fizessem parte dela. Para criação da função em comum dos relátorios definida na interface da fábrica, gerarRelatorio(), sempre deve ser passada uma data como parâmetro para a consulta, para assim, poder fazer a lógica da função buscando os dados referentes a esta data (data esta que será conforme o tipo do relátorio, diário -> data completa, mês -> mes e ano, ano -> somente ano).

Para facilitar o uso desse backend criado para os meus colegas de equipe, criei um facade, onde era só eles chamarem as funções que já tinham como manipular o banco, sem precisar saber de Hibernate (como eu fiz no trabalho da Comanda do Restaurante).

Com o backend pronto comecei a auxiliar os meninos no front-end do JavaFx, onde eles haviam criado uma classe de controle mainCrontroller, que utilizava as funções do Facade, inserindo e fazendo consultas no banco. Vale ressaltar que foi utilizado um Adapter para manipular a data passada.

## Tela de Inserção

Aqui podemos ver que podemos inserir os 4 tipos (receita, empréstimo, despesa e aplicação), clicando nos botões na parte inferior da tela e escrevendo os dados da inserção

<div align="center">\
  <img src="https://user-images.githubusercontent.com/71076681/250305373-c337c3e0-b93b-406c-9343-e447b31a7fca.png" alt="Tela Insercao"/>
</div>

## Tela de Consulta

Aqui temos a possibilidade de todas as consultas (diária, semanal, mensal e anual), da mesma maneira da tela de inserção.

<div align="center">\
  <img src="https://user-images.githubusercontent.com/71076681/250305392-c0a8576f-7395-420f-9f4c-c1677ac2d85e.png" alt="Tela Consulta"/>
</div>
