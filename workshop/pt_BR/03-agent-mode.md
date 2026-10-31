<!-- l10n-sync: source-file="workshop/03-agent-mode.md" -->
# Parte 3: Construa o jogo com fluxos de trabalho agênticos

---

Nesta parte, o Copilot passa de planejador a implementador. Em vez de escrever código linha por linha, você descreve o que quer e deixa o Copilot trabalhar nos arquivos necessários.

## Tarefa 1: Conecte a batalha

<!-- track:vscode:start -->
1. Mude para o modo **Agent** no Copilot Chat.
2. Digite este prompt:
<!-- track:vscode:end -->

<!-- track:cli:start -->
1. Volte ao fluxo padrão de programação do Copilot CLI (ou continue no modo autopilot se quiser que o Copilot avance até você interrompê-lo).
2. Se for útil, mencione o arquivo da página para dar mais contexto: `@src/pages/index.astro`.
3. Digite este prompt:
<!-- track:cli:end -->

   > Adicione JavaScript do lado do cliente à página de batalha para que:
   > 1. Ao clicar no botão Battle, os dois nomes de usuário sejam obtidos dos campos.
   > 2. Seja verificado se ambos foram preenchidos (mostre um erro caso contrário).
   > 3. Os dados de contribuições dos dois usuários sejam buscados em paralelo pela nossa API.
   > 4. Os gráficos de contribuições sejam exibidos em grades coloridas — cada dia deve ser um quadrado colorido da paleta do GitHub.
   > 5. Um selo VS seja exibido entre os dois usuários.
   > 6. Sejam exibidos o nome de usuário, o total de contribuições e o intervalo de datas de cada pessoa.
   > 7. Os estados de carregamento e os erros sejam tratados.
   > 8. A ação também seja disparada ao pressionar Enter nos campos.
   > 9. Por enquanto, a interface simples já criada seja mantida.
   >
   > Use interfaces do TypeScript para a estrutura de dados de contribuições.

<!-- track:vscode:start -->
3. Deixe o Agent Mode implementar as alterações em `index.astro`.
4. Revise as alterações propostas na visualização de diff antes de aceitá-las.
<!-- track:vscode:end -->

<!-- track:cli:start -->
4. Deixe o Copilot CLI trabalhar em `src/pages/index.astro`.
5. Use `/diff` para inspecionar as alterações geradas e depois aprove-as.
<!-- track:cli:end -->

## Tarefa 2: Teste a batalha

> **⚠️ Não está vendo as alterações?** Se a página de batalha não foi atualizada, pare o servidor de desenvolvimento (`Ctrl+C`), reinicie com `npm run dev` e atualize o navegador.

1. Insira `octocat` e `torvalds` como os nomes de usuário e clique em **Battle**.
2. Você deve ver os dois gráficos de contribuições lado a lado, com grades de quadrados coloridos.
3. Teste os casos de erro:
   - Deixe um ou ambos os campos vazios e clique em Battle — deve aparecer um erro de validação.
   - Insira um nome de usuário inválido — o aplicativo deve exibir um erro da API.
4. Pressione **Enter** em qualquer campo — a batalha deve ser iniciada como se você tivesse clicado no botão.

## Tarefa 3: Itere com o Copilot

Se algo não estiver certo, envie comentários de acompanhamento ao Copilot. Por exemplo:

- *“Os quadrados de contribuição estão grandes demais; ajuste para 12 × 12 px.”*
- *“Adicione uma dica ao passar o cursor que mostre a data e o número de contribuições.”*
- *“O estado de carregamento precisa de uma animação pulsante.”*

<!-- track:vscode:start -->
O Agent Mode lida naturalmente com alterações em vários arquivos e iterações. Cada prompt de acompanhamento aproveita a conversa anterior, para que você refine a implementação aos poucos sem começar do zero.
<!-- track:vscode:end -->

<!-- track:cli:start -->
As sessões do Copilot CLI mantêm o histórico, então cada acompanhamento se baseia nos anteriores. Use `/session` ou `/context` para inspecionar o contexto que o Copilot está mantendo e `/review` após uma iteração maior para procurar bugs ou melhorias.
<!-- track:cli:end -->

## Dicas para esta parte

- **Seja específico sobre o que você quer** — requisitos claros levam a resultados melhores.
- **Divida tarefas grandes em prompts menores** se o Copilot sair do rumo.
- **Revise as alterações antes de aceitá-las** — inspecionar o diff é mais rápido do que reescrever depois.
- **Teste o aplicativo logo após cada etapa de implementação** para localizar os problemas.

## ✅ Parte 3 concluída

Você aprendeu a:

- Usar o Copilot para **implementar funcionalidades em vários arquivos**.
- **Iterar nos resultados** com comentários de acompanhamento específicos.
- Gerenciar o **ciclo completo de uma funcionalidade**: implementação, revisão, teste e refinamento.
