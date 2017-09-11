---
title: "Genéricos y atributos (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
caps.latest.revision: 13
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
ms.openlocfilehash: 5136ae928a3a4b6f8ec4d86100d695f958d55858
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="22515-102">Genéricos y atributos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="22515-102">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="22515-103">Los atributos pueden aplicarse a los tipos genéricos de la misma manera que los tipos no genéricos.</span><span class="sxs-lookup"><span data-stu-id="22515-103">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="22515-104">Para obtener más información sobre la aplicación de los atributos, vea [Atributos](../../../csharp/programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="22515-104">For more information on applying attributes, see [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="22515-105">Los atributos personalizados solo se permiten para hacer referencia a tipos genéricos abiertos, que son tipos genéricos para los que no se proporciona ningún argumento de tipo, y tipos genéricos construidos cerrados, que proporcionan argumentos para todos los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="22515-105">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="22515-106">En los ejemplos siguientes se usa este atributo personalizado:</span><span class="sxs-lookup"><span data-stu-id="22515-106">The following examples use this custom attribute:</span></span>  
  
 <span data-ttu-id="22515-107">[!code-cs[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="22515-107">[!code-cs[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]</span></span>  
  
 <span data-ttu-id="22515-108">Un atributo puede hacer referencia a un tipo genérico abierto:</span><span class="sxs-lookup"><span data-stu-id="22515-108">An attribute can reference an open generic type:</span></span>  
  
 <span data-ttu-id="22515-109">[!code-cs[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="22515-109">[!code-cs[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]</span></span>  
  
 <span data-ttu-id="22515-110">Especifica varios parámetros de tipo con el número de comas apropiado.</span><span class="sxs-lookup"><span data-stu-id="22515-110">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="22515-111">En este ejemplo, `GenericClass2` tiene dos parámetros de tipo:</span><span class="sxs-lookup"><span data-stu-id="22515-111">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 <span data-ttu-id="22515-112">[!code-cs[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="22515-112">[!code-cs[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]</span></span>  
  
 <span data-ttu-id="22515-113">Un atributo puede hacer referencia a un tipo genérico construido cerrado:</span><span class="sxs-lookup"><span data-stu-id="22515-113">An attribute can reference a closed constructed generic type:</span></span>  
  
 <span data-ttu-id="22515-114">[!code-cs[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="22515-114">[!code-cs[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]</span></span>  
  
 <span data-ttu-id="22515-115">Un atributo que hace referencia a un parámetro de tipo genérico provocará un error en tiempo de compilación:</span><span class="sxs-lookup"><span data-stu-id="22515-115">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 <span data-ttu-id="22515-116">[!code-cs[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="22515-116">[!code-cs[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]</span></span>  
  
 <span data-ttu-id="22515-117">Un tipo genérico no puede heredarse de <xref:System.Attribute>:</span><span class="sxs-lookup"><span data-stu-id="22515-117">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 <span data-ttu-id="22515-118">[!code-cs[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="22515-118">[!code-cs[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]</span></span>  
  
 <span data-ttu-id="22515-119">Para obtener información sobre un tipo genérico o un parámetro de tipo en tiempo de ejecución, puede usar los métodos de <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="22515-119">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="22515-120">Para obtener más información, vea [Genéricos y reflexión](../../../csharp/programming-guide/generics/generics-and-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="22515-120">For more information, see [Generics and Reflection](../../../csharp/programming-guide/generics/generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22515-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="22515-121">See Also</span></span>  
 <span data-ttu-id="22515-122">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="22515-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="22515-123">[Genéricos](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="22515-123">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 [<span data-ttu-id="22515-124">Atributos</span><span class="sxs-lookup"><span data-stu-id="22515-124">Attributes</span></span>](https://msdn.microsoft.com/library/5x6cd29c)

