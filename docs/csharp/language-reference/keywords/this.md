---
title: this (Referencia de C#)
description: Palabra clave this (Referencia de C#)
keywords: this (C#), palabra clave this (C#), palabra clave this (Referencia de C#), palabra clave this (Referencia del lenguaje de C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- this
- this_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
caps.latest.revision: 19
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
ms.openlocfilehash: 1e764bbd85d06a3b1898f6574064b2844f6d6813
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="this-c-reference"></a><span data-ttu-id="5d437-104">this (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5d437-104">this (C# Reference)</span></span>
<span data-ttu-id="5d437-105">La palabra clave `this` hace referencia a la instancia actual de la clase y también se usa como modificador del primer parámetro de un método de extensión.</span><span class="sxs-lookup"><span data-stu-id="5d437-105">The `this` keyword refers to the current instance of the class and is also used as a modifier of the first parameter of an extension method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d437-106">En este artículo se describe el uso de `this` con instancias de clase.</span><span class="sxs-lookup"><span data-stu-id="5d437-106">This article discusses the use of `this` with class instances.</span></span> <span data-ttu-id="5d437-107">Para obtener más información sobre su uso en métodos de extensión, vea [Métodos de extensión](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="5d437-107">For more information about its use in extension methods, see [Extension Methods](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span>  
  
 <span data-ttu-id="5d437-108">A continuación se indican usos habituales de `this`:</span><span class="sxs-lookup"><span data-stu-id="5d437-108">The following are common uses of `this`:</span></span>  
  
-   <span data-ttu-id="5d437-109">Para calificar a miembros ocultos por nombres similares, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5d437-109">To qualify members hidden by similar names, for example:</span></span>  
  
 <span data-ttu-id="5d437-110">[!code-cs[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5d437-110">[!code-cs[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]</span></span>  
  
-   <span data-ttu-id="5d437-111">Para pasar un objeto como parámetro a otros métodos, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5d437-111">To pass an object as a parameter to other methods, for example:</span></span>  
  
    ```  
    CalcTax(this);  
    ```  
  
-   <span data-ttu-id="5d437-112">Para declarar indizadores, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5d437-112">To declare indexers, for example:</span></span>  
  
 <span data-ttu-id="5d437-113">[!code-cs[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5d437-113">[!code-cs[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]</span></span>  
  
 <span data-ttu-id="5d437-114">Las funciones miembro estáticas no tienen un puntero `this`, debido a que existen en el nivel de clase y no como parte de un objeto.</span><span class="sxs-lookup"><span data-stu-id="5d437-114">Static member functions, because they exist at the class level and not as part of an object, do not have a `this` pointer.</span></span> <span data-ttu-id="5d437-115">Es un error hacer referencia a `this` en un método estático.</span><span class="sxs-lookup"><span data-stu-id="5d437-115">It is an error to refer to `this` in a static method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d437-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d437-116">Example</span></span>  
 <span data-ttu-id="5d437-117">En este ejemplo, se usa `this` para calificar los miembros de la clase `Employee`, `name` y `alias`, que están ocultos por nombres similares.</span><span class="sxs-lookup"><span data-stu-id="5d437-117">In this example, `this` is used to qualify the `Employee` class members, `name` and `alias`, which are hidden by similar names.</span></span> <span data-ttu-id="5d437-118">También se usa para pasar un objeto al método `CalcTax`, que pertenece a otra clase.</span><span class="sxs-lookup"><span data-stu-id="5d437-118">It is also used to pass an object to the method `CalcTax`, which belongs to another class.</span></span>  
  
 <span data-ttu-id="5d437-119">[!code-cs[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="5d437-119">[!code-cs[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5d437-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="5d437-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5d437-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d437-121">See Also</span></span>  
 <span data-ttu-id="5d437-122">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="5d437-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="5d437-123">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5d437-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5d437-124">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="5d437-124">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="5d437-125">[base](../../../csharp/language-reference/keywords/base.md) </span><span class="sxs-lookup"><span data-stu-id="5d437-125">[base](../../../csharp/language-reference/keywords/base.md) </span></span>  
 [<span data-ttu-id="5d437-126">Métodos</span><span class="sxs-lookup"><span data-stu-id="5d437-126">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

