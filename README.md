# Boas vindas ao repositório do Projeto de Trivia!

## O que foi desenvolvido

Um jogo de perguntas e respostas baseado no jogo **Trivia** _(tipo um show do milhão americano rs)_ utilizando _React e Redux_.

O app começa com uma tela onde a pessoa que joga coloca seu nome e seu e-mail. O e-mail será usado para buscar a foto associada no site [Gravatar](https://pt.gravatar.com/) (se houver).

Logo após, ela é redirecionada para o jogo onde deve escolher uma das respostas disponíveis para cada uma das perguntas. A resposta deve ser marcada antes de o contador de tempo chegar a zero, caso contrário a resposta deve ser considerada como errada.

Cada acerto dá à pessoa que joga pontos que deverão ser computados num placar no header da aplicação.

Após 5 perguntas respondidas, a pessoa que joga é redirecionada para uma tela de score, onde o texto mostrado vai depender do número de acertos.

No final de cada jogo, a pessoa que joga pode acessar o ranking com as melhores pontuações.

A pessoa que joga pode configurar algumas opções para o jogo em uma tela de configurações acessível a partir do header do app.

---

## Equipe de Desenvolvimento

- [Miguel Miranda](https://www.linkedin.com/in/miguel-miranda-a161701a4/)

- [Kevin Mendes](https://www.linkedin.com/in/kevin-mendes-silva/)

---

## Requisitos do projeto

Nesse projeto, a pessoa que joga deve conseguir completar o jogo e conseguir ver seu placar depois de responder todas as 5 perguntas, além de acessar a tela de configurações e de ranking.


1. Todos os elementos devem respeitar os atributos descritos no protótipo;

#### Tela de início:

2. A pessoa que joga deve conseguir escrever seu nome no input de texto;

3. A pessoa que joga deve conseguir escrever seu email no input de email;

4. O Botão no canto superior direito leva para a tela de configurações;

5. Após clicar no botão "Jogar", a pessoa deve ser redirecionada para a tela do jogo;

6. Ao clicar no botão "Jogar", uma requisição para a API do Trivia deve ser feita para pegar o token de jogador;

7. O token deve ser armazenado na aplicação e enviado em todas as requisições seguintes.

#### Tela do jogo:

8. O header deve conter a imagem de perfil vinda do Gravatar, o nome da pessoa (digitado na tela de início) e o placar zerado;

9. A pergunta e suas alternativas de resposta devem ser recebidas da API do Trivia;

10. A categoria da pergunta e seu texto devem ser mostradas para a pessoa que está jogando. Essas informações devem vir dos campos category e question, respectivamente;

11. As alternativas devem ser mostradas em ordem aleatória, misturando as incorretas com a correta;

12. Só deve ser possível escolher uma resposta correta por pergunta;

13. Para perguntas com type:"boolean", mostrar somente 2 campos (um para cada resposta possível);

14. Para perguntas com type:"multiple", mostrar a quantidade necessária de campos (um para cada resposta possível);

15. Ao clicar em uma resposta, a resposta correta deve ficar verde e as incorretas, vermelhas;

16. Ao clicar na resposta correta, pontos devem ser somados no placar da pessoa que está jogando;

17. A pessoa que joga tem 30 segundos para responder cada pergunta. Um temporizador deve aparecer na tela da pessoa, começando de 30 segundos e indo de forma decrescente até o zero;

18. A fórmula para cálculo dos pontos por pergunta é: `10 + (timer * dificuldade)`, onde timer é o tempo restante no contador de tempo e dificuldade é `hard: 3, medium: 2, easy: 1`, dependendo da pergunta. Exemplo: Se no momento da resposta correta o timer estiver contando 17 segundos, e a dificuldade da pergunta é 2 (média), a pontuação deve ser: `10 + (17 * 2) = 44`;

19. Caso a pergunta não seja respondida a tempo, a resposta é considerada como errada;

20. Respostas incorretas não somam pontos ao placar;

21. Após a resposta ser dada, o botão "Próxima" deve aparecer. Ao clicar nesse botão, a próxima pergunta deve aparecer na tela;

22. Após responder 5 perguntas, a pessoa que está jogando deve ser redirecionada para a tela de feedback;

23. Caso a API retorne um response_code: 3 (token expirado), a pessoa que está jogando deve ser redirecionada para a tela de início, sem nenhuma informação prévia salva.

#### Tela de feedback:

24. Deve-se mostrar o placar no header junto com o nome da pessoa que está jogando;

25. A mensagem deve ser "Podia ser melhor..." caso a pessoa que está jogando acerte menos de 3 perguntas;

26. A mensagem deve ser "Mandou bem!" caso a pessoa que está jogando acerte 3 perguntas ou mais;

27. O placar da pessoa que está jogando também deve ser mostrado em uma mensagem de feedback;

28. O número de perguntas que a pessoa que está jogando acertou deve ser mostrado;

29. Ao clicar no botão "Jogar novamente" a pessoa que está jogando deve ser redirecionada para a tela de início, sem nenhuma informação prévia salva;

30. Ao clicar no botão "Ver Ranking" a pessoa que está jogando deve ser redirecionada para a tela de ranking.

#### Tela de ranking:

31. Deve-se mostrar uma lista com a imagem de perfil vinda do Gravatar, nome e pontuação das pessoas que jogaram em ordem decrescente (da maior pontuação para a menor);

32. O ranking deve ser armazenado no navegador através do `localStorage`.

#### Tela de configurações:

33. Ao mudar o valor do dropdown categoria, apenas perguntas da categoria selecionada devem aparecer para a pessoa que está jogando. Essa configuração será identificada pela chave category no retorno da API;

34. Ao mudar o valor do dropdown dificuldade, apenas perguntas da dificuldade selecionada devem aparecer para a pessoa que está jogando. Essa configuração será identificada pela chave difficulty no retorno da API;

35. Ao mudar o valor do dropdown tipo, apenas perguntas do tipo selecionado devem aparecer para a pessoa que está jogando. Essa configuração será identificada pela chave type no retorno da API.

---
