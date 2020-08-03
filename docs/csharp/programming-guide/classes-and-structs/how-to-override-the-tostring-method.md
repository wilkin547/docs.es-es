---
title: Procedimiento para invalidar el método ToString - Guía de programación de C#
description: Obtenga información sobre cómo invalidar el método ToString en C#. Todas las clases o estructuras heredan Object y obtienen ToString, que devuelve una representación de cadena de ese objeto.
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: 65b34b485d4b90173a4c956dd0ebaaa590a0c7c9
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865013"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="1448f-104">Procedimiento para invalidar el método ToString (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="1448f-104">How to override the ToString method (C# Programming Guide)</span></span>

<span data-ttu-id="1448f-105">Cada clase o struct de C# hereda implícitamente la clase <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="1448f-105">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="1448f-106">Por consiguiente, cada objeto de C# obtiene el método <xref:System.Object.ToString%2A>, que devuelve una representación de cadena de ese objeto.</span><span class="sxs-lookup"><span data-stu-id="1448f-106">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="1448f-107">Por ejemplo, todas las variables de tipo `int` tienen un método `ToString`, que las habilita para devolver su contenido como cadena:</span><span class="sxs-lookup"><span data-stu-id="1448f-107">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#37)]  
  
 <span data-ttu-id="1448f-108">Cuando cree una clase o struct personalizados, debe reemplazar el método <xref:System.Object.ToString%2A> para proporcionar información sobre el tipo al código de cliente.</span><span class="sxs-lookup"><span data-stu-id="1448f-108">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="1448f-109">Para obtener información sobre cómo usar cadenas de formato y otros tipos de formato personalizado con el método `ToString`, vea [Aplicar formato a tipos](../../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="1448f-109">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1448f-110">Cuando decida qué información va a proporcionar a través de este método, considere si la clase o struct se va a usar alguna vez en código que no sea de confianza.</span><span class="sxs-lookup"><span data-stu-id="1448f-110">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="1448f-111">Asegúrese de que no proporciona información que pueda ser aprovechada por código malintencionado.</span><span class="sxs-lookup"><span data-stu-id="1448f-111">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
<span data-ttu-id="1448f-112">Para reemplazar el método `ToString` en una clase o struct:</span><span class="sxs-lookup"><span data-stu-id="1448f-112">To override the `ToString` method in your class or struct:</span></span>
  
1. <span data-ttu-id="1448f-113">Declare un método `ToString` con los modificadores y el tipo de valor devuelto siguientes:</span><span class="sxs-lookup"><span data-stu-id="1448f-113">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2. <span data-ttu-id="1448f-114">Implemente el método para que devuelva una cadena.</span><span class="sxs-lookup"><span data-stu-id="1448f-114">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="1448f-115">En el ejemplo siguiente, se devuelve el nombre de la clase, además de los datos específicos de una instancia concreta de la clase.</span><span class="sxs-lookup"><span data-stu-id="1448f-115">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     [!code-csharp[csProgGuideInheritance#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#36)]  
  
     <span data-ttu-id="1448f-116">Se puede probar el método `ToString` tal y como se muestra en el siguiente ejemplo de código:</span><span class="sxs-lookup"><span data-stu-id="1448f-116">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="1448f-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1448f-117">See also</span></span>

- <xref:System.IFormattable>
- [<span data-ttu-id="1448f-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1448f-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1448f-119">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="1448f-119">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="1448f-120">Cadenas</span><span class="sxs-lookup"><span data-stu-id="1448f-120">Strings</span></span>](../strings/index.md)
- [<span data-ttu-id="1448f-121">string</span><span class="sxs-lookup"><span data-stu-id="1448f-121">string</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="1448f-122">override</span><span class="sxs-lookup"><span data-stu-id="1448f-122">override</span></span>](../../language-reference/keywords/override.md)
- [<span data-ttu-id="1448f-123">virtual</span><span class="sxs-lookup"><span data-stu-id="1448f-123">virtual</span></span>](../../language-reference/keywords/virtual.md)
- [<span data-ttu-id="1448f-124">Aplicación de formato a tipos</span><span class="sxs-lookup"><span data-stu-id="1448f-124">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
