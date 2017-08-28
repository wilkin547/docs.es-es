---
title: "Cómo: Obtener acceso a una clase de colección mediante Foreach (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- collection classes [C#], foreach statement
ms.assetid: a6b9cf5c-6c8d-4223-b12c-288949434493
caps.latest.revision: 21
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2ad81ab699b079f4aabb04a886211e94a937335d
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-access-a-collection-class-with-foreach-c-programming-guide"></a>Cómo: Obtener acceso a una clase de colección mediante Foreach (Guía de programación de C#)
En el ejemplo de código siguiente se muestra cómo se escribe una clase Collection no genérica que se puede usar con la instrucción [foreach](../../../csharp/language-reference/keywords/foreach-in.md). En el ejemplo se define una clase de tokenizador de cadenas.  
  
> [!NOTE]
>  En este ejemplo se representa el procedimiento recomendado solo cuando no se puede usar una clase Collection genérica. Para obtener un ejemplo de cómo se implementa una clase de colección genérica con seguridad de tipos que admita <xref:System.Collections.Generic.IEnumerable%601>, vea [Iteradores](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
 En el ejemplo, el siguiente segmento de código usa la clase `Tokens` para dividir la frase "This is a sample sentence." en tokens usando " " y "-" como separadores. Después, el código muestra esos tokens mediante una instrucción `foreach`.  
  
 [!code-cs[csProgGuideCollections#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 Internamente, la clase `Tokens` usa una matriz para almacenar los tokens. Como las matrices implementan <xref:System.Collections.IEnumerator> y <xref:System.Collections.IEnumerable>, el ejemplo de código podría haber usado los métodos de enumeración de la matriz (<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> y <xref:System.Collections.IEnumerator.Current%2A>) en lugar de definirlos en la clase `Tokens`. Las definiciones de los métodos se incluyen en el ejemplo para clarificar cómo están definidos y qué hace cada uno.  
  
 [!code-cs[csProgGuideCollections#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_2.cs)]  
  
 En C#, no es necesario para una clase de colección implementar <xref:System.Collections.IEnumerable> y <xref:System.Collections.IEnumerator> para que sean compatibles con `foreach`. Si la clase tiene los miembros <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> y <xref:System.Collections.IEnumerator.Current%2A> necesarios, funcionará con `foreach`. Omitir las interfaces tiene la ventaja de que permite definir un tipo de valor devuelto de `Current` que es más específico que <xref:System.Object>. Esto proporciona seguridad de tipos.  
  
 Por ejemplo, cambie las siguientes líneas del ejemplo anterior.  
  
```csharp  
// Change the Tokens class so that it no longer implements IEnumerable.  
public class Tokens  
{  
    // . . .  
  
    // Change the return type for the GetEnumerator method.  
    public TokenEnumerator GetEnumerator()  
    {   }  
  
    // Change TokenEnumerator so that it no longer implements IEnumerator.  
    public class TokenEnumerator  
    {  
        // . . .  
  
        // Change the return type of method Current to string.  
        public string Current  
        {   }  
    }  
 }  
```  
  
 Dado que `Current` devuelve una cadena, el compilador puede detectar cuándo se usa un tipo incompatible en una instrucción `foreach`, como se muestra en el código siguiente.  
  
```csharp  
// Error: Cannot convert type string to int.  
foreach (int item in f)    
```  
  
 El inconveniente de omitir <xref:System.Collections.IEnumerable> y <xref:System.Collections.IEnumerator> es que la clase de colección ya no puede interactuar con las instrucciones `foreach` (o equivalentes) de otros lenguajes compatibles con Common Language Runtime.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Generic>   
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)  (Matrices)  
 [Colecciones](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)

