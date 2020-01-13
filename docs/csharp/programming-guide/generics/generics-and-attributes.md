---
title: 'Genéricos y atributos: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 47bf4e8f07a8b6778db8fa675d745d362dc10d7d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75703031"
---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="fdfe5-102">Genéricos y atributos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="fdfe5-102">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="fdfe5-103">Los atributos pueden aplicarse a los tipos genéricos de la misma manera que los tipos no genéricos.</span><span class="sxs-lookup"><span data-stu-id="fdfe5-103">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="fdfe5-104">Para obtener más información sobre la aplicación de los atributos, vea [Atributos](../concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="fdfe5-104">For more information on applying attributes, see [Attributes](../concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="fdfe5-105">Los atributos personalizados solo se permiten para hacer referencia a tipos genéricos abiertos, que son tipos genéricos para los que no se proporciona ningún argumento de tipo, y tipos genéricos construidos cerrados, que proporcionan argumentos para todos los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="fdfe5-105">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="fdfe5-106">En los ejemplos siguientes se usa este atributo personalizado:</span><span class="sxs-lookup"><span data-stu-id="fdfe5-106">The following examples use this custom attribute:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#48](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#48)]  
  
 <span data-ttu-id="fdfe5-107">Un atributo puede hacer referencia a un tipo genérico abierto:</span><span class="sxs-lookup"><span data-stu-id="fdfe5-107">An attribute can reference an open generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#49](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#49)]  
  
 <span data-ttu-id="fdfe5-108">Especifica varios parámetros de tipo con el número de comas apropiado.</span><span class="sxs-lookup"><span data-stu-id="fdfe5-108">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="fdfe5-109">En este ejemplo, `GenericClass2` tiene dos parámetros de tipo:</span><span class="sxs-lookup"><span data-stu-id="fdfe5-109">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#50)]  
  
 <span data-ttu-id="fdfe5-110">Un atributo puede hacer referencia a un tipo genérico construido cerrado:</span><span class="sxs-lookup"><span data-stu-id="fdfe5-110">An attribute can reference a closed constructed generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#51)]  
  
 <span data-ttu-id="fdfe5-111">Un atributo que hace referencia a un parámetro de tipo genérico provocará un error en tiempo de compilación:</span><span class="sxs-lookup"><span data-stu-id="fdfe5-111">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#52](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#52)]  
  
 <span data-ttu-id="fdfe5-112">Un tipo genérico no puede heredarse de <xref:System.Attribute>:</span><span class="sxs-lookup"><span data-stu-id="fdfe5-112">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#53)]  
  
 <span data-ttu-id="fdfe5-113">Para obtener información sobre un tipo genérico o un parámetro de tipo en tiempo de ejecución, puede usar los métodos de <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="fdfe5-113">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="fdfe5-114">Para obtener más información, vea [Genéricos y reflexión](./generics-and-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="fdfe5-114">For more information, see [Generics and Reflection](./generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdfe5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdfe5-115">See also</span></span>

- [<span data-ttu-id="fdfe5-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fdfe5-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fdfe5-117">Genéricos</span><span class="sxs-lookup"><span data-stu-id="fdfe5-117">Generics</span></span>](./index.md)
- [<span data-ttu-id="fdfe5-118">Atributos</span><span class="sxs-lookup"><span data-stu-id="fdfe5-118">Attributes</span></span>](../../../standard/attributes/index.md)
