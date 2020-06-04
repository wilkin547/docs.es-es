---
title: Procedimiento para iterar una enumeración
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: fb6fbdd45ca0e84ccb9fc55296d78e3867d5fe25
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414432"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a><span data-ttu-id="7f045-102">Cómo: Recorrer en iteración una enumeración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7f045-102">How to: Iterate Through An Enumeration in Visual Basic</span></span>
<span data-ttu-id="7f045-103">Las enumeraciones proporcionan una forma cómoda de trabajar con conjuntos de constantes relacionadas y asociar valores constantes con nombres.</span><span class="sxs-lookup"><span data-stu-id="7f045-103">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="7f045-104">Para recorrer en iteración una enumeración, puede moverla a una matriz mediante el <xref:System.Enum.GetValues%2A> método.</span><span class="sxs-lookup"><span data-stu-id="7f045-104">To iterate through an enumeration, you can move it into an array using the <xref:System.Enum.GetValues%2A> method.</span></span> <span data-ttu-id="7f045-105">También puede recorrer en iteración una enumeración mediante una `For...Each` instrucción, utilizando el <xref:System.Enum.GetNames%2A> <xref:System.Enum.GetValues%2A> método o para extraer la cadena o el valor numérico.</span><span class="sxs-lookup"><span data-stu-id="7f045-105">You could also iterate through an enumeration using a `For...Each` statement, using the <xref:System.Enum.GetNames%2A> or <xref:System.Enum.GetValues%2A> method to extract the string or numeric value.</span></span>  
  
### <a name="to-iterate-through-an-enumeration"></a><span data-ttu-id="7f045-106">Para recorrer en iteración una enumeración</span><span class="sxs-lookup"><span data-stu-id="7f045-106">To iterate through an enumeration</span></span>  
  
- <span data-ttu-id="7f045-107">Declare una matriz y convierta la enumeración en ella con el <xref:System.Enum.GetValues%2A> método antes de pasar la matriz como lo haría con cualquier otra variable.</span><span class="sxs-lookup"><span data-stu-id="7f045-107">Declare an array and convert the enumeration to it with the <xref:System.Enum.GetValues%2A> method before passing the array as you would any other variable.</span></span> <span data-ttu-id="7f045-108">En el ejemplo siguiente se muestra cada miembro de la enumeración <xref:Microsoft.VisualBasic.FirstDayOfWeek> a medida que recorre en iteración la enumeración.</span><span class="sxs-lookup"><span data-stu-id="7f045-108">The following example displays each member of the enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> as it iterates through the enumeration.</span></span>  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="7f045-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7f045-109">See also</span></span>

- [<span data-ttu-id="7f045-110">Información general sobre las enumeraciones</span><span class="sxs-lookup"><span data-stu-id="7f045-110">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="7f045-111">Cómo: Declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="7f045-111">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="7f045-112">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="7f045-112">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="7f045-113">Procedimiento para determinar la cadena asociada a un valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="7f045-113">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="7f045-114">Procedimiento para hacer referencia al miembro de una enumeración</span><span class="sxs-lookup"><span data-stu-id="7f045-114">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="7f045-115">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="7f045-115">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="7f045-116">Matrices</span><span class="sxs-lookup"><span data-stu-id="7f045-116">Arrays</span></span>](../arrays/index.md)
