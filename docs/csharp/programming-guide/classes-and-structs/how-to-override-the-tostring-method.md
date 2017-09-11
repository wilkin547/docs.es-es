---
title: "Cómo: Invalidar el método ToString (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
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
ms.openlocfilehash: 60cec855286a3bb572a0bacd08c0f7920a1fc912
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="0813b-102">Cómo: Invalidar el método ToString (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="0813b-102">How to: Override the ToString Method (C# Programming Guide)</span></span>
<span data-ttu-id="0813b-103">Cada clase o struct de C# hereda implícitamente la clase <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="0813b-103">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="0813b-104">Por consiguiente, cada objeto de C# obtiene el método <xref:System.Object.ToString%2A>, que devuelve una representación de cadena de ese objeto.</span><span class="sxs-lookup"><span data-stu-id="0813b-104">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="0813b-105">Por ejemplo, todas las variables de tipo `int` tienen un método `ToString`, que las habilita para devolver su contenido como cadena:</span><span class="sxs-lookup"><span data-stu-id="0813b-105">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 <span data-ttu-id="0813b-106">[!code-cs[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0813b-106">[!code-cs[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]</span></span>  
  
 <span data-ttu-id="0813b-107">Cuando cree una clase o struct personalizados, debe reemplazar el método <xref:System.Object.ToString%2A> para proporcionar información sobre el tipo al código de cliente.</span><span class="sxs-lookup"><span data-stu-id="0813b-107">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="0813b-108">Para obtener información sobre cómo usar cadenas de formato y otros tipos de formato personalizado con el método `ToString`, vea [Aplicar formato a tipos](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="0813b-108">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0813b-109">Cuando decida qué información va a proporcionar a través de este método, considere si la clase o struct se va a usar alguna vez en código que no sea de confianza.</span><span class="sxs-lookup"><span data-stu-id="0813b-109">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="0813b-110">Asegúrese de que no proporciona información que pueda ser aprovechada por código malintencionado.</span><span class="sxs-lookup"><span data-stu-id="0813b-110">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
### <a name="to-override-the-tostring-method-in-your-class-or-struct"></a><span data-ttu-id="0813b-111">Para reemplazar el método ToString en una clase o struct</span><span class="sxs-lookup"><span data-stu-id="0813b-111">To override the ToString method in your class or struct</span></span>  
  
1.  <span data-ttu-id="0813b-112">Declare un método `ToString` con los modificadores y el tipo de valor devuelto siguientes:</span><span class="sxs-lookup"><span data-stu-id="0813b-112">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2.  <span data-ttu-id="0813b-113">Implemente el método para que devuelva una cadena.</span><span class="sxs-lookup"><span data-stu-id="0813b-113">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="0813b-114">En el ejemplo siguiente, se devuelve el nombre de la clase, además de los datos específicos de una instancia concreta de la clase.</span><span class="sxs-lookup"><span data-stu-id="0813b-114">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     <span data-ttu-id="0813b-115">[!code-cs[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="0813b-115">[!code-cs[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]</span></span>  
  
     <span data-ttu-id="0813b-116">Se puede probar el método `ToString` tal y como se muestra en el siguiente ejemplo de código:</span><span class="sxs-lookup"><span data-stu-id="0813b-116">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     <span data-ttu-id="0813b-117">[!code-cs[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="0813b-117">[!code-cs[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0813b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0813b-118">See Also</span></span>  
 <span data-ttu-id="0813b-119"><xref:System.IFormattable></span><span class="sxs-lookup"><span data-stu-id="0813b-119"><xref:System.IFormattable></span></span>   
 <span data-ttu-id="0813b-120">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0813b-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0813b-121">[Clases y estructuras](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="0813b-121">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="0813b-122">[Cadenas](../../../csharp/programming-guide/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="0813b-122">[Strings](../../../csharp/programming-guide/strings/index.md) </span></span>  
 <span data-ttu-id="0813b-123">[string](../../../csharp/language-reference/keywords/string.md) </span><span class="sxs-lookup"><span data-stu-id="0813b-123">[string](../../../csharp/language-reference/keywords/string.md) </span></span>  
 <span data-ttu-id="0813b-124">[new](../../../csharp/language-reference/keywords/new.md) </span><span class="sxs-lookup"><span data-stu-id="0813b-124">[new](../../../csharp/language-reference/keywords/new.md) </span></span>  
 <span data-ttu-id="0813b-125">[override](../../../csharp/language-reference/keywords/override.md) </span><span class="sxs-lookup"><span data-stu-id="0813b-125">[override](../../../csharp/language-reference/keywords/override.md) </span></span>  
 <span data-ttu-id="0813b-126">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span><span class="sxs-lookup"><span data-stu-id="0813b-126">[virtual](../../../csharp/language-reference/keywords/virtual.md) </span></span>  
 [<span data-ttu-id="0813b-127">Aplicación de formato a tipos</span><span class="sxs-lookup"><span data-stu-id="0813b-127">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)

