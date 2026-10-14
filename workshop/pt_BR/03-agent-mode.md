<!-- l10n-sync: source-file="03-agent-mode.md" -->
# Parte 3: Construa o Jogo com Fluxos Agênticos

---

Esta é a parte em que o Copilot passa de planejador a implementador. Em vez de escrever código linha por linha, você descreve o que deseja e deixa o Copilot realizar o trabalho nos arquivos que precisam mudar.

## Tarefa 1: Conecte a Batalha

<!-- track:vscode:start -->
1. Mude para o modo **Agent** no Copilot Chat.
2. Insira este prompt:
<!-- track:vscode:end -->

<!-- track:cli:start -->
1. Volte o Copilot CLI para seu fluxo normal de codificação (ou permaneça no modo autopilot se quiser que o Copilot continue trabalhando até você pará-lo).
2. Mencione o arquivo da página para contexto extra, se for útil: `@src/pages/index.astro`
3. Insira este prompt:
<!-- track:cli:end -->

   > Add client-side JavaScript to the battle page that:
   > 1. When the Battle button is clicked, gets both usernames from the inputs
   > 2. Validates both are filled (show error if not)
   > 3. Fetches both users' contribution data in parallel from our API
   > 4. Renders contribution graphs as colored grids — each day is a colored square using GitHub's color palette
   > 5. Shows a VS badge between the two users
   > 6. Displays username, total contributions, and date range for each user
   > 7. Handles loading states and errors
   > 8. Also triggers on Enter key in input fields.
   > 9. Simple UI for now that is already scaffolded.
   >
   > Use TypeScript interfaces for the contribution data structure.

<!-- track:vscode:start -->
3. Deixe o Agent Mode trabalhar na implementação em `index.astro`.
4. Revise as alterações propostas na visualização de diff antes de aceitá-las.
<!-- track:vscode:end -->

<!-- track:cli:start -->
4. Deixe o Copilot CLI trabalhar na implementação em `src/pages/index.astro`.
5. Use `/diff` para inspecionar as alterações geradas e, em seguida, aprove-as.
<!-- track:cli:end -->

## Tarefa 2: Teste a Batalha

> **⚠️ Não está vendo as mudanças?** Se a página de batalha não tiver atualizado, pare o servidor de desenvolvimento (`Ctrl+C`) e reinicie com `npm run dev`, depois atualize seu navegador.

1. Insira `octocat` e `torvalds` como os dois nomes de usuário e clique em **Battle**.
2. Você deve ver ambos os gráficos de contribuição renderizados lado a lado com grids coloridos.
3. Teste os casos de erro:
   - Deixe um ou ambos os campos vazios e clique em Battle — você deve ver um erro de validação.
   - Insira um nome de usuário inválido — o app deve exibir um erro da API.
4. Teste pressionando **Enter** em qualquer campo de entrada — deve disparar a batalha assim como clicar no botão.

## Tarefa 3: Itere com o Copilot

Se algo não estiver totalmente correto, dê feedback de acompanhamento diretamente ao Copilot. Por exemplo:

- *"The contribution squares are too large, make them 12x12px"*
- *"Add a hover tooltip showing the date and contribution count"*
- *"The loading state needs a pulse animation"*

<!-- track:vscode:start -->
O Agent Mode lida com alterações em múltiplos arquivos e iterações de forma natural. Cada prompt de acompanhamento se baseia na conversa anterior, permitindo que você refine a implementação de forma incremental sem recomeçar do zero.
<!-- track:vscode:end -->

<!-- track:cli:start -->
As sessões do Copilot CLI mantêm o histórico, então cada prompt de acompanhamento se baseia no anterior. Use `/session` ou `/context` se quiser inspecionar o que o Copilot está carregando adiante, e `/review` depois de uma iteração maior se quiser uma passada extra em busca de bugs ou polimento.
<!-- track:cli:end -->

## Dicas para Esta Parte

- **Seja específico sobre o que você quer** — requisitos claros levam a resultados melhores.
- **Divida tarefas grandes em prompts menores** se o Copilot sair do rumo.
- **Revise as alterações antes de aceitar** — é mais rápido inspecionar o código gerado do que reescrevê-lo depois.
- **Teste o app imediatamente após cada passagem de implementação** para que os problemas fiquem localizados.

## ✅ Parte 3 Concluída

Você aprendeu a:

- Usar o Copilot para **trabalho de implementação em múltiplos arquivos**
- **Iterar nos resultados** com prompts de acompanhamento focados
- Lidar com o **ciclo completo de uma funcionalidade** — implementação, revisão, teste e refinamento
