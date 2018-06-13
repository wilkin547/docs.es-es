---
title: Ansi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: c7037acac58de56a396bd89f595ef897743ff4e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595084"
---
# <a name="ansi-visual-basic"></a><span data-ttu-id="a73bc-102">Ansi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a73bc-102">Ansi (Visual Basic)</span></span>
<span data-ttu-id="a73bc-103">Especifica que Visual Basic debe calcular las referencias de todas las cadenas con valores de American National Standards Institute (ANSI) sin tener en cuenta el nombre del procedimiento externo que se declara.</span><span class="sxs-lookup"><span data-stu-id="a73bc-103">Specifies that Visual Basic should marshal all strings to American National Standards Institute (ANSI) values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="a73bc-104">Cuando se llama a un procedimiento definido fuera del proyecto, el compilador de Visual Basic no tiene acceso a la información que necesita para llamar correctamente al procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a73bc-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly.</span></span> <span data-ttu-id="a73bc-105">Esta información incluye donde se encuentra el procedimiento, el lo identifica, su secuencia de llamada y el tipo de valor devuelto y juego de caracteres de la cadena que utiliza.</span><span class="sxs-lookup"><span data-stu-id="a73bc-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="a73bc-106">El [instrucción Declare](../../../visual-basic/language-reference/statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.</span><span class="sxs-lookup"><span data-stu-id="a73bc-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="a73bc-107">El `charsetmodifier` parte de la `Declare` instrucción proporciona la información del conjunto de caracteres para calcular referencias de cadenas durante una llamada al procedimiento externo.</span><span class="sxs-lookup"><span data-stu-id="a73bc-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="a73bc-108">También afecta al modo en que Visual Basic busca el archivo externo para el nombre del procedimiento externo.</span><span class="sxs-lookup"><span data-stu-id="a73bc-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="a73bc-109">El `Ansi` modificador especifica que Visual Basic debe calcular las referencias de todas las cadenas a valores ANSI y debe buscar el procedimiento sin modificar su nombre durante la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a73bc-109">The `Ansi` modifier specifies that Visual Basic should marshal all strings to ANSI values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="a73bc-110">Si no se especifica ningún modificador de juego de caracteres, `Ansi` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a73bc-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a73bc-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a73bc-111">Remarks</span></span>  
 <span data-ttu-id="a73bc-112">El `Ansi` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="a73bc-112">The `Ansi` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="a73bc-113">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a73bc-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="a73bc-114">Notas de desarrollador de Smart Device</span><span class="sxs-lookup"><span data-stu-id="a73bc-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="a73bc-115">No se admite esta palabra clave.</span><span class="sxs-lookup"><span data-stu-id="a73bc-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a73bc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a73bc-116">See Also</span></span>  
 [<span data-ttu-id="a73bc-117">Auto</span><span class="sxs-lookup"><span data-stu-id="a73bc-117">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)  
 [<span data-ttu-id="a73bc-118">Unicode</span><span class="sxs-lookup"><span data-stu-id="a73bc-118">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [<span data-ttu-id="a73bc-119">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="a73bc-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
