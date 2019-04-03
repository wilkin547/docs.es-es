---
title: Filtrar Agrupar valores de constantes relacionadas juntos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], constants
- constants [Visual Basic], grouping together
ms.assetid: 09d61da5-c940-4126-a79f-ba93c36653dc
ms.openlocfilehash: 9174bcd2385103cf7fa1daf3133e388f9b4998a4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843767"
---
# <a name="how-to-group-related-constant-values-together-visual-basic"></a><span data-ttu-id="f720f-102">Filtrar Agrupar valores de constantes relacionadas juntos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f720f-102">How to: Group Related Constant Values Together (Visual Basic)</span></span>
<span data-ttu-id="f720f-103">Una enumeración es la mejor manera de agrupar constantes relacionadas.</span><span class="sxs-lookup"><span data-stu-id="f720f-103">An enumeration is the best way to group related constants together.</span></span> <span data-ttu-id="f720f-104">Crear una enumeración con el `Enum` instrucción en la sección de declaraciones de una clase o un módulo.</span><span class="sxs-lookup"><span data-stu-id="f720f-104">You create an enumeration with the `Enum` statement in the declarations section of a class or a module.</span></span> <span data-ttu-id="f720f-105">Para obtener más información, vea [Cómo: Declarar una enumeración](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span><span class="sxs-lookup"><span data-stu-id="f720f-105">For more information, see [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md).</span></span>  
  
### <a name="to-group-related-constant-values"></a><span data-ttu-id="f720f-106">Al grupo de valores de constantes relacionadas</span><span class="sxs-lookup"><span data-stu-id="f720f-106">To group related constant values</span></span>  
  
1.  <span data-ttu-id="f720f-107">Escriba una declaración que incluye un nivel de acceso del código, el `Enum` palabra clave y un nombre válido.</span><span class="sxs-lookup"><span data-stu-id="f720f-107">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name.</span></span> <span data-ttu-id="f720f-108">Este ejemplo se crea el `Private` enumeración, `temperatureValues`.</span><span class="sxs-lookup"><span data-stu-id="f720f-108">This example creates the `Private` enumeration, `temperatureValues`.</span></span>  
  
     [!code-vb[VbEnumsTask#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#21)]  
  
2.  <span data-ttu-id="f720f-109">Defina las constantes en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="f720f-109">Define the constants in the enumeration.</span></span> <span data-ttu-id="f720f-110">Este ejemplo se crea el `Public` enumeración `temperatureValues` y asigna sus valores.</span><span class="sxs-lookup"><span data-stu-id="f720f-110">This example creates the `Public` enumeration `temperatureValues` and assigns its values.</span></span>  
  
     [!code-vb[VbEnumsTask#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f720f-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f720f-111">See also</span></span>

- [<span data-ttu-id="f720f-112">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="f720f-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="f720f-113">Cómo: Hacer referencia a un miembro de enumeración</span><span class="sxs-lookup"><span data-stu-id="f720f-113">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="f720f-114">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="f720f-114">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="f720f-115">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="f720f-115">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="f720f-116">Tipos de datos constantes y literales</span><span class="sxs-lookup"><span data-stu-id="f720f-116">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)
- [<span data-ttu-id="f720f-117">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="f720f-117">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
