---
title: Procedimiento para determinar la cadena asociada a un valor de enumeración
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 4138759bfbb049b77406fc536219b40d3ed9e2a5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058774"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="37f83-102">Cómo: Determinar la cadena asociada a un valor de enumeración (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37f83-102">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>

<span data-ttu-id="37f83-103">Los <xref:System.Enum.GetValues%2A> <xref:System.Enum.GetNames%2A> métodos y permiten determinar las cadenas y los valores asociados a los miembros de enumeración.</span><span class="sxs-lookup"><span data-stu-id="37f83-103">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="37f83-104">Para determinar la cadena asociada a una enumeración</span><span class="sxs-lookup"><span data-stu-id="37f83-104">To determine the string associated with an enumeration</span></span>  
  
- <span data-ttu-id="37f83-105">Use el <xref:System.Enum.GetNames%2A> método para recuperar las cadenas asociadas a los miembros de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="37f83-105">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="37f83-106">En este ejemplo se declara una enumeración, `flavorEnum` y, a continuación, se usa el <xref:System.Enum.GetNames%2A> método para mostrar las cadenas asociadas a cada miembro.</span><span class="sxs-lookup"><span data-stu-id="37f83-106">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="37f83-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="37f83-107">See also</span></span>

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [<span data-ttu-id="37f83-108">Cómo: Declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="37f83-108">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="37f83-109">Procedimiento para hacer referencia al miembro de una enumeración</span><span class="sxs-lookup"><span data-stu-id="37f83-109">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="37f83-110">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="37f83-110">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="37f83-111">Cómo: Recorrer en iteración una enumeración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37f83-111">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="37f83-112">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="37f83-112">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="37f83-113">Instrucción Enum</span><span class="sxs-lookup"><span data-stu-id="37f83-113">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)
