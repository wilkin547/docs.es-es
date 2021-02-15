---
description: 'Más información acerca de cómo: agrupar valores de constantes relacionadas (Visual Basic)'
title: Procedimiento para agrupar valores de constantes relacionadas
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: ddd60696d2c751810e49ecbcb537589bedc58abf
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471596"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="fbc00-103">Cómo: Agrupar valores de constantes relacionadas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fbc00-103">How to: Group Related Constant Values Together (Visual Basic)</span></span>

<span data-ttu-id="fbc00-104">Una enumeración es la mejor manera de agrupar constantes relacionadas.</span><span class="sxs-lookup"><span data-stu-id="fbc00-104">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="fbc00-105">Cree una enumeración con la `Enum` instrucción en la sección de declaraciones de una clase o módulo.</span><span class="sxs-lookup"><span data-stu-id="fbc00-105">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="fbc00-106">Para obtener más información, vea [Cómo: declarar una enumeración](how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="fbc00-106">For more information, see [How to: Declare an Enumeration](how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="fbc00-107">Para agrupar los valores constantes relacionados</span><span class="sxs-lookup"><span data-stu-id="fbc00-107">To group related constant values</span></span>  
  
1. <span data-ttu-id="fbc00-108">Escriba una declaración que incluya un nivel de acceso de código, la `Enum` palabra clave y un nombre válido.</span><span class="sxs-lookup"><span data-stu-id="fbc00-108">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="fbc00-109">En este ejemplo se crea la `Private` enumeración, `temperatureValues` .</span><span class="sxs-lookup"><span data-stu-id="fbc00-109">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2. <span data-ttu-id="fbc00-110">Defina las constantes en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="fbc00-110">Define the constants in the enumeration.</span></span> <span data-ttu-id="fbc00-111">En este ejemplo se crea la `Public` enumeración `temperatureValues` y se asignan sus valores.</span><span class="sxs-lookup"><span data-stu-id="fbc00-111">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="fbc00-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fbc00-112">See also</span></span>

- [<span data-ttu-id="fbc00-113">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="fbc00-113">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="fbc00-114">Procedimiento para hacer referencia al miembro de una enumeración</span><span class="sxs-lookup"><span data-stu-id="fbc00-114">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="fbc00-115">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="fbc00-115">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="fbc00-116">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="fbc00-116">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="fbc00-117">Tipos de datos constantes y literales</span><span class="sxs-lookup"><span data-stu-id="fbc00-117">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)
- [<span data-ttu-id="fbc00-118">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="fbc00-118">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
