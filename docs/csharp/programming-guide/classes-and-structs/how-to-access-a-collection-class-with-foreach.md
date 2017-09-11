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
# <a name="how-to-access-a-collection-class-with-foreach-c-programming-guide"></a><span data-ttu-id="3ade9-102">Cómo: Obtener acceso a una clase de colección mediante Foreach (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="3ade9-102">How to: Access a Collection Class with foreach (C# Programming Guide)</span></span>
<span data-ttu-id="3ade9-103">En el ejemplo de código siguiente se muestra cómo se escribe una clase Collection no genérica que se puede usar con la instrucción [foreach](../../../csharp/language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="3ade9-103">The following code example illustrates how to write a non-generic collection class that can be used with [foreach](../../../csharp/language-reference/keywords/foreach-in.md).</span></span> <span data-ttu-id="3ade9-104">En el ejemplo se define una clase de tokenizador de cadenas.</span><span class="sxs-lookup"><span data-stu-id="3ade9-104">The example defines a string tokenizer class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ade9-105">En este ejemplo se representa el procedimiento recomendado solo cuando no se puede usar una clase Collection genérica.</span><span class="sxs-lookup"><span data-stu-id="3ade9-105">This example represents recommended practice only when you cannot use a generic collection class.</span></span> <span data-ttu-id="3ade9-106">Para obtener un ejemplo de cómo se implementa una clase de colección genérica con seguridad de tipos que admita <xref:System.Collections.Generic.IEnumerable%601>, vea [Iteradores](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="3ade9-106">For an example of how to implement a type-safe generic collection class that supports <xref:System.Collections.Generic.IEnumerable%601>, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
 <span data-ttu-id="3ade9-107">En el ejemplo, el siguiente segmento de código usa la clase `Tokens` para dividir la frase "This is a sample sentence."</span><span class="sxs-lookup"><span data-stu-id="3ade9-107">In the example, the following code segment uses the `Tokens` class to break the sentence "This is a sample sentence."</span></span> <span data-ttu-id="3ade9-108">en tokens usando " " y "-" como separadores.</span><span class="sxs-lookup"><span data-stu-id="3ade9-108">into tokens by using ' ' and '-' as separators.</span></span> <span data-ttu-id="3ade9-109">Después, el código muestra esos tokens mediante una instrucción `foreach`.</span><span class="sxs-lookup"><span data-stu-id="3ade9-109">The code then displays those tokens by using a `foreach` statement.</span></span>  
  
 <span data-ttu-id="3ade9-110">[!code-cs[csProgGuideCollections#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3ade9-110">[!code-cs[csProgGuideCollections#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ade9-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3ade9-111">Example</span></span>  
 <span data-ttu-id="3ade9-112">Internamente, la clase `Tokens` usa una matriz para almacenar los tokens.</span><span class="sxs-lookup"><span data-stu-id="3ade9-112">Internally, the `Tokens` class uses an array to store the tokens.</span></span> <span data-ttu-id="3ade9-113">Como las matrices implementan <xref:System.Collections.IEnumerator> y <xref:System.Collections.IEnumerable>, el ejemplo de código podría haber usado los métodos de enumeración de la matriz (<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> y <xref:System.Collections.IEnumerator.Current%2A>) en lugar de definirlos en la clase `Tokens`.</span><span class="sxs-lookup"><span data-stu-id="3ade9-113">Because arrays implement <xref:System.Collections.IEnumerator> and <xref:System.Collections.IEnumerable>, the code example could have used the array's enumeration methods (<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A>, and <xref:System.Collections.IEnumerator.Current%2A>) instead of defining them in the `Tokens` class.</span></span> <span data-ttu-id="3ade9-114">Las definiciones de los métodos se incluyen en el ejemplo para clarificar cómo están definidos y qué hace cada uno.</span><span class="sxs-lookup"><span data-stu-id="3ade9-114">The method definitions are included in the example to clarify how they are defined and what each does.</span></span>  
  
 <span data-ttu-id="3ade9-115">[!code-cs[csProgGuideCollections#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="3ade9-115">[!code-cs[csProgGuideCollections#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_2.cs)]</span></span>  
  
 <span data-ttu-id="3ade9-116">En C#, no es necesario para una clase de colección implementar <xref:System.Collections.IEnumerable> y <xref:System.Collections.IEnumerator> para que sean compatibles con `foreach`.</span><span class="sxs-lookup"><span data-stu-id="3ade9-116">In C#, it is not necessary for a collection class to implement <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> to be compatible with `foreach`.</span></span> <span data-ttu-id="3ade9-117">Si la clase tiene los miembros <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> y <xref:System.Collections.IEnumerator.Current%2A> necesarios, funcionará con `foreach`.</span><span class="sxs-lookup"><span data-stu-id="3ade9-117">If the class has the required <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A>, and <xref:System.Collections.IEnumerator.Current%2A> members, it will work with `foreach`.</span></span> <span data-ttu-id="3ade9-118">Omitir las interfaces tiene la ventaja de que permite definir un tipo de valor devuelto de `Current` que es más específico que <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="3ade9-118">Omitting the interfaces has the advantage of enabling you to define a return type for `Current` that is more specific than <xref:System.Object>.</span></span> <span data-ttu-id="3ade9-119">Esto proporciona seguridad de tipos.</span><span class="sxs-lookup"><span data-stu-id="3ade9-119">This provides type safety.</span></span>  
  
 <span data-ttu-id="3ade9-120">Por ejemplo, cambie las siguientes líneas del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="3ade9-120">For example, change the following lines in the previous example.</span></span>  
  
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
  
 <span data-ttu-id="3ade9-121">Dado que `Current` devuelve una cadena, el compilador puede detectar cuándo se usa un tipo incompatible en una instrucción `foreach`, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="3ade9-121">Because `Current` returns a string, the compiler can detect when an incompatible type is used in a `foreach` statement, as shown in the following code.</span></span>  
  
```csharp  
// Error: Cannot convert type string to int.  
foreach (int item in f)    
```  
  
 <span data-ttu-id="3ade9-122">El inconveniente de omitir <xref:System.Collections.IEnumerable> y <xref:System.Collections.IEnumerator> es que la clase de colección ya no puede interactuar con las instrucciones `foreach` (o equivalentes) de otros lenguajes compatibles con Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3ade9-122">The disadvantage of omitting <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> is that the collection class is no longer interoperable with the `foreach` statements, or equivalent statements, of other common language runtime languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ade9-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ade9-123">See Also</span></span>  
 <span data-ttu-id="3ade9-124"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="3ade9-124"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="3ade9-125">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="3ade9-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="3ade9-126">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3ade9-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3ade9-127">[Arrays](../../../csharp/programming-guide/arrays/index.md)  (Matrices)</span><span class="sxs-lookup"><span data-stu-id="3ade9-127">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 [<span data-ttu-id="3ade9-128">Colecciones</span><span class="sxs-lookup"><span data-stu-id="3ade9-128">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)

