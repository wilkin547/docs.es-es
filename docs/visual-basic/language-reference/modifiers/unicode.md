---
title: Unicode
ms.date: 07/20/2015
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
ms.openlocfilehash: 9b1bc40bb52244deefc0486d3a40c4b961ad1ee5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402686"
---
# <a name="unicode-visual-basic"></a><span data-ttu-id="baa6c-102">Unicode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="baa6c-102">Unicode (Visual Basic)</span></span>
<span data-ttu-id="baa6c-103">Especifica que Visual Basic debe serializar todas las cadenas en valores Unicode, independientemente del nombre del procedimiento externo que se está declarando.</span><span class="sxs-lookup"><span data-stu-id="baa6c-103">Specifies that Visual Basic should marshal all strings to Unicode values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="baa6c-104">Cuando se llama a un procedimiento definido fuera del proyecto, el compilador Visual Basic no tiene acceso a la información que debe tener para poder llamar al procedimiento correctamente.</span><span class="sxs-lookup"><span data-stu-id="baa6c-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have in order to call the procedure correctly.</span></span> <span data-ttu-id="baa6c-105">Esta información incluye dónde se encuentra el procedimiento, cómo se identifica, su secuencia de llamada y tipo de valor devuelto, y el juego de caracteres de cadena que usa.</span><span class="sxs-lookup"><span data-stu-id="baa6c-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="baa6c-106">La [instrucción Declare](../statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.</span><span class="sxs-lookup"><span data-stu-id="baa6c-106">The [Declare Statement](../statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="baa6c-107">La `charsetmodifier` parte de la `Declare` instrucción proporciona la información del juego de caracteres para calcular las referencias de cadenas durante una llamada al procedimiento externo.</span><span class="sxs-lookup"><span data-stu-id="baa6c-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information to marshal strings during a call to the external procedure.</span></span> <span data-ttu-id="baa6c-108">También afecta al modo en que Visual Basic busca el nombre del procedimiento externo en el archivo externo.</span><span class="sxs-lookup"><span data-stu-id="baa6c-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="baa6c-109">El `Unicode` modificador especifica que Visual Basic debe serializar todas las cadenas en valores Unicode y debe buscar el procedimiento sin modificar su nombre durante la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="baa6c-109">The `Unicode` modifier specifies that Visual Basic should marshal all strings to Unicode values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="baa6c-110">Si no se especifica ningún modificador de juego de caracteres, `Ansi` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="baa6c-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="baa6c-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="baa6c-111">Remarks</span></span>  
 <span data-ttu-id="baa6c-112">El `Unicode` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="baa6c-112">The `Unicode` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="baa6c-113">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="baa6c-113">Declare Statement</span></span>](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="baa6c-114">Notas para desarrolladores de Smart Device</span><span class="sxs-lookup"><span data-stu-id="baa6c-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="baa6c-115">Esta palabra clave no es compatible.</span><span class="sxs-lookup"><span data-stu-id="baa6c-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baa6c-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="baa6c-116">See also</span></span>

- [<span data-ttu-id="baa6c-117">Ansi</span><span class="sxs-lookup"><span data-stu-id="baa6c-117">Ansi</span></span>](ansi.md)
- [<span data-ttu-id="baa6c-118">Auto</span><span class="sxs-lookup"><span data-stu-id="baa6c-118">Auto</span></span>](auto.md)
- [<span data-ttu-id="baa6c-119">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="baa6c-119">Keywords</span></span>](../keywords/index.md)
