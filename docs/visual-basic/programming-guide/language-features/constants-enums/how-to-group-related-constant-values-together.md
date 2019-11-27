---
title: 'Cómo: Agrupar valores de constantes relacionadas'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 151eefee4f69e1db8ba40f91334da8a051b95732
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354040"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="039c8-102">Cómo: Agrupar valores de constantes relacionadas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="039c8-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="039c8-103">Una enumeración es la mejor manera de agrupar constantes relacionadas.</span><span class="sxs-lookup"><span data-stu-id="039c8-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="039c8-104">Cree una enumeración con la instrucción `Enum` en la sección de declaraciones de una clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="039c8-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="039c8-105">Para obtener más información, vea [Cómo: declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="039c8-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="039c8-106">Para agrupar los valores constantes relacionados</span><span class="sxs-lookup"><span data-stu-id="039c8-106">To group related constant values</span></span>  
  
1. <span data-ttu-id="039c8-107">Escriba una declaración que incluya un nivel de acceso de código, la palabra clave `Enum` y un nombre válido.</span><span class="sxs-lookup"><span data-stu-id="039c8-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="039c8-108">En este ejemplo se crea la enumeración `Private` `temperatureValues`.</span><span class="sxs-lookup"><span data-stu-id="039c8-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. <span data-ttu-id="039c8-109">Defina las constantes en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="039c8-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="039c8-110">En este ejemplo se crea la enumeración `Public` `temperatureValues` y se asignan sus valores.</span><span class="sxs-lookup"><span data-stu-id="039c8-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="039c8-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="039c8-111">See also</span></span>

- [<span data-ttu-id="039c8-112">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="039c8-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="039c8-113">Hacer referencia al miembro de una enumeración</span><span class="sxs-lookup"><span data-stu-id="039c8-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="039c8-114">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="039c8-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="039c8-115">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="039c8-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="039c8-116">Tipos de datos constantes y literales</span><span class="sxs-lookup"><span data-stu-id="039c8-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="039c8-117">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="039c8-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
