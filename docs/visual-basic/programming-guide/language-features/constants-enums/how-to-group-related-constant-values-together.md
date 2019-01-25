---
title: Procedimiento Agrupar valores de constantes relacionadas juntos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 04697092534daa6f83a29e69dcdc509644fa6147
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558688"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="11b24-102">Procedimiento Agrupar valores de constantes relacionadas juntos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11b24-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="11b24-103">Una enumeración es la mejor manera de agrupar constantes relacionadas.</span><span class="sxs-lookup"><span data-stu-id="11b24-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="11b24-104">Crear una enumeración con el `Enum` instrucción en la sección de declaraciones de una clase o un módulo.</span><span class="sxs-lookup"><span data-stu-id="11b24-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="11b24-105">Para obtener más información, vea [Cómo: Declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="11b24-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="11b24-106">Al grupo de valores de constantes relacionadas</span><span class="sxs-lookup"><span data-stu-id="11b24-106">To group related constant values</span></span>  
  
1.  <span data-ttu-id="11b24-107">Escriba una declaración que incluye un nivel de acceso del código, el `Enum` palabra clave y un nombre válido.</span><span class="sxs-lookup"><span data-stu-id="11b24-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="11b24-108">Este ejemplo se crea el `Private` enumeración, `temperatureValues`.</span><span class="sxs-lookup"><span data-stu-id="11b24-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_1.vb)]  
  
2.  <span data-ttu-id="11b24-109">Defina las constantes en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="11b24-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="11b24-110">Este ejemplo se crea el `Public` enumeración `temperatureValues` y asigna sus valores.</span><span class="sxs-lookup"><span data-stu-id="11b24-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-group-related-constant-values-together_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="11b24-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="11b24-111">See also</span></span>
- [<span data-ttu-id="11b24-112">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="11b24-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="11b24-113">Cómo: Hacer referencia a un miembro de enumeración</span><span class="sxs-lookup"><span data-stu-id="11b24-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="11b24-114">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="11b24-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="11b24-115">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="11b24-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="11b24-116">Tipos de datos constantes y literales</span><span class="sxs-lookup"><span data-stu-id="11b24-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="11b24-117">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="11b24-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
