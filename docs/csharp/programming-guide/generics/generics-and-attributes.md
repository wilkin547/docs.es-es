---
title: 'Genéricos y atributos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 99a24a7069145dfad5ce6c9c91f2a8653eb9a224
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589643"
---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="0cc82-102">Genéricos y atributos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="0cc82-102">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="0cc82-103">Los atributos pueden aplicarse a los tipos genéricos de la misma manera que los tipos no genéricos.</span><span class="sxs-lookup"><span data-stu-id="0cc82-103">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="0cc82-104">Para obtener más información sobre la aplicación de los atributos, vea [Atributos](../concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="0cc82-104">For more information on applying attributes, see [Attributes](../concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="0cc82-105">Los atributos personalizados solo se permiten para hacer referencia a tipos genéricos abiertos, que son tipos genéricos para los que no se proporciona ningún argumento de tipo, y tipos genéricos construidos cerrados, que proporcionan argumentos para todos los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="0cc82-105">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="0cc82-106">En los ejemplos siguientes se usa este atributo personalizado:</span><span class="sxs-lookup"><span data-stu-id="0cc82-106">The following examples use this custom attribute:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#48](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#48)]  
  
 <span data-ttu-id="0cc82-107">Un atributo puede hacer referencia a un tipo genérico abierto:</span><span class="sxs-lookup"><span data-stu-id="0cc82-107">An attribute can reference an open generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#49](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#49)]  
  
 <span data-ttu-id="0cc82-108">Especifica varios parámetros de tipo con el número de comas apropiado.</span><span class="sxs-lookup"><span data-stu-id="0cc82-108">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="0cc82-109">En este ejemplo, `GenericClass2` tiene dos parámetros de tipo:</span><span class="sxs-lookup"><span data-stu-id="0cc82-109">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#50)]  
  
 <span data-ttu-id="0cc82-110">Un atributo puede hacer referencia a un tipo genérico construido cerrado:</span><span class="sxs-lookup"><span data-stu-id="0cc82-110">An attribute can reference a closed constructed generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#51)]  
  
 <span data-ttu-id="0cc82-111">Un atributo que hace referencia a un parámetro de tipo genérico provocará un error en tiempo de compilación:</span><span class="sxs-lookup"><span data-stu-id="0cc82-111">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#52](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#52)]  
  
 <span data-ttu-id="0cc82-112">Un tipo genérico no puede heredarse de <xref:System.Attribute>:</span><span class="sxs-lookup"><span data-stu-id="0cc82-112">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#53)]  
  
 <span data-ttu-id="0cc82-113">Para obtener información sobre un tipo genérico o un parámetro de tipo en tiempo de ejecución, puede usar los métodos de <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="0cc82-113">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="0cc82-114">Para obtener más información, vea [Genéricos y reflexión](./generics-and-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="0cc82-114">For more information, see [Generics and Reflection](./generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cc82-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cc82-115">See also</span></span>

- [<span data-ttu-id="0cc82-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0cc82-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0cc82-117">Genéricos</span><span class="sxs-lookup"><span data-stu-id="0cc82-117">Generics</span></span>](./index.md)
- [<span data-ttu-id="0cc82-118">Atributos</span><span class="sxs-lookup"><span data-stu-id="0cc82-118">Attributes</span></span>](../../../standard/attributes/index.md)
