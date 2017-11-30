---
title: this (Referencia de C#)
description: Palabra clave this (Referencia de C#)
keywords: this (C#), palabra clave this (C#), palabra clave this (Referencia de C#), palabra clave this (Referencia del lenguaje de C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- this
- this_CSharpKeyword
helpviewer_keywords: this keyword [C#]
ms.assetid: d4f827fe-4710-410b-89b8-867dad44b8a3
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f159967707061481a34e72a97ec8cc8316d982ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="this-c-reference"></a><span data-ttu-id="8c369-104">this (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="8c369-104">this (C# Reference)</span></span>
<span data-ttu-id="8c369-105">La palabra clave `this` hace referencia a la instancia actual de la clase y también se usa como modificador del primer parámetro de un método de extensión.</span><span class="sxs-lookup"><span data-stu-id="8c369-105">The `this` keyword refers to the current instance of the class and is also used as a modifier of the first parameter of an extension method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c369-106">En este artículo se describe el uso de `this` con instancias de clase.</span><span class="sxs-lookup"><span data-stu-id="8c369-106">This article discusses the use of `this` with class instances.</span></span> <span data-ttu-id="8c369-107">Para obtener más información sobre su uso en métodos de extensión, vea [Métodos de extensión](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="8c369-107">For more information about its use in extension methods, see [Extension Methods](../../../csharp/programming-guide/classes-and-structs/extension-methods.md).</span></span>  
  
 <span data-ttu-id="8c369-108">A continuación se indican usos habituales de `this`:</span><span class="sxs-lookup"><span data-stu-id="8c369-108">The following are common uses of `this`:</span></span>  
  
-   <span data-ttu-id="8c369-109">Para calificar a miembros ocultos por nombres similares, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8c369-109">To qualify members hidden by similar names, for example:</span></span>  
  
 [!code-csharp[csrefKeywordsAccess#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_1.cs)]  
  
-   <span data-ttu-id="8c369-110">Para pasar un objeto como parámetro a otros métodos, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8c369-110">To pass an object as a parameter to other methods, for example:</span></span>  
  
    ```  
    CalcTax(this);  
    ```  
  
-   <span data-ttu-id="8c369-111">Para declarar indizadores, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8c369-111">To declare indexers, for example:</span></span>  
  
 [!code-csharp[csrefKeywordsAccess#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_2.cs)]  
  
 <span data-ttu-id="8c369-112">Las funciones miembro estáticas no tienen un puntero `this`, debido a que existen en el nivel de clase y no como parte de un objeto.</span><span class="sxs-lookup"><span data-stu-id="8c369-112">Static member functions, because they exist at the class level and not as part of an object, do not have a `this` pointer.</span></span> <span data-ttu-id="8c369-113">Es un error hacer referencia a `this` en un método estático.</span><span class="sxs-lookup"><span data-stu-id="8c369-113">It is an error to refer to `this` in a static method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c369-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8c369-114">Example</span></span>  
 <span data-ttu-id="8c369-115">En este ejemplo, se usa `this` para calificar los miembros de la clase `Employee`, `name` y `alias`, que están ocultos por nombres similares.</span><span class="sxs-lookup"><span data-stu-id="8c369-115">In this example, `this` is used to qualify the `Employee` class members, `name` and `alias`, which are hidden by similar names.</span></span> <span data-ttu-id="8c369-116">También se usa para pasar un objeto al método `CalcTax`, que pertenece a otra clase.</span><span class="sxs-lookup"><span data-stu-id="8c369-116">It is also used to pass an object to the method `CalcTax`, which belongs to another class.</span></span>  
  
 [!code-csharp[csrefKeywordsAccess#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/this_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8c369-117">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="8c369-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8c369-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c369-118">See Also</span></span>  
 [<span data-ttu-id="8c369-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="8c369-119">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8c369-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8c369-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8c369-121">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="8c369-121">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="8c369-122">base</span><span class="sxs-lookup"><span data-stu-id="8c369-122">base</span></span>](../../../csharp/language-reference/keywords/base.md)  
 [<span data-ttu-id="8c369-123">Métodos</span><span class="sxs-lookup"><span data-stu-id="8c369-123">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)
