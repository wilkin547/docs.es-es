---
title: yield (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- yield
- yield_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
caps.latest.revision: 46
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 7ac24019390be8501e32b944fb1f9527636815eb
ms.lasthandoff: 03/13/2017

---
# <a name="yield-c-reference"></a>yield (Referencia de C#)
Cuando se usa la palabra clave `yield` en una instrucción, se indica que el método, el operador o el descriptor de acceso `get` en el que aparece es un iterador. Al usar `yield` para definir un iterador ya no es necesaria una clase adicional explícita (la clase que retiene el estado para una enumeración; vea un ejemplo en <xref:System.Collections.Generic.IEnumerator%601>) al implementar los patrones <xref:System.Collections.IEnumerable> y <xref:System.Collections.IEnumerator> para un tipo de colección personalizado.  
  
 En el ejemplo siguiente se muestran las dos formas de la instrucción `yield`.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## <a name="remarks"></a>Comentarios  
 Utilice una instrucción `yield return` para devolver cada elemento de uno en uno.  
  
 Para consumir un método iterador, use una instrucción [foreach](../../../csharp/language-reference/keywords/foreach-in.md) o una consulta LINQ. Cada iteración del bucle `foreach` llama al método iterador. Cuando se alcanza una instrucción `yield return` en el método iterador, se devuelve `expression` y se conserva la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.  
  
 Puede usar una instrucción `yield break` para finalizar la iteración.  
  
 Para obtener más información sobre los iteradores, vea [Iteradores](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="iterator-methods-and-get-accessors"></a>Métodos de iterador y descriptores de acceso get  
 La declaración de un iterador debe cumplir los requisitos siguientes:  
  
-   El tipo de valor devuelto debe ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.  
  
-   La declaración no puede tener ningún parámetro [ref](../../../csharp/language-reference/keywords/ref.md) ni [out](../../../csharp/language-reference/keywords/out.md).  
  
 El tipo `yield` de un iterador que devuelve <xref:System.Collections.IEnumerable> o <xref:System.Collections.IEnumerator> es `object`.  Si el iterador devuelve <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Collections.Generic.IEnumerator%601>, debe haber una conversión implícita del tipo de la expresión en la instrucción `yield return` al parámetro de tipo genérico.  
  
 No se puede incluir una instrucción `yield return` ni `yield break` en los métodos que tengan las siguientes características:  
  
-   Métodos anónimos. Para obtener más información, vea [Métodos anónimos](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).  
  
-   Métodos que contienen bloques inseguros. Para obtener más información, vea [unsafe](../../../csharp/language-reference/keywords/unsafe.md).  
  
## <a name="exception-handling"></a>Control de excepciones  
 Una instrucción `yield return` no puede encontrarse en un bloque try-catch. Una instrucción `yield return` puede encontrarse en el bloque try de una instrucción try-finally.  
  
 Una instrucción `yield break` puede encontrarse en un bloque try o un bloque catch, pero no en un bloque finally.  
  
 Si el cuerpo `foreach` (fuera del método iterador) produce una excepción, se ejecuta un bloque `finally` en el método iterador.  
  
## <a name="technical-implementation"></a>Implementación técnica  
 El código siguiente devuelve un valor `IEnumerable<string>` desde un método iterador y, a continuación, recorre sus elementos en iteración.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 La llamada a `MyIteratorMethod` no ejecuta el cuerpo del método. En su lugar, la llamada devuelve un valor `IEnumerable<string>` en la variable `elements`.  
  
 En una iteración del bucle `foreach`, se llama al método <xref:System.Collections.IEnumerator.MoveNext%2A> para `elements`. Esta llamada ejecuta el cuerpo de `MyIteratorMethod` hasta que se alcanza la siguiente instrucción `yield return`. La expresión devuelta por la instrucción `yield return` determina no solo el valor de la variable `element` para que la use el cuerpo del bucle, sino también la propiedad <xref:System.Collections.Generic.IEnumerator%601.Current%2A> de los elementos, que es un valor `IEnumerable<string>`.  
  
 En cada iteración subsiguiente del bucle `foreach`, la ejecución del cuerpo del iterador continúa desde donde se dejó, deteniéndose de nuevo al alcanzar una instrucción `yield return`. El bucle `foreach` se completa al alcanzar el fin del método iterador o una instrucción `yield break`.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente tiene una instrucción `yield return` que está dentro de un bucle `for`. Cada iteración del cuerpo de instrucción `foreach` en `Process` crea una llamada a la función de iterador `Power`. Cada llamada a la función de iterador prosigue con la siguiente ejecución de la instrucción `yield return`, que se produce durante la siguiente iteración del bucle `for`.  
  
 El tipo de valor devuelto del método iterador es <xref:System.Collections.IEnumerable>, que es un tipo de interfaz de iteradores. Cuando se llama al método iterador, este devuelve un objeto enumerable que contiene las potencias de un número.  
  
 [!code-cs[csrefKeywordsContextual#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un descriptor de acceso `get` que es un iterador. En el ejemplo, cada una de las instrucciones `yield return` devuelve una instancia de una clase definida por el usuario.  
  
 [!code-cs[csrefKeywordsContextual#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_2.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)   
 [Iteradores](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)
