---
title: Ansi
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: 67792e52c21555bef46548e9ab0a6ebd32061071
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373205"
---
# <a name="ansi-visual-basic"></a><span data-ttu-id="0e8cb-102">Ansi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e8cb-102">Ansi (Visual Basic)</span></span>
<span data-ttu-id="0e8cb-103">Especifica que Visual Basic debe serializar todas las cadenas en valores de American National Standards Institute (ANSI), independientemente del nombre del procedimiento externo que se está declarando.</span><span class="sxs-lookup"><span data-stu-id="0e8cb-103">Specifies that Visual Basic should marshal all strings to American National Standards Institute (ANSI) values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="0e8cb-104">Cuando se llama a un procedimiento definido fuera del proyecto, el compilador Visual Basic no tiene acceso a la información que necesita para llamar al procedimiento correctamente.</span><span class="sxs-lookup"><span data-stu-id="0e8cb-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly.</span></span> <span data-ttu-id="0e8cb-105">Esta información incluye dónde se encuentra el procedimiento, cómo se identifica, su secuencia de llamada y tipo de valor devuelto, y el juego de caracteres de cadena que usa.</span><span class="sxs-lookup"><span data-stu-id="0e8cb-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="0e8cb-106">La [instrucción Declare](../statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.</span><span class="sxs-lookup"><span data-stu-id="0e8cb-106">The [Declare Statement](../statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="0e8cb-107">La `charsetmodifier` parte de la `Declare` instrucción proporciona la información del juego de caracteres para calcular las referencias de las cadenas durante una llamada al procedimiento externo.</span><span class="sxs-lookup"><span data-stu-id="0e8cb-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="0e8cb-108">También afecta al modo en que Visual Basic busca el nombre del procedimiento externo en el archivo externo.</span><span class="sxs-lookup"><span data-stu-id="0e8cb-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="0e8cb-109">El `Ansi` modificador especifica que Visual Basic debe calcular las referencias de todas las cadenas a valores ANSI y debe buscar el procedimiento sin modificar su nombre durante la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="0e8cb-109">The `Ansi` modifier specifies that Visual Basic should marshal all strings to ANSI values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="0e8cb-110">Si no se especifica ningún modificador de juego de caracteres, `Ansi` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0e8cb-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e8cb-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0e8cb-111">Remarks</span></span>  
 <span data-ttu-id="0e8cb-112">El `Ansi` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="0e8cb-112">The `Ansi` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="0e8cb-113">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="0e8cb-113">Declare Statement</span></span>](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="0e8cb-114">Notas para desarrolladores de Smart Device</span><span class="sxs-lookup"><span data-stu-id="0e8cb-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="0e8cb-115">Esta palabra clave no es compatible.</span><span class="sxs-lookup"><span data-stu-id="0e8cb-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e8cb-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e8cb-116">See also</span></span>

- [<span data-ttu-id="0e8cb-117">Auto</span><span class="sxs-lookup"><span data-stu-id="0e8cb-117">Auto</span></span>](auto.md)
- [<span data-ttu-id="0e8cb-118">Unicode</span><span class="sxs-lookup"><span data-stu-id="0e8cb-118">Unicode</span></span>](unicode.md)
- [<span data-ttu-id="0e8cb-119">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="0e8cb-119">Keywords</span></span>](../keywords/index.md)
