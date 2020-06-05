---
title: Procedimiento para hacer referencia al miembro de una enumeración
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: 66c527bd4ba4721065de8fca8534fe652d0139be
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414419"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a><span data-ttu-id="298a7-102">Cómo: Hacer referencia al miembro de una enumeración (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="298a7-102">How to: Refer to an Enumeration Member (Visual Basic)</span></span>
<span data-ttu-id="298a7-103">Las enumeraciones proporcionan una manera cómoda de trabajar con conjuntos de constantes relacionadas y de asociar valores constantes con nombres.</span><span class="sxs-lookup"><span data-stu-id="298a7-103">Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names.</span></span> <span data-ttu-id="298a7-104">Por ejemplo, puede declarar una enumeración para un conjunto de constantes de tipo entero asociadas con los días de la semana y, después, usar los nombres de los días en lugar de sus valores enteros en el código.</span><span class="sxs-lookup"><span data-stu-id="298a7-104">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
 <span data-ttu-id="298a7-105">Puede evitar el uso de nombres completos con la `Imports` instrucción.</span><span class="sxs-lookup"><span data-stu-id="298a7-105">You can avoid using fully qualified names with the `Imports` statement.</span></span> <span data-ttu-id="298a7-106">Para obtener más información, vea [enumeraciones y calificación de nombres](enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="298a7-106">For more information, see [Enumerations and Name Qualification](enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-refer-to-an-enumeration-member"></a><span data-ttu-id="298a7-107">Para hacer referencia a un miembro de enumeración</span><span class="sxs-lookup"><span data-stu-id="298a7-107">To refer to an enumeration member</span></span>  
  
- <span data-ttu-id="298a7-108">Califique el nombre del miembro con la enumeración.</span><span class="sxs-lookup"><span data-stu-id="298a7-108">Qualify the member name with the enumeration.</span></span> <span data-ttu-id="298a7-109">Por ejemplo, en el ejemplo siguiente se asigna el `Saturday` miembro de la `FirstDayOfWeek` enumeración a la variable `DayValue` .</span><span class="sxs-lookup"><span data-stu-id="298a7-109">For example, the following example assigns the `Saturday` member of the `FirstDayOfWeek` enumeration to the variable `DayValue`.</span></span>  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="298a7-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="298a7-110">See also</span></span>

- [<span data-ttu-id="298a7-111">Cómo: Declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="298a7-111">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="298a7-112">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="298a7-112">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="298a7-113">Cómo: Recorrer en iteración una enumeración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="298a7-113">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="298a7-114">Procedimiento para determinar la cadena asociada a un valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="298a7-114">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="298a7-115">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="298a7-115">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
