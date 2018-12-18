---
title: 'Procedimiento Invalidar el método ToString: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: 0be35b64e9df3ec2a78c62735b1b7072e092f073
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240745"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="844d5-102">Procedimiento Invalidar el método ToString (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="844d5-102">How to: Override the ToString Method (C# Programming Guide)</span></span>
<span data-ttu-id="844d5-103">Cada clase o struct de C# hereda implícitamente la clase <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="844d5-103">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="844d5-104">Por consiguiente, cada objeto de C# obtiene el método <xref:System.Object.ToString%2A>, que devuelve una representación de cadena de ese objeto.</span><span class="sxs-lookup"><span data-stu-id="844d5-104">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="844d5-105">Por ejemplo, todas las variables de tipo `int` tienen un método `ToString`, que las habilita para devolver su contenido como cadena:</span><span class="sxs-lookup"><span data-stu-id="844d5-105">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_1.cs)]  
  
 <span data-ttu-id="844d5-106">Cuando cree una clase o struct personalizados, debe reemplazar el método <xref:System.Object.ToString%2A> para proporcionar información sobre el tipo al código de cliente.</span><span class="sxs-lookup"><span data-stu-id="844d5-106">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="844d5-107">Para obtener información sobre cómo usar cadenas de formato y otros tipos de formato personalizado con el método `ToString`, vea [Aplicar formato a tipos](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="844d5-107">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="844d5-108">Cuando decida qué información va a proporcionar a través de este método, considere si la clase o struct se va a usar alguna vez en código que no sea de confianza.</span><span class="sxs-lookup"><span data-stu-id="844d5-108">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="844d5-109">Asegúrese de que no proporciona información que pueda ser aprovechada por código malintencionado.</span><span class="sxs-lookup"><span data-stu-id="844d5-109">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
### <a name="to-override-the-tostring-method-in-your-class-or-struct"></a><span data-ttu-id="844d5-110">Para reemplazar el método ToString en una clase o struct</span><span class="sxs-lookup"><span data-stu-id="844d5-110">To override the ToString method in your class or struct</span></span>  
  
1.  <span data-ttu-id="844d5-111">Declare un método `ToString` con los modificadores y el tipo de valor devuelto siguientes:</span><span class="sxs-lookup"><span data-stu-id="844d5-111">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2.  <span data-ttu-id="844d5-112">Implemente el método para que devuelva una cadena.</span><span class="sxs-lookup"><span data-stu-id="844d5-112">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="844d5-113">En el ejemplo siguiente, se devuelve el nombre de la clase, además de los datos específicos de una instancia concreta de la clase.</span><span class="sxs-lookup"><span data-stu-id="844d5-113">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     [!code-csharp[csProgGuideInheritance#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_2.cs)]  
  
     <span data-ttu-id="844d5-114">Se puede probar el método `ToString` tal y como se muestra en el siguiente ejemplo de código:</span><span class="sxs-lookup"><span data-stu-id="844d5-114">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-override-the-tostring-method_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="844d5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="844d5-115">See Also</span></span>

- <xref:System.IFormattable>  
- [<span data-ttu-id="844d5-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="844d5-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="844d5-117">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="844d5-117">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [<span data-ttu-id="844d5-118">Cadenas</span><span class="sxs-lookup"><span data-stu-id="844d5-118">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
- [<span data-ttu-id="844d5-119">string</span><span class="sxs-lookup"><span data-stu-id="844d5-119">string</span></span>](../../../csharp/language-reference/keywords/string.md)  
- [<span data-ttu-id="844d5-120">new</span><span class="sxs-lookup"><span data-stu-id="844d5-120">new</span></span>](../../../csharp/language-reference/keywords/new.md)  
- [<span data-ttu-id="844d5-121">override</span><span class="sxs-lookup"><span data-stu-id="844d5-121">override</span></span>](../../../csharp/language-reference/keywords/override.md)  
- [<span data-ttu-id="844d5-122">virtual</span><span class="sxs-lookup"><span data-stu-id="844d5-122">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)  
- [<span data-ttu-id="844d5-123">Aplicación de formato a tipos</span><span class="sxs-lookup"><span data-stu-id="844d5-123">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
