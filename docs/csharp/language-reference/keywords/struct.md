---
title: struct (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: ddea59e76835ccccd07c299f819796336cddada8
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172154"
---
# <a name="struct-c-reference"></a><span data-ttu-id="efa6d-102">struct (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="efa6d-102">struct (C# Reference)</span></span>
<span data-ttu-id="efa6d-103">Un tipo `struct` es un tipo de valor que normalmente se usa para encapsular pequeños grupos de variables relacionadas, como las coordenadas de un rectángulo o las características de un elemento en un inventario.</span><span class="sxs-lookup"><span data-stu-id="efa6d-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="efa6d-104">En el siguiente ejemplo se muestra una declaración de struct simple:</span><span class="sxs-lookup"><span data-stu-id="efa6d-104">The following example shows a simple struct declaration:</span></span>  
  
```csharp  
public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="efa6d-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="efa6d-105">Remarks</span></span>  
 <span data-ttu-id="efa6d-106">Los structs también pueden contener [constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md), [constantes](../../../csharp/programming-guide/classes-and-structs/constants.md), [campos](../../../csharp/programming-guide/classes-and-structs/fields.md), [métodos](../../../csharp/programming-guide/classes-and-structs/methods.md), [propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md), [indexadores](../../../csharp/programming-guide/indexers/index.md), [operadores](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [eventos](../../../csharp/programming-guide/events/index.md) y [tipos anidados](../../../csharp/programming-guide/classes-and-structs/nested-types.md), aunque si se necesitan varios de estos miembros, puede considerar la posibilidad de crear su propio tipo de clase.</span><span class="sxs-lookup"><span data-stu-id="efa6d-106">Structs can also contain [constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md), [constants](../../../csharp/programming-guide/classes-and-structs/constants.md), [fields](../../../csharp/programming-guide/classes-and-structs/fields.md), [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [indexers](../../../csharp/programming-guide/indexers/index.md), [operators](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [events](../../../csharp/programming-guide/events/index.md), and [nested types](../../../csharp/programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>  
  
 <span data-ttu-id="efa6d-107">Para obtener ejemplos, vea [Usar estructuras](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="efa6d-107">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
 <span data-ttu-id="efa6d-108">Los structs pueden implementar una interfaz, pero no pueden heredar de otro struct.</span><span class="sxs-lookup"><span data-stu-id="efa6d-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="efa6d-109">Por ese motivo, los miembros de struct no se pueden declarar como `protected`.</span><span class="sxs-lookup"><span data-stu-id="efa6d-109">For that reason, struct members cannot be declared as `protected`.</span></span>  
  
 <span data-ttu-id="efa6d-110">Para obtener más información, vea [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md).</span><span class="sxs-lookup"><span data-stu-id="efa6d-110">For more information, see [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="efa6d-111">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="efa6d-111">Examples</span></span>  
 <span data-ttu-id="efa6d-112">Para obtener ejemplos y más información, vea [Usar estructuras](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="efa6d-112">For examples and more information, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="efa6d-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="efa6d-113">C# Language Specification</span></span>  
 <span data-ttu-id="efa6d-114">Para obtener ejemplos, vea [Usar estructuras](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="efa6d-114">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa6d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="efa6d-115">See Also</span></span>  
 [<span data-ttu-id="efa6d-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="efa6d-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="efa6d-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="efa6d-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="efa6d-118">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="efa6d-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="efa6d-119">Tabla de valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="efa6d-119">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)  
 [<span data-ttu-id="efa6d-120">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="efa6d-120">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="efa6d-121">Tipos</span><span class="sxs-lookup"><span data-stu-id="efa6d-121">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="efa6d-122">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="efa6d-122">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="efa6d-123">class</span><span class="sxs-lookup"><span data-stu-id="efa6d-123">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
 [<span data-ttu-id="efa6d-124">interface</span><span class="sxs-lookup"><span data-stu-id="efa6d-124">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
 [<span data-ttu-id="efa6d-125">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="efa6d-125">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
