---
title: struct (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: 46cf0b66a50685a717818fe762ad4f1de36d6156
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185750"
---
# <a name="struct-c-reference"></a><span data-ttu-id="395aa-102">struct (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="395aa-102">struct (C# Reference)</span></span>

<span data-ttu-id="395aa-103">Un tipo `struct` es un tipo de valor que normalmente se usa para encapsular pequeños grupos de variables relacionadas, como las coordenadas de un rectángulo o las características de un elemento en un inventario.</span><span class="sxs-lookup"><span data-stu-id="395aa-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="395aa-104">En el siguiente ejemplo se muestra una declaración de struct simple:</span><span class="sxs-lookup"><span data-stu-id="395aa-104">The following example shows a simple struct declaration:</span></span>

```csharp
public struct Book
{
    public decimal price;
    public string title;
    public string author;
}
```

## <a name="remarks"></a><span data-ttu-id="395aa-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="395aa-105">Remarks</span></span>

<span data-ttu-id="395aa-106">Los structs también pueden contener [constructores](../../programming-guide/classes-and-structs/constructors.md), [constantes](../../programming-guide/classes-and-structs/constants.md), [campos](../../programming-guide/classes-and-structs/fields.md), [métodos](../../programming-guide/classes-and-structs/methods.md), [propiedades](../../programming-guide/classes-and-structs/properties.md), [indexadores](../../programming-guide/indexers/index.md), [operadores](../../programming-guide/statements-expressions-operators/operators.md), [eventos](../../programming-guide/events/index.md) y [tipos anidados](../../programming-guide/classes-and-structs/nested-types.md), aunque si se necesitan varios de estos miembros, puede considerar la posibilidad de crear su propio tipo de clase.</span><span class="sxs-lookup"><span data-stu-id="395aa-106">Structs can also contain [constructors](../../programming-guide/classes-and-structs/constructors.md), [constants](../../programming-guide/classes-and-structs/constants.md), [fields](../../programming-guide/classes-and-structs/fields.md), [methods](../../programming-guide/classes-and-structs/methods.md), [properties](../../programming-guide/classes-and-structs/properties.md), [indexers](../../programming-guide/indexers/index.md), [operators](../../programming-guide/statements-expressions-operators/operators.md), [events](../../programming-guide/events/index.md), and [nested types](../../programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>

<span data-ttu-id="395aa-107">Para obtener ejemplos, vea [Usar estructuras](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="395aa-107">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

<span data-ttu-id="395aa-108">Los structs pueden implementar una interfaz, pero no pueden heredar de otro struct.</span><span class="sxs-lookup"><span data-stu-id="395aa-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="395aa-109">Por ese motivo, los miembros de struct no se pueden declarar como `protected`.</span><span class="sxs-lookup"><span data-stu-id="395aa-109">For that reason, struct members cannot be declared as `protected`.</span></span>

<span data-ttu-id="395aa-110">Para obtener más información, vea [Structs](../../programming-guide/classes-and-structs/structs.md).</span><span class="sxs-lookup"><span data-stu-id="395aa-110">For more information, see [Structs](../../programming-guide/classes-and-structs/structs.md).</span></span>

## <a name="examples"></a><span data-ttu-id="395aa-111">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="395aa-111">Examples</span></span>

<span data-ttu-id="395aa-112">Para obtener ejemplos y más información, vea [Usar estructuras](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="395aa-112">For examples and more information, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="395aa-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="395aa-113">C# language specification</span></span>

<span data-ttu-id="395aa-114">Para obtener ejemplos, vea [Usar estructuras](../../programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="395aa-114">For examples, see [Using Structs](../../programming-guide/classes-and-structs/using-structs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="395aa-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="395aa-115">See also</span></span>

- [<span data-ttu-id="395aa-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="395aa-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="395aa-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="395aa-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="395aa-118">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="395aa-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="395aa-119">Tabla de valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="395aa-119">Default Values Table</span></span>](default-values-table.md)
- [<span data-ttu-id="395aa-120">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="395aa-120">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="395aa-121">Tipos</span><span class="sxs-lookup"><span data-stu-id="395aa-121">Types</span></span>](types.md)
- [<span data-ttu-id="395aa-122">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="395aa-122">Value Types</span></span>](value-types.md)
- [<span data-ttu-id="395aa-123">class</span><span class="sxs-lookup"><span data-stu-id="395aa-123">class</span></span>](class.md)
- [<span data-ttu-id="395aa-124">interface</span><span class="sxs-lookup"><span data-stu-id="395aa-124">interface</span></span>](interface.md)
- [<span data-ttu-id="395aa-125">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="395aa-125">Classes and Structs</span></span>](../../programming-guide/classes-and-structs/index.md)