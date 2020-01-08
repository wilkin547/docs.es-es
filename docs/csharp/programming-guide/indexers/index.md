---
title: 'Indexadores: Guía de programación de C#'
ms.date: 03/10/2017
f1_keywords:
- cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
ms.openlocfilehash: c00f506a682ec5d9805537b80159fd41d2174b67
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75702953"
---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="c10a0-102">Indizadores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="c10a0-102">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="c10a0-103">Los indizadores permiten indizar las instancias de una clase o struct como matrices.</span><span class="sxs-lookup"><span data-stu-id="c10a0-103">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="c10a0-104">El valor indizado se puede establecer o recuperar sin especificar explícitamente un miembro de tipo o de instancia.</span><span class="sxs-lookup"><span data-stu-id="c10a0-104">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="c10a0-105">Son similares a [propiedades](../classes-and-structs/properties.md), excepto en que sus descriptores de acceso usan parámetros.</span><span class="sxs-lookup"><span data-stu-id="c10a0-105">Indexers resemble [properties](../classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  

 <span data-ttu-id="c10a0-106">En el ejemplo siguiente se define una clase genérica con métodos de descriptor de acceso [get](../../language-reference/keywords/get.md) y [set](../../language-reference/keywords/set.md) sencillos para asignar y recuperar valores.</span><span class="sxs-lookup"><span data-stu-id="c10a0-106">The following example defines a generic class with simple [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="c10a0-107">La clase `Program` crea una instancia de esta clase para almacenar cadenas.</span><span class="sxs-lookup"><span data-stu-id="c10a0-107">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
> <span data-ttu-id="c10a0-108">Para obtener más ejemplos, vea [Secciones relacionadas](./index.md#BKMK_RelatedSections).</span><span class="sxs-lookup"><span data-stu-id="c10a0-108">For more examples, see [Related Sections](./index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="c10a0-109">Definiciones de cuerpos de expresión</span><span class="sxs-lookup"><span data-stu-id="c10a0-109">Expression Body Definitions</span></span>  
 
<span data-ttu-id="c10a0-110">Es habitual que un descriptor de acceso get o set de un indizador conste de una única instrucción que devuelve o establece un valor.</span><span class="sxs-lookup"><span data-stu-id="c10a0-110">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="c10a0-111">Los miembros con forma de expresión proporcionan una sintaxis simplificada para admitir este escenario.</span><span class="sxs-lookup"><span data-stu-id="c10a0-111">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="c10a0-112">A partir de C# 6, un indizador de solo lectura puede implementarse como un miembro con forma de expresión, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c10a0-112">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

<span data-ttu-id="c10a0-113">Tenga en cuenta que `=>` presenta el cuerpo de la expresión y que la palabra clave `get` no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="c10a0-113">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span> 

<span data-ttu-id="c10a0-114">A partir de C# 7.0, los descriptores de acceso get y set se pueden implementar como miembros con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="c10a0-114">Starting with C# 7.0, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="c10a0-115">En este caso, sí deben utilizarse las palabras clave `get` y `set`.</span><span class="sxs-lookup"><span data-stu-id="c10a0-115">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="c10a0-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c10a0-116">For example:</span></span>

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a><span data-ttu-id="c10a0-117">Información general sobre los indizadores</span><span class="sxs-lookup"><span data-stu-id="c10a0-117">Indexers Overview</span></span>  
  
- <span data-ttu-id="c10a0-118">Los indizadores permiten indizar objetos de manera similar a como se hace con las matrices.</span><span class="sxs-lookup"><span data-stu-id="c10a0-118">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
- <span data-ttu-id="c10a0-119">Un descriptor de acceso `get` devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="c10a0-119">A `get` accessor returns a value.</span></span> <span data-ttu-id="c10a0-120">Un descriptor de acceso `set` asigna un valor.</span><span class="sxs-lookup"><span data-stu-id="c10a0-120">A `set` accessor assigns a value.</span></span>  
  
- <span data-ttu-id="c10a0-121">La palabra clave [this](../../language-reference/keywords/this.md) se usa para definir los indizadores.</span><span class="sxs-lookup"><span data-stu-id="c10a0-121">The [this](../../language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
- <span data-ttu-id="c10a0-122">La palabra clave [value](../../language-reference/keywords/value.md) se usa para definir el valor asignado por el indizador `set`.</span><span class="sxs-lookup"><span data-stu-id="c10a0-122">The [value](../../language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
- <span data-ttu-id="c10a0-123">Los indizadores no tienen que ser indizados por un valor entero; depende de usted cómo definir el mecanismo de búsqueda concreto.</span><span class="sxs-lookup"><span data-stu-id="c10a0-123">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
- <span data-ttu-id="c10a0-124">Los indizadores se pueden sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="c10a0-124">Indexers can be overloaded.</span></span>  
  
- <span data-ttu-id="c10a0-125">Los indizadores pueden tener más de un parámetro formal, por ejemplo, al tener acceso a una matriz bidimensional.</span><span class="sxs-lookup"><span data-stu-id="c10a0-125">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
## <a name="BKMK_RelatedSections"></a> <span data-ttu-id="c10a0-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c10a0-126">Related Sections</span></span>  
  
- [<span data-ttu-id="c10a0-127">Utilizar indizadores</span><span class="sxs-lookup"><span data-stu-id="c10a0-127">Using Indexers</span></span>](./using-indexers.md)  
  
- [<span data-ttu-id="c10a0-128">Indizadores en Interfaces</span><span class="sxs-lookup"><span data-stu-id="c10a0-128">Indexers in Interfaces</span></span>](./indexers-in-interfaces.md)  
  
- [<span data-ttu-id="c10a0-129">Comparación entre propiedades e indizadores</span><span class="sxs-lookup"><span data-stu-id="c10a0-129">Comparison Between Properties and Indexers</span></span>](./comparison-between-properties-and-indexers.md)  
  
- [<span data-ttu-id="c10a0-130">Restringir la accesibilidad del descriptor de acceso</span><span class="sxs-lookup"><span data-stu-id="c10a0-130">Restricting Accessor Accessibility</span></span>](../classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="c10a0-131">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c10a0-131">C# Language Specification</span></span>  

<span data-ttu-id="c10a0-132">Para obtener más información, vea la sección [Indizadores](~/_csharplang/spec/classes.md#indexers) de [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="c10a0-132">For more information, see [Indexers](~/_csharplang/spec/classes.md#indexers) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="c10a0-133">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="c10a0-133">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c10a0-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="c10a0-134">See also</span></span>

- [<span data-ttu-id="c10a0-135">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c10a0-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c10a0-136">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c10a0-136">Properties</span></span>](../classes-and-structs/properties.md)
