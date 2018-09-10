---
title: Parámetros de tipos genéricos (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: 5bb19e13a6e34e2e22ebc3f9d46edd85fbe0176e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513714"
---
# <a name="generic-type-parameters-c-programming-guide"></a><span data-ttu-id="26baf-102">Parámetros de tipos genéricos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="26baf-102">Generic Type Parameters (C# Programming Guide)</span></span>
<span data-ttu-id="26baf-103">En un tipo genérico o en una definición de método, un parámetro de tipo es un marcador de posición para un tipo específico que un cliente especifica cuando crean instancias de una variable del tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="26baf-103">In a generic type or method definition, a type parameters is a placeholder for a specific type that a client specifies when they instantiate a variable of the generic type.</span></span> <span data-ttu-id="26baf-104">Una clase genérica, como `GenericList<T>` que se muestra en [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md), no puede usarse como está porque no es realmente un tipo; es más parecida a un plano para un tipo.</span><span class="sxs-lookup"><span data-stu-id="26baf-104">A generic class, such as `GenericList<T>` listed in [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md), cannot be used as-is because it is not really a type; it is more like a blueprint for a type.</span></span> <span data-ttu-id="26baf-105">Para usar `GenericList<T>`, el código cliente debe declarar y crear instancias de un tipo construido especificando un argumento de tipo dentro de corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="26baf-105">To use `GenericList<T>`, client code must declare and instantiate a constructed type by specifying a type argument inside the angle brackets.</span></span> <span data-ttu-id="26baf-106">El argumento de tipo de esta clase determinada puede ser cualquier tipo reconocido por el compilador.</span><span class="sxs-lookup"><span data-stu-id="26baf-106">The type argument for this particular class can be any type recognized by the compiler.</span></span> <span data-ttu-id="26baf-107">Puede crearse cualquier número de instancias de tipo construidas, usando cada una un argumento de tipo diferente, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="26baf-107">Any number of constructed type instances can be created, each one using a different type argument, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_1.cs)]  
  
 <span data-ttu-id="26baf-108">En cada una de estas instancias de `GenericList<T>`, cada aparición de `T` en la clase se sustituirá en tiempo de ejecución con el argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="26baf-108">In each of these instances of `GenericList<T>`, every occurrence of `T` in the class will be substituted at run time with the type argument.</span></span> <span data-ttu-id="26baf-109">Mediante esta sustitución, hemos creado tres objetos eficaces y con seguridad de tipos independientes con una definición de clase única.</span><span class="sxs-lookup"><span data-stu-id="26baf-109">By means of this substitution, we have created three separate type-safe and efficient objects using a single class definition.</span></span> <span data-ttu-id="26baf-110">Para obtener más información sobre cómo se realiza esta sustitución mediante CLR, vea [Genéricos en tiempo de ejecución](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span><span class="sxs-lookup"><span data-stu-id="26baf-110">For more information on how this substitution is performed by the CLR, see [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span></span>  
  
## <a name="type-parameter-naming-guidelines"></a><span data-ttu-id="26baf-111">Instrucciones de nomenclatura de los parámetros de tipo</span><span class="sxs-lookup"><span data-stu-id="26baf-111">Type Parameter Naming Guidelines</span></span>  
  
-   <span data-ttu-id="26baf-112">**Asigne** nombres descriptivos a los parámetros de tipo genérico, a no ser que un nombre de una sola letra sea completamente claro y un nombre descriptivo no agregue ningún valor.</span><span class="sxs-lookup"><span data-stu-id="26baf-112">**Do** name generic type parameters with descriptive names, unless a single letter name is completely self explanatory and a descriptive name would not add value.</span></span>  
  
     [!code-csharp[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_2.cs)]  
  
-   <span data-ttu-id="26baf-113">**Considere** el uso de T como el nombre del parámetro de tipo para los tipos con un parámetro de tipo de una sola letra.</span><span class="sxs-lookup"><span data-stu-id="26baf-113">**Consider** using T as the type parameter name for types with one single letter type parameter.</span></span>  
  
     [!code-csharp[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_3.cs)]  
  
-   <span data-ttu-id="26baf-114">**Establezca** el prefijo "T" a los nombres de parámetro de tipo descriptivos.</span><span class="sxs-lookup"><span data-stu-id="26baf-114">**Do** prefix descriptive type parameter names with "T".</span></span>  
  
     [!code-csharp[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_4.cs)]  
  
-   <span data-ttu-id="26baf-115">**Considere** la posibilidad de indicar restricciones que se encuentran en un parámetro de tipo en el nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="26baf-115">**Consider** indicating constraints placed on a type parameter in the name of parameter.</span></span> <span data-ttu-id="26baf-116">Por ejemplo, un parámetro restringido a `ISession` puede llamarse `TSession`.</span><span class="sxs-lookup"><span data-stu-id="26baf-116">For example, a parameter constrained to `ISession` may be called `TSession`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26baf-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="26baf-117">See Also</span></span>

- <xref:System.Collections.Generic>  
- [<span data-ttu-id="26baf-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="26baf-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="26baf-119">Genéricos</span><span class="sxs-lookup"><span data-stu-id="26baf-119">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)  
- [<span data-ttu-id="26baf-120">Diferencias entre plantillas de C++ y tipos genéricos de C#</span><span class="sxs-lookup"><span data-stu-id="26baf-120">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)
