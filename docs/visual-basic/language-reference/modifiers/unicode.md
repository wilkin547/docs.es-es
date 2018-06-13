---
title: Unicode (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
ms.openlocfilehash: a61fd8e10c39569d92dd84180f678a1ff05a9310
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595727"
---
# <a name="unicode-visual-basic"></a><span data-ttu-id="e7a29-102">Unicode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7a29-102">Unicode (Visual Basic)</span></span>
<span data-ttu-id="e7a29-103">Especifica que Visual Basic debe calcular las referencias de todas las cadenas con valores de Unicode sin tener en cuenta el nombre del procedimiento externo que se declara.</span><span class="sxs-lookup"><span data-stu-id="e7a29-103">Specifies that Visual Basic should marshal all strings to Unicode values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="e7a29-104">Cuando se llama a un procedimiento definido fuera del proyecto, el compilador de Visual Basic no tiene acceso a la información necesaria para llamar correctamente al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="e7a29-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have in order to call the procedure correctly.</span></span> <span data-ttu-id="e7a29-105">Esta información incluye donde se encuentra el procedimiento, el lo identifica, su secuencia de llamada y el tipo de valor devuelto y juego de caracteres de la cadena que utiliza.</span><span class="sxs-lookup"><span data-stu-id="e7a29-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="e7a29-106">El [instrucción Declare](../../../visual-basic/language-reference/statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.</span><span class="sxs-lookup"><span data-stu-id="e7a29-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="e7a29-107">El `charsetmodifier` parte de la `Declare` instrucción proporciona la información del conjunto de caracteres para serializar cadenas durante una llamada al procedimiento externo.</span><span class="sxs-lookup"><span data-stu-id="e7a29-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information to marshal strings during a call to the external procedure.</span></span> <span data-ttu-id="e7a29-108">También afecta al modo en que Visual Basic busca el archivo externo para el nombre del procedimiento externo.</span><span class="sxs-lookup"><span data-stu-id="e7a29-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="e7a29-109">El `Unicode` modificador especifica que Visual Basic debe calcular las referencias de todas las cadenas a valores Unicode y buscar el procedimiento sin modificar su nombre durante la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e7a29-109">The `Unicode` modifier specifies that Visual Basic should marshal all strings to Unicode values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="e7a29-110">Si no se especifica ningún modificador de juego de caracteres, `Ansi` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e7a29-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7a29-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e7a29-111">Remarks</span></span>  
 <span data-ttu-id="e7a29-112">El `Unicode` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="e7a29-112">The `Unicode` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="e7a29-113">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e7a29-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="e7a29-114">Notas de desarrollador de Smart Device</span><span class="sxs-lookup"><span data-stu-id="e7a29-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="e7a29-115">No se admite esta palabra clave.</span><span class="sxs-lookup"><span data-stu-id="e7a29-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7a29-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7a29-116">See Also</span></span>  
 [<span data-ttu-id="e7a29-117">Ansi</span><span class="sxs-lookup"><span data-stu-id="e7a29-117">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [<span data-ttu-id="e7a29-118">Auto</span><span class="sxs-lookup"><span data-stu-id="e7a29-118">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)  
 [<span data-ttu-id="e7a29-119">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e7a29-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
