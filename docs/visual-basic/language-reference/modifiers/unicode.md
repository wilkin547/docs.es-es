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
ms.openlocfilehash: b3c9452f8d144fb18ea3efcb35b85caed80e8692
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778682"
---
# <a name="unicode-visual-basic"></a><span data-ttu-id="ae57d-102">Unicode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae57d-102">Unicode (Visual Basic)</span></span>
<span data-ttu-id="ae57d-103">Especifica que Visual Basic debe serializar todas las cadenas como valores Unicode independientemente del nombre del procedimiento externo que se declara.</span><span class="sxs-lookup"><span data-stu-id="ae57d-103">Specifies that Visual Basic should marshal all strings to Unicode values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="ae57d-104">Cuando se llama a un procedimiento definido fuera del proyecto, el compilador de Visual Basic no tiene acceso a la información debe tener para llamar correctamente al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ae57d-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have in order to call the procedure correctly.</span></span> <span data-ttu-id="ae57d-105">Esta información incluye dónde se encuentra el procedimiento, el cómo se identifica, su secuencia de llamada y el tipo de valor devuelto y el carácter de cadena juego que utiliza.</span><span class="sxs-lookup"><span data-stu-id="ae57d-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="ae57d-106">El [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.</span><span class="sxs-lookup"><span data-stu-id="ae57d-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="ae57d-107">El `charsetmodifier` parte en la `Declare` instrucción proporciona la información del conjunto de caracteres para serializar cadenas durante una llamada al procedimiento externo.</span><span class="sxs-lookup"><span data-stu-id="ae57d-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information to marshal strings during a call to the external procedure.</span></span> <span data-ttu-id="ae57d-108">También afecta a cómo Visual Basic busca el archivo externo para el nombre del procedimiento externo.</span><span class="sxs-lookup"><span data-stu-id="ae57d-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="ae57d-109">El `Unicode` modificador especifica que Visual Basic debe serializar todas las cadenas como valores Unicode y debe buscar el procedimiento sin modificar su nombre durante la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ae57d-109">The `Unicode` modifier specifies that Visual Basic should marshal all strings to Unicode values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="ae57d-110">Si se especifica ningún modificador de conjunto de caracteres, `Ansi` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ae57d-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae57d-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ae57d-111">Remarks</span></span>  
 <span data-ttu-id="ae57d-112">El `Unicode` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="ae57d-112">The `Unicode` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="ae57d-113">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ae57d-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="ae57d-114">Notas de desarrollador de dispositivos inteligentes</span><span class="sxs-lookup"><span data-stu-id="ae57d-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="ae57d-115">No se admite esta palabra clave.</span><span class="sxs-lookup"><span data-stu-id="ae57d-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae57d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae57d-116">See also</span></span>

- [<span data-ttu-id="ae57d-117">Ansi</span><span class="sxs-lookup"><span data-stu-id="ae57d-117">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)
- [<span data-ttu-id="ae57d-118">Auto</span><span class="sxs-lookup"><span data-stu-id="ae57d-118">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)
- [<span data-ttu-id="ae57d-119">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="ae57d-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
