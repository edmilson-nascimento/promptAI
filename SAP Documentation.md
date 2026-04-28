Entendido perfeitamente. O formato correto é:

- Indicador de coluna + **TAB** + Texto (sem espaços entre indicador e tab)
- A linha começa **sem** tabulações iniciais

Ou seja, o que eu estava gerando errado era as duas tabulações iniciais — o formato real é direto: `U1\t&PURPOSE&`.

Aqui está o prompt atualizado:

---

```markdown
# Prompt para Documentação SAP ABAP (Formato Padrão SE61)

Atue como especialista SAP ABAP e crie documentação técnica seguindo
o formato exato abaixo.

## FORMATO DE SAÍDA ESPERADO:

1. **Estrutura de Colunas:**
   - Coluna 1 (2 chars): Indicador de linha
     - `U1` = Título de secção principal (underline 1)
     - `U2` = Subtítulo de secção (underline 2)
     - `AS` = Linha de texto normal (assemble)
     - `B1` = Item de lista com bullet (bullet 1)
     - `=`  = Continuação de linha anterior
   
2. **Formatação CRÍTICA:**
   - Cada linha começa com: INDICADOR + TAB + Texto
   - NÃO há tabulações ou espaços antes do indicador
   - Limite de 72 caracteres por linha de texto
   - Quebras de linha usam `=` como indicador

3. **Exemplo correto:**
```
U1	&PURPOSE&
AS	This method retrieves the equipment number for odor
=	validation against the compatibility matrix.
B1	Returns empty if plant or equipment is initial.
U2	&SELECTION&
AS	Private method - called internally within ORDER_ASSIGN.
```

4. **Seções Obrigatórias (nesta ordem):**
```
U1	&PURPOSE&
U1	&INTEGRATION&
U1	&PREREQUISITES&
U1	&FEATURES&
U2	&SELECTION&
U2	&STANDARD_VARIANTS&
U2	&OUTPUT&
U1	&ACTIVITIES&
U1	&EXAMPLE&
```

5. **Regras de Conteúdo:**
   - `&PURPOSE&`: Objetivo principal, descrição funcional, RICEF ID
   - `&INTEGRATION&`: Chamadores e delegações (Called by / Delegates to)
   - `&PREREQUISITES&`: Pré-requisitos (usar B1 para lista)
   - `&FEATURES&`: Características principais (usar B1 para lista)
   - `&SELECTION&`: Como aceder/executar o método
   - `&OUTPUT&`: Parâmetros de retorno (usar AS por parâmetro)
   - Secções sem conteúdo: apenas `AS` sem texto (linha vazia)

## INFORMAÇÕES NECESSÁRIAS:

Para gerar a documentação, fornecer:
- Nome do objeto / método
- Descrição funcional
- RICEF ID (se aplicável)
- Chamadores conhecidos
- Delegações (outros métodos/classes chamados)
- Parâmetros de entrada relevantes
- Parâmetros de saída / retorno
- Pré-requisitos
- Funcionalidades principais

## EXEMPLO DE PEDIDO:

"Crie documentação para o método GET_EQUIPMENT_ODOR da classe
ZCL_COCD_EQP_EQUIP_CTRL. RICEF: AMS_GL013/ETIS094.
Objetivo: Recupera o EQUNR canónico para validação do matriz de odor."

---

IMPORTANTE:
- Idioma: [Português ou Inglês - especificar]
- Limite HARD de 72 caracteres por linha de texto
- Indicador + TAB + Texto — sem prefixo antes do indicador
- Seguir rigorosamente os indicadores (U1, U2, AS, B1, =)
- Secções vazias devem conter `AS` + TAB (sem texto)
```

---
