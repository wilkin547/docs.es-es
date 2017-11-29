---
title: "Cómo: Agrupar valores de constantes relacionadas (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be57b56047654d6eb3536bb0b8f63eca27decdb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="a533d-102">Cómo: Agrupar valores de constantes relacionadas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a533d-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="a533d-103">Una enumeración es la mejor manera de agrupar constantes relacionadas.</span><span class="sxs-lookup"><span data-stu-id="a533d-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="a533d-104">Cree una enumeración con el `Enum` instrucción en la sección de declaraciones de una clase o un módulo.</span><span class="sxs-lookup"><span data-stu-id="a533d-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="a533d-105">Para obtener más información, consulte [Cómo: declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="a533d-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="a533d-106">Al grupo de valores de constantes relacionadas</span><span class="sxs-lookup"><span data-stu-id="a533d-106">To group related constant values</span></span>  
  
1.  <span data-ttu-id="a533d-107">Escriba una declaración que incluya un nivel de acceso del código, la `Enum` palabra clave y un nombre válido.</span><span class="sxs-lookup"><span data-stu-id="a533d-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="a533d-108">Este ejemplo se crea el `Private` enumeración, `temperatureValues`.</span><span class="sxs-lookup"><span data-stu-id="a533d-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_1.vb)]  
  
2.  <span data-ttu-id="a533d-109">Defina las constantes en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="a533d-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="a533d-110">Este ejemplo se crea el `Public` enumeración `temperatureValues` y asigna sus valores.</span><span class="sxs-lookup"><span data-stu-id="a533d-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a533d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a533d-111">See Also</span></span>  
 [<span data-ttu-id="a533d-112">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="a533d-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="a533d-113">Hacer referencia al miembro de una enumeración</span><span class="sxs-lookup"><span data-stu-id="a533d-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="a533d-114">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="a533d-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="a533d-115">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="a533d-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="a533d-116">Tipos de datos constantes y literales</span><span class="sxs-lookup"><span data-stu-id="a533d-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="a533d-117">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="a533d-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
