---
title: WithEvents
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 48261e27de302c1809c9725e6e2fc0705a803930
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84386781"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="7958f-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7958f-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="7958f-103">Especifica que una o varias variables de miembro declaradas hacen referencia a una instancia de una clase que puede generar eventos.</span><span class="sxs-lookup"><span data-stu-id="7958f-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="7958f-104">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7958f-104">Remarks</span></span>

<span data-ttu-id="7958f-105">Cuando una variable se define mediante `WithEvents` , puede especificar mediante declaración que un método controla los eventos de la variable mediante la `Handles` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="7958f-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="7958f-106">Solo se puede usar `WithEvents` en el nivel de clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="7958f-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="7958f-107">Esto significa que el contexto de la declaración de una `WithEvents` variable debe ser una clase o módulo y no puede ser un archivo de código fuente, un espacio de nombres, una estructura o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7958f-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="7958f-108">No se puede usar `WithEvents` en un miembro de estructura.</span><span class="sxs-lookup"><span data-stu-id="7958f-108">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="7958f-109">Solo puede declarar variables individuales, no matrices, con `WithEvents` .</span><span class="sxs-lookup"><span data-stu-id="7958f-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="7958f-110">Reglas</span><span class="sxs-lookup"><span data-stu-id="7958f-110">Rules</span></span>

<span data-ttu-id="7958f-111">**Tipos de elemento.**</span><span class="sxs-lookup"><span data-stu-id="7958f-111">**Element Types.**</span></span> <span data-ttu-id="7958f-112">Debe declarar `WithEvents` variables como variables de objeto para que puedan aceptar instancias de clase.</span><span class="sxs-lookup"><span data-stu-id="7958f-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="7958f-113">Sin embargo, no se pueden declarar como `Object` .</span><span class="sxs-lookup"><span data-stu-id="7958f-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="7958f-114">Debe declararlos como la clase específica que puede provocar los eventos.</span><span class="sxs-lookup"><span data-stu-id="7958f-114">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="7958f-115">El `WithEvents` modificador se puede usar en este contexto: [instrucción Dim](../statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="7958f-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="7958f-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7958f-116">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="7958f-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7958f-117">See also</span></span>

- [<span data-ttu-id="7958f-118">Asas</span><span class="sxs-lookup"><span data-stu-id="7958f-118">Handles</span></span>](../statements/handles-clause.md)
- [<span data-ttu-id="7958f-119">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="7958f-119">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="7958f-120">Eventos</span><span class="sxs-lookup"><span data-stu-id="7958f-120">Events</span></span>](../../programming-guide/language-features/events/index.md)
