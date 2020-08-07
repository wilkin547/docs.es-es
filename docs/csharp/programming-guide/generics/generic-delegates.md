---
title: 'Delegados genéricos: Guía de programación de C#'
description: Aprenda a usar delegados genéricos en C#. Vea ejemplos de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: d99271ca9f12e95743d633caac16aaa4151e9c41
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301910"
---
# <a name="generic-delegates-c-programming-guide"></a><span data-ttu-id="32fb7-104">Delegados genéricos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="32fb7-104">Generic Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="32fb7-105">Un [delegado](../../language-reference/builtin-types/reference-types.md) puede definir sus propios parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="32fb7-105">A [delegate](../../language-reference/builtin-types/reference-types.md) can define its own type parameters.</span></span> <span data-ttu-id="32fb7-106">El código que hace referencia al delegado genérico puede especificar el tipo de argumento para crear un tipo construido abierto, igual que al crear una instancia de una clase genérica o al llamar a un método genérico, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="32fb7-106">Code that references the generic delegate can specify the type argument to create a closed constructed type, just like when instantiating a generic class or calling a generic method, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#36)]  
  
 <span data-ttu-id="32fb7-107">C# 2.0 tiene una nueva característica denominada conversión de grupo de métodos, que se aplica a los tipos delegados concretos y genéricos, y permite escribir la línea anterior con esta sintaxis simplificada:</span><span class="sxs-lookup"><span data-stu-id="32fb7-107">C# version 2.0 has a new feature called method group conversion, which applies to concrete as well as generic delegate types, and enables you to write the previous line with this simplified syntax:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#37)]  
  
 <span data-ttu-id="32fb7-108">Los delegados definidos dentro de una clase genérica pueden usar los parámetros de tipo de la clase genérica de la misma manera que lo hacen los métodos de clase.</span><span class="sxs-lookup"><span data-stu-id="32fb7-108">Delegates defined within a generic class can use the generic class type parameters in the same way that class methods do.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#38)]  
  
 <span data-ttu-id="32fb7-109">El código que hace referencia al delegado debe especificar el argumento de tipo de la clase contenedora, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="32fb7-109">Code that references the delegate must specify the type argument of the containing class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#39)]  
  
 <span data-ttu-id="32fb7-110">Los delegados genéricos son especialmente útiles para definir eventos basados en el patrón de diseño habitual porque el argumento del remitente puede estar fuertemente tipado y ya no tiene que convertirse a y de <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="32fb7-110">Generic delegates are especially useful in defining events based on the typical design pattern because the sender argument can be strongly typed and no longer has to be cast to and from <xref:System.Object>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#40)]  
  
## <a name="see-also"></a><span data-ttu-id="32fb7-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="32fb7-111">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="32fb7-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="32fb7-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="32fb7-113">Introducción a los genéricos</span><span class="sxs-lookup"><span data-stu-id="32fb7-113">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="32fb7-114">Métodos genéricos</span><span class="sxs-lookup"><span data-stu-id="32fb7-114">Generic Methods</span></span>](./generic-methods.md)
- [<span data-ttu-id="32fb7-115">Clases genéricas</span><span class="sxs-lookup"><span data-stu-id="32fb7-115">Generic Classes</span></span>](./generic-classes.md)
- [<span data-ttu-id="32fb7-116">Interfaces genéricas</span><span class="sxs-lookup"><span data-stu-id="32fb7-116">Generic Interfaces</span></span>](./generic-interfaces.md)
- [<span data-ttu-id="32fb7-117">Delegados</span><span class="sxs-lookup"><span data-stu-id="32fb7-117">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="32fb7-118">Genéricos</span><span class="sxs-lookup"><span data-stu-id="32fb7-118">Generics</span></span>](../../../standard/generics/index.md)
