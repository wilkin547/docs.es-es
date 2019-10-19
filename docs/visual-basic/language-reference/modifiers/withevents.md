---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 50d5a768393e90d28d150b451405e35e6f4c7953
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583042"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="5ee2e-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ee2e-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="5ee2e-103">Especifica que una o varias variables de miembro declaradas hacen referencia a una instancia de una clase que puede generar eventos.</span><span class="sxs-lookup"><span data-stu-id="5ee2e-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>

## <a name="remarks"></a><span data-ttu-id="5ee2e-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5ee2e-104">Remarks</span></span>

<span data-ttu-id="5ee2e-105">Cuando una variable se define utilizando `WithEvents`, puede especificar mediante declaración que un método controla los eventos de la variable mediante la palabra clave `Handles`.</span><span class="sxs-lookup"><span data-stu-id="5ee2e-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>

<span data-ttu-id="5ee2e-106">Solo se puede usar `WithEvents` en el nivel de clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="5ee2e-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="5ee2e-107">Esto significa que el contexto de la declaración de una variable `WithEvents` debe ser una clase o módulo y no puede ser un archivo de código fuente, un espacio de nombres, una estructura o un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5ee2e-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>

<span data-ttu-id="5ee2e-108">No se puede usar `WithEvents` en un miembro de estructura.</span><span class="sxs-lookup"><span data-stu-id="5ee2e-108">You cannot use `WithEvents` on a structure member.</span></span>

<span data-ttu-id="5ee2e-109">Solo se pueden declarar variables individuales, no matrices, con `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="5ee2e-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>

## <a name="rules"></a><span data-ttu-id="5ee2e-110">Reglas</span><span class="sxs-lookup"><span data-stu-id="5ee2e-110">Rules</span></span>

<span data-ttu-id="5ee2e-111">**Tipos de elemento.**</span><span class="sxs-lookup"><span data-stu-id="5ee2e-111">**Element Types.**</span></span> <span data-ttu-id="5ee2e-112">Debe declarar `WithEvents` variables como variables de objeto para que puedan aceptar instancias de clase.</span><span class="sxs-lookup"><span data-stu-id="5ee2e-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="5ee2e-113">Sin embargo, no puede declararlos como `Object`.</span><span class="sxs-lookup"><span data-stu-id="5ee2e-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="5ee2e-114">Debe declararlos como la clase específica que puede provocar los eventos.</span><span class="sxs-lookup"><span data-stu-id="5ee2e-114">You must declare them as the specific class that can raise the events.</span></span>

<span data-ttu-id="5ee2e-115">El modificador `WithEvents` se puede usar en este contexto: [instrucción Dim](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="5ee2e-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>

## <a name="example"></a><span data-ttu-id="5ee2e-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ee2e-116">Example</span></span>

```vb
Dim WithEvents app As Application
```

## <a name="see-also"></a><span data-ttu-id="5ee2e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ee2e-117">See also</span></span>

- [<span data-ttu-id="5ee2e-118">Handles</span><span class="sxs-lookup"><span data-stu-id="5ee2e-118">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="5ee2e-119">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5ee2e-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="5ee2e-120">Eventos</span><span class="sxs-lookup"><span data-stu-id="5ee2e-120">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
