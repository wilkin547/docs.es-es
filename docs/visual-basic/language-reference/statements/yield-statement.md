---
title: "Yield (instrucción) (Visual Basic) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
caps.latest.revision: 22
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
ms.openlocfilehash: 393a9f4de3e801aed5932aef0e2b13d76b003965
ms.lasthandoff: 03/13/2017

---
# <a name="yield-statement-visual-basic"></a>Yield (Instrucción) (Visual Basic)
Envía el siguiente elemento de una colección a un `For Each...Next` instrucción.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Yield expression  
```  
  
#### <a name="parameters"></a>Parámetros  
  
|Término|Definición|  
|---|---|  
|`expression`|Obligatorio. Una expresión que se puede convertir implícitamente al tipo de la función del iterador o `Get` descriptor de acceso que contiene el `Yield` instrucción.|  
  
## <a name="remarks"></a>Comentarios  
 El `Yield` instrucción devuelve un elemento de una colección a la vez. El `Yield` instrucción se incluye en una función de iterador o `Get` descriptor de acceso, que realizan iteraciones personalizadas en una colección.  
  
 Utilizar una función de iterador mediante un [For Each... Next (instrucción)](../../../visual-basic/language-reference/statements/for-each-next-statement.md) o una consulta LINQ. Cada iteración de la `For Each` bucle llama a la función del iterador. Cuando un `Yield` se alcanza la instrucción en la función de iterador, `expression` se devuelve, y se conserva la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.  
  
 Debe existir una conversión implícita del tipo de `expression` en el `Yield` instrucción para el tipo de valor devuelto del iterador.  
  
 Puede usar un `Exit Function` o `Return` instrucción para finalizar la iteración.  
  
 "Producción" no es una palabra reservada y tiene un significado especial solo cuando se utiliza en una `Iterator` función o `Get` descriptor de acceso.  
  
 Para obtener más información acerca de las funciones de iterador y `Get` descriptores de acceso, consulte [iteradores](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="iterator-functions-and-get-accessors"></a>Funciones de iterador y descriptores de acceso Get  
 La declaración de una función de iterador o `Get` descriptor de acceso debe cumplir los siguientes requisitos:  
  
-   Debe incluir un [iterador](../../../visual-basic/language-reference/modifiers/iterator.md) modificador.  
  
-   El tipo devuelto debe ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, o <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable>  
  
-   No puede tener ninguno `ByRef` parámetros.  
  
 Una función de iterador no puede aparecer en un evento, un constructor de instancia, un constructor estático o un destructor estático.  
  
 Una función de iterador puede ser una función anónima. Para más información, vea [Iteradores](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="exception-handling"></a>Control de excepciones  
 Un `Yield` instrucción puede estar dentro de un `Try` bloquear de un [intente... Catch... Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Un `Try` bloque con un `Yield` instrucción puede tener `Catch` bloquea y puede tener un `Finally` bloque.  
  
 Un `Yield` instrucción no puede estar dentro de un `Catch` bloque o una `Finally` bloque.  
  
 Si el `For Each` cuerpo (fuera de la función de iterador) produce una excepción, un `Catch` no se ejecuta el bloque de la función del iterador, pero un `Finally` se ejecuta el bloque de la función del iterador. Un `Catch` bloque dentro de una función de iterador captura solo las excepciones que se producen dentro de la función de iterador.  
  
## <a name="technical-implementation"></a>Implementación técnica  
 El siguiente código devuelve una `IEnumerable (Of String)` desde una función de iterador y, a continuación, recorre en iteración los elementos de la `IEnumerable (Of String)`.  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 La llamada a `MyIteratorFunction` no ejecuta el cuerpo de la función. En su lugar, la llamada devuelve un valor `IEnumerable(Of String)` en la variable `elements`.  
  
 En una iteración de la `For Each` bucles, el <xref:System.Collections.IEnumerator.MoveNext%2A>se invoca para `elements`.</xref:System.Collections.IEnumerator.MoveNext%2A> Esta llamada ejecuta el cuerpo de `MyIteratorFunction` hasta que se alcanza la siguiente instrucción `Yield`. El `Yield` instrucción devuelve una expresión que no sólo determina el valor de la `element` variable para su consumo por el cuerpo del bucle, sino también el <xref:System.Collections.Generic.IEnumerator%601.Current%2A>Propiedades de elementos, que es una `IEnumerable (Of String)`.</xref:System.Collections.Generic.IEnumerator%601.Current%2A>  
  
 En cada iteración subsiguiente del bucle `For Each`, la ejecución del cuerpo del iterador continúa desde donde se dejó, deteniéndose de nuevo al alcanzar una instrucción `Yield`. El `For Each` bucle completa al final de la función del iterador o una `Return` o `Exit Function` se alcanza la instrucción.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente tiene un `Yield` instrucción que se encuentra dentro de un [para... Siguiente](../../../visual-basic/language-reference/statements/for-next-statement.md) bucle. Cada iteración de la [para cada](../../../visual-basic/language-reference/statements/for-each-next-statement.md) cuerpo de la instrucción en `Main` crea una llamada a la `Power` función del iterador. Cada llamada a la función de iterador prosigue con la siguiente ejecución de la instrucción `Yield`, que se produce durante la siguiente iteración del bucle `For…Next`.  
  
 El tipo devuelto del método iterador es <xref:System.Collections.Generic.IEnumerable%601>, un tipo de interfaz de iterador.</xref:System.Collections.Generic.IEnumerable%601> Cuando se llama al método iterador, este devuelve un objeto enumerable que contiene las potencias de un número.  
  
 [!code-vb[VbVbalrStatements&#98;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un descriptor de acceso `Get` que es un iterador. La declaración de propiedad incluye un `Iterator` modificador.  
  
 [!code-vb[VbVbalrStatements&#99;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]  
  
 Para obtener ejemplos adicionales, consulte [iteradores](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="requirements"></a>Requisitos  
 [!INCLUDE[vs_dev11_long](../../../csharp/includes/vs_dev11_long_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Iteradores](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)   
 [Instrucciones](../../../visual-basic/language-reference/statements/index.md)
