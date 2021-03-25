---
description: 'init (palabra clave): Referencia de C#'
title: 'init (palabra clave): Referencia de C#'
ms.date: 03/03/2021
f1_keywords:
- init
- init_CSharpKeyword
helpviewer_keywords:
- init keyword [C#]
ms.openlocfilehash: 2271b5332c8bfd3223d0c034a44eca4e2ca0ca54
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190446"
---
# <a name="init-c-reference"></a><span data-ttu-id="12d6c-103">init (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="12d6c-103">init (C# Reference)</span></span>

<span data-ttu-id="12d6c-104">En C# 9 y versiones posteriores, la palabra clave `init` define un método de *descriptor de acceso* en una propiedad o un indizador.</span><span class="sxs-lookup"><span data-stu-id="12d6c-104">In C# 9 and later, the `init` keyword defines an *accessor* method in a property or indexer.</span></span> <span data-ttu-id="12d6c-105">Un establecedor de solo inicio asigna un valor a la propiedad o al elemento de indizador únicamente durante la construcción del objeto.</span><span class="sxs-lookup"><span data-stu-id="12d6c-105">An init-only setter assigns a value to the property or the indexer element only during object construction.</span></span> <span data-ttu-id="12d6c-106">Para obtener más información y ejemplos, vea [Propiedades](../../programming-guide/classes-and-structs/properties.md), [Propiedades autoimplementadas](../../programming-guide/classes-and-structs/auto-implemented-properties.md) e [Indexadores](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="12d6c-106">For more information and examples, see [Properties](../../programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md), and [Indexers](../../programming-guide/indexers/index.md).</span></span>

<span data-ttu-id="12d6c-107">En el ejemplo siguiente se definen los descriptores de acceso `get` y `init` para una propiedad denominada `Seconds`.</span><span class="sxs-lookup"><span data-stu-id="12d6c-107">The following example defines both a `get` and an `init` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="12d6c-108">Usa un campo privado denominado `_seconds` para respaldar el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="12d6c-108">It uses a private field named `_seconds` to back the property value.</span></span>

[!code-csharp[init#1](snippets/InitExample1.cs)]

<span data-ttu-id="12d6c-109">A menudo, el descriptor de acceso `init` consta de una única instrucción que asigna un valor, como en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="12d6c-109">Often, the `init` accessor consists of a single statement that assigns a value, as it did in the previous example.</span></span> <span data-ttu-id="12d6c-110">Puede implementar el descriptor de acceso `init` como un miembro con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="12d6c-110">You can implement the `init` accessor as an expression-bodied member.</span></span> <span data-ttu-id="12d6c-111">En el ejemplo siguiente se implementan los descriptores de acceso `get` y `init` como miembros con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="12d6c-111">The following example implements both the `get` and the `init` accessors as expression-bodied members.</span></span>

[!code-csharp[init#3](snippets/InitExample3.cs)]
  
<span data-ttu-id="12d6c-112">En los casos sencillos en los que los descriptores de acceso `get` y `init` de una propiedad no realizan ninguna operación aparte de establecer o recuperar un valor en un campo de respaldo privado, puede aprovechar la compatibilidad del compilador de C# con las propiedades implementadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="12d6c-112">For simple cases in which a property's `get` and `init` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="12d6c-113">En el ejemplo siguiente se implementa `Hours` como una propiedad implementada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="12d6c-113">The following example implements `Hours` as an auto-implemented property.</span></span>

[!code-csharp[init#2](snippets/InitExample2.cs)]
  
## <a name="c-language-specification"></a><span data-ttu-id="12d6c-114">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="12d6c-114">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="12d6c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="12d6c-115">See also</span></span>

- [<span data-ttu-id="12d6c-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="12d6c-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="12d6c-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="12d6c-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="12d6c-118">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="12d6c-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="12d6c-119">Propiedades</span><span class="sxs-lookup"><span data-stu-id="12d6c-119">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)
