---
title: 'struct: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 8d9a23a0813423571c894758257b284ad67a72e2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744649"
---
# <a name="struct-c-reference"></a><span data-ttu-id="f53ed-102">struct (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f53ed-102">struct (C# Reference)</span></span>

<span data-ttu-id="f53ed-103">Un tipo `struct` es un tipo de valor que normalmente se usa para encapsular pequeños grupos de variables relacionadas, como las coordenadas de un rectángulo o las características de un elemento en un inventario.</span><span class="sxs-lookup"><span data-stu-id="f53ed-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="f53ed-104">En el siguiente ejemplo se muestra una declaración de struct simple:</span><span class="sxs-lookup"><span data-stu-id="f53ed-104">The following example shows a simple struct declaration:</span></span>

```csharp
public struct Book
{
    public decimal price;
    public string title;
    public string author;
}
```

## <a name="remarks"></a><span data-ttu-id="f53ed-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f53ed-105">Remarks</span></span>

<span data-ttu-id="f53ed-106">Los structs también pueden contener [constructores](../../programming-guide/classes-and-structs/constructors.md), [constantes](../../programming-guide/classes-and-structs/constants.md), [campos](../../programming-guide/classes-and-structs/fields.md), [métodos](../../programming-guide/classes-and-structs/methods.md), [propiedades](../../programming-guide/classes-and-structs/properties.md), [indexadores](../../programming-guide/indexers/index.md), [operadores](../operators/index.md), [eventos](../../programming-guide/events/index.md) y [tipos anidados](../../programming-guide/classes-and-structs/nested-types.md), aunque si se necesitan varios de estos miembros, puede considerar la posibilidad de crear su propio tipo de clase.</span><span class="sxs-lookup"><span data-stu-id="f53ed-106">Structs can also contain [constructors](../../programming-guide/classes-and-structs/constructors.md), [constants](../../programming-guide/classes-and-structs/constants.md), [fields](../../programming-guide/classes-and-structs/fields.md), [methods](../../programming-guide/classes-and-structs/methods.md), [properties](../../programming-guide/classes-and-structs/properties.md), [indexers](../../programming-guide/indexers/index.md), [operators](../operators/index.md), [events](../../programming-guide/events/index.md), and [nested types](../../programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>

<span data-ttu-id="f53ed-107">Para obtener ejemplos, vea [Usar estructuras](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="f53ed-107">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

<span data-ttu-id="f53ed-108">Los structs pueden implementar una interfaz, pero no pueden heredar de otro struct.</span><span class="sxs-lookup"><span data-stu-id="f53ed-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="f53ed-109">Por ese motivo, los miembros de struct no se pueden declarar como `protected`.</span><span class="sxs-lookup"><span data-stu-id="f53ed-109">For that reason, struct members cannot be declared as `protected`.</span></span>

<span data-ttu-id="f53ed-110">Para obtener más información, vea [Structs](../../programming-guide/classes-and-structs/structs.md).</span><span class="sxs-lookup"><span data-stu-id="f53ed-110">For more information, see [Structs](../../programming-guide/classes-and-structs/structs.md).</span></span>

## <a name="examples"></a><span data-ttu-id="f53ed-111">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f53ed-111">Examples</span></span>

<span data-ttu-id="f53ed-112">Para obtener ejemplos y más información, vea [Usar estructuras](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="f53ed-112">For examples and more information, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f53ed-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f53ed-113">C# language specification</span></span>

<span data-ttu-id="f53ed-114">Para obtener ejemplos, vea [Usar estructuras](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="f53ed-114">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f53ed-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f53ed-115">See also</span></span>

- [<span data-ttu-id="f53ed-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f53ed-116">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f53ed-117">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="f53ed-117">C# keywords</span></span>](index.md)
- [<span data-ttu-id="f53ed-118">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="f53ed-118">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="f53ed-119">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="f53ed-119">Value types</span></span>](../builtin-types/value-types.md)
- [<span data-ttu-id="f53ed-120">class</span><span class="sxs-lookup"><span data-stu-id="f53ed-120">class</span></span>](class.md)
- [<span data-ttu-id="f53ed-121">interface</span><span class="sxs-lookup"><span data-stu-id="f53ed-121">interface</span></span>](interface.md)
- [<span data-ttu-id="f53ed-122">Clases y estructuras</span><span class="sxs-lookup"><span data-stu-id="f53ed-122">Classes and structs</span></span>](../../programming-guide/classes-and-structs/index.md)
