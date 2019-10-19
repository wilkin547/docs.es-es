---
title: Yield (Instrucción) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: 57b36bb32e1a575a645f7a15045bf0898dd10dfd
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582215"
---
# <a name="yield-statement-visual-basic"></a>Yield (Instrucción) (Visual Basic)
Envía el siguiente elemento de una colección a una instrucción `For Each...Next`.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Yield expression  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Término|de esquema JSON|  
|---|---|  
|`expression`|Requerido. Una expresión que se pueda convertir implícitamente al tipo de la función de iterador o `Get` descriptor de acceso que contiene la instrucción `Yield`.|  
  
## <a name="remarks"></a>Comentarios  
 La instrucción `Yield` devuelve un elemento de una colección a la vez. La instrucción `Yield` se incluye en una función de iterador o en un descriptor de acceso `Get`, que realiza iteraciones personalizadas en una colección.  
  
 Utilice una función de iterador mediante un [... Instrucción Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) o una consulta LINQ. Cada iteración del bucle `For Each` llama a la función de iterador. Cuando se alcanza una instrucción `Yield` en la función de iterador, se devuelve `expression` y se conserva la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.  
  
 Debe existir una conversión implícita del tipo de `expression` de la instrucción `Yield` al tipo de valor devuelto del iterador.  
  
 Puede usar una instrucción `Exit Function` o `Return` para finalizar la iteración.  
  
 "Yield" no es una palabra reservada y tiene un significado especial solo cuando se utiliza en una función de `Iterator` o un descriptor de acceso `Get`.  
  
 Para obtener más información sobre las funciones de iterador y los descriptores de acceso `Get`, vea [iteradores](../../programming-guide/concepts/iterators.md).  
  
## <a name="iterator-functions-and-get-accessors"></a>Funciones de iterador y obtener descriptores de acceso  
 La declaración de una función de iterador o `Get` descriptor de acceso debe cumplir los siguientes requisitos:  
  
- Debe incluir un modificador de [iterador](../../../visual-basic/language-reference/modifiers/iterator.md) .  
  
- El tipo de valor devuelto debe ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.  
  
- No puede tener ningún parámetro `ByRef`.  
  
 Una función de iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático o un destructor estático.  
  
 Una función de iterador puede ser una función anónima. Para más información, vea [Iteradores](../../programming-guide/concepts/iterators.md).  
  
## <a name="exception-handling"></a>Control de excepciones  
 Una instrucción `Yield` puede estar dentro de un bloque `Try` de una instrucción [try... Detectar... Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Un bloque `Try` que tiene una instrucción `Yield` puede tener bloques `Catch` y puede tener un bloque `Finally`.  
  
 Una instrucción `Yield` no puede estar dentro de un bloque de `Catch` o un bloque `Finally`.  
  
 Si el cuerpo de `For Each` (fuera de la función de iterador) produce una excepción, no se ejecuta un bloque de `Catch` en la función de iterador, pero se ejecuta un bloque de `Finally` en la función de iterador. Un bloque `Catch` dentro de una función de iterador solo detecta las excepciones que se producen dentro de la función de iterador.  
  
## <a name="technical-implementation"></a>Implementación técnica  
 El código siguiente devuelve un `IEnumerable (Of String)` de una función de iterador y, a continuación, recorre en iteración los elementos de la `IEnumerable (Of String)`.  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 La llamada a `MyIteratorFunction` no ejecuta el cuerpo de la función. En su lugar, la llamada devuelve un valor `IEnumerable(Of String)` en la variable `elements`.  
  
 En una iteración del bucle `For Each`, se llama al método <xref:System.Collections.IEnumerator.MoveNext%2A> para `elements`. Esta llamada ejecuta el cuerpo de `MyIteratorFunction` hasta que se alcanza la siguiente instrucción `Yield`. La instrucción `Yield` devuelve una expresión que determina no solo el valor de la variable `element` para su consumo por parte del cuerpo del bucle, sino también la propiedad <xref:System.Collections.Generic.IEnumerator%601.Current%2A> de los elementos, que es una `IEnumerable (Of String)`.  
  
 En cada iteración subsiguiente del bucle `For Each`, la ejecución del cuerpo del iterador continúa desde donde se dejó, deteniéndose de nuevo al alcanzar una instrucción `Yield`. El bucle de `For Each` se completa cuando se alcanza el final de la función de iterador o una instrucción `Return` o `Exit Function`.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente tiene una instrucción `Yield` que está dentro de un [... Siguiente](../../../visual-basic/language-reference/statements/for-next-statement.md) bucle. Cada iteración del cuerpo de la instrucción [for each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) en `Main` crea una llamada a la función de iterador `Power`. Cada llamada a la función de iterador prosigue con la siguiente ejecución de la instrucción `Yield`, que se produce durante la siguiente iteración del bucle `For…Next`.  
  
 El tipo de valor devuelto del método iterador es <xref:System.Collections.Generic.IEnumerable%601>, un tipo de interfaz de iterador. Cuando se llama al método iterador, este devuelve un objeto enumerable que contiene las potencias de un número.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un descriptor de acceso `Get` que es un iterador. La declaración de propiedad incluye un modificador `Iterator`.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Para obtener más ejemplos, vea [iteradores](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Vea también

- [Instrucciones](../../../visual-basic/language-reference/statements/index.md)
