---
title: Auto (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: e4beb320b3aa0cadb790dd3ab92255496bc32f05
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843843"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="fdb08-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fdb08-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="fdb08-103">Especifica que Visual Basic debe serializar las cadenas según las reglas de .NET Framework basadas en el nombre externo del procedimiento externo que se declara.</span><span class="sxs-lookup"><span data-stu-id="fdb08-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="fdb08-104">Cuando se llama a un procedimiento definido fuera del proyecto, el compilador de Visual Basic no tiene acceso a la información que debe tener para llamar correctamente al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="fdb08-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="fdb08-105">Esta información incluye dónde se encuentra el procedimiento, el cómo se identifica, su secuencia de llamada y el tipo de valor devuelto y el carácter de cadena juego que utiliza.</span><span class="sxs-lookup"><span data-stu-id="fdb08-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="fdb08-106">El [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.</span><span class="sxs-lookup"><span data-stu-id="fdb08-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="fdb08-107">El `charsetmodifier` parte en la `Declare` instrucción proporciona la información del conjunto de caracteres para la serialización de cadenas durante una llamada al procedimiento externo.</span><span class="sxs-lookup"><span data-stu-id="fdb08-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="fdb08-108">También afecta a cómo Visual Basic busca el archivo externo para el nombre del procedimiento externo.</span><span class="sxs-lookup"><span data-stu-id="fdb08-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="fdb08-109">El `Auto` modificador especifica que Visual Basic debe serializar las cadenas según las reglas de .NET Framework y que debe determinar el juego de la plataforma de tiempo de ejecución y, posiblemente, de caracteres base modificar el nombre del procedimiento externo si inicial de búsqueda se produce un error.</span><span class="sxs-lookup"><span data-stu-id="fdb08-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="fdb08-110">Para obtener más información, vea "Juegos de caracteres" en [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fdb08-110">For more information, see "Character Sets" in [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="fdb08-111">Si se especifica ningún modificador de conjunto de caracteres, `Ansi` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fdb08-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdb08-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fdb08-112">Remarks</span></span>  
 <span data-ttu-id="fdb08-113">El `Auto` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="fdb08-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="fdb08-114">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="fdb08-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="fdb08-115">Notas de desarrollador de dispositivos inteligentes</span><span class="sxs-lookup"><span data-stu-id="fdb08-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="fdb08-116">No se admite esta palabra clave.</span><span class="sxs-lookup"><span data-stu-id="fdb08-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb08-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdb08-117">See also</span></span>

- [<span data-ttu-id="fdb08-118">Ansi</span><span class="sxs-lookup"><span data-stu-id="fdb08-118">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)
- [<span data-ttu-id="fdb08-119">Unicode</span><span class="sxs-lookup"><span data-stu-id="fdb08-119">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="fdb08-120">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="fdb08-120">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
