---
title: Procedimiento Determinar la cadena asociada con un valor de enumeración (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 92d2e9918429c9cf408f288f832e4615b95ad423
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690194"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="26290-102">Procedimiento Determinar la cadena asociada con un valor de enumeración (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26290-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>
<span data-ttu-id="26290-103">El <xref:System.Enum.GetValues%2A> y <xref:System.Enum.GetNames%2A> métodos permiten determinar las cadenas y valores asociados a los miembros de enumeración.</span><span class="sxs-lookup"><span data-stu-id="26290-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="26290-104">Para determinar la cadena asociada a una enumeración</span><span class="sxs-lookup"><span data-stu-id="26290-104">To determine the string associated with an enumeration</span></span>  
  
-   <span data-ttu-id="26290-105">Use el <xref:System.Enum.GetNames%2A> método para recuperar las cadenas asociadas a los miembros de enumeración.</span><span class="sxs-lookup"><span data-stu-id="26290-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="26290-106">En este ejemplo declara una enumeración, `flavorEnum`, a continuación, usa el <xref:System.Enum.GetNames%2A> método para mostrar las cadenas asociadas a cada miembro.</span><span class="sxs-lookup"><span data-stu-id="26290-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-determine-the-string-associated-with-an-enumeration-value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="26290-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="26290-107">See also</span></span>
- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [<span data-ttu-id="26290-108">Cómo: Declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="26290-108">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="26290-109">Cómo: Hacer referencia a un miembro de enumeración</span><span class="sxs-lookup"><span data-stu-id="26290-109">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="26290-110">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="26290-110">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="26290-111">Cómo: Recorrer en iteración una enumeración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26290-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="26290-112">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="26290-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="26290-113">Enum (instrucción)</span><span class="sxs-lookup"><span data-stu-id="26290-113">Enum Statement</span></span>](../../../../visual-basic/language-reference/statements/enum-statement.md)
