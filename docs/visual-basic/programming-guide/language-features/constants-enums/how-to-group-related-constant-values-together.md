---
title: Procedimiento Agrupar valores de constantes relacionadas juntos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 63475487c8a35f5b306b28d4e7097324bef00d85
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977830"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="0b36a-102">Procedimiento Agrupar valores de constantes relacionadas juntos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b36a-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="0b36a-103">Una enumeración es la mejor manera de agrupar constantes relacionadas.</span><span class="sxs-lookup"><span data-stu-id="0b36a-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="0b36a-104">Crear una enumeración con el `Enum` instrucción en la sección de declaraciones de una clase o un módulo.</span><span class="sxs-lookup"><span data-stu-id="0b36a-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="0b36a-105">Para obtener más información, vea [Cómo: Declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="0b36a-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="0b36a-106">Al grupo de valores de constantes relacionadas</span><span class="sxs-lookup"><span data-stu-id="0b36a-106">To group related constant values</span></span>  
  
1.  <span data-ttu-id="0b36a-107">Escriba una declaración que incluye un nivel de acceso del código, el `Enum` palabra clave y un nombre válido.</span><span class="sxs-lookup"><span data-stu-id="0b36a-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="0b36a-108">Este ejemplo se crea el `Private` enumeración, `temperatureValues`.</span><span class="sxs-lookup"><span data-stu-id="0b36a-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2.  <span data-ttu-id="0b36a-109">Defina las constantes en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="0b36a-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="0b36a-110">Este ejemplo se crea el `Public` enumeración `temperatureValues` y asigna sus valores.</span><span class="sxs-lookup"><span data-stu-id="0b36a-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0b36a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b36a-111">See also</span></span>
- [<span data-ttu-id="0b36a-112">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="0b36a-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="0b36a-113">Cómo: Hacer referencia a un miembro de enumeración</span><span class="sxs-lookup"><span data-stu-id="0b36a-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="0b36a-114">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="0b36a-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="0b36a-115">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="0b36a-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="0b36a-116">Tipos de datos constantes y literales</span><span class="sxs-lookup"><span data-stu-id="0b36a-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="0b36a-117">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="0b36a-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
