---
title: 'Cómo: Hacer referencia al miembro de una enumeración'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: 01db5b84783eda45cd7867dc8fea8a69fc18b98a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353990"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a><span data-ttu-id="b2519-102">Cómo: Hacer referencia al miembro de una enumeración (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b2519-102">How to: Refer to an Enumeration Member (Visual Basic)</span></span>
<span data-ttu-id="b2519-103">Las enumeraciones proporcionan una manera cómoda de trabajar con conjuntos de constantes relacionadas y de asociar valores constantes con nombres.</span><span class="sxs-lookup"><span data-stu-id="b2519-103">Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names.</span></span> <span data-ttu-id="b2519-104">Por ejemplo, puede declarar una enumeración para un conjunto de constantes de tipo entero asociadas con los días de la semana y, después, usar los nombres de los días en lugar de sus valores enteros en el código.</span><span class="sxs-lookup"><span data-stu-id="b2519-104">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
 <span data-ttu-id="b2519-105">Puede evitar el uso de nombres completos con la instrucción `Imports`.</span><span class="sxs-lookup"><span data-stu-id="b2519-105">You can avoid using fully qualified names with the `Imports` statement.</span></span> <span data-ttu-id="b2519-106">Para obtener más información, vea [enumeraciones y calificación de nombres](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="b2519-106">For more information, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-refer-to-an-enumeration-member"></a><span data-ttu-id="b2519-107">Para hacer referencia a un miembro de enumeración</span><span class="sxs-lookup"><span data-stu-id="b2519-107">To refer to an enumeration member</span></span>  
  
- <span data-ttu-id="b2519-108">Califique el nombre del miembro con la enumeración.</span><span class="sxs-lookup"><span data-stu-id="b2519-108">Qualify the member name with the enumeration.</span></span> <span data-ttu-id="b2519-109">Por ejemplo, en el ejemplo siguiente se asigna el miembro `Saturday` de la enumeración `FirstDayOfWeek` a la variable `DayValue`.</span><span class="sxs-lookup"><span data-stu-id="b2519-109">For example, the following example assigns the `Saturday` member of the `FirstDayOfWeek` enumeration to the variable `DayValue`.</span></span>  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="b2519-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2519-110">See also</span></span>

- [<span data-ttu-id="b2519-111">Cómo: declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="b2519-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="b2519-112">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="b2519-112">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="b2519-113">Cómo: recorrer en iteración una enumeración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b2519-113">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="b2519-114">Determinar la cadena asociada a un valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="b2519-114">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="b2519-115">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="b2519-115">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
