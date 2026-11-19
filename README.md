# Banco de Horas

Site simples para calcular hora extra, desconto e o saldo do banco de horas a partir das batidas do ponto.

Você preenche a entrada, o almoço e a saída. O site mostra na hora:

- se o dia gerou hora extra ou desconto;
- como fica o seu saldo;
- a que horas sair para fechar a jornada, para não mexer no saldo ou para usar as horas do banco.

---

## Funcionalidades

- **Saldo do banco de horas** sempre visível no topo, atualizado a cada dia lançado.
- **Batidas do ponto**: entrada, saída para almoço, volta do almoço e saída. O botão *Marcar agora* coloca a hora atual na próxima batida vazia.
- **Saídas no meio do expediente** (médico, banco…): o tempo fora é descontado do dia.
- **Régua do dia**: linha do tempo com o tempo trabalhado, o almoço, as saídas e o que falta trabalhar.
- **Horários de saída**: a que horas sair para fechar a jornada, para não mexer no saldo, para começar a gerar hora extra ou para usar todo o saldo.
- **Tolerância configurável**:
  - *Por batida* (padrão, 5 min): cada batida pode variar até a tolerância sem contar; passou disso, conta a diferença inteira daquela batida.
  - *Pelo total do dia*: se a diferença do dia ficar dentro da tolerância, não conta; passou, conta tudo.
- **Horário de trabalho por dia da semana**, com dias de folga. Trabalho em dia de folga conta todo como hora extra.
- **Lançar como dia normal**: lança o dia com o horário padrão, sem hora extra nem desconto, em um clique.
- **Lançar folga**, de um dia ou de vários dias seguidos, com motivo opcional:
  - *Folga usando o banco de horas*: desconta do saldo a jornada de cada dia.
  - *Folga sem desconto*: feriado, atestado, férias ou folga dada pela empresa. O saldo não muda.
- **Feriados nacionais automáticos**: no dia do feriado, o site sugere lançar como folga sem desconto em um clique. Carnaval e Corpus Christi aparecem como ponto facultativo. Pode ser desligado em Ajustes.
- **Dias lançados**: histórico com o resultado e o saldo depois de cada dia. Dá para **editar** ou **excluir** qualquer dia, e o saldo é corrigido sozinho.
- **Resumo do mês**: escolha o mês e veja a hora extra, os descontos, as folgas, o resultado e como o saldo começou e terminou.
- **Desfazer**: logo depois de lançar, salvar, lançar folga ou excluir, um botão permite voltar atrás.
- **Sequência automática**: depois de lançar ou editar, o site vai para o próximo dia útil ainda não lançado.
- **Backup**: baixe um arquivo com todos os dados e restaure em outro navegador, computador ou celular.
- **Como usar**: guia dentro do próprio site explicando cada parte.
- Funciona no computador e no celular, com tema claro e escuro conforme o sistema.

## Como usar

### Uma vez só

1. Abra **Ajustes** e coloque o **saldo atual** do seu extrato de ponto. Digite só os números: `430` vira `04:30`.
2. Confira o **horário de trabalho** de cada dia da semana.
3. Confira a **tolerância** e a regra (por batida ou pelo total do dia).

### No dia a dia

1. O site abre sempre no dia de hoje. Use **‹** e **›** para trocar de dia.
2. Preencha as batidas. Enquanto a saída estiver vazia, o quadro ao lado mostra a que horas sair.
3. Com a saída preenchida, aparece o resultado do dia e como fica o saldo.
4. Clique em **Lançar dia**. O resultado entra no saldo e o site vai para o próximo dia útil.

Em um dia sem nada diferente, use **Lançar como dia normal**.

### Exemplo da tolerância por batida

Horário padrão das 07:00 às 17:00, com tolerância de 5 min por batida:

| Batida | Real | Diferença | Conta? |
|---|---|---|---|
| Entrada | 06:53 | 7 min antes | Sim, **+7 min** |
| Saída | 17:02 | 2 min depois | Não (dentro da tolerância) |

Resultado do dia: **+7 min** de hora extra.

## Onde ficam os dados

Os dados ficam salvos **apenas no navegador** de quem usa o site (`localStorage`). Nada é enviado para servidor nenhum, e o repositório não guarda nenhuma informação pessoal.

Por isso:

- cada navegador e cada aparelho tem os seus próprios dados;
- limpar os dados do navegador apaga o saldo e o histórico;
- abrir o arquivo direto do computador e abrir pelo GitHub Pages são endereços diferentes, então os dados não são compartilhados entre eles.

Para não perder nada, use **Ajustes → Baixar backup** de vez em quando. O arquivo `.json` baixado pode ser carregado em **Ajustes → Restaurar backup** em qualquer navegador ou aparelho.

## Rodar no computador

Não precisa instalar nada. Baixe o `index.html` e abra no navegador com dois cliques.

## Publicar no GitHub Pages

1. Crie um repositório público no GitHub e envie o `index.html` (e este `README.md`) para a branch `main`.
2. No repositório, vá em **Settings → Pages**.
3. Em **Source**, escolha **Deploy from a branch**. Em **Branch**, escolha `main` e a pasta `/ (root)`. Clique em **Save**.
4. Depois de 1 a 2 minutos, o site fica disponível em `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`.

A cada novo `git push`, o site é atualizado sozinho.

## Tecnologia

- Um único arquivo `index.html` com HTML, CSS e JavaScript puros, sem frameworks e sem etapa de build.
- Fonte [Manrope](https://fonts.google.com/specimen/Manrope) carregada do Google Fonts. Sem internet, o site usa a fonte do sistema e continua funcionando.
- Ícone da aba em SVG embutido no próprio arquivo.

## Aviso

Este site é uma ferramenta pessoal de apoio para conferir as horas. O saldo oficial é sempre o do sistema de ponto da empresa.
