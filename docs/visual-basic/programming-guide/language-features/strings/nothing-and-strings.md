---
title: Nothing y cadenas
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: dfc43748d0754f0a6a29763c42ab82d9937f89f8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344293"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="71f0a-102">Nothing y cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="71f0a-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="71f0a-103">The Visual Basic runtime and the .NET Framework evaluate `Nothing` differently when it comes to strings.</span><span class="sxs-lookup"><span data-stu-id="71f0a-103">The Visual Basic runtime and the .NET Framework evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="71f0a-104">Visual Basic Runtime and the .NET Framework</span><span class="sxs-lookup"><span data-stu-id="71f0a-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="71f0a-105">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="71f0a-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="71f0a-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span><span class="sxs-lookup"><span data-stu-id="71f0a-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="71f0a-107">The .NET Framework does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="71f0a-107">The .NET Framework does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71f0a-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="71f0a-108">See also</span></span>

- [<span data-ttu-id="71f0a-109">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="71f0a-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
