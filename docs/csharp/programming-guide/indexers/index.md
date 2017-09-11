---
title: "Indizadores (Guía de programación de C#)"
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.indexers
dev_langs:
- CSharp
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
caps.latest.revision: 29
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
ms.openlocfilehash: 784308f3073114cd0c07cf15edae527a2654edec
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="5fed5-102">Indizadores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="5fed5-102">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="5fed5-103">Los indizadores permiten indizar las instancias de una clase o struct como matrices.</span><span class="sxs-lookup"><span data-stu-id="5fed5-103">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="5fed5-104">El valor indizado se puede establecer o recuperar sin especificar explícitamente un miembro de tipo o de instancia.</span><span class="sxs-lookup"><span data-stu-id="5fed5-104">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="5fed5-105">Son similares a [propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md), excepto en que sus descriptores de acceso usan parámetros.</span><span class="sxs-lookup"><span data-stu-id="5fed5-105">Indexers resemble [properties](../../../csharp/programming-guide/classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  
 
 <span data-ttu-id="5fed5-106">En el ejemplo siguiente se define una clase genérica con métodos de descriptor de acceso [get](../../../csharp/language-reference/keywords/get.md) y [set](../../../csharp/language-reference/keywords/set.md) sencillos para asignar y recuperar valores.</span><span class="sxs-lookup"><span data-stu-id="5fed5-106">The following example defines a generic class with simple [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="5fed5-107">La clase `Program` crea una instancia de esta clase para almacenar cadenas.</span><span class="sxs-lookup"><span data-stu-id="5fed5-107">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 <span data-ttu-id="5fed5-108">[!code-cs[indizadores 1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5fed5-108">[!code-cs[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5fed5-109">Para obtener más ejemplos, vea [Secciones relacionadas](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span><span class="sxs-lookup"><span data-stu-id="5fed5-109">For more examples, see [Related Sections](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="5fed5-110">Definiciones de cuerpos de expresión</span><span class="sxs-lookup"><span data-stu-id="5fed5-110">Expression Body Definitions</span></span>  
 
<span data-ttu-id="5fed5-111">Es habitual que un descriptor de acceso get o set de un indizador conste de una única instrucción que devuelve o establece un valor.</span><span class="sxs-lookup"><span data-stu-id="5fed5-111">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="5fed5-112">Los miembros con forma de expresión proporcionan una sintaxis simplificada para admitir este escenario.</span><span class="sxs-lookup"><span data-stu-id="5fed5-112">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="5fed5-113">A partir de C# 6, un indizador de solo lectura puede implementarse como un miembro con forma de expresión, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5fed5-113">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

<span data-ttu-id="5fed5-114">[!code-cs[indizadores 2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5fed5-114">[!code-cs[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]</span></span>  

<span data-ttu-id="5fed5-115">Tenga en cuenta que `=>` presenta el cuerpo de la expresión y que la palabra clave `get` no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="5fed5-115">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span> 

<span data-ttu-id="5fed5-116">A partir de C# 7, los descriptores de acceso get y set se pueden implementar como miembros con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="5fed5-116">Starting with C# 7, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="5fed5-117">En este caso, sí deben utilizarse las palabras clave `get` y `set`.</span><span class="sxs-lookup"><span data-stu-id="5fed5-117">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="5fed5-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5fed5-118">For example:</span></span>

<span data-ttu-id="5fed5-119">[!code-cs[indizadores 3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="5fed5-119">[!code-cs[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]</span></span>  
  
## <a name="indexers-overview"></a><span data-ttu-id="5fed5-120">Información general sobre los indizadores</span><span class="sxs-lookup"><span data-stu-id="5fed5-120">Indexers Overview</span></span>  
  
-   <span data-ttu-id="5fed5-121">Los indizadores permiten indizar objetos de manera similar a como se hace con las matrices.</span><span class="sxs-lookup"><span data-stu-id="5fed5-121">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
-   <span data-ttu-id="5fed5-122">Un descriptor de acceso `get` devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="5fed5-122">A `get` accessor returns a value.</span></span> <span data-ttu-id="5fed5-123">Un descriptor de acceso `set` asigna un valor.</span><span class="sxs-lookup"><span data-stu-id="5fed5-123">A `set` accessor assigns a value.</span></span>  
  
-   <span data-ttu-id="5fed5-124">La palabra clave [this](../../../csharp/language-reference/keywords/this.md) se usa para definir los indizadores.</span><span class="sxs-lookup"><span data-stu-id="5fed5-124">The [this](../../../csharp/language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
-   <span data-ttu-id="5fed5-125">La palabra clave [value](../../../csharp/language-reference/keywords/value.md) se usa para definir el valor asignado por el indizador `set`.</span><span class="sxs-lookup"><span data-stu-id="5fed5-125">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
-   <span data-ttu-id="5fed5-126">Los indizadores no tienen que ser indizados por un valor entero; depende de usted cómo definir el mecanismo de búsqueda concreto.</span><span class="sxs-lookup"><span data-stu-id="5fed5-126">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
-   <span data-ttu-id="5fed5-127">Los indizadores se pueden sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="5fed5-127">Indexers can be overloaded.</span></span>  
  
-   <span data-ttu-id="5fed5-128">Los indizadores pueden tener más de un parámetro formal, por ejemplo, al tener acceso a una matriz bidimensional.</span><span class="sxs-lookup"><span data-stu-id="5fed5-128">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
##  <span data-ttu-id="5fed5-129"><a name="BKMK_RelatedSections"></a> Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="5fed5-129"><a name="BKMK_RelatedSections"></a> Related Sections</span></span>  
  
-   [<span data-ttu-id="5fed5-130">Utilizar indizadores</span><span class="sxs-lookup"><span data-stu-id="5fed5-130">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="5fed5-131">Indizadores en Interfaces</span><span class="sxs-lookup"><span data-stu-id="5fed5-131">Indexers in Interfaces</span></span>](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [<span data-ttu-id="5fed5-132">Comparación entre propiedades e indizadores</span><span class="sxs-lookup"><span data-stu-id="5fed5-132">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [<span data-ttu-id="5fed5-133">Restringir la accesibilidad del descriptor de acceso</span><span class="sxs-lookup"><span data-stu-id="5fed5-133">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="5fed5-134">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="5fed5-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5fed5-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fed5-135">See Also</span></span>  
 <span data-ttu-id="5fed5-136">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5fed5-136">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="5fed5-137">Propiedades</span><span class="sxs-lookup"><span data-stu-id="5fed5-137">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)

