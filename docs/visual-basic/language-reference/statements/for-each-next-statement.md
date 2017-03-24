---
title: For Each... Next Statement (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ForEach
- vb.ForEachNext
- vb.Each
- ForEachNext
dev_langs:
- VB
helpviewer_keywords:
- infinite loops
- Next statement, For Each...Next
- endless loops
- loop structures, For Each...Next
- loops, endless
- Each keyword
- instructions, repeating
- For Each statement
- collections, instruction repetition
- loops, infinite
- For Each...Next statements
- For keyword [Visual Basic], For Each...Next statements
- Exit statement, For Each...Next statements
- iteration
ms.assetid: ebce3120-95c3-42b1-b70b-fa7da40c75e2
caps.latest.revision: 56
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e0173877fa4a57da76fd774d70ce63d2beda23ad
ms.lasthandoff: 03/13/2017

---
# <a name="for-eachnext-statement-visual-basic"></a>Instrucción For Each...Next (Visual Basic)
Repite un grupo de instrucciones para cada elemento de una colección.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
For Each element [ As datatype ] In group  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ element ]  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`element`|Necesario en el `For Each` instrucción. Opcional en el `Next` instrucción. Variable. Se utiliza para recorrer en iteración los elementos de la colección.|  
|`datatype`|Requerido si `element` ya no está declarado. Tipo de datos de `element`.|  
|`group`|Obligatorio. Una variable con un tipo que es un objeto o colección. Hace referencia a la colección en la que el `statements` deben repetirse.|  
|`statements`|Opcional. Una o más instrucciones entre `For Each` y `Next` que se ejecutan en cada elemento de `group`.|  
|`Continue For`|Opcional. Transfiere el control al principio de la `For Each` bucle.|  
|`Exit For`|Opcional. Transfiere el control fuera de la `For Each` bucle.|  
|`Next`|Obligatorio. Termina la definición de la `For Each` bucle.|  
  
## <a name="simple-example"></a>Ejemplo sencillo  
 Use a `For Each`... `Next` un bucle cuando desea repetir un conjunto de instrucciones para cada elemento de una colección o matriz.  
  
> [!TIP]
>  A [For... Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md) funciona bien cuando puede asociar cada iteración de un bucle con una variable de control y determinar los valores inicial y final de la variable. Sin embargo, cuando se trata de una colección, el concepto de valores iniciales y finales no es significativo y no necesariamente sabe cuántos elementos tiene la colección. En este tipo de caso, un `For Each`... `Next` bucle suele ser una mejor opción.  
  
 En el ejemplo siguiente, la `For Each`...`Next` instrucción recorre en iteración todos los elementos de una colección de lista.  
  
 [!code-vb[VbVbalrStatements&#121;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_1.vb)]  
  
 Para obtener más ejemplos, vea [colecciones](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) y [matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="nested-loops"></a>Bucles anidados  
 Puede anidar `For Each` bucles colocando un bucle dentro de otro.  
  
 En el ejemplo siguiente se muestra anidada `For Each`...`Next` estructuras.  
  
 [!code-vb[VbVbalrStatements&#122;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_2.vb)]  
  
 Al anidar bucles, cada bucle debe tener un único `element` variable.  
  
 También puede anidar diferentes tipos de estructuras de control entre sí. Para obtener más información, consulte [estructuras de Control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Exit For y continuar para  
 El [Exit For](../../../visual-basic/language-reference/statements/exit-statement.md) instrucción hace que la ejecución salir de la `For`...`Next` bucle y transfiere el control a la instrucción que sigue a la `Next` instrucción.  
  
 El `Continue For` instrucción transfiere el control inmediatamente a la siguiente iteración del bucle. Para obtener más información, consulte [instrucción Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 En el ejemplo siguiente se muestra cómo utilizar el `Continue For` y `Exit For` instrucciones.  
  
 [!code-vb[VbVbalrStatements&#123;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_3.vb)]  
  
 Puede colocar cualquier número de `Exit For` las instrucciones en un `For Each` bucle. Cuando se utiliza dentro anidados `For Each` bucles, `Exit For` hace que la ejecución salir del bucle y transfiere el control más interno al siguiente nivel más alto de anidamiento.  
  
 `Exit For`a menudo se usa después de una evaluación de alguna condición, por ejemplo, en un `If`... `Then`... `Else` (estructura). Desea usar `Exit For` para las condiciones siguientes:  
  
-   Continuar recorrer en iteración es innecesario o imposible. Esto podría deberse a un valor erróneo o una solicitud de finalización.  
  
-   Se detecta una excepción en un `Try`... `Catch`... `Finally`. Puede usar `Exit For` al final de la `Finally` bloque.  
  
-   Hay un bucle interminable, que es un bucle que se puede ejecutar un número grande o incluso infinito de veces. Si detecta una condición de ese tipo, puede usar `Exit For` para salir del bucle. Para obtener más información, consulte [hacer... Instrucción de bucle](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="iterators"></a>Iteradores  
 Utiliza un *iterador* para realizar una iteración personalizada sobre una colección. Un iterador puede ser una función o un `Get` descriptor de acceso. Utiliza un `Yield` instrucción para devolver cada elemento de la colección a la vez.  
  
 Puede llamar a un iterador con un `For Each...Next` instrucción. Cada iteración de la `For Each` bucle llama el iterador. Cuando un `Yield` se alcanza la instrucción en el iterador, la expresión en el `Yield` instrucción se devuelve y se conserva la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama al iterador.  
  
 En el ejemplo siguiente se utiliza una función de iterador. La función de iterador tiene un `Yield` instrucción que se encuentra dentro de un [para... Siguiente](../../../visual-basic/language-reference/statements/for-next-statement.md) bucle. En el `ListEvenNumbers` método, cada iteración de la `For Each` cuerpo de instrucción crea una llamada a la función del iterador, que se dirige a la siguiente `Yield` instrucción.  
  
 [!code-vb[127 VbVbalrStatements](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_4.vb)]  
  
 Para obtener más información, consulte [iteradores](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7), [instrucción Yield](../../../visual-basic/language-reference/statements/yield-statement.md), y [iterador](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
## <a name="technical-implementation"></a>Implementación técnica  
 Cuando un `For Each`...`Next` ejecuciones de instrucción, Visual Basic evalúa la colección sólo una vez, antes de que comience el bucle. Si cambia el bloque de instrucciones `element` o `group`, estos cambios no afectan a la iteración del bucle.  
  
 Cuando todos los elementos de la colección se han asignado correctamente a `element`, `For Each` se detiene un bucle y el control pasa a la siguiente instrucción el `Next` instrucción.  
  
 Si `element` todavía no se ha declarado fuera de este bucle, se debe declarar en el `For Each` instrucción. Puede declarar el tipo de `element` explícitamente mediante una `As` , o bien puede confiar en la inferencia de tipos para asignar el tipo. En cualquier caso, el ámbito de `element` es el cuerpo del bucle. Sin embargo, no puede declarar `element` fuera y dentro del bucle.  
  
 Opcionalmente, puede especificar `element` en el `Next` instrucción. Esto mejora la legibilidad del programa, especialmente si tiene anidados `For Each` bucles. Debe especificar la misma variable como el que aparece en la correspondiente `For Each` instrucción.  
  
 Desea evitar cambiar el valor de `element` dentro de un bucle. Esto puede hacer más difícil de leer y depurar el código. Cambiar el valor de `group` no afecta a la colección o sus elementos, que se determinan al entra en el bucle.  
  
 Cuando está anidar bucles, si un `Next` instrucción de un nivel de anidamiento externo se encuentra antes de la `Next` de un nivel interno, el compilador señala un error. Sin embargo, el compilador puede detectar este error se superponen sólo si se especifica `element` en cada `Next` instrucción.  
  
 Si el código depende del recorrido de una colección en un orden concreto, un `For Each`... `Next` bucle no es la mejor elección, a menos que conozca las características del objeto enumerador que expone la colección. El orden de recorrido no está determinado por Visual Basic, sino por el <xref:System.Collections.IEnumerator.MoveNext%2A>método del objeto enumerador.</xref:System.Collections.IEnumerator.MoveNext%2A> Por lo tanto, no puede predecir qué elemento de la colección es el primero que se devuelve en `element`, o que es el siguiente en ser devuelto tras un elemento dado. Puede conseguir resultados más confiables con una estructura de bucle diferente, como `For`... `Next` or `Do`... `Loop`.  
  
 Tipo de datos de `element` deberá ser tal que el tipo de datos de los elementos de `group` puede convertir en él.  
  
 Tipo de datos de `group` debe ser un tipo de referencia que hace referencia a una colección o una matriz que es enumerable. Normalmente, esto significa que `group` hace referencia a un objeto que implementa el <xref:System.Collections.IEnumerable>interfaz de la `System.Collections` espacio de nombres o la <xref:System.Collections.Generic.IEnumerable%601>interfaz de la `System.Collections.Generic` espacio de nombres.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable> `System.Collections.IEnumerable`define la <xref:System.Collections.IEnumerable.GetEnumerator%2A>método, que devuelve un objeto enumerador para la colección.</xref:System.Collections.IEnumerable.GetEnumerator%2A> El objeto enumerador implementa la `System.Collections.IEnumerator` interfaz de la `System.Collections` espacio de nombres y expone el <xref:System.Collections.IEnumerator.Current%2A>propiedad y <xref:System.Collections.IEnumerator.Reset%2A>y <xref:System.Collections.IEnumerator.MoveNext%2A>métodos.</xref:System.Collections.IEnumerator.MoveNext%2A> </xref:System.Collections.IEnumerator.Reset%2A> </xref:System.Collections.IEnumerator.Current%2A> Visual Basic utiliza éstos para recorrer la colección.  
  
### <a name="narrowing-conversions"></a>Conversiones de restricción  
 Cuando `Option Strict` se establece en `On`, las conversiones de restricción suelen provocan errores del compilador. En un `For Each` instrucción, sin embargo, las conversiones de los elementos de `group` a `element` se evalúan y se realiza en tiempo de ejecución y se suprimen los errores de compilador causados por las conversiones de restricción.  
  
 En el ejemplo siguiente, la asignación de `m` como valor inicial para `n` no se compila cuando `Option Strict` porque se encuentra en la conversión de un `Long` a una `Integer` es una conversión de restricción. En el `For Each` instrucción, sin embargo, ningún error del compilador es notificado, aunque la asignación a `number` requiere la misma conversión de `Long` a `Integer`. En el `For Each` se produce un error en tiempo de ejecución de instrucción que contiene un número elevado, cuando <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A>se aplica a la gran cantidad.</xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A>  
  
 [!code-vb[VbVbalrStatements&#89;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_5.vb)]  
  
### <a name="ienumerator-calls"></a>Llamadas de IEnumerator  
 Cuando la ejecución de un `For Each`... `Next` inicia el bucle, Visual Basic comprueba que `group` hace referencia a un objeto válido de la colección. De lo contrario, produce una excepción. De lo contrario, llama a la <xref:System.Collections.IEnumerator.MoveNext%2A>(método) y el <xref:System.Collections.IEnumerator.Current%2A>propiedad del objeto enumerador para devolver el primer elemento.</xref:System.Collections.IEnumerator.Current%2A> </xref:System.Collections.IEnumerator.MoveNext%2A> Si `MoveNext` indica que no hay ningún elemento siguiente, es decir, si la colección está vacía, el `For Each` se detiene un bucle y el control pasa a la siguiente instrucción el `Next` instrucción. De lo contrario, Visual Basic establece `element` para el primer elemento y se ejecuta el bloque de instrucciones.  
  
 Cada vez que Visual Basic encuentra la `Next` instrucción, devuelve a la `For Each` instrucción. Llama de nuevo a `MoveNext` y `Current` para devolver el elemento siguiente y, a uno ejecuta el bloque o se detiene el bucle según el resultado. Este proceso continúa hasta que `MoveNext` indica que no hay ningún elemento siguiente o `Exit For` se encuentra la instrucción.  
  
 **Modificar la colección.** El objeto enumerador devuelto por <xref:System.Collections.IEnumerable.GetEnumerator%2A>normalmente no permite cambiar la colección agregando, eliminando, reemplazando o reordenación de elementos.</xref:System.Collections.IEnumerable.GetEnumerator%2A> Si cambia la colección después de haber iniciado un `For Each`... `Next` bucles, el objeto enumerador deja de ser válido y el siguiente intento de acceso a un elemento hace un <xref:System.InvalidOperationException>excepción.</xref:System.InvalidOperationException>  
  
 Sin embargo, este bloqueo de modificación no viene determinado por [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], sino por la implementación de la <xref:System.Collections.IEnumerable>interfaz.</xref:System.Collections.IEnumerable> Es posible implementar `IEnumerable` de forma que permite la modificación durante la iteración. Si piensa realizar dicha modificación dinámica, asegúrese de que comprende las características de la `IEnumerable` implementación en la colección que está utilizando.  
  
 **Modificar elementos de la colección.** El <xref:System.Collections.IEnumerator.Current%2A>es propiedad del objeto del enumerador [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), y devuelve una copia local de cada elemento de la colección.</xref:System.Collections.IEnumerator.Current%2A> Esto significa que no pueden modificar los propios elementos en un `For Each`... `Next` loop. Cualquier modificación realizada afecta sólo a la copia local de `Current` y no se reflejará en la colección subyacente. Sin embargo, si un elemento es un tipo de referencia, puede modificar los miembros de la instancia a la que señala. En el ejemplo siguiente se modifica el `BackColor` miembro de cada `thisControl` elemento. Sin embargo, no puede modificar `thisControl` propio.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 En el ejemplo anterior se puede modificar el `BackColor` miembro de cada `thisControl` elemento, aunque no puede modificar `thisControl` propio.  
  
 **Recorrer matrices.** Porque el <xref:System.Array>la clase implementa la <xref:System.Collections.IEnumerable>interfaz, todas las matrices exponen el <xref:System.Array.GetEnumerator%2A>método.</xref:System.Array.GetEnumerator%2A> </xref:System.Collections.IEnumerable> </xref:System.Array> Esto significa que puede iterar a través de una matriz con un `For Each`... `Next` loop. Sin embargo, sólo puede leer elementos de la matriz. No se pueden cambiar.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se enumeran todas las carpetas en el directorio C:\ mediante el uso de la <xref:System.IO.DirectoryInfo>clase.</xref:System.IO.DirectoryInfo>  
  
 [!code-vb[VbVbalrStatements&#124;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_6.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un procedimiento para ordenar una colección. El ejemplo ordena las instancias de un `Car` clase que se almacenan en un <xref:System.Collections.Generic.List%601>.</xref:System.Collections.Generic.List%601> El `Car` la clase implementa la <xref:System.IComparable%601>interfaz, que requiere que el <xref:System.IComparable%601.CompareTo%2A>método implementarse.</xref:System.IComparable%601.CompareTo%2A> </xref:System.IComparable%601>  
  
 Cada llamada a la <xref:System.IComparable%601.CompareTo%2A>este método realiza una comparación única que se utiliza para ordenar.</xref:System.IComparable%601.CompareTo%2A> Código escrito por el usuario en el `CompareTo` método devuelve un valor de comparación del objeto actual con otro objeto. El valor devuelto es menor que cero si el objeto actual es menor que el otro objeto, mayor que cero si el objeto actual es mayor que el otro objeto y cero si son iguales. Esto permite definir en el código los criterios de mayor que, menor que e igual.  
  
 En el `ListCars` (método), el `cars.Sort()` instrucción ordena la lista. Esta llamada a la <xref:System.Collections.Generic.List%601.Sort%2A>método de la <xref:System.Collections.Generic.List%601>hace que el `CompareTo` método al que llamar automáticamente para la `Car` objetos en la `List`.</xref:System.Collections.Generic.List%601> </xref:System.Collections.Generic.List%601.Sort%2A>  
  
 [!code-vb[VbVbalrStatements&#125;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_7.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Colecciones](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)   
 [Para... Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Estructuras de bucle](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [While... End While (instrucción)](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [DO... Instrucción del bucle](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [Conversiones de restricción y ampliación](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Inicializadores de objeto: Tipos con nombre y anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Inicializadores de colección](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)
