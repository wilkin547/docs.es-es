---
title: Instrucción Yield
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: 783785f2a078b6ad8f975846c44ee4e716a12773
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866507"
---
# <a name="yield-statement-visual-basic"></a>Yield (Instrucción) (Visual Basic)

Envía el siguiente elemento de una colección a una `For Each...Next` instrucción.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Yield expression  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Término|Definición|  
|---|---|  
|`expression`|Obligatorio. Una expresión que se pueda convertir implícitamente al tipo de la función de iterador o `Get` descriptor de acceso que contiene la `Yield` instrucción.|  
  
## <a name="remarks"></a>Comentarios  

 La `Yield` instrucción devuelve un elemento de una colección a la vez. La `Yield` instrucción se incluye en una función de iterador o `Get` descriptor de acceso, que realiza iteraciones personalizadas en una colección.  
  
 Utilice una función de iterador mediante un [... Instrucción Next](for-each-next-statement.md) o una consulta LINQ. Cada iteración del `For Each` bucle llama a la función de iterador. Cuando `Yield` se alcanza una instrucción en la función de iterador, `expression` se devuelve y se conserva la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.  
  
 Debe existir una conversión implícita del tipo de `expression` en la `Yield` instrucción al tipo de valor devuelto del iterador.  
  
 Puede usar una `Exit Function` instrucción o `Return` para finalizar la iteración.  
  
 "Yield" no es una palabra reservada y tiene un significado especial solo cuando se usa en una `Iterator` función o un `Get` descriptor de acceso.  
  
 Para obtener más información sobre las funciones de iterador y los `Get` descriptores de acceso, vea [iteradores](../../programming-guide/concepts/iterators.md).  
  
## <a name="iterator-functions-and-get-accessors"></a>Funciones de iterador y obtener descriptores de acceso  

 La declaración de una función de iterador o `Get` descriptor de acceso debe cumplir los siguientes requisitos:  
  
- Debe incluir un modificador de [iterador](../modifiers/iterator.md) .  
  
- El tipo de valor devuelto debe ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.  
  
- No puede tener ningún `ByRef` parámetro.  
  
 Una función de iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático o un destructor estático.  
  
 Una función de iterador puede ser una función anónima. Para obtener más información, consulta [Iteradores](../../programming-guide/concepts/iterators.md).  
  
## <a name="exception-handling"></a>Control de excepciones  

 Una `Yield` instrucción puede estar dentro `Try` de un bloque de instrucciones [try... Detectar... Finally](try-catch-finally-statement.md). Un `Try` bloque que tiene una `Yield` instrucción puede tener `Catch` bloques y puede tener un `Finally` bloque.  
  
 Una `Yield` instrucción no puede estar dentro de un `Catch` bloque o un `Finally` bloque.  
  
 Si el `For Each` cuerpo (fuera de la función de iterador) produce una excepción, `Catch` no se ejecuta un bloque de la función de iterador, pero `Finally` se ejecuta un bloque en la función de iterador. Un `Catch` bloque dentro de una función de iterador solo detecta las excepciones que se producen dentro de la función de iterador.  
  
## <a name="technical-implementation"></a>Implementación técnica  

 El código siguiente devuelve un `IEnumerable (Of String)` a partir de una función de iterador y, a continuación, recorre en iteración los elementos de `IEnumerable (Of String)` .  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 La llamada a `MyIteratorFunction` no ejecuta el cuerpo de la función. En su lugar, la llamada devuelve un valor `IEnumerable(Of String)` en la variable `elements`.  
  
 En una iteración del bucle `For Each`, se llama al método <xref:System.Collections.IEnumerator.MoveNext%2A> para `elements`. Esta llamada ejecuta el cuerpo de `MyIteratorFunction` hasta que se alcanza la siguiente instrucción `Yield`. La `Yield` instrucción devuelve una expresión que determina no solo el valor de la `element` variable para su consumo por parte del cuerpo del bucle, sino también la <xref:System.Collections.Generic.IEnumerator%601.Current%2A> propiedad de los elementos, que es `IEnumerable (Of String)` .  
  
 En cada iteración subsiguiente del bucle `For Each`, la ejecución del cuerpo del iterador continúa desde donde se dejó, deteniéndose de nuevo al alcanzar una instrucción `Yield`. El `For Each` bucle se completa cuando se alcanza el final de la función de iterador o una `Return` `Exit Function` instrucción o.  
  
## <a name="example"></a>Ejemplo  

 El ejemplo siguiente tiene una `Yield` instrucción que está dentro [de un... Siguiente](for-next-statement.md) bucle. Cada iteración del cuerpo de la instrucción [for each](for-each-next-statement.md) en `Main` crea una llamada a la `Power` función de iterador. Cada llamada a la función de iterador prosigue con la siguiente ejecución de la instrucción `Yield`, que se produce durante la siguiente iteración del bucle `For…Next`.  
  
 El tipo de valor devuelto del método iterador es <xref:System.Collections.Generic.IEnumerable%601> , un tipo de interfaz de iterador. Cuando se llama al método iterador, este devuelve un objeto enumerable que contiene las potencias de un número.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra un descriptor de acceso `Get` que es un iterador. La declaración de propiedad incluye un `Iterator` modificador.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Para obtener más ejemplos, vea [iteradores](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Vea también

- [Instrucciones](index.md)
