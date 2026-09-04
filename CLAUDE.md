# Instruções do projeto

Idioma: **responda sempre em português do Brasil**, incluindo planos, perguntas,
resumos e mensagens de commit. Termos técnicos consagrados podem ficar em inglês.

## Fluxo obrigatório: pensar antes de codar

Não comece a escrever código assim que receber um pedido. Siga estas quatro
etapas, nesta ordem, para qualquer tarefa que envolva criar ou alterar código.

### 1. Entender antes de agir

Antes de propor qualquer solução:

- Leia o código existente que a mudança vai tocar. Não presuma como algo funciona.
- Identifique o problema real por trás do pedido, não apenas a solução sugerida.
- Se duas leituras razoáveis do pedido levarem a trabalhos diferentes, **pergunte**.
  Apresente as opções com o custo/benefício de cada uma, em vez de adivinhar.
- Decisões de rotina, com um padrão óbvio, você mesmo toma — só diga qual adotou.

### 2. Planejar e submeter à aprovação

Para qualquer tarefa que não seja trivial (mais de um arquivo, mudança de
comportamento, nova funcionalidade), apresente um plano **antes** de editar:

- O que será alterado, arquivo por arquivo.
- Em que ordem, quebrado em etapas pequenas e verificáveis.
- O que fica **fora** do escopo.
- Quais riscos existem e o que pode quebrar.

Espere a aprovação do plano antes de executar.

### 3. Executar por etapas

- Uma etapa de cada vez, mantendo o projeto em estado funcional ao final de cada uma.
- Mudança mínima que resolve o problema. Não amplie o escopo por conta própria.
- Se durante a execução o plano se mostrar errado, pare, explique o que mudou e
  proponha o ajuste — não siga um plano que você já sabe estar furado.

### 4. Verificar de verdade

Uma etapa só está concluída quando foi comprovada:

- Rode os testes, o lint e o typecheck do projeto. Cole a saída real.
- Para correção de bug: reproduza a falha primeiro, depois mostre ela resolvida.
- Nunca desative, pule ou marque um teste como ignorado para "ficar verde".
- Relate o resultado honestamente. Se algo falhou ou ficou de fora, diga
  explicitamente o que foi e por quê. Não afirme que está pronto sem ter verificado.

## Como reportar

- Seja direto: o que foi feito, o que foi verificado, o que ficou pendente.
- Cite arquivos no formato `caminho/arquivo.ext:linha`.
- Sem elogios, sem enrolação, sem repetir o que já foi combinado.

## Skill `/planejar`

O fluxo acima está detalhado, passo a passo, na skill do projeto em
`.claude/skills/planejar/SKILL.md`. Use `/planejar` para conduzi-lo
explicitamente em uma tarefa.
