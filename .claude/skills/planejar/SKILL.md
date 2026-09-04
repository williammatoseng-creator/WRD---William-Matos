---
name: planejar
description: Conduz o fluxo completo "pensar antes de codar" — investiga o código, faz as perguntas que faltam, apresenta um plano por etapas para aprovação, executa uma etapa de cada vez e verifica cada uma com a saída real dos testes. Use quando o usuário invocar /planejar, ou quando pedir para planejar, estruturar, pensar antes de mexer, avaliar como fazer, ou quando a tarefa envolver mais de um arquivo, mudança de comportamento ou nova funcionalidade — inclusive quando ele só descrever a necessidade, como "como a gente faria isso?", "antes de mexer, me diz o que vai mudar" ou "não sai codando, pensa primeiro".
---

# Planejar antes de codar

Objetivo: nunca escrever código a partir de suposição. Primeiro entender, depois
combinar o plano, depois executar em etapas verificáveis.

Responda sempre em **português do Brasil**.

## Fase 1 — Investigar

Não escreva nem edite nada nesta fase. Levante os fatos:

1. **Ler o código que a mudança vai tocar.** Encontre os arquivos, funções e
   testes envolvidos. Nunca presuma como algo funciona — abra e leia.
2. **Mapear o entorno.** O que chama esse código? O que depende dele? Existe
   padrão parecido já resolvido no projeto que deva ser seguido?
3. **Identificar a infraestrutura de verificação.** Qual é o comando de teste,
   de lint e de typecheck? Onde ficam os testes existentes? Se não houver,
   registre isso — vai virar risco no plano.
4. **Separar o pedido do problema.** O usuário pediu uma solução; qual é o
   problema por trás dela? Se a solução pedida não resolve o problema real,
   diga isso no plano, com a alternativa.

Ao final desta fase, você deve conseguir citar arquivos concretos no formato
`caminho/arquivo.ext:linha`. Se não consegue, ainda não investigou o suficiente.

## Fase 2 — Perguntar o que estiver ambíguo

Antes de apresentar o plano, resolva as dúvidas que mudariam o trabalho:

- **Pergunte** quando duas leituras razoáveis do pedido levarem a implementações
  diferentes. Apresente as opções com o custo/benefício de cada uma.
- **Decida sozinho** as escolhas de rotina que têm um padrão óbvio no projeto —
  apenas registre no plano qual padrão você adotou e por quê.
- Uma pergunta boa é fechada e acionável ("A validação deve rejeitar ou apenas
  avisar?"), não aberta ("Como você quer que funcione?").
- Não acumule perguntas irrelevantes. Se nada é ambíguo, siga direto para o plano.

## Fase 3 — Apresentar o plano e esperar aprovação

O plano tem cinco seções, nesta ordem:

1. **Entendimento** — o problema em uma ou duas frases, com os arquivos
   relevantes citados. Mostra que você leu o código, não que adivinhou.
2. **Etapas** — numeradas, pequenas, na ordem de execução. Cada etapa diz
   qual arquivo muda e **como ela será verificada**. Uma etapa que não pode
   ser verificada está grande demais: quebre-a.
3. **Fora do escopo** — o que deliberadamente não será feito nesta rodada.
   Protege contra o escopo crescer sozinho durante a execução.
4. **Riscos** — o que pode quebrar, o que não tem cobertura de teste, o que
   depende de informação que você não tem.
5. **Verificação final** — os comandos exatos que serão rodados ao final
   (teste, lint, typecheck) para comprovar que está pronto.

**Pare aqui e espere a aprovação.** Não comece a editar porque o plano "está
claro". A aprovação é do usuário, não sua.

## Fase 4 — Executar por etapas

- Uma etapa de cada vez. Ao final de cada uma, o projeto fica funcional.
- Mudança mínima que resolve o problema. Não aproveite a passagem para
  refatorar, renomear ou "melhorar de leve" o que está em volta.
- **Se o plano se mostrar errado no meio do caminho, pare.** Explique o que
  você descobriu, por que o plano não se sustenta e proponha o ajuste. Nunca
  siga executando um plano que você já sabe estar furado.
- Se surgir um problema fora do escopo, anote e relate ao final — não corrija
  por conta própria.

## Fase 5 — Verificar de verdade

Uma etapa só está concluída quando foi comprovada:

- Rode os testes, o lint e o typecheck. **Cole a saída real**, não um resumo
  do que você espera que tenha acontecido.
- Para correção de bug: **reproduza a falha primeiro**, mostre o erro, depois
  aplique a correção e mostre o mesmo comando passando.
- Para funcionalidade nova: escreva o teste que a cobre. Sem teste, diga
  explicitamente que ficou sem cobertura.
- **Prove que o teste novo tem valor.** Um teste que passa não demonstra nada
  se ele passaria também com o defeito presente. Desfaça a correção
  temporariamente — em cópia, nunca no arquivo bom — e confirme que o teste
  falha. Se ele passa dos dois lados, ele não protege nada: refaça o teste,
  não o código. Volte ao estado corrigido antes de seguir.
- **Nunca** desative, pule ou marque um teste como ignorado para ficar verde.
  Teste falhando é informação, não obstáculo.

## Fase 6 — Reportar

Direto, sem elogios e sem repetir o que já foi combinado:

- **Feito** — o que mudou, com os arquivos em `caminho/arquivo.ext:linha`.
- **Verificado** — quais comandos rodaram e qual foi o resultado.
- **Pendente** — o que falhou, o que ficou de fora e por quê.

Se algo não foi verificado, diga que não foi verificado. Nunca afirme que
está pronto sem ter comprovado.

## Quando pular este fluxo

Tarefa realmente trivial — corrigir um typo, ajustar uma string, alterar uma
constante em um único arquivo — não precisa de plano formal. Faça, verifique
e relate. Na dúvida entre trivial e não trivial, trate como não trivial.
