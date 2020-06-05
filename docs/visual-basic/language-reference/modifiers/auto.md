---
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
ms.openlocfilehash: b9bdeed55788252c71b8fb1c995c140cbfdf60eb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373133"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="20089-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20089-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="20089-103">Especifica que Visual Basic debe serializar las cadenas según las reglas de .NET Framework basadas en el nombre externo del procedimiento externo que se va a declarar.</span><span class="sxs-lookup"><span data-stu-id="20089-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="20089-104">Cuando se llama a un procedimiento definido fuera del proyecto, el compilador Visual Basic no tiene acceso a la información que debe tener para llamar al procedimiento correctamente.</span><span class="sxs-lookup"><span data-stu-id="20089-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="20089-105">Esta información incluye dónde se encuentra el procedimiento, cómo se identifica, su secuencia de llamada y tipo de valor devuelto, y el juego de caracteres de cadena que usa.</span><span class="sxs-lookup"><span data-stu-id="20089-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="20089-106">La [instrucción Declare](../statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.</span><span class="sxs-lookup"><span data-stu-id="20089-106">The [Declare Statement](../statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="20089-107">La `charsetmodifier` parte de la `Declare` instrucción proporciona la información del juego de caracteres para calcular las referencias de las cadenas durante una llamada al procedimiento externo.</span><span class="sxs-lookup"><span data-stu-id="20089-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="20089-108">También afecta al modo en que Visual Basic busca el nombre del procedimiento externo en el archivo externo.</span><span class="sxs-lookup"><span data-stu-id="20089-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="20089-109">El `Auto` modificador especifica que Visual Basic debe serializar las cadenas según las reglas de .NET Framework y que debe determinar el juego de caracteres base de la plataforma en tiempo de ejecución y, posiblemente, modificar el nombre del procedimiento externo si se produce un error en la búsqueda inicial.</span><span class="sxs-lookup"><span data-stu-id="20089-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="20089-110">Para obtener más información, vea "juegos de caracteres" en [instrucción Declare](../statements/declare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="20089-110">For more information, see "Character Sets" in [Declare Statement](../statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="20089-111">Si no se especifica ningún modificador de juego de caracteres, `Ansi` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="20089-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20089-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="20089-112">Remarks</span></span>  
 <span data-ttu-id="20089-113">El `Auto` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="20089-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="20089-114">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="20089-114">Declare Statement</span></span>](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="20089-115">Notas para desarrolladores de Smart Device</span><span class="sxs-lookup"><span data-stu-id="20089-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="20089-116">Esta palabra clave no es compatible.</span><span class="sxs-lookup"><span data-stu-id="20089-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20089-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="20089-117">See also</span></span>

- [<span data-ttu-id="20089-118">Ansi</span><span class="sxs-lookup"><span data-stu-id="20089-118">Ansi</span></span>](ansi.md)
- [<span data-ttu-id="20089-119">Unicode</span><span class="sxs-lookup"><span data-stu-id="20089-119">Unicode</span></span>](unicode.md)
- [<span data-ttu-id="20089-120">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="20089-120">Keywords</span></span>](../keywords/index.md)
