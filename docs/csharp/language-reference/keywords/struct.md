---
title: struct (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e8a848d5543291ef335e72cb7806158827e865dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="struct-c-reference"></a><span data-ttu-id="4c956-102">struct (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4c956-102">struct (C# Reference)</span></span>
<span data-ttu-id="4c956-103">Un tipo `struct` es un tipo de valor que normalmente se usa para encapsular pequeños grupos de variables relacionadas, como las coordenadas de un rectángulo o las características de un elemento en un inventario.</span><span class="sxs-lookup"><span data-stu-id="4c956-103">A `struct` type is a value type that is typically used to encapsulate small groups of related variables, such as the coordinates of a rectangle or the characteristics of an item in an inventory.</span></span> <span data-ttu-id="4c956-104">En el siguiente ejemplo se muestra una declaración de struct simple:</span><span class="sxs-lookup"><span data-stu-id="4c956-104">The following example shows a simple struct declaration:</span></span>  
  
```  
public struct Book  
{  
    public decimal price;  
    public string title;  
    public string author;  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="4c956-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4c956-105">Remarks</span></span>  
 <span data-ttu-id="4c956-106">Los structs también pueden contener [constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md), [constantes](../../../csharp/programming-guide/classes-and-structs/constants.md), [campos](../../../csharp/programming-guide/classes-and-structs/fields.md), [métodos](../../../csharp/programming-guide/classes-and-structs/methods.md), [propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md), [indexadores](../../../csharp/programming-guide/indexers/index.md), [operadores](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [eventos](../../../csharp/programming-guide/events/index.md) y [tipos anidados](../../../csharp/programming-guide/classes-and-structs/nested-types.md), aunque si se necesitan varios de estos miembros, puede considerar la posibilidad de crear su propio tipo de clase.</span><span class="sxs-lookup"><span data-stu-id="4c956-106">Structs can also contain [constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md), [constants](../../../csharp/programming-guide/classes-and-structs/constants.md), [fields](../../../csharp/programming-guide/classes-and-structs/fields.md), [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [indexers](../../../csharp/programming-guide/indexers/index.md), [operators](../../../csharp/programming-guide/statements-expressions-operators/operators.md), [events](../../../csharp/programming-guide/events/index.md), and [nested types](../../../csharp/programming-guide/classes-and-structs/nested-types.md), although if several such members are required, you should consider making your type a class instead.</span></span>  
  
 <span data-ttu-id="4c956-107">Para obtener ejemplos, vea [Usar estructuras](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="4c956-107">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
 <span data-ttu-id="4c956-108">Los structs pueden implementar una interfaz, pero no pueden heredar de otro struct.</span><span class="sxs-lookup"><span data-stu-id="4c956-108">Structs can implement an interface but they cannot inherit from another struct.</span></span> <span data-ttu-id="4c956-109">Por ese motivo, los miembros de struct no se pueden declarar como `protected`.</span><span class="sxs-lookup"><span data-stu-id="4c956-109">For that reason, struct members cannot be declared as `protected`.</span></span>  
  
 <span data-ttu-id="4c956-110">Para obtener más información, vea [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md).</span><span class="sxs-lookup"><span data-stu-id="4c956-110">For more information, see [Structs](../../../csharp/programming-guide/classes-and-structs/structs.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4c956-111">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4c956-111">Examples</span></span>  
 <span data-ttu-id="4c956-112">Para obtener ejemplos y más información, vea [Usar estructuras](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="4c956-112">For examples and more information, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4c956-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="4c956-113">C# Language Specification</span></span>  
 <span data-ttu-id="4c956-114">Para obtener ejemplos, vea [Usar estructuras](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span><span class="sxs-lookup"><span data-stu-id="4c956-114">For examples, see [Using Structs](../../../csharp/programming-guide/classes-and-structs/using-structs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c956-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c956-115">See Also</span></span>  
 [<span data-ttu-id="4c956-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="4c956-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4c956-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4c956-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4c956-118">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="4c956-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="4c956-119">Tabla de valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="4c956-119">Default Values Table</span></span>](../../../csharp/language-reference/keywords/default-values-table.md)  
 [<span data-ttu-id="4c956-120">Tabla de tipos integrados</span><span class="sxs-lookup"><span data-stu-id="4c956-120">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="4c956-121">Tipos</span><span class="sxs-lookup"><span data-stu-id="4c956-121">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="4c956-122">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="4c956-122">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="4c956-123">class</span><span class="sxs-lookup"><span data-stu-id="4c956-123">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
 [<span data-ttu-id="4c956-124">interface</span><span class="sxs-lookup"><span data-stu-id="4c956-124">interface</span></span>](../../../csharp/language-reference/keywords/interface.md)  
 [<span data-ttu-id="4c956-125">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="4c956-125">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
