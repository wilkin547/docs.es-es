---
title: Vs basado en cero. Acceso basado en una cadena en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 911f063d6ca9a3f5d88a1f50d9df7f908a488f66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="5b5cb-102">Vs basado en cero. Acceso basado en una cadena en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5b5cb-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="5b5cb-103">Este tema se compara cómo [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] y [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] proporcionan acceso a los caracteres de una cadena.</span><span class="sxs-lookup"><span data-stu-id="5b5cb-103">This topic compares how [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide access to the characters in a string.</span></span> <span data-ttu-id="5b5cb-104">El [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] siempre proporciona acceso basado en cero a los caracteres de una cadena, mientras que [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] proporciona acceso basado en cero y basado en uno, dependiendo de la función.</span><span class="sxs-lookup"><span data-stu-id="5b5cb-104">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] always provides zero-based access to the characters in a string, whereas [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="5b5cb-105">Basado en uno</span><span class="sxs-lookup"><span data-stu-id="5b5cb-105">One-Based</span></span>  
 <span data-ttu-id="5b5cb-106">Para obtener un ejemplo de una base uno [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] funcionar, tenga en cuenta el `Mid` función.</span><span class="sxs-lookup"><span data-stu-id="5b5cb-106">For an example of a one-based [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] function, consider the `Mid` function.</span></span> <span data-ttu-id="5b5cb-107">Toma un argumento que indica la posición del carácter en el que comenzará la subcadena, empezando por la posición 1.</span><span class="sxs-lookup"><span data-stu-id="5b5cb-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="5b5cb-108">El [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> método toma un índice del carácter en la cadena a la que la subcadena consiste en iniciar, empezando por la posición 0.</span><span class="sxs-lookup"><span data-stu-id="5b5cb-108">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="5b5cb-109">Por lo tanto, si tiene una cadena "ABCDE", los caracteres individuales se numeran 1,2,3,4,5 para su uso con el `Mid` función, pero 0,1,2,3,4 para su uso con el <xref:System.String.Substring%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="5b5cb-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="5b5cb-110">Basado en cero</span><span class="sxs-lookup"><span data-stu-id="5b5cb-110">Zero-Based</span></span>  
 <span data-ttu-id="5b5cb-111">Para obtener un ejemplo de una base cero [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] funcionar, tenga en cuenta el `Split` función.</span><span class="sxs-lookup"><span data-stu-id="5b5cb-111">For an example of a zero-based [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] function, consider the `Split` function.</span></span> <span data-ttu-id="5b5cb-112">Divide una cadena y devuelve una matriz que contiene las subcadenas.</span><span class="sxs-lookup"><span data-stu-id="5b5cb-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="5b5cb-113">El [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> método también divide una cadena y devuelve una matriz que contiene las subcadenas.</span><span class="sxs-lookup"><span data-stu-id="5b5cb-113">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="5b5cb-114">Dado que la `Split` función y <xref:System.String.Split%2A> devuelto del método [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] matrices, deben ser basado en cero.</span><span class="sxs-lookup"><span data-stu-id="5b5cb-114">Because the `Split` function and <xref:System.String.Split%2A> method return [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b5cb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b5cb-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:System.String.Substring%2A>  
 <xref:System.String.Split%2A>  
 [<span data-ttu-id="5b5cb-116">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5b5cb-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
