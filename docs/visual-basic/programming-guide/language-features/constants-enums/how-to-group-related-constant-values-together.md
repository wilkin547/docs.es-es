---
title: Procedimiento para agrupar valores de constantes relacionadas
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: d2393af8b0c2b0c2e528f9908a78fbc7f182c8cf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414445"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="cde44-102">Cómo: Agrupar valores de constantes relacionadas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cde44-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="cde44-103">Una enumeración es la mejor manera de agrupar constantes relacionadas.</span><span class="sxs-lookup"><span data-stu-id="cde44-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="cde44-104">Cree una enumeración con la `Enum` instrucción en la sección de declaraciones de una clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="cde44-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="cde44-105">Para obtener más información, vea [Cómo: declarar una enumeración](how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="cde44-105">For more information, see [How to: Declare an Enumeration](how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="cde44-106">Para agrupar los valores constantes relacionados</span><span class="sxs-lookup"><span data-stu-id="cde44-106">To group related constant values</span></span>  
  
1. <span data-ttu-id="cde44-107">Escriba una declaración que incluya un nivel de acceso de código, la `Enum` palabra clave y un nombre válido.</span><span class="sxs-lookup"><span data-stu-id="cde44-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="cde44-108">En este ejemplo se crea la `Private` enumeración, `temperatureValues` .</span><span class="sxs-lookup"><span data-stu-id="cde44-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. <span data-ttu-id="cde44-109">Defina las constantes en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="cde44-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="cde44-110">En este ejemplo se crea la `Public` enumeración `temperatureValues` y se asignan sus valores.</span><span class="sxs-lookup"><span data-stu-id="cde44-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cde44-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cde44-111">See also</span></span>

- [<span data-ttu-id="cde44-112">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="cde44-112">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="cde44-113">Procedimiento para hacer referencia al miembro de una enumeración</span><span class="sxs-lookup"><span data-stu-id="cde44-113">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="cde44-114">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="cde44-114">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="cde44-115">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="cde44-115">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="cde44-116">Tipos de datos constantes y literales</span><span class="sxs-lookup"><span data-stu-id="cde44-116">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="cde44-117">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="cde44-117">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
