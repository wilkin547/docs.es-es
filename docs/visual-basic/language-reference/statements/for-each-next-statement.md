---
title: "Instrucci&#243;n For Each...Next (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ForEach"
  - "vb.ForEachNext"
  - "vb.Each"
  - "ForEachNext"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "bucles infinitos"
  - "Instrucción Next, For Each...Next"
  - "bucles sin fin"
  - "estructuras de bucle, For Each...Next"
  - "bucles, sin fin"
  - "Each (palabra clave)"
  - "instrucciones, repetición"
  - "For Each (instrucción)"
  - "colecciones, repetición de instrucciones"
  - "bucles, infinitos"
  - "For Each...Next (instrucciones)"
  - "palabra clave For [Visual Basic], instrucciones For Each...Next"
  - "Instrucción Exit, instrucciones For Each...Next"
  - "iteración"
ms.assetid: ebce3120-95c3-42b1-b70b-fa7da40c75e2
caps.latest.revision: 56
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 56
---
# Instrucci&#243;n For Each...Next (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Repite un grupo de instrucciones para cada elemento de una colección.  
  
## Sintaxis  
  
```  
For Each element [ As datatype ] In group  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ element ]  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`element`|Se requiere en la instrucción `For Each`.  Opcional en la instrucción `Next`.  Variable.  Se usa para recorrer en iteración los elementos de la colección.|  
|`datatype`|Requerido si `element` no ya se ha declarado.  Tipo de datos de `element`.|  
|`group`|Requerido.  Una variable con un tipo que es un tipo de colección o un objeto.  Hace referencia a la colección sobre la que se debe repetir la ejecución de `statements`.|  
|`statements`|Opcional.  Una o más instrucciones entre `For Each` y `Next` que se ejecutan en cada elemento de `group`.|  
|`Continue For`|Opcional.  Transfiere el control al principio del bucle `For Each`.|  
|`Exit For`|Opcional.  Transfiere el control fuera del bucle `For Each`.|  
|`Next`|Requerido.  Termina la definición del bucle `For Each`.|  
  
## Ejemplo simple  
 Utilice un bucle `For Each`...`Next` cuando desee repetir un conjunto de instrucciones para cada elemento de una colección o matriz.  
  
> [!TIP]
>  Una [For...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-next-statement.md) funciona bien cuando se puede asociar cada iteración de un bucle con una variable de control y determinar los valores iniciales y finales de esa variable.  Sin embargo, cuando está trabajando con una colección, el concepto de inicial y de configuración final no es significativo, y no conoce necesariamente cuántos elementos tiene la colección.  En este tipo de caso, un bucle de `For Each`…`Next` suele ser una opción mejor.  
  
 En el siguiente ejemplo, la instrucción de `For Each`…`Next` recorre en iteración todos los elementos de una colección list.  
  
 [!code-vb[VbVbalrStatements#121](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_1.vb)]  
  
 Para obtener más ejemplos, vea [Colecciones](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md) y [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## Bucles anidados  
 Se pueden anidar bucles `For Each` colocando un bucle dentro de otro.  
  
 El ejemplo siguiente demuestra estructuras `For Each`...`Next` anidadas.  
  
 [!code-vb[VbVbalrStatements#122](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_2.vb)]  
  
 Cuando se anida bucles, cada bucle debe tener una variable única de `element`.  
  
 También puede anidar distintos tipos de estructuras de control unos dentro de otros.  Para obtener más información, vea [Estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## Exit For y Continue For  
 La ejecución de las causas de la instrucción de [Exit For](../../../visual-basic/language-reference/statements/exit-statement.md) salir del bucle de `For`…`Next` y transfiere el control a la instrucción que sigue a la instrucción de `Next`.  
  
 la instrucción `Continue For` transfiere el control inmediatamente a la siguiente iteración del bucle.  Para obtener más información, vea [Continue \(Instrucción\)](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 En el siguiente ejemplo se muestra cómo utilizar las instrucciones `Continue For` y `Exit For`.  
  
 [!code-vb[VbVbalrStatements#123](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_3.vb)]  
  
 Puede colocar cualquier número de instrucciones `Exit For` en un bucle `For Each` .  Cuando se utiliza dentro de bucles `For Each` anidados, `Exit For` hace que la ejecución salga del bucle más profundo y transfiera el control al siguiente nivel de anidamiento.  
  
 `Exit For` se utiliza a menudo después de evaluar alguna condición, por ejemplo, en una estructura `If`...`Then`...`Else`.  Puede que desee utilizar `Exit For` para las siguientes condiciones:  
  
-   Continuar la iteración es innecesario o imposible.  Esto podría deberse a un valor erróneo o una solicitud de terminación.  
  
-   Se detecta una excepción en `Try`...`Catch`...`Finally`.  Puede utilizar `Exit For` al final del bloque `Finally` .  
  
-   Hay un bucle infinito, que es un bucle que se podría ejecutar muchas o incluso infinitas veces.  Si se detecta este tipo de condición, se puede utilizar `Exit For` para escapar del bucle.  Para obtener más información, vea [Do...Loop \(Instrucción\)](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## Iteradores  
 Utiliza *un iterador* para realizar una iteración personalizada en una colección.  Un iterador puede ser una función o un descriptor de acceso de `Get`.  Utilice una instrucción de `Yield` para devolver cada elemento de la colección de uno en uno.  
  
 Se llama a un iterador mediante una instrucción `For Each...Next`.  Cada iteración del bucle `For Each` llama el iterador.  Cuando una instrucción de `Yield` se consigue en el iterador, la expresión en la instrucción de `Yield` se devuelve, y la ubicación actual en el código se conserva.  La ejecución se reinicia desde esta ubicación la próxima vez que se llame al iterador.  
  
 El ejemplo siguiente utiliza una función de iterador.  La función de iterador tiene una instrucción de `Yield` que está dentro de un bucle de [For… Next](../../../visual-basic/language-reference/statements/for-next-statement.md).  En el método de `ListEvenNumbers`, cada iteración del cuerpo de instrucción de `For Each` crea una llamada a la función de iterador, que continúa a `Yield` la instrucción siguiente.  
  
 [!code-vb[VbVbalrStatements#127](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_4.vb)]  
  
 Para obtener más información, vea [Iteradores](../Topic/Iterators%20\(C%23%20and%20Visual%20Basic\).md), [Yield \(Instrucción\)](../../../visual-basic/language-reference/statements/yield-statement.md) y [Iterador](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
## Implementación técnica  
 Cuando una instrucción de `For Each`…`Next` ejecuta, Visual Basic evalúa la colección sólo una vez, antes de que el bucle se inicie.  Si el bloque de instrucciones cambia `element` o `group`, estos cambios no afectan a la iteración del bucle.  
  
 Cuando todos los elementos de la colección se han asignado correctamente a `element`, el bucle `For Each` se detiene y el control pasa a la instrucción que sigue a la instrucción `Next`.  
  
 Si `element` no se ha declarado fuera de este bucle, éste debe ser en la instrucción de `For Each`.  Puede declarar el tipo de `element` explícitamente mediante una instrucción `As` o bien puede basarse en la inferencia de tipos para asignar el tipo.  En ambos casos, el ámbito de `element` es el cuerpo del bucle.  Sin embargo, no se puede declarar `element` fuera y dentro del bucle.  
  
 Opcionalmente, puede especificarse `element` en la instrucción `Next`.  Esto mejora la legibilidad del programa, sobre todo si se han anidado bucles `For Each`.  La variable que se especifique debe ser igual a la que aparece en la instrucción `For Each` correspondiente.  
  
 Puede que desee evitar cambiar el valor de `element` dentro de un bucle.  Esto puede hacer más difícil leer y depurar el código.  Cambiar el valor de `group` no afecta a la colección o sus elementos, que se determinan cuando el bucle primero se escribió.  
  
 Cuando está bucles de anidamiento, si una instrucción de `Next` de un nivel de anidamiento externo se encuentra antes de que `Next` de un nivel interno, el compilador señala un error.  Sin embargo, el compilador sólo puede detectar este error superpuesto si se especifica `element` en cada instrucción `Next`.  
  
 Si el código depende de recorrer una colección en un orden concreto, un bucle de `For Each`…`Next` no es la mejor opción, a menos que sepa las características del objeto de enumerador que la colección expone.  El orden de recorrido no está determinada por Visual Basic, sino por el método de <xref:System.Collections.IEnumerator.MoveNext%2A> del objeto de enumerador.  Por tanto, tal vez no pueda predecir qué elemento de la colección es el primero que se devuelve en `element` o qué elemento es el siguiente en ser devuelto tras un elemento dado.  Es posible obtener resultados más confiables si se utiliza una estructura de bucle diferente, tal como `For`...`Next` o `Do`...`Loop`.  
  
 El tipo de datos de `element` debe ser tal que el tipo de datos de los elementos de `group` se pueda convertir en él.  
  
 El tipo de datos de `group` debe ser un tipo de referencia que hace referencia a una colección o a una matriz que es enumerable.  Normalmente, esto significa que `group` hace referencia a un objeto que implementa la interfaz <xref:System.Collections.IEnumerable> del espacio de nombres `System.Collections` o la interfaz <xref:System.Collections.Generic.IEnumerable%601> del espacio de nombres `System.Collections.Generic`.  `System.Collections.IEnumerable` define el método <xref:System.Collections.IEnumerable.GetEnumerator%2A>, que devuelve un objeto enumerador para la colección.  El objeto enumerador implementa la interfaz `System.Collections.IEnumerator` del espacio de nombres `System.Collections` y expone la propiedad <xref:System.Collections.IEnumerator.Current%2A> y los métodos <xref:System.Collections.IEnumerator.Reset%2A> y <xref:System.Collections.IEnumerator.MoveNext%2A>.  Visual Basic los utiliza para recorrer la colección.  
  
### Conversiones de restricción  
 Cuando `Option Strict` está establecido en `On`, las conversiones de restricción suelen producir errores del compilador.  Sin embargo, en una instrucción `For Each`, las conversiones de los elementos de `group` a `element` se evalúan y realizan en tiempo de ejecución, y se suprimen los errores del compilador causados por las conversiones de restricción.  
  
 En el ejemplo siguiente, la asignación de `m` como valor inicial para `n` no compila a `Option Strict` está activado porque la conversión de `Long` a `Integer` es una conversión de restricción.  En la instrucción `For Each`, sin embargo, no se informa de ningún error del compilador, a pesar de que la asignación a `number` requiere la misma conversión de `Long` a `Integer`.  En la instrucción `For Each` que contiene un gran número, se produce un error en tiempo de ejecución cuando <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> se aplica al gran número.  
  
 [!code-vb[VbVbalrStatements#89](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_5.vb)]  
  
### Llamadas a IEnumerator  
 Cuando comienza la ejecución de un bucle `For Each`...`Next`, Visual Basic comprueba que `group` hace referencia a un objeto de colección válido.  Si no, produce una excepción.  De lo contrario, llama al método <xref:System.Collections.IEnumerator.MoveNext%2A> y a la propiedad <xref:System.Collections.IEnumerator.Current%2A> del objeto enumerador para devolver el primer elemento.  Si `MoveNext` indica que no hay un elemento siguiente, es decir, si la colección está vacía, el bucle `For Each` se detiene y el control pasa a la instrucción que sigue a `Next`.  De lo contrario, Visual Basic establece `element` en el primer elemento y ejecuta el bloque de instrucciones.  
  
 Cada vez que Visual Basic encuentra la instrucción `Next`, vuelve a la instrucción `For Each`.  Llama de nuevo a `MoveNext` y `Current` para devolver el elemento siguiente, y una vez más ejecuta el bloque o se detiene el bucle según el resultado.  Este proceso continúa hasta que `MoveNext` indica que no hay ningún elemento siguiente o se encuentra una instrucción `Exit For`.  
  
 **Modificar la colección.** El objeto de enumerador devuelto por <xref:System.Collections.IEnumerable.GetEnumerator%2A> no permite normalmente cambiar la colección agregar, eliminar, reemplazando, o si ningún elemento.  Si se modifica la colección después de haber iniciado un bucle `For Each`...`Next`, el objeto enumerador deja de ser válido y el siguiente intento de acceso a un elemento produce una excepción <xref:System.InvalidOperationException>.  
  
 Sin embargo, este bloqueo de la modificación no está determinado por [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], sino por la implementación de la interfaz de <xref:System.Collections.IEnumerable>.  Es posible implementar `IEnumerable` de modo que se permita la modificación durante la iteración.  Si piensa realizar este tipo de modificación dinámica, asegúrese de que conoce las características de la implementación de `IEnumerable` en la colección que está utilizando.  
  
 **Modificar los elementos de colección.** La propiedad <xref:System.Collections.IEnumerator.Current%2A> del objeto enumerador es [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) y devuelve una copia local de cada elemento de la colección.  Esto significa que no es posible modificar los propios elementos en un bucle `For Each`...`Next`.  Cualquier modificación que cree solo afecta a la copia local de `Current` y no se refleja de nuevo en la colección subyacente.  Sin embargo, si un elemento es un tipo de referencia, es posible modificar los miembros de la instancia a los que apunta.  El ejemplo siguiente se modifica el miembro de `BackColor` de cada elemento de `thisControl`.  No puede, sin embargo, modificar `thisControl` propio.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 En el ejemplo anterior se puede modificar el miembro `BackColor` de cada elemento `thisControl`, aunque no se puede modificar el propio elemento `thisControl`.  
  
 **Recorrer matrices.** Dado que la clase <xref:System.Array> implementa la interfaz <xref:System.Collections.IEnumerable>, todas las matrices exponen el método <xref:System.Array.GetEnumerator%2A>.  Esto significa que es posible recorrer una matriz con un bucle `For Each`...`Next`.  Sin embargo, solo se pueden leer los elementos de la matriz.  No se pueden cambiar.  
  
## Ejemplo  
 El ejemplo siguiente muestra todas las carpetas del directorio C:\\ utilizando la clase <xref:System.IO.DirectoryInfo> .  
  
 [!code-vb[VbVbalrStatements#124](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_6.vb)]  
  
## Ejemplo  
 El ejemplo siguiente muestra un procedimiento para ordenar una colección.  El ejemplo ordena las instancias de una clase de `Car` almacenados en <xref:System.Collections.Generic.List%601>.  La clase `Car` implementa la interfaz <xref:System.IComparable%601>, que requiere que el método <xref:System.IComparable%601.CompareTo%2A> se implemente.  
  
 Cada llamada al método de <xref:System.IComparable%601.CompareTo%2A> crea una única comparación que se utiliza para ordenar.  El código escrito por el usuario en el método `CompareTo` devuelve un valor para cada comparación del objeto actual con otro objeto.  El valor devuelto es menor que cero si el objeto actual es menor que otro objeto, mayor que cero si el objeto actual es mayor que otro objeto y cero si son iguales.  Esto permite definir en el código los criterios para la evaluación mayor que, menor que, e igual que.  
  
 En el método `ListCars`, la expresión `cars.Sort()` ordena la lista.  Esta llamada al método <xref:System.Collections.Generic.List%601.Sort%2A> de <xref:System.Collections.Generic.List%601> hace que el método `CompareTo` sea llamado automáticamente para los objetos de clase `Car` en `List`.  
  
 [!code-vb[VbVbalrStatements#125](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-each-next-statement_7.vb)]  
  
## Vea también  
 [Colecciones](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)   
 [For...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Estructuras de bucles](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [While...End While \(Instrucción\)](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [Do...Loop \(Instrucción\)](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Inicializadores de objeto: Tipos con nombre y anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Inicializadores de colección](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)