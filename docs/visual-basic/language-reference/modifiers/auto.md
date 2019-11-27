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
ms.openlocfilehash: 7ea46e5f8b882bb986f23e792b240bad0c5be7a5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351616"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="13bd2-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="13bd2-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="13bd2-103">Especifica que Visual Basic debe serializar las cadenas según las reglas de .NET Framework basadas en el nombre externo del procedimiento externo que se va a declarar.</span><span class="sxs-lookup"><span data-stu-id="13bd2-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="13bd2-104">Cuando se llama a un procedimiento definido fuera del proyecto, el compilador Visual Basic no tiene acceso a la información que debe tener para llamar al procedimiento correctamente.</span><span class="sxs-lookup"><span data-stu-id="13bd2-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="13bd2-105">Esta información incluye dónde se encuentra el procedimiento, cómo se identifica, su secuencia de llamada y tipo de valor devuelto, y el juego de caracteres de cadena que usa.</span><span class="sxs-lookup"><span data-stu-id="13bd2-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="13bd2-106">La [instrucción Declare](../../../visual-basic/language-reference/statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.</span><span class="sxs-lookup"><span data-stu-id="13bd2-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="13bd2-107">La parte `charsetmodifier` de la instrucción `Declare` proporciona la información del juego de caracteres para calcular las referencias de las cadenas durante una llamada al procedimiento externo.</span><span class="sxs-lookup"><span data-stu-id="13bd2-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="13bd2-108">También afecta al modo en que Visual Basic busca el nombre del procedimiento externo en el archivo externo.</span><span class="sxs-lookup"><span data-stu-id="13bd2-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="13bd2-109">El modificador `Auto` especifica que Visual Basic debe serializar las cadenas según las reglas de .NET Framework y que debe determinar el juego de caracteres base de la plataforma en tiempo de ejecución y, posiblemente, modificar el nombre del procedimiento externo si se produce un error en la búsqueda inicial.</span><span class="sxs-lookup"><span data-stu-id="13bd2-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="13bd2-110">Para obtener más información, vea "juegos de caracteres" en [instrucción Declare](../../../visual-basic/language-reference/statements/declare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="13bd2-110">For more information, see "Character Sets" in [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="13bd2-111">Si no se especifica ningún modificador de juego de caracteres, `Ansi` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="13bd2-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13bd2-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="13bd2-112">Remarks</span></span>  
 <span data-ttu-id="13bd2-113">El modificador `Auto` se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="13bd2-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="13bd2-114">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="13bd2-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="13bd2-115">Notas para desarrolladores de Smart Device</span><span class="sxs-lookup"><span data-stu-id="13bd2-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="13bd2-116">Esta palabra clave no es compatible.</span><span class="sxs-lookup"><span data-stu-id="13bd2-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13bd2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="13bd2-117">See also</span></span>

- [<span data-ttu-id="13bd2-118">Ansi</span><span class="sxs-lookup"><span data-stu-id="13bd2-118">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)
- [<span data-ttu-id="13bd2-119">Unicode</span><span class="sxs-lookup"><span data-stu-id="13bd2-119">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="13bd2-120">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="13bd2-120">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
