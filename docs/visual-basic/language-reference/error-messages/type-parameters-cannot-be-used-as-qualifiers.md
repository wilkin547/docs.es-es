---
description: 'Más información acerca de: BC32098: los parámetros de tipo no se pueden usar como calificadores'
title: Los parámetros de tipo no se pueden utilizar como calificadores
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 61be8e81c9cf6c7a8339c7bbf0ad9566f582eb57
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99675057"
---
# <a name="bc32098-type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="48ff3-103">BC32098: los parámetros de tipo no se pueden usar como calificadores</span><span class="sxs-lookup"><span data-stu-id="48ff3-103">BC32098: Type parameters cannot be used as qualifiers</span></span>

<span data-ttu-id="48ff3-104">Un elemento de programación está calificado con una cadena de calificación que incluye un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="48ff3-104">A programming element is qualified with a qualification string that includes a type parameter.</span></span>

<span data-ttu-id="48ff3-105">Un parámetro de tipo representa un requisito para un tipo que se va a proporcionar cuando se construya el tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="48ff3-105">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="48ff3-106">No representa un tipo definido específico.</span><span class="sxs-lookup"><span data-stu-id="48ff3-106">It does not represent a specific defined type.</span></span> <span data-ttu-id="48ff3-107">Una cadena de calificación debe incluir solo los elementos que se definen en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="48ff3-107">A qualification string must include only elements that are defined at compile time.</span></span>

<span data-ttu-id="48ff3-108">El código siguiente puede generar este error:</span><span class="sxs-lookup"><span data-stu-id="48ff3-108">The following code can generate this error:</span></span>

```vb
Public Function CheckText(Of c As System.Windows.Forms.Control)(
    badText As String) As Boolean

    Dim saveText As c.Text
    ' Insert code to look for badText within saveText.
End Function
```

 <span data-ttu-id="48ff3-109">**Identificador de error:** BC32098</span><span class="sxs-lookup"><span data-stu-id="48ff3-109">**Error ID:** BC32098</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="48ff3-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="48ff3-110">To correct this error</span></span>

1. <span data-ttu-id="48ff3-111">Quite el parámetro de tipo de la cadena de calificación o reemplácelo por un tipo definido.</span><span class="sxs-lookup"><span data-stu-id="48ff3-111">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>

2. <span data-ttu-id="48ff3-112">Si necesita usar un tipo construido para buscar el elemento de programación que se va a calificar, debe usar la lógica de programa adicional.</span><span class="sxs-lookup"><span data-stu-id="48ff3-112">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>

## <a name="see-also"></a><span data-ttu-id="48ff3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="48ff3-113">See also</span></span>

- [<span data-ttu-id="48ff3-114">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="48ff3-114">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="48ff3-115">Tipos genéricos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="48ff3-115">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="48ff3-116">Type List</span><span class="sxs-lookup"><span data-stu-id="48ff3-116">Type List</span></span>](../statements/type-list.md)
