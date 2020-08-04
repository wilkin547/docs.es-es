---
title: 'Indexadores: Guía de programación de C#'
description: Los indizadores de C# permiten indizar instancias de clase o struct como matrices. Puede establecer u obtener el valor indizado sin especificar un tipo o un miembro de instancia.
ms.date: 03/10/2017
f1_keywords:
- cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
ms.openlocfilehash: 07e0ae4294373817e10bb79920c73ec1e275d169
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303119"
---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="4d254-104">Indizadores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="4d254-104">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="4d254-105">Los indizadores permiten indizar las instancias de una clase o struct como matrices.</span><span class="sxs-lookup"><span data-stu-id="4d254-105">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="4d254-106">El valor indizado se puede establecer o recuperar sin especificar explícitamente un miembro de tipo o de instancia.</span><span class="sxs-lookup"><span data-stu-id="4d254-106">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="4d254-107">Son similares a [propiedades](../classes-and-structs/properties.md), excepto en que sus descriptores de acceso usan parámetros.</span><span class="sxs-lookup"><span data-stu-id="4d254-107">Indexers resemble [properties](../classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  

 <span data-ttu-id="4d254-108">En el ejemplo siguiente se define una clase genérica con métodos de descriptor de acceso [get](../../language-reference/keywords/get.md) y [set](../../language-reference/keywords/set.md) sencillos para asignar y recuperar valores.</span><span class="sxs-lookup"><span data-stu-id="4d254-108">The following example defines a generic class with simple [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="4d254-109">La clase `Program` crea una instancia de esta clase para almacenar cadenas.</span><span class="sxs-lookup"><span data-stu-id="4d254-109">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
> <span data-ttu-id="4d254-110">Para obtener más ejemplos, vea [Secciones relacionadas](./index.md#BKMK_RelatedSections).</span><span class="sxs-lookup"><span data-stu-id="4d254-110">For more examples, see [Related Sections](./index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="4d254-111">Definiciones de cuerpos de expresión</span><span class="sxs-lookup"><span data-stu-id="4d254-111">Expression Body Definitions</span></span>  

<span data-ttu-id="4d254-112">Es habitual que un descriptor de acceso get o set de un indizador conste de una única instrucción que devuelve o establece un valor.</span><span class="sxs-lookup"><span data-stu-id="4d254-112">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="4d254-113">Los miembros con forma de expresión proporcionan una sintaxis simplificada para admitir este escenario.</span><span class="sxs-lookup"><span data-stu-id="4d254-113">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="4d254-114">A partir de C# 6, un indizador de solo lectura puede implementarse como un miembro con forma de expresión, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4d254-114">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

<span data-ttu-id="4d254-115">Tenga en cuenta que `=>` presenta el cuerpo de la expresión y que la palabra clave `get` no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="4d254-115">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span>

<span data-ttu-id="4d254-116">A partir de C# 7.0, los descriptores de acceso get y set se pueden implementar como miembros con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="4d254-116">Starting with C# 7.0, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="4d254-117">En este caso, sí deben utilizarse las palabras clave `get` y `set`.</span><span class="sxs-lookup"><span data-stu-id="4d254-117">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="4d254-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4d254-118">For example:</span></span>

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a><span data-ttu-id="4d254-119">Información general sobre los indizadores</span><span class="sxs-lookup"><span data-stu-id="4d254-119">Indexers Overview</span></span>  
  
- <span data-ttu-id="4d254-120">Los indizadores permiten indizar objetos de manera similar a como se hace con las matrices.</span><span class="sxs-lookup"><span data-stu-id="4d254-120">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
- <span data-ttu-id="4d254-121">Un descriptor de acceso `get` devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="4d254-121">A `get` accessor returns a value.</span></span> <span data-ttu-id="4d254-122">Un descriptor de acceso `set` asigna un valor.</span><span class="sxs-lookup"><span data-stu-id="4d254-122">A `set` accessor assigns a value.</span></span>  
  
- <span data-ttu-id="4d254-123">La palabra clave [this](../../language-reference/keywords/this.md) se usa para definir los indizadores.</span><span class="sxs-lookup"><span data-stu-id="4d254-123">The [this](../../language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
- <span data-ttu-id="4d254-124">La palabra clave [value](../../language-reference/keywords/value.md) se usa para definir el valor asignado por el indizador `set`.</span><span class="sxs-lookup"><span data-stu-id="4d254-124">The [value](../../language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
- <span data-ttu-id="4d254-125">Los indizadores no tienen que ser indizados por un valor entero; depende de usted cómo definir el mecanismo de búsqueda concreto.</span><span class="sxs-lookup"><span data-stu-id="4d254-125">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
- <span data-ttu-id="4d254-126">Los indizadores se pueden sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="4d254-126">Indexers can be overloaded.</span></span>  
  
- <span data-ttu-id="4d254-127">Los indizadores pueden tener más de un parámetro formal, por ejemplo, al tener acceso a una matriz bidimensional.</span><span class="sxs-lookup"><span data-stu-id="4d254-127">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
## <a name="related-sections"></a><a name="BKMK_RelatedSections"></a> <span data-ttu-id="4d254-128">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="4d254-128">Related Sections</span></span>  
  
- [<span data-ttu-id="4d254-129">Utilizar indizadores</span><span class="sxs-lookup"><span data-stu-id="4d254-129">Using Indexers</span></span>](./using-indexers.md)  
  
- [<span data-ttu-id="4d254-130">Indizadores en Interfaces</span><span class="sxs-lookup"><span data-stu-id="4d254-130">Indexers in Interfaces</span></span>](./indexers-in-interfaces.md)  
  
- [<span data-ttu-id="4d254-131">Comparación entre propiedades e indizadores</span><span class="sxs-lookup"><span data-stu-id="4d254-131">Comparison Between Properties and Indexers</span></span>](./comparison-between-properties-and-indexers.md)  
  
- [<span data-ttu-id="4d254-132">Restringir la accesibilidad del descriptor de acceso</span><span class="sxs-lookup"><span data-stu-id="4d254-132">Restricting Accessor Accessibility</span></span>](../classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="4d254-133">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="4d254-133">C# Language Specification</span></span>  

<span data-ttu-id="4d254-134">Para obtener más información, vea la sección [Indizadores](~/_csharplang/spec/classes.md#indexers) de [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="4d254-134">For more information, see [Indexers](~/_csharplang/spec/classes.md#indexers) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="4d254-135">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="4d254-135">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4d254-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d254-136">See also</span></span>

- [<span data-ttu-id="4d254-137">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4d254-137">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4d254-138">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4d254-138">Properties</span></span>](../classes-and-structs/properties.md)
