---
description: 'set keyword: Referencia de C#'
title: 'set keyword: Referencia de C#'
ms.date: 03/10/2017
f1_keywords:
- set
- set_CSharpKeyword
helpviewer_keywords:
- set keyword [C#]
ms.assetid: 30d7e4e5-cc2e-4635-a597-14a724879619
ms.openlocfilehash: ff0c99e5d4d6271351783befd6650d9a77f39886
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89136920"
---
# <a name="set-c-reference"></a><span data-ttu-id="46602-103">set (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="46602-103">set (C# Reference)</span></span>

<span data-ttu-id="46602-104">La palabra clave `set` define un método de *descriptor de acceso* en una propiedad o indexador que asigna el valor de la propiedad o del elemento del indexador.</span><span class="sxs-lookup"><span data-stu-id="46602-104">The `set` keyword defines an *accessor* method in a property or indexer that assigns a value to the property or the indexer element.</span></span> <span data-ttu-id="46602-105">Para obtener más información y ejemplos, vea [Propiedades](../../programming-guide/classes-and-structs/properties.md), [Propiedades autoimplementadas](../../programming-guide/classes-and-structs/auto-implemented-properties.md) e [Indexadores](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="46602-105">For more information and examples, see [Properties](../../programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md), and [Indexers](../../programming-guide/indexers/index.md).</span></span>

<span data-ttu-id="46602-106">En el ejemplo siguiente se definen unos descriptores de acceso `get` y `set` para una propiedad denominada `Seconds`.</span><span class="sxs-lookup"><span data-stu-id="46602-106">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="46602-107">Usa un campo privado denominado `_seconds` para respaldar el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="46602-107">It uses a private field named `_seconds` to back the property value.</span></span>

[!code-csharp[set#1](~/samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]

<span data-ttu-id="46602-108">A menudo, el descriptor de acceso `set` consta de una única instrucción que asigna un valor, como en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="46602-108">Often, the `set` accessor consists of a single statement that assigns a value, as it did in the previous example.</span></span> <span data-ttu-id="46602-109">A partir de C# 7.0, se puede implementar el descriptor de acceso `set` como un miembro con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="46602-109">Starting with C# 7.0, you can implement the `set` accessor as an expression-bodied member.</span></span> <span data-ttu-id="46602-110">En el ejemplo siguiente se implementan los descriptores de acceso `get` y `set` como miembros con forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="46602-110">The following example implements both the `get` and the `set` accessors as expression-bodied members.</span></span>

[!code-csharp[set#3](~/samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]
  
<span data-ttu-id="46602-111">En los casos sencillos en los que los descriptores de acceso `get` y `set` de una propiedad no realizan ninguna operación aparte de establecer o recuperar un valor en un campo de respaldo privado, puede aprovechar la compatibilidad del compilador de C# con las propiedades implementadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="46602-111">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="46602-112">En el ejemplo siguiente se implementa `Hours` como una propiedad implementada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="46602-112">The following example implements `Hours` as an auto-implemented property.</span></span>

[!code-csharp[set#2](~/samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]
  
## <a name="c-language-specification"></a><span data-ttu-id="46602-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="46602-113">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="46602-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="46602-114">See also</span></span>

- [<span data-ttu-id="46602-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="46602-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="46602-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="46602-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="46602-117">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="46602-117">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="46602-118">Propiedades</span><span class="sxs-lookup"><span data-stu-id="46602-118">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)
