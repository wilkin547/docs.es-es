---
title: 'Parámetros de tipos genéricos: Guía de programación de C#'
description: Aprenda sobre la definición de tipo genérico en C#, donde un parámetro de tipo es un marcador de posición para un tipo que un cliente especifica para una instancia del tipo genérico.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: dc37029378ac1e9ec194d95b561787761d69a9fd
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299258"
---
# <a name="generic-type-parameters-c-programming-guide"></a><span data-ttu-id="701b7-103">Parámetros de tipos genéricos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="701b7-103">Generic type parameters (C# Programming Guide)</span></span>

<span data-ttu-id="701b7-104">En un tipo genérico o en una definición de método, un parámetro de tipo es un marcador de posición para un tipo específico que un cliente especifica cuando crean instancias de una variable del tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="701b7-104">In a generic type or method definition, a type parameter is a placeholder for a specific type that a client specifies when they create an instance of the generic type.</span></span> <span data-ttu-id="701b7-105">Una clase genérica, como `GenericList<T>` que se muestra en [Introducción a los genéricos](./index.md), no puede usarse como está porque no es realmente un tipo; es más parecida a un plano para un tipo.</span><span class="sxs-lookup"><span data-stu-id="701b7-105">A generic class, such as `GenericList<T>` listed in [Introduction to Generics](./index.md), cannot be used as-is because it is not really a type; it is more like a blueprint for a type.</span></span> <span data-ttu-id="701b7-106">Para usar `GenericList<T>`, el código cliente debe declarar y crear instancias de un tipo construido especificando un argumento de tipo dentro de corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="701b7-106">To use `GenericList<T>`, client code must declare and instantiate a constructed type by specifying a type argument inside the angle brackets.</span></span> <span data-ttu-id="701b7-107">El argumento de tipo de esta clase determinada puede ser cualquier tipo reconocido por el compilador.</span><span class="sxs-lookup"><span data-stu-id="701b7-107">The type argument for this particular class can be any type recognized by the compiler.</span></span> <span data-ttu-id="701b7-108">Puede crearse cualquier número de instancias de tipo construidas, usando cada una un argumento de tipo diferente, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="701b7-108">Any number of constructed type instances can be created, each one using a different type argument, as follows:</span></span>  
  
[!code-csharp[csProgGuideGenerics#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#7)]  
  
<span data-ttu-id="701b7-109">En cada una de estas instancias de `GenericList<T>`, cada aparición de `T` en la clase se sustituye en tiempo de ejecución con el argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="701b7-109">In each of these instances of `GenericList<T>`, every occurrence of `T` in the class is substituted at run time with the type argument.</span></span> <span data-ttu-id="701b7-110">Mediante esta sustitución, hemos creado tres objetos eficaces y con seguridad de tipos independientes con una definición de clase única.</span><span class="sxs-lookup"><span data-stu-id="701b7-110">By means of this substitution, we have created three separate type-safe and efficient objects using a single class definition.</span></span> <span data-ttu-id="701b7-111">Para obtener más información sobre cómo se realiza esta sustitución mediante CLR, vea [Genéricos en tiempo de ejecución](./generics-in-the-run-time.md).</span><span class="sxs-lookup"><span data-stu-id="701b7-111">For more information on how this substitution is performed by the CLR, see [Generics in the Run Time](./generics-in-the-run-time.md).</span></span>  
  
## <a name="type-parameter-naming-guidelines"></a><span data-ttu-id="701b7-112">Instrucciones de nomenclatura de los parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="701b7-112">Type parameter naming guidelines</span></span>  
  
- <span data-ttu-id="701b7-113">**Asigne** nombres descriptivos a los parámetros de tipo genérico, a no ser que un nombre de una sola letra sea completamente claro y un nombre descriptivo no agregue ningún valor.</span><span class="sxs-lookup"><span data-stu-id="701b7-113">**Do** name generic type parameters with descriptive names, unless a single letter name is completely self explanatory and a descriptive name would not add value.</span></span>  
  
   [!code-csharp[csProgGuideGenerics#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#8)]  
  
- <span data-ttu-id="701b7-114">**Considere** el uso de T como el nombre del parámetro de tipo para los tipos con un parámetro de tipo de una sola letra.</span><span class="sxs-lookup"><span data-stu-id="701b7-114">**Consider** using T as the type parameter name for types with one single letter type parameter.</span></span>  
  
   [!code-csharp[csProgGuideGenerics#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#9)]  
  
- <span data-ttu-id="701b7-115">**Establezca** el prefijo "T" a los nombres de parámetro de tipo descriptivos.</span><span class="sxs-lookup"><span data-stu-id="701b7-115">**Do** prefix descriptive type parameter names with "T".</span></span>  
  
   [!code-csharp[csProgGuideGenerics#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#10)]  
  
- <span data-ttu-id="701b7-116">**Considere** la posibilidad de indicar restricciones que se encuentran en un parámetro de tipo en el nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="701b7-116">**Consider** indicating constraints placed on a type parameter in the name of parameter.</span></span> <span data-ttu-id="701b7-117">Por ejemplo, un parámetro restringido a `ISession` puede llamarse `TSession`.</span><span class="sxs-lookup"><span data-stu-id="701b7-117">For example, a parameter constrained to `ISession` may be called `TSession`.</span></span>

<span data-ttu-id="701b7-118">La regla de análisis de código [CA1715](/visualstudio/code-quality/ca1715) puede usarse para asegurarse de que los parámetros de tipo se denominan apropiadamente.</span><span class="sxs-lookup"><span data-stu-id="701b7-118">The code analysis rule [CA1715](/visualstudio/code-quality/ca1715) can be used to ensure that type parameters are named appropriately.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="701b7-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="701b7-119">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="701b7-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="701b7-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="701b7-121">Genéricos</span><span class="sxs-lookup"><span data-stu-id="701b7-121">Generics</span></span>](./index.md)
- [<span data-ttu-id="701b7-122">Diferencias entre plantillas de C++ y tipos genéricos de C#</span><span class="sxs-lookup"><span data-stu-id="701b7-122">Differences Between C++ Templates and C# Generics</span></span>](./differences-between-cpp-templates-and-csharp-generics.md)
