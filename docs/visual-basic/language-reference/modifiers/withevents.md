---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords:
- WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
ms.openlocfilehash: 75d118ee2bd4918c3a936cb341864ddc5315726b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778643"
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="dfb10-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfb10-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="dfb10-103">Especifica que una o más variables de miembro declaradas hacen referencia a una instancia de una clase que puede provocar eventos.</span><span class="sxs-lookup"><span data-stu-id="dfb10-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfb10-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dfb10-104">Remarks</span></span>  
 <span data-ttu-id="dfb10-105">Cuando una variable se define utilizando `WithEvents`, puede especificar mediante declaración que un método controla los eventos de la variable mediante el `Handles` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="dfb10-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>  
  
 <span data-ttu-id="dfb10-106">Puede usar `WithEvents` sólo en el nivel de clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="dfb10-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="dfb10-107">Esto significa que el contexto de declaración de un `WithEvents` variable debe ser una clase o módulo y no puede ser un archivo de código fuente, el espacio de nombres, la estructura o el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="dfb10-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>  
  
 <span data-ttu-id="dfb10-108">No puede usar `WithEvents` en un miembro de estructura.</span><span class="sxs-lookup"><span data-stu-id="dfb10-108">You cannot use `WithEvents` on a structure member.</span></span>  
  
 <span data-ttu-id="dfb10-109">Puede declarar solo las variables individuales, no las matrices, con `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="dfb10-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="dfb10-110">Reglas</span><span class="sxs-lookup"><span data-stu-id="dfb10-110">Rules</span></span>  
  
- <span data-ttu-id="dfb10-111">**Tipos de elemento.**</span><span class="sxs-lookup"><span data-stu-id="dfb10-111">**Element Types.**</span></span> <span data-ttu-id="dfb10-112">Debe declarar `WithEvents` variables como variables de objeto para que puedan aceptar instancias de clase.</span><span class="sxs-lookup"><span data-stu-id="dfb10-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="dfb10-113">Sin embargo, no se puede declarar como `Object`.</span><span class="sxs-lookup"><span data-stu-id="dfb10-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="dfb10-114">Se debe declarar como la clase específica que puede provocar los eventos.</span><span class="sxs-lookup"><span data-stu-id="dfb10-114">You must declare them as the specific class that can raise the events.</span></span>  
  
 <span data-ttu-id="dfb10-115">El `WithEvents` modificador se puede usar en este contexto: [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="dfb10-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfb10-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="dfb10-116">See also</span></span>

- [<span data-ttu-id="dfb10-117">Handles</span><span class="sxs-lookup"><span data-stu-id="dfb10-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
- [<span data-ttu-id="dfb10-118">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="dfb10-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="dfb10-119">Eventos</span><span class="sxs-lookup"><span data-stu-id="dfb10-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
