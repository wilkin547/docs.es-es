---
title: "Indizadores (Guía de programación de C#)"
ms.date: 03/10/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
caps.latest.revision: "29"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: db49a602b83940cab3f87dea17accb92a2be825d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="bce61-102">Indizadores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="bce61-102">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="bce61-103">Los indizadores permiten indizar las instancias de una clase o struct como matrices.</span><span class="sxs-lookup"><span data-stu-id="bce61-103">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="bce61-104">El valor indizado se puede establecer o recuperar sin especificar explícitamente un miembro de tipo o de instancia.</span><span class="sxs-lookup"><span data-stu-id="bce61-104">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="bce61-105">Son similares a [propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md), excepto en que sus descriptores de acceso usan parámetros.</span><span class="sxs-lookup"><span data-stu-id="bce61-105">Indexers resemble [properties](../../../csharp/programming-guide/classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  
 
 <span data-ttu-id="bce61-106">En el ejemplo siguiente se define una clase genérica con métodos de descriptor de acceso [get](../../../csharp/language-reference/keywords/get.md) y [set](../../../csharp/language-reference/keywords/set.md) sencillos para asignar y recuperar valores.</span><span class="sxs-lookup"><span data-stu-id="bce61-106">The following example defines a generic class with simple [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="bce61-107">La clase `Program` crea una instancia de esta clase para almacenar cadenas.</span><span class="sxs-lookup"><span data-stu-id="bce61-107">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
>  <span data-ttu-id="bce61-108">Para obtener más ejemplos, vea [Secciones relacionadas](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span><span class="sxs-lookup"><span data-stu-id="bce61-108">For more examples, see [Related Sections](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="bce61-109">Definiciones de cuerpos de expresión</span><span class="sxs-lookup"><span data-stu-id="bce61-109">Expression Body Definitions</span></span>  
 
<span data-ttu-id="bce61-110">Es habitual que un descriptor de acceso get o set de un indizador conste de una única instrucción que devuelve o establece un valor.</span><span class="sxs-lookup"><span data-stu-id="bce61-110">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="bce61-111">Los miembros con forma de expresión proporcionan una sintaxis simplificada para admitir este escenario.</span><span class="sxs-lookup"><span data-stu-id="bce61-111">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="bce61-112">A partir de C# 6, un indizador de solo lectura puede implementarse como un miembro con forma de expresión, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="bce61-112">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

<span data-ttu-id="bce61-113">Tenga en cuenta que `=>` presenta el cuerpo de la expresión y que la palabra clave `get` no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="bce61-113">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span> 

<span data-ttu-id="bce61-114">A partir de C# 7, los descriptores de acceso get y set se pueden implementar como miembros con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="bce61-114">Starting with C# 7, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="bce61-115">En este caso, sí deben utilizarse las palabras clave `get` y `set`.</span><span class="sxs-lookup"><span data-stu-id="bce61-115">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="bce61-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bce61-116">For example:</span></span>

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a><span data-ttu-id="bce61-117">Información general sobre los indizadores</span><span class="sxs-lookup"><span data-stu-id="bce61-117">Indexers Overview</span></span>  
  
-   <span data-ttu-id="bce61-118">Los indizadores permiten indizar objetos de manera similar a como se hace con las matrices.</span><span class="sxs-lookup"><span data-stu-id="bce61-118">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
-   <span data-ttu-id="bce61-119">Un descriptor de acceso `get` devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="bce61-119">A `get` accessor returns a value.</span></span> <span data-ttu-id="bce61-120">Un descriptor de acceso `set` asigna un valor.</span><span class="sxs-lookup"><span data-stu-id="bce61-120">A `set` accessor assigns a value.</span></span>  
  
-   <span data-ttu-id="bce61-121">La palabra clave [this](../../../csharp/language-reference/keywords/this.md) se usa para definir los indizadores.</span><span class="sxs-lookup"><span data-stu-id="bce61-121">The [this](../../../csharp/language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
-   <span data-ttu-id="bce61-122">La palabra clave [value](../../../csharp/language-reference/keywords/value.md) se usa para definir el valor asignado por el indizador `set`.</span><span class="sxs-lookup"><span data-stu-id="bce61-122">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
-   <span data-ttu-id="bce61-123">Los indizadores no tienen que ser indizados por un valor entero; depende de usted cómo definir el mecanismo de búsqueda concreto.</span><span class="sxs-lookup"><span data-stu-id="bce61-123">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
-   <span data-ttu-id="bce61-124">Los indizadores se pueden sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="bce61-124">Indexers can be overloaded.</span></span>  
  
-   <span data-ttu-id="bce61-125">Los indizadores pueden tener más de un parámetro formal, por ejemplo, al tener acceso a una matriz bidimensional.</span><span class="sxs-lookup"><span data-stu-id="bce61-125">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
##  <a name="BKMK_RelatedSections"></a> <span data-ttu-id="bce61-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="bce61-126">Related Sections</span></span>  
  
-   [<span data-ttu-id="bce61-127">Utilizar indizadores</span><span class="sxs-lookup"><span data-stu-id="bce61-127">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="bce61-128">Indizadores en Interfaces</span><span class="sxs-lookup"><span data-stu-id="bce61-128">Indexers in Interfaces</span></span>](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [<span data-ttu-id="bce61-129">Comparación entre propiedades e indizadores</span><span class="sxs-lookup"><span data-stu-id="bce61-129">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [<span data-ttu-id="bce61-130">Restringir la accesibilidad del descriptor de acceso</span><span class="sxs-lookup"><span data-stu-id="bce61-130">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="bce61-131">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="bce61-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bce61-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="bce61-132">See Also</span></span>  
 [<span data-ttu-id="bce61-133">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="bce61-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="bce61-134">Propiedades</span><span class="sxs-lookup"><span data-stu-id="bce61-134">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
