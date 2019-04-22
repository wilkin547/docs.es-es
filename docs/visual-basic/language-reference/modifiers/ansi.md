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
ms.openlocfilehash: 98dafab3e524ea371bba228eb231e28d46cc3b4e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819460"
---
# <a name="ansi-visual-basic"></a><span data-ttu-id="34fa8-102">Ansi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="34fa8-102">Ansi (Visual Basic)</span></span>
<span data-ttu-id="34fa8-103">Especifica que Visual Basic debe serializar todas las cadenas en valores de American National Standards Institute (ANSI) independientemente del nombre del procedimiento externo que se declara.</span><span class="sxs-lookup"><span data-stu-id="34fa8-103">Specifies that Visual Basic should marshal all strings to American National Standards Institute (ANSI) values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="34fa8-104">Cuando se llama a un procedimiento definido fuera del proyecto, el compilador de Visual Basic no tiene acceso a la información que necesita para llamar al procedimiento correctamente.</span><span class="sxs-lookup"><span data-stu-id="34fa8-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly.</span></span> <span data-ttu-id="34fa8-105">Esta información incluye dónde se encuentra el procedimiento, el cómo se identifica, su secuencia de llamada y el tipo de valor devuelto y el carácter de cadena juego que utiliza.</span><span class="sxs-lookup"><span data-stu-id="34fa8-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="34fa8-106">El [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.</span><span class="sxs-lookup"><span data-stu-id="34fa8-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="34fa8-107">El `charsetmodifier` parte en la `Declare` instrucción proporciona la información del conjunto de caracteres para la serialización de cadenas durante una llamada al procedimiento externo.</span><span class="sxs-lookup"><span data-stu-id="34fa8-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="34fa8-108">También afecta a cómo Visual Basic busca el archivo externo para el nombre del procedimiento externo.</span><span class="sxs-lookup"><span data-stu-id="34fa8-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="34fa8-109">El `Ansi` modificador especifica que Visual Basic debe serializar todas las cadenas como valores ANSI y buscar el procedimiento sin modificar su nombre durante la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="34fa8-109">The `Ansi` modifier specifies that Visual Basic should marshal all strings to ANSI values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="34fa8-110">Si se especifica ningún modificador de conjunto de caracteres, `Ansi` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="34fa8-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34fa8-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="34fa8-111">Remarks</span></span>  
 <span data-ttu-id="34fa8-112">El `Ansi` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="34fa8-112">The `Ansi` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="34fa8-113">Declare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="34fa8-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="34fa8-114">Notas de desarrollador de dispositivos inteligentes</span><span class="sxs-lookup"><span data-stu-id="34fa8-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="34fa8-115">No se admite esta palabra clave.</span><span class="sxs-lookup"><span data-stu-id="34fa8-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34fa8-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="34fa8-116">See also</span></span>

- [<span data-ttu-id="34fa8-117">Auto</span><span class="sxs-lookup"><span data-stu-id="34fa8-117">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)
- [<span data-ttu-id="34fa8-118">Unicode</span><span class="sxs-lookup"><span data-stu-id="34fa8-118">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="34fa8-119">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="34fa8-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
