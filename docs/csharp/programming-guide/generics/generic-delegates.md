---
title: 'Delegados genéricos: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: 4e57256328fc81a485670b47fcf8fd1c38e26fac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712226"
---
# <a name="generic-delegates-c-programming-guide"></a><span data-ttu-id="ac9f9-102">Delegados genéricos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="ac9f9-102">Generic Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="ac9f9-103">Un [delegado](../../language-reference/builtin-types/reference-types.md) puede definir sus propios parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="ac9f9-103">A [delegate](../../language-reference/builtin-types/reference-types.md) can define its own type parameters.</span></span> <span data-ttu-id="ac9f9-104">El código que hace referencia al delegado genérico puede especificar el tipo de argumento para crear un tipo construido abierto, igual que al crear una instancia de una clase genérica o al llamar a un método genérico, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ac9f9-104">Code that references the generic delegate can specify the type argument to create a closed constructed type, just like when instantiating a generic class or calling a generic method, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#36)]  
  
 <span data-ttu-id="ac9f9-105">C# 2.0 tiene una nueva característica denominada conversión de grupo de métodos, que se aplica a los tipos delegados concretos y genéricos, y permite escribir la línea anterior con esta sintaxis simplificada:</span><span class="sxs-lookup"><span data-stu-id="ac9f9-105">C# version 2.0 has a new feature called method group conversion, which applies to concrete as well as generic delegate types, and enables you to write the previous line with this simplified syntax:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#37)]  
  
 <span data-ttu-id="ac9f9-106">Los delegados definidos dentro de una clase genérica pueden usar los parámetros de tipo de la clase genérica de la misma manera que lo hacen los métodos de clase.</span><span class="sxs-lookup"><span data-stu-id="ac9f9-106">Delegates defined within a generic class can use the generic class type parameters in the same way that class methods do.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#38)]  
  
 <span data-ttu-id="ac9f9-107">El código que hace referencia al delegado debe especificar el argumento de tipo de la clase contenedora, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ac9f9-107">Code that references the delegate must specify the type argument of the containing class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#39)]  
  
 <span data-ttu-id="ac9f9-108">Los delegados genéricos son especialmente útiles para definir eventos basados en el patrón de diseño habitual porque el argumento del remitente puede estar fuertemente tipado y ya no tiene que convertirse a y de <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="ac9f9-108">Generic delegates are especially useful in defining events based on the typical design pattern because the sender argument can be strongly typed and no longer has to be cast to and from <xref:System.Object>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#40)]  
  
## <a name="see-also"></a><span data-ttu-id="ac9f9-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac9f9-109">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="ac9f9-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ac9f9-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ac9f9-111">Introducción a los genéricos</span><span class="sxs-lookup"><span data-stu-id="ac9f9-111">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="ac9f9-112">Métodos genéricos</span><span class="sxs-lookup"><span data-stu-id="ac9f9-112">Generic Methods</span></span>](./generic-methods.md)
- [<span data-ttu-id="ac9f9-113">Clases genéricas</span><span class="sxs-lookup"><span data-stu-id="ac9f9-113">Generic Classes</span></span>](./generic-classes.md)
- [<span data-ttu-id="ac9f9-114">Interfaces genéricas</span><span class="sxs-lookup"><span data-stu-id="ac9f9-114">Generic Interfaces</span></span>](./generic-interfaces.md)
- [<span data-ttu-id="ac9f9-115">Delegados</span><span class="sxs-lookup"><span data-stu-id="ac9f9-115">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="ac9f9-116">Genéricos</span><span class="sxs-lookup"><span data-stu-id="ac9f9-116">Generics</span></span>](../../../standard/generics/index.md)
