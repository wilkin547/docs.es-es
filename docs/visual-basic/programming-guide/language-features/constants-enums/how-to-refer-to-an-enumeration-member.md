---
title: Procedimiento Hacer referencia a un miembro de enumeración (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: e9ea359d58dfa11f7bba7fec3d31955e18d24953
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813982"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a><span data-ttu-id="20848-102">Procedimiento Hacer referencia a un miembro de enumeración (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20848-102">How to: Refer to an Enumeration Member (Visual Basic)</span></span>
<span data-ttu-id="20848-103">Las enumeraciones proporcionan una forma cómoda para trabajar con conjuntos de constantes relacionadas y asociar valores constantes con nombres.</span><span class="sxs-lookup"><span data-stu-id="20848-103">Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names.</span></span> <span data-ttu-id="20848-104">Por ejemplo, puede declarar una enumeración para un conjunto de constantes de tipo entero asociadas con los días de la semana y, después, usar los nombres de los días en lugar de sus valores enteros en el código.</span><span class="sxs-lookup"><span data-stu-id="20848-104">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
 <span data-ttu-id="20848-105">Se puede evitar usar nombres completos con el `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="20848-105">You can avoid using fully qualified names with the `Imports` statement.</span></span> <span data-ttu-id="20848-106">Para obtener más información, consulte [enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="20848-106">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-refer-to-an-enumeration-member"></a><span data-ttu-id="20848-107">Para hacer referencia a un miembro de enumeración</span><span class="sxs-lookup"><span data-stu-id="20848-107">To refer to an enumeration member</span></span>  
  
-   <span data-ttu-id="20848-108">Calificar el nombre del miembro con la enumeración.</span><span class="sxs-lookup"><span data-stu-id="20848-108">Qualify the member name with the enumeration.</span></span> <span data-ttu-id="20848-109">Por ejemplo, en el ejemplo siguiente se asigna el `Saturday` miembro de la `FirstDayOfWeek` enumeración a la variable `DayValue`.</span><span class="sxs-lookup"><span data-stu-id="20848-109">For example, the following example assigns the `Saturday` member of the `FirstDayOfWeek` enumeration to the variable `DayValue`.</span></span>  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="20848-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="20848-110">See also</span></span>

- [<span data-ttu-id="20848-111">Cómo: Declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="20848-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="20848-112">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="20848-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="20848-113">Cómo: Recorrer en iteración una enumeración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20848-113">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="20848-114">Cómo: Determinar la cadena asociada con un valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="20848-114">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="20848-115">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="20848-115">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
