# Prompts AI

![AI-ready](https://img.shields.io/badge/AI-ready-purple?style=flat-square) 

**Breve descrição:** Este arquivo reúne princípios, exemplos práticos e templates para ajudar você a formular prompts claros e eficientes ao interagir com modelos de IA. Use os guias abaixo para definir papel, contexto e formato de saída desejado.

## Princípios básicos
Para criar um prompt eficaz, responda às perguntas abaixo:
- Quem?
- Quando?
- Para quê?

Itens opcionais:
- Peça que a IA faça perguntas de esclarecimento
- Especifique o tipo e o formato da resposta desejada

### Quem?
Defina o papel, a experiência e o tom que a IA deve assumir para orientar a perspectiva da resposta.
Exemplo: "Atue como consultor e arquiteto SAP ABAP, com ampla experiência e comunicação objetiva."

### Quando?
Contextualize o momento, o status ou o período relevante para a solicitação, assim a IA pode adaptar sua recomendação.
Exemplo: "Este é um desenvolvimento já concluído que precisa ser revisado e otimizado." 

### Para quê?
Explique claramente o objetivo final da solicitação, para que a IA direcione a resposta ao resultado esperado.
Exemplo: "Preciso revisar uma classe seguindo as guidelines de design e qualidade, e sugerir melhorias." 

### Faça perguntas
Peça à IA que solicite informações adicionais quando necessário — isso evita respostas incompletas.
Exemplo: "Faça perguntas para obter contexto ou dados faltantes antes de elaborar uma solução." 

### Tipo e saída de resposta
Indique o formato desejado (ex.: lista, resumo, passos, código) e o nível de detalhe esperado.
Exemplo: "Forneça a resposta em uma lista numerada com passos acionáveis e exemplos de código quando aplicável."

## Atento as respostas
Para melhor performance, fique atento as perguntas sugeridas ao final e tente ligar a sequencia de processamento a partir dessas respostas para manter os passos logicos.


# Prompt para Documentação SAP ABAP (Formato Padrão)

Atue como especialista SAP ABAP e crie uma documentação técnica seguindo o formato padrão abaixo:

## FORMATO DE SAÍDA ESPERADO:

1. **Estrutura de Colunas:**
   - Coluna 1 (4 chars): Indicadores de linha
     - `U1` = Linha de título/seção (underline 1)
     - `U2` = Linha de subtítulo/seção (underline 2)
     - `AS` = Linha de texto normal (assemble)
     - `B1` = Item de lista com bullet (bullet 1)
     - `=`  = Continuação de linha anterior
   
2. **Formatação:**
   - Cada linha DEVE começar com DUAS tabulações (tabs)
   - Após as tabulações: Indicador de coluna + TAB + Texto
   - Limite de 72 caracteres por linha de texto
   - Quebras de linha usam `=` como indicador

3. **Seções Obrigatórias:**
```
   U1    &PURPOSE&
   U1    &INTEGRATION&
   U1    &PREREQUISITES&
   U1    &FEATURES&
   U2    &SELECTION&
   U2    &STANDARD_VARIANTS&
   U2    &OUTPUT&
   U1    &ACTIVITIES&
   U1    &EXAMPLE&
```

4. **Regras de Conteúdo:**
   - &PURPOSE&: Objetivo principal, descrição funcional, RICEF ID
   - &INTEGRATION&: Integrações com outros objetos/transações
   - &PREREQUISITES&: Pré-requisitos (usar B1 para lista)
   - &FEATURES&: Características principais (usar B1 para lista)
   - &SELECTION&: Como acessar/executar
   - Seções vazias devem conter apenas AS sem texto

## INFORMAÇÕES NECESSÁRIAS:

Para gerar a documentação, preciso de:
- Nome do objeto (Function Group, View, Programa, etc.)
- Descrição funcional
- RICEF ID (se aplicável)
- Tabelas/objetos relacionados
- Campos principais
- Integrações (se houver)
- Pré-requisitos
- Funcionalidades principais

## EXEMPLO DE USO:

"Crie documentação para o Function Group SAPLZPP_XXXX que mantém a tabela 
ZPP_XXXX com campos MANDT, WERKS, FIELD1. RICEF: AMS_GLXXX / ETISXXX. 
Objetivo: [descrever objetivo]"

---

IMPORTANTE: 
- Idioma: [Português ou Inglês - especificar]
- Sempre manter limite de 72 caracteres por linha
- Usar duas tabulações no início de cada linha
- Seguir rigorosamente os indicadores de coluna (U1, AS, B1, =)