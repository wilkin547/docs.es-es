---
description: 'Más información acerca de: auto (Visual Basic)'
title: Automático
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: 9601b6c253d4366c453950b4d8f3c5b2caf3805f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774686"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="80cf7-103">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80cf7-103">Auto (Visual Basic)</span></span>

<span data-ttu-id="80cf7-104">Especifica que Visual Basic debe serializar las cadenas según las reglas de .NET Framework basadas en el nombre externo del procedimiento externo que se va a declarar.</span><span class="sxs-lookup"><span data-stu-id="80cf7-104">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="80cf7-105">Cuando se llama a un procedimiento definido fuera del proyecto, el compilador Visual Basic no tiene acceso a la información que debe tener para llamar al procedimiento correctamente.</span><span class="sxs-lookup"><span data-stu-id="80cf7-105">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="80cf7-106">Esta información incluye dónde se encuentra el procedimiento, cómo se identifica, su secuencia de llamada y tipo de valor devuelto, y el juego de caracteres de cadena que usa.</span><span class="sxs-lookup"><span data-stu-id="80cf7-106">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="80cf7-107">La [instrucción Declare](../statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.</span><span class="sxs-lookup"><span data-stu-id="80cf7-107">The [Declare Statement](../statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="80cf7-108">La `charsetmodifier` parte de la `Declare` instrucción proporciona la información del juego de caracteres para calcular las referencias de las cadenas durante una llamada al procedimiento externo.</span><span class="sxs-lookup"><span data-stu-id="80cf7-108">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="80cf7-109">También afecta al modo en que Visual Basic busca el nombre del procedimiento externo en el archivo externo.</span><span class="sxs-lookup"><span data-stu-id="80cf7-109">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="80cf7-110">El `Auto` modificador especifica que Visual Basic debe serializar las cadenas según las reglas de .NET Framework y que debe determinar el juego de caracteres base de la plataforma en tiempo de ejecución y, posiblemente, modificar el nombre del procedimiento externo si se produce un error en la búsqueda inicial.</span><span class="sxs-lookup"><span data-stu-id="80cf7-110">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="80cf7-111">Para obtener más información, vea "juegos de caracteres" en [instrucción Declare](../statements/declare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="80cf7-111">For more information, see "Character Sets" in [Declare Statement](../statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="80cf7-112">Si no se especifica ningún modificador de juego de caracteres, `Ansi` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="80cf7-112">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80cf7-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="80cf7-113">Remarks</span></span>  

 <span data-ttu-id="80cf7-114">El `Auto` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="80cf7-114">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="80cf7-115">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="80cf7-115">Declare Statement</span></span>](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="80cf7-116">Notas para desarrolladores de Smart Device</span><span class="sxs-lookup"><span data-stu-id="80cf7-116">Smart Device Developer Notes</span></span>  

 <span data-ttu-id="80cf7-117">Esta palabra clave no es compatible.</span><span class="sxs-lookup"><span data-stu-id="80cf7-117">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80cf7-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="80cf7-118">See also</span></span>

- [<span data-ttu-id="80cf7-119">Ansi</span><span class="sxs-lookup"><span data-stu-id="80cf7-119">Ansi</span></span>](ansi.md)
- [<span data-ttu-id="80cf7-120">Unicode</span><span class="sxs-lookup"><span data-stu-id="80cf7-120">Unicode</span></span>](unicode.md)
- [<span data-ttu-id="80cf7-121">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="80cf7-121">Keywords</span></span>](../keywords/index.md)
