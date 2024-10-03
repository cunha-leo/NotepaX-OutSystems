# NotepaX - Sistema de Flashcards para Estudos

## 1. Introdução

O NotepaX é um sistema de flashcards desenvolvido na plataforma **OutSystems Reactive**, com o objetivo de auxiliar no processo de estudo e fixação de conteúdos de aprendizagem. Este projeto foi desenvolvido como parte prática do **módulo de Introdução ao OutSystems** da **Academia RafaOutSystems Expert**, consolidando os conceitos fundamentais da plataforma em um projeto prático e funcional.

## 2. Objetivos do Projeto

- Aplicar os conceitos básicos do OutSystems para criar uma aplicação que auxilie no estudo de forma interativa.
- Desenvolver um sistema de gerenciamento de cards, implementando as funcionalidades de **CRUD** (Create, Read, Update, Delete) para tópicos e flashcards.
- Implementar um sistema de revisão de flashcards, utilizando técnicas de repetição espaçada para melhorar a retenção de conhecimento.

## 3. Funcionalidades do Projeto

- **Cadastro e Gerenciamento de Tópicos:** Criar, editar e excluir tópicos para organizar os conteúdos de estudo.
- **Cadastro e Gerenciamento de Cards:** Adicionar, editar e excluir cards dentro dos tópicos, permitindo a construção de perguntas e respostas.
- **Sistema de Revisão de Cards:** Implementar a técnica de repetição espaçada, permitindo ao usuário revisar os cards de maneira eficiente até que todas as respostas sejam acertadas.
- **Botão de Reset e Função de Review:** A opção de resetar o baralho de cards ao final da revisão, permitindo recomeçar o ciclo de estudo do zero.

## 4. Tecnologias e Ferramentas Utilizadas

- **OutSystems Reactive:** Para o desenvolvimento da aplicação e lógica de negócios.
- **Server Actions e Client Actions:** Utilizadas para implementar o CRUD e a lógica de revisão dos cards.
- **Banco de Dados Interno do OutSystems:** Gerenciamento dos dados relacionados a usuários, tópicos e cards.

## 5. Estrutura do Banco de Dados

O banco de dados foi modelado de acordo com os conceitos introdutórios do OutSystems:

- **Tabela MainSubject**(Assunto Principal)
- **Tabela Topic**(Tópico do Card)
- **Tabela Card**(Detalhes do Card)
- **Tabela User_Extension e User**(Para o gerenciamento de usuários e recuperação de senha)

![Visualização do ER do Projeto NotepaX](./assets/img/Model%20ER/ER.png)
![Visualização do ER do Projeto NotepaX](./assets/img/Model%20ER/ER2.png)
![Visualização do ER do Projeto NotepaX](./assets/img/Model%20ER/ER3.png)

## 6. Estrutura de Telas e Navegação

- **Telas de Login:** Utiliza a tabela padrão User do OutSystems, com a funcionalidade de recuperação de senha usando um código secreto.

Login

- Login
  ![Visualização da Tela Principal e Tópicos](./assets/img/System/Login/System_Login.png)

- Recovery Password
  ![Visualização da Tela Principal e Tópicos](./assets/img/System/Login/System_RecoveryPassword.png)

- User Register
  ![Visualização da Tela Principal e Tópicos](./assets/img/System/Login/System_UserRegister.png)
  
- **Tela Principal:** Apresenta os assuntos principais, possibilitando a navegação para os tópicos e cards.

Subject Login

- Subject List(Lista de Assunto Principal):
  ![Visualização da Tela Principal e Tópicos](./assets/img/System/SubjectList/System_Main_SubjectList.png)

- New Subject List:
  ![Visualização da Tela Principal e Tópicos](./assets/img/System/SubjectList/System_New_SubjectList.png)

- Edit Subject List:
  ![Visualização da Tela Principal e Tópicos](./assets/img/System/SubjectList/System_Edit_SubjectList.png)

- **Tela de Tópicos e Cards:** Permite adicionar, editar e excluir tópicos e cards, seguindo as práticas de CRUD.

Topic

- New topic
  - Topic(Criação de Tópicos a partir da Subject List Edit):

  ![Visualização da Tela Principal e Tópicos](./assets/img/System/Topic/System_New_Topic.png)

- Edit Topic
  ![Visualização da Tela Principal e Tópicos](./assets/img/System/Topic/System_Edit_Topic.png)

Card

- New Card
  ![Visualização da Tela Principal e Tópicos](./assets/img/System/Card/System_New_Card.png)

- Edit Card
  ![Visualização da Tela Principal e Tópicos](./assets/img/System/Card/System_Edit_Card.png)

- **Tela de Revisão de Cards:** Exibe os flashcards para o usuário indicar se acertou ou errou, proporcionando uma revisão interativa e prática.

Review

- Starting Review
  ![Visualização da Tela de Revisão de Cards](./assets/img/System/Review/System_Starting%20Review.png)

- Main Review
  ![Visualização da Tela de Revisão de Cards](./assets/img/System/Review/System_Main%20Review.png)

- Ongoing review
  ![Visualização da Tela de Revisão de Cards](./assets/img/System/Review/System_Ongoing%20review.png)

- Review Completed
  ![Visualização da Tela de Revisão de Cards](./assets/img/System/Review/System_Review%20Completed.png)
  
## 7. Lógica de Negócio Implementada

- **CRUD Completo:** Implementação completa para todas as entidades do projeto (Assunto Principal, Tópico e Card), seguindo os princípios básicos do OutSystems.
- **Repetição Espaçada:** O sistema revisa os cards que o usuário marcou como incorretos até que sejam acertados, garantindo a retenção do conteúdo.
- **Validações:** Implementadas para assegurar que os dados inseridos pelo usuário são válidos e completos.

  ![Exemplo de Lógica de Negócio - Server Action](./assets/img/Actions/Server%20Actions/Structure.png)

## 8. Principais Server Actions e Client Actions

- **User_Create e User_Recovery:** Ações que gerenciam o cadastro e a recuperação de senha de usuários.

  ![Visualização da Ação User_Create](./assets/img/Actions/Server%20Actions/User/User_Create.png)
  
- **MainSubject_CreateOrUpdate e MainSubject_Delete:** Manipulam a criação, atualização e exclusão de Assuntos Principais.

  ![Visualização da Ação MainSubject_CreateOrUpdate](./assets/img/Actions/Server%20Actions/MainSubject/MainSubject_CreateOrUpdate.png)
  
- **Topic_CreateOrUpdate e Topic_Delete:** Realizam as operações de CRUD para os Tópicos.

  ![Visualização da Ação Topic_CreateOrUpdate](./assets/img/Actions/Server%20Actions/Topic/Topic_CreateOrUpdate.png)
  
- **Card_CreateOrUpdate e Card_Delete:** Gerenciam as operações de CRUD para os Cards.

  ![Visualização da Ação Card_CreateOrUpdate](./assets/img/Actions/Server%20Actions/Card/Card_CreateOrUpdate.png)
  
- **Get_NextCard:** Responsável por recuperar o próximo card na sequência de revisão.

  ![Visualização da Ação Get_NextCard](./assets/img/Actions/Server%20Actions/Card/Get_NextCard.png)

## 9. Processos de Revisão e Resolução de Cards

O processo de revisão é a funcionalidade central do NotepaX:

- Ao acessar a revisão, o usuário visualiza o título do card e, ao virar, a resposta correta.
- O usuário marca se acertou ou errou; cards incorretos voltam ao ciclo até que sejam acertados.
- Uma vez que todos os cards são revisados corretamente, o processo de revisão é concluído, e o usuário pode reiniciá-lo com o botão de reset.

Review

- Starting Review
  ![Visualização da Tela de Revisão de Cards](./assets/img/System/Review/System_Starting%20Review.png)

- Main Review
  ![Visualização da Tela de Revisão de Cards](./assets/img/System/Review/System_Main%20Review.png)

- Ongoing review
  ![Visualização da Tela de Revisão de Cards](./assets/img/System/Review/System_Ongoing%20review.png)

- Review Completed
  ![Visualização da Tela de Revisão de Cards](./assets/img/System/Review/System_Review%20Completed.png)

## 10. Recursos Adicionais

- **Botão Play/Refresh:** Inicia o processo de revisão dos cards e permite resetar para revisar novamente após a conclusão.

  ![Visualização do Botão Play e Reset](./assets/img/System/Card/Studio_Card%20Review%20Buttons.png)
  
- **Estruturação de Navegação:** Segue as melhores práticas de navegação para garantir que o usuário possa facilmente transitar entre as telas de assuntos, tópicos e cards.

## 11. Considerações Finais

O NotepaX foi desenvolvido como um projeto prático para consolidar os conhecimentos do módulo introdutório de OutSystems, utilizando a abordagem OutSystems Reactive. O projeto demonstrou a aplicação dos fundamentos de construção de uma aplicação completa, desde a estruturação de banco de dados até a implementação de lógica e interface de usuário, fortalecendo a base de conhecimentos essenciais para o desenvolvimento low-code.

## 12. Contribua e Conecte-se

Se você gostou deste projeto, sinta-se à vontade para fazer um **Fork**, **Compartilhar**, ou deixar uma **Star**! 🟊

Assista o vídeo do projeto clicando aqui 👇😊
[![Alt Text](./assets/img/Post/Design%20sem%20nome.png)](https://www.youtube.com/watch?v=cpPO5nh_c4M)

Confira também outros repositórios no meu [GitHub](https://github.com/cunha-leo/) e acompanhe minha jornada e atualizações profissionais no meu [LinkedIn](https://www.linkedin.com/in/leo-cunha-allves/). Vamos crescer juntos e compartilhar conhecimento!

### 🔗 Links Úteis

- [Web NotepaX](https://personal-gqcyt0y3.outsystemscloud.com/NotepaX/)
- [NotepaX GitHub](https://github.com/cunha-leo/NotepaX-OutSystems)
- [Meu GitHub](https://github.com/cunha-leo/)
- [Meu LinkedIn](https://www.linkedin.com/in/leo-cunha-allves/)
