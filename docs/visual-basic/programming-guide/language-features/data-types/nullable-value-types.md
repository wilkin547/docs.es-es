---
title: Tipos que admiten valores null (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8734114b9d657066a0ef0b2d648f0290c03b1cbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="nullable-value-types-visual-basic"></a>Tipos que admiten valores null (Visual Basic)
A veces se trabaja con un tipo de valor que no tiene un valor definido en determinadas circunstancias. Por ejemplo, podría tener un campo en una base de datos distinguir entre tener un valor asignado que es significativo y no tener un valor asignado. Tipos de valor se pueden extender para tomar sus valores normales o un valor null. Este tipo de extensión se llama un *tipo que acepta valores NULL*.  
  
 Cada tipo que acepta valores NULL se construye a partir de la interfaz genérica <xref:System.Nullable%601> estructura. Considere la posibilidad de una base de datos que realiza el seguimiento de las actividades relacionadas con el trabajo. En el ejemplo siguiente se crea un que aceptan valores NULL `Boolean` escriba y declara una variable de ese tipo. Puede escribir la declaración de tres maneras:  
  
 [!code-vb[VbVbalrNullableValue#1](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_1.vb)]  
  
 La variable `ridesBusToWork` puede contener un valor de `True`, un valor de `False`, o ningún valor en absoluto. Su valor predeterminado inicial no es ningún valor en absoluto, que en este caso podría significar que la información no se ha obtenido para esta persona. En cambio, `False` puede significar que se ha obtenido la información y la persona que no utiliza el autobús para que funcione.  
  
 Puede declarar variables y propiedades con tipos que aceptan valores NULL y puede declarar una matriz con elementos de un tipo que acepta valores NULL. Puede declarar procedimientos con tipos que aceptan valores NULL como parámetros y puede devolver un tipo que acepta valores NULL de un `Function` procedimiento.  
  
 No se puede construir un tipo que acepta valores NULL en un tipo de referencia como una matriz, un `String`, o una clase. El tipo subyacente debe ser un tipo de valor. Para obtener más información, consulte [tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
## <a name="using-a-nullable-type-variable"></a>Uso de una Variable de tipo que acepta valores null  
 Los miembros más importantes de un tipo que acepta valores NULL son sus <xref:System.Nullable%601.HasValue%2A> y <xref:System.Nullable%601.Value%2A> propiedades. Para una variable de un tipo que acepta valores NULL, <xref:System.Nullable%601.HasValue%2A> indica si la variable contiene un valor definido. Si <xref:System.Nullable%601.HasValue%2A> es `True`, puede leer el valor de <xref:System.Nullable%601.Value%2A>. Tenga en cuenta que ambos <xref:System.Nullable%601.HasValue%2A> y <xref:System.Nullable%601.Value%2A> son `ReadOnly` propiedades.  
  
### <a name="default-values"></a>Valores predeterminados  
 Cuando se declara una variable con un tipo que acepta valores NULL, su <xref:System.Nullable%601.HasValue%2A> propiedad tiene un valor predeterminado de `False`. Esto significa que, de forma predeterminada, la variable no tiene ningún valor definido, en lugar del valor predeterminado de su tipo de valor subyacente. En el ejemplo siguiente, la variable `numberOfChildren` inicialmente no tiene ningún valor definido, aunque el valor predeterminado de la `Integer` tipo es 0.  
  
 [!code-vb[VbVbalrNullableValue#2](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_2.vb)]  
  
 Un valor null es útil para indicar un valor indefinido o desconocido. Si `numberOfChildren` se ha declarado como `Integer`, no habría ningún valor que podría indicar que la información no está disponible actualmente.  
  
### <a name="storing-values"></a>Almacenar valores  
 Almacenar un valor en una variable o propiedad de un tipo que acepta valores NULL de la manera habitual. En el ejemplo siguiente se asigna un valor a la variable `numberOfChildren` declarada en el ejemplo anterior.  
  
 [!code-vb[VbVbalrNullableValue#3](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_3.vb)]  
  
 Si una variable o propiedad de un tipo que acepta valores NULL contiene un valor definido, puede provocar que se vuelve a su estado inicial de no tener un valor asignado. Para ello, Establece la variable o propiedad para `Nothing`, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrNullableValue#4](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_4.vb)]  
  
> [!NOTE]
>  Aunque puede asignar `Nothing` a una variable de un tipo que acepta valores NULL, no puede probarlo para `Nothing` utilizando el signo igual. Comparación que utiliza el signo igual, `someVar = Nothing`, siempre se evalúa como `Nothing`. Puede probar la variable <xref:System.Nullable%601.HasValue%2A> propiedad `False`, o probar mediante el `Is` o `IsNot` operador.  
  
### <a name="retrieving-values"></a>Recuperar valores  
 Para recuperar el valor de una variable de un tipo que acepta valores NULL, debe probar su <xref:System.Nullable%601.HasValue%2A> propiedad para confirmar que tiene un valor. Si se intenta leer el valor cuando <xref:System.Nullable%601.HasValue%2A> es `False`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] produce una <xref:System.InvalidOperationException> excepción. En el ejemplo siguiente se muestra la manera recomendada de leer la variable `numberOfChildren` de los ejemplos anteriores.  
  
 [!code-vb[VbVbalrNullableValue#5](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_5.vb)]  
  
## <a name="comparing-nullable-types"></a>Compara los tipos que aceptan valores null  
 Cuando acepta valores NULL `Boolean` se usan variables en expresiones booleanas, el resultado puede ser `True`, `False`, o `Nothing`. La siguiente es la tabla truth para `And` y `Or`. Dado que `b1` y `b2` ahora tiene tres valores posibles, hay nueve combinaciones para evaluar.  
  
|B1|B2|B1 y b2|B1 o b2|  
|--------|--------|---------------|--------------|  
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|  
|`Nothing`|`True`|`Nothing`|`True`|  
|`Nothing`|`False`|`False`|`Nothing`|  
|`True`|`Nothing`|`Nothing`|`True`|  
|`True`|`True`|`True`|`True`|  
|`True`|`False`|`False`|`True`|  
|`False`|`Nothing`|`False`|`Nothing`|  
|`False`|`True`|`False`|`True`|  
|`False`|`False`|`False`|`False`|  
  
 Cuando el valor de una variable o expresión booleana es `Nothing`, no es ni `true` ni `false`. Considere el ejemplo siguiente.  
  
 [!code-vb[VbVbalrNullableValue#6](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_6.vb)]  
  
 En este ejemplo, `b1 And b2` se evalúa como `Nothing`. Como resultado, el `Else` cláusula se ejecuta en cada uno de ellos `If` instrucción y el resultado es el siguiente:  
  
 `Expression is not true`  
  
 `Expression is not false`  
  
> [!NOTE]
>  `AndAlso`y `OrElse`, evaluación de cortocircuito que usan debe evaluar sus segundos operandos cuando el primero se evalúa como `Nothing`.  
  
## <a name="propagation"></a>Propagación  
 Si uno o ambos operandos de una aritmética, comparación, MAYÚS o de operación de tipo admite valores NULL, el resultado de la operación también es que aceptan valores NULL. Si ambos operandos tienen valores que no sean `Nothing`, la operación se realiza en los valores subyacentes de los operandos, como si ninguno fuera un tipo que acepta valores NULL. En el ejemplo siguiente, las variables `compare1` y `sum1` son con tipo implícito. Si sitúa el puntero del mouse sobre ellos, verá que el compilador deduce los tipos que aceptan valores NULL para ambos.  
  
 [!code-vb[VbVbalrNullableValue#7](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_7.vb)]  
  
 Si uno o ambos operandos tienen un valor de `Nothing`, el resultado será `Nothing`.  
  
 [!code-vb[VbVbalrNullableValue#8](../../../../visual-basic/programming-guide/language-features/data-types/codesnippet/VisualBasic/nullable-value-types_8.vb)]  
  
## <a name="using-nullable-types-with-data"></a>Utilizar tipos que aceptan valores NULL con datos  
 Una base de datos es uno de los lugares más importantes para utilizar tipos que aceptan valores NULL. Actualmente, no todos los objetos de base de datos admiten tipos que aceptan valores NULL, pero sí los adaptadores de tabla generado por el diseñador. Vea "Compatibilidad de TableAdapter con tipos que aceptan valores null" en [información general sobre TableAdapter](/visualstudio/data-tools/tableadapter-overview).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.InvalidOperationException>  
 <xref:System.Nullable%601.HasValue%2A>  
 [Utilizar tipos que aceptan valores NULL](../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Solución de problemas de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Introducción a TableAdapter](/visualstudio/data-tools/tableadapter-overview)  
 [If (operador)](../../../../visual-basic/language-reference/operators/if-operator.md)  
 [Inferencia de tipo de variable local](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Is (operador)](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot (operador)](../../../../visual-basic/language-reference/operators/isnot-operator.md)
