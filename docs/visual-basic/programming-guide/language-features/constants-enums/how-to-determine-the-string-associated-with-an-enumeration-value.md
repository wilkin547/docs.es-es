---
description: 'Más información acerca de cómo: determinar la cadena asociada a un valor de enumeración (Visual Basic)'
title: Procedimiento para determinar la cadena asociada a un valor de enumeración
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic]
- strings [Visual Basic], enumeration values
- values [Visual Basic], enumeration members
ms.assetid: 9253e7c8-579c-49a2-8f26-392b20ea99eb
ms.openlocfilehash: 391cb097fa8163f7131cc30f85f8a4f85ba826a4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471609"
---
# <a name="how-to-determine-the-string-associated-with-an-enumeration-value-visual-basic"></a><span data-ttu-id="794eb-103">Cómo: Determinar la cadena asociada a un valor de enumeración (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="794eb-103">How to: Determine the String Associated with an Enumeration Value (Visual Basic)</span></span>

<span data-ttu-id="794eb-104">Los <xref:System.Enum.GetValues%2A> <xref:System.Enum.GetNames%2A> métodos y permiten determinar las cadenas y los valores asociados a los miembros de enumeración.</span><span class="sxs-lookup"><span data-stu-id="794eb-104">The <xref:System.Enum.GetValues%2A> and <xref:System.Enum.GetNames%2A> methods allow you to determine the strings and values associated with enumeration members.</span></span>  
  
### <a name="to-determine-the-string-associated-with-an-enumeration"></a><span data-ttu-id="794eb-105">Para determinar la cadena asociada a una enumeración</span><span class="sxs-lookup"><span data-stu-id="794eb-105">To determine the string associated with an enumeration</span></span>  
  
- <span data-ttu-id="794eb-106">Use el <xref:System.Enum.GetNames%2A> método para recuperar las cadenas asociadas a los miembros de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="794eb-106">Use the <xref:System.Enum.GetNames%2A> method to retrieve the strings associated with the enumeration members.</span></span> <span data-ttu-id="794eb-107">En este ejemplo se declara una enumeración, `flavorEnum` y, a continuación, se usa el <xref:System.Enum.GetNames%2A> método para mostrar las cadenas asociadas a cada miembro.</span><span class="sxs-lookup"><span data-stu-id="794eb-107">This example declares an enumeration, `flavorEnum`, then uses the <xref:System.Enum.GetNames%2A> method to display the strings associated with each member.</span></span>  
  
     [!code-vb[VbEnumsTask#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="794eb-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="794eb-108">See also</span></span>

- <xref:System.Enum.GetValues%2A>
- <xref:System.Enum.GetNames%2A>
- <xref:System.Enum>
- [<span data-ttu-id="794eb-109">Cómo: Declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="794eb-109">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="794eb-110">Procedimiento para hacer referencia al miembro de una enumeración</span><span class="sxs-lookup"><span data-stu-id="794eb-110">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="794eb-111">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="794eb-111">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="794eb-112">Cómo: Recorrer en iteración una enumeración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="794eb-112">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="794eb-113">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="794eb-113">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="794eb-114">Instrucción Enum</span><span class="sxs-lookup"><span data-stu-id="794eb-114">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)
