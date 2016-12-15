---
title: "Tipos que admiten valores null (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Nullable"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "? [Visual Basic]"
  - "tipos de datos [Visual Basic], que aceptan valores NULL"
  - "tipos que aceptan valores NULL"
  - "tipos que admiten valores null [Visual Basic]"
  - "tipos [Visual Basic], que aceptan valores NULL"
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Tipos que admiten valores null (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

A veces trabaja con un tipo de valor que no tiene un valor definido en ciertas circunstancias.  Por ejemplo, puede que un campo de una base de datos tenga que distinguir entre tener un valor asignado que es significativo y no tener un valor asignado.  Los tipos de valor se pueden extender para tomar sus valores normales o un valor nulo.  Este tipo de extensión se denomina un *tipo que acepta valores NULL*.  
  
 Los tipos que aceptan valores NULL se construyen a partir de la estructura genérica <xref:System.Nullable%601>.  Considere una base de datos que realiza el seguimiento de las actividades relacionadas con el trabajo.  El ejemplo siguiente construye un tipo `Boolean` que acepta valores NULL y declara una variable de ese tipo.  Puede escribir la declaración de tres maneras:  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_1.vb)]  
  
 La variable `ridesBusToWork` pueden contener un valor `True`, un valor `False` o ninguno de ellos.  Su valor predeterminado inicial es ningún valor, lo que en este caso podría significar que todavía no se ha obtenido la información correspondiente a esta persona.  `False`, por su parte, podría significar que se ha obtenido la información y la persona no utiliza el autobús para ir al trabajo.  
  
 Puede declarar variables y propiedades con tipos que aceptan valores NULL y puede declarar una matriz con elementos de un tipo que acepta valores NULL.  Puede declarar procedimientos con tipos que aceptan valores NULL como parámetros y puede devolver un tipo que acepta valores NULL de un procedimiento `Function`.  
  
 No puede construir un tipo que acepta valores NULL en un tipo de referencia como una matriz, un objeto `String` o una clase.  El tipo subyacente debe ser un tipo de valor.  Para obtener más información, vea [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
## Utilizar una variable de tipo que acepta valores NULL  
 Los miembros más importantes de un tipo que acepta valores NULL son sus propiedades <xref:System.Nullable%601.HasValue%2A> y <xref:System.Nullable%601.Value%2A>.  En una variable de un tipo que acepta valores NULL, <xref:System.Nullable%601.HasValue%2A> indica si la variable contiene un valor definido.  Si <xref:System.Nullable%601.HasValue%2A> tiene el valor `True`, puede leer el valor de <xref:System.Nullable%601.Value%2A>.  Observe que <xref:System.Nullable%601.HasValue%2A> y <xref:System.Nullable%601.Value%2A> son propiedades de tipo `ReadOnly`.  
  
### Valores predeterminados  
 Cuando declara una variable con un tipo que acepta valores NULL, su propiedad <xref:System.Nullable%601.HasValue%2A> tiene un valor predeterminado de `False`.  Esto significa que la variable no tiene ningún valor definido de forma predeterminada, en lugar del valor predeterminado de su tipo de valor subyacente.  En el ejemplo siguiente, la variable `numberOfChildren` no tiene inicialmente ningún valor definido, aunque el valor predeterminado del tipo `Integer` es 0.  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_2.vb)]  
  
 Un valor nulo es útil para indicar un valor indefinido o desconocido.  Si `numberOfChildren` se hubiese declarado como `Integer`, no habría ningún valor que indicase que la información no está disponible actualmente.  
  
### Almacenar valores  
 El almacenamiento de un valor en una variable o una propiedad que acepta valores NULL se realiza de la manera habitual.  En el ejemplo siguiente se asigna un valor a la variable `numberOfChildren` declarada en el ejemplo anterior.  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_3.vb)]  
  
 Si una variable o una propiedad de un tipo que acepta valores NULL contiene un valor definido, puede determinar que vuelva a su estado inicial, es decir, sin ningún valor asignado.  Para ello, establece la variable o la propiedad como `Nothing`, según se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_4.vb)]  
  
> [!NOTE]
>  Aunque puede asignar `Nothing` a una variable que acepta valores Null, no puede probarla con `Nothing` usando el signo igual.  La comparación que usa el signo igual, `someVar = Nothing`, siempre se evalúa como `Nothing`.  Puede probar la propiedad <xref:System.Nullable%601.HasValue%2A> de la variable con `False` o probar mediante el operador `Is` o `IsNot`.  
  
### Recuperar valores  
 Para recuperar el valor de una variable de un tipo que acepta valores NULL, debe probar previamente su propiedad <xref:System.Nullable%601.HasValue%2A> para confirmar que incluye un valor.  Si intenta leer el valor cuando <xref:System.Nullable%601.HasValue%2A> es `False`, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] produce una excepción <xref:System.InvalidOperationException>.  En el ejemplo siguiente se muestra la manera recomendada de leer la variable `numberOfChildren` de los ejemplos anteriores.  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_5.vb)]  
  
## Comparar tipos que aceptan valores NULL  
 Cuando se usan en expresiones booleanas variables `Boolean` que aceptan valores NULL, el resultado puede ser `True`, `False` o `Nothing`.  A continuación, se muestra la tabla de valores de verdad para `And` y `Or`.  Dado que `b1` y `b2` tienen ahora tres posibles valores, hay nueve combinaciones que se pueden evaluar.  
  
|b1|b2|b1 Y b2|b1 O b2|  
|--------|--------|-------------|-------------|  
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|  
|`Nothing`|`True`|`Nothing`|`True`|  
|`Nothing`|`False`|`False`|`Nothing`|  
|`True`|`Nothing`|`Nothing`|`True`|  
|`True`|`True`|`True`|`True`|  
|`True`|`False`|`False`|`True`|  
|`False`|`Nothing`|`False`|`Nothing`|  
|`False`|`True`|`False`|`True`|  
|`False`|`False`|`False`|`False`|  
  
 Cuando el valor de una variable o expresión booleana es `Nothing`, no es `true`  ni `false`.  Considere el ejemplo siguiente.  
  
 [!code-vb[VbVbalrNullableValue#6](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_6.vb)]  
  
 En este ejemplo, `b1 And b2` se evalúa como `Nothing`.  Como resultado, la cláusula `Else` se ejecuta en cada instrucción `If` y el resultado es como sigue:  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  `AndAlso` y `OrElse`, que usan la evaluación de cortocircuito, deben evaluar sus segundos operandos cuando el primero se evalúa como `Nothing`.  
  
## Propagación  
 Si uno de los operandos o ambos operandos de una operación aritmética, de comparación, de desplazamiento o con tipos aceptan valores NULL, el resultado de la operación también acepta valores NULL.  Si ambos operandos tienen valores que no son `Nothing`, la operación se realiza con los valores subyacentes de los operandos, como si ninguno fuera un tipo que acepta valores NULL.  En el ejemplo siguiente, las variables `compare1` y `sum1` son variables de tipo implícito.  Si coloca el puntero del mouse sobre ellas, observará que el compilador deduce los tipos que aceptan valores NULL para ambas variables.  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_7.vb)]  
  
 Si uno o ambos operandos tienen el valor `Nothing`, el resultado será `Nothing`.  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_8.vb)]  
  
## Utilizar tipos que aceptan valores NULL con datos  
 Una base de datos es uno de los lugares más importantes para utilizar tipos que aceptan valores NULL.  No todos los objetos de base de datos son actualmente compatibles con los tipos que aceptan valores NULL, pero sí lo son los adaptadores de tablas generadas por el diseñador.  Vea la sección sobre compatibilidad de TableAdapter con tipos que aceptan valores NULL en [Información general sobre TableAdapter](/visual-studio/data-tools/tableadapter-overview).  
  
## Vea también  
 <xref:System.InvalidOperationException>   
 <xref:System.Nullable%601.HasValue%2A>   
 [Utilizar tipos que aceptan valores NULL](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)   
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Solucionar problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Información general sobre TableAdapter](/visual-studio/data-tools/tableadapter-overview)   
 [If \(operador\)](../../../../visual-basic/language-reference/operators/if-operator.md)   
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Is \(Operador\)](../../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot \(Operador\)](../../../../visual-basic/language-reference/operators/isnot-operator.md)