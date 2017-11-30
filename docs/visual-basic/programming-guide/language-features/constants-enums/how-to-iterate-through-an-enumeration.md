---
title: "Cómo: Recorrer en iteración una enumeración en Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 439e6eae7d475316625a2cc1d3a70a9e7181f68a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a><span data-ttu-id="74bde-102">Cómo: Recorrer en iteración una enumeración en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="74bde-102">How to: Iterate Through An Enumeration in Visual Basic</span></span>
<span data-ttu-id="74bde-103">Las enumeraciones proporcionan una forma cómoda de trabajar con conjuntos de constantes relacionadas y asociar valores constantes con nombres.</span><span class="sxs-lookup"><span data-stu-id="74bde-103">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="74bde-104">Para recorrer en iteración una enumeración, se puede mover a una matriz mediante el <xref:System.Enum.GetValues%2A> método.</span><span class="sxs-lookup"><span data-stu-id="74bde-104">To iterate through an enumeration, you can move it into an array using the <xref:System.Enum.GetValues%2A> method.</span></span> <span data-ttu-id="74bde-105">También puede iterar a través de una enumeración con un `For...Each` (instrucción), con el <xref:System.Enum.GetNames%2A> o <xref:System.Enum.GetValues%2A> método para extraer el valor de cadena o numérica.</span><span class="sxs-lookup"><span data-stu-id="74bde-105">You could also iterate through an enumeration using a `For...Each` statement, using the <xref:System.Enum.GetNames%2A> or <xref:System.Enum.GetValues%2A> method to extract the string or numeric value.</span></span>  
  
### <a name="to-iterate-through-an-enumeration"></a><span data-ttu-id="74bde-106">Para recorrer en iteración una enumeración</span><span class="sxs-lookup"><span data-stu-id="74bde-106">To iterate through an enumeration</span></span>  
  
-   <span data-ttu-id="74bde-107">Declarar una matriz y convierta la enumeración en ella con el <xref:System.Enum.GetValues%2A> método antes de pasar la matriz como haría cualquier otra variable.</span><span class="sxs-lookup"><span data-stu-id="74bde-107">Declare an array and convert the enumeration to it with the <xref:System.Enum.GetValues%2A> method before passing the array as you would any other variable.</span></span> <span data-ttu-id="74bde-108">En el ejemplo siguiente se muestra cada miembro de la enumeración <xref:Microsoft.VisualBasic.FirstDayOfWeek> tal y como se recorre en iteración la enumeración.</span><span class="sxs-lookup"><span data-stu-id="74bde-108">The following example displays each member of the enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> as it iterates through the enumeration.</span></span>  
  
     [!code-vb[VbEnumsTask#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-iterate-through-an-enumeration_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="74bde-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="74bde-109">See Also</span></span>  
 [<span data-ttu-id="74bde-110">Información general sobre las enumeraciones</span><span class="sxs-lookup"><span data-stu-id="74bde-110">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="74bde-111">Cómo: declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="74bde-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="74bde-112">Cuándo se debe utilizar una enumeración</span><span class="sxs-lookup"><span data-stu-id="74bde-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="74bde-113">Determinar la cadena asociada a un valor de enumeración</span><span class="sxs-lookup"><span data-stu-id="74bde-113">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="74bde-114">Hacer referencia al miembro de una enumeración</span><span class="sxs-lookup"><span data-stu-id="74bde-114">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="74bde-115">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="74bde-115">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="74bde-116">Matrices</span><span class="sxs-lookup"><span data-stu-id="74bde-116">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
