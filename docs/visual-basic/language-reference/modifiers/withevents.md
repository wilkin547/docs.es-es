---
title: WithEvents (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.WithEvents
- WithEvents
helpviewer_keywords: WithEvents keyword [Visual Basic]
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 68a58fd130c04f2ed0cb1f2e5b9250f6c85f120d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="withevents-visual-basic"></a><span data-ttu-id="1c8bf-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c8bf-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="1c8bf-103">Especifica que una o más variables de miembro declaradas hacen referencia a una instancia de una clase que puede provocar eventos.</span><span class="sxs-lookup"><span data-stu-id="1c8bf-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c8bf-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c8bf-104">Remarks</span></span>  
 <span data-ttu-id="1c8bf-105">Cuando una variable se define utilizando `WithEvents`, puede especificar mediante declaración que un método controla los eventos de la variable mediante la `Handles` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="1c8bf-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>  
  
 <span data-ttu-id="1c8bf-106">Puede usar `WithEvents` sólo en el nivel de clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="1c8bf-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="1c8bf-107">Esto significa que el contexto de la declaración de un `WithEvents` variable debe ser una clase o módulo y no puede ser un archivo de código fuente, el espacio de nombres, la estructura o el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1c8bf-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>  
  
 <span data-ttu-id="1c8bf-108">No se puede utilizar `WithEvents` en un miembro de estructura.</span><span class="sxs-lookup"><span data-stu-id="1c8bf-108">You cannot use `WithEvents` on a structure member.</span></span>  
  
 <span data-ttu-id="1c8bf-109">Puede declarar variables individuales solo, no las matrices, con `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="1c8bf-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="1c8bf-110">Reglas</span><span class="sxs-lookup"><span data-stu-id="1c8bf-110">Rules</span></span>  
  
-   <span data-ttu-id="1c8bf-111">**Tipos de elemento.**</span><span class="sxs-lookup"><span data-stu-id="1c8bf-111">**Element Types.**</span></span> <span data-ttu-id="1c8bf-112">Debe declarar `WithEvents` variables como variables de objeto para que puedan aceptar instancias de clase.</span><span class="sxs-lookup"><span data-stu-id="1c8bf-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="1c8bf-113">Sin embargo, no se puede declarar como `Object`.</span><span class="sxs-lookup"><span data-stu-id="1c8bf-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="1c8bf-114">Se debe declarar como la clase específica que puede provocar los eventos.</span><span class="sxs-lookup"><span data-stu-id="1c8bf-114">You must declare them as the specific class that can raise the events.</span></span>  
  
 <span data-ttu-id="1c8bf-115">El `WithEvents` modificador se puede usar en este contexto: [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="1c8bf-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c8bf-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c8bf-116">See Also</span></span>  
 [<span data-ttu-id="1c8bf-117">Handles</span><span class="sxs-lookup"><span data-stu-id="1c8bf-117">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [<span data-ttu-id="1c8bf-118">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="1c8bf-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="1c8bf-119">Eventos</span><span class="sxs-lookup"><span data-stu-id="1c8bf-119">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
