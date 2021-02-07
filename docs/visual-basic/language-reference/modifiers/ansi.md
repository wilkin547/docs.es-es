---
description: 'Más información acerca de: ANSI (Visual Basic)'
title: Ansi
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: c93472cbf6a8203f05353e0394b52c44686c0070
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701201"
---
# <a name="ansi-visual-basic"></a><span data-ttu-id="4c038-103">Ansi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c038-103">Ansi (Visual Basic)</span></span>

<span data-ttu-id="4c038-104">Especifica que Visual Basic debe serializar todas las cadenas en valores de American National Standards Institute (ANSI), independientemente del nombre del procedimiento externo que se está declarando.</span><span class="sxs-lookup"><span data-stu-id="4c038-104">Specifies that Visual Basic should marshal all strings to American National Standards Institute (ANSI) values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="4c038-105">Cuando se llama a un procedimiento definido fuera del proyecto, el compilador Visual Basic no tiene acceso a la información que necesita para llamar al procedimiento correctamente.</span><span class="sxs-lookup"><span data-stu-id="4c038-105">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly.</span></span> <span data-ttu-id="4c038-106">Esta información incluye dónde se encuentra el procedimiento, cómo se identifica, su secuencia de llamada y tipo de valor devuelto, y el juego de caracteres de cadena que usa.</span><span class="sxs-lookup"><span data-stu-id="4c038-106">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="4c038-107">La [instrucción Declare](../statements/declare-statement.md) crea una referencia a un procedimiento externo y proporciona esta información necesaria.</span><span class="sxs-lookup"><span data-stu-id="4c038-107">The [Declare Statement](../statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="4c038-108">La `charsetmodifier` parte de la `Declare` instrucción proporciona la información del juego de caracteres para calcular las referencias de las cadenas durante una llamada al procedimiento externo.</span><span class="sxs-lookup"><span data-stu-id="4c038-108">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="4c038-109">También afecta al modo en que Visual Basic busca el nombre del procedimiento externo en el archivo externo.</span><span class="sxs-lookup"><span data-stu-id="4c038-109">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="4c038-110">El `Ansi` modificador especifica que Visual Basic debe calcular las referencias de todas las cadenas a valores ANSI y debe buscar el procedimiento sin modificar su nombre durante la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4c038-110">The `Ansi` modifier specifies that Visual Basic should marshal all strings to ANSI values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="4c038-111">Si no se especifica ningún modificador de juego de caracteres, `Ansi` es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4c038-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c038-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4c038-112">Remarks</span></span>  

 <span data-ttu-id="4c038-113">El `Ansi` modificador se puede usar en este contexto:</span><span class="sxs-lookup"><span data-stu-id="4c038-113">The `Ansi` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="4c038-114">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="4c038-114">Declare Statement</span></span>](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="4c038-115">Notas para desarrolladores de Smart Device</span><span class="sxs-lookup"><span data-stu-id="4c038-115">Smart Device Developer Notes</span></span>  

 <span data-ttu-id="4c038-116">Esta palabra clave no es compatible.</span><span class="sxs-lookup"><span data-stu-id="4c038-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c038-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c038-117">See also</span></span>

- [<span data-ttu-id="4c038-118">Automático</span><span class="sxs-lookup"><span data-stu-id="4c038-118">Auto</span></span>](auto.md)
- [<span data-ttu-id="4c038-119">Unicode</span><span class="sxs-lookup"><span data-stu-id="4c038-119">Unicode</span></span>](unicode.md)
- [<span data-ttu-id="4c038-120">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c038-120">Keywords</span></span>](../keywords/index.md)
