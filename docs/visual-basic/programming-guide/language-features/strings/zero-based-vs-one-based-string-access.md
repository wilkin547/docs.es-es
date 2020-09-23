---
title: Acceso a cadenas basado en cero y basado en uno
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: 91d3fb9d7bfdf3d5af27fc6499583640946a802f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072293"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="cce6b-102">Acceso de base cero y de base uno a a cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cce6b-102">Zero-based vs. One-based String Access in Visual Basic</span></span>

<span data-ttu-id="cce6b-103">En este tema se compara cómo Visual Basic y el .NET Framework proporcionan acceso a los caracteres de una cadena.</span><span class="sxs-lookup"><span data-stu-id="cce6b-103">This topic compares how Visual Basic and the .NET Framework provide access to the characters in a string.</span></span> <span data-ttu-id="cce6b-104">El .NET Framework siempre proporciona acceso de base cero a los caracteres de una cadena, mientras que Visual Basic proporciona acceso basado en cero y basado en uno, en función de la función.</span><span class="sxs-lookup"><span data-stu-id="cce6b-104">The .NET Framework always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="cce6b-105">Basado en uno</span><span class="sxs-lookup"><span data-stu-id="cce6b-105">One-Based</span></span>  

 <span data-ttu-id="cce6b-106">Para obtener un ejemplo de una función de Visual Basic basada en uno, considere la `Mid` función.</span><span class="sxs-lookup"><span data-stu-id="cce6b-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="cce6b-107">Toma un argumento que indica la posición del carácter en el que comenzará la subcadena, comenzando por la posición 1.</span><span class="sxs-lookup"><span data-stu-id="cce6b-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="cce6b-108">El <xref:System.String.Substring%2A?displayProperty=nameWithType> método .NET Framework toma un índice del carácter de la cadena en la que se va a iniciar la subcadena, empezando por la posición 0.</span><span class="sxs-lookup"><span data-stu-id="cce6b-108">The .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="cce6b-109">Por lo tanto, si tiene una cadena "ABCDe", los caracteres individuales se numeran de 1, 2, 3, 4, 5 para su uso con la `Mid` función, pero 0, 1, 2, 3, 4 para su uso con el <xref:System.String.Substring%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="cce6b-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="cce6b-110">Basado en cero</span><span class="sxs-lookup"><span data-stu-id="cce6b-110">Zero-Based</span></span>  

 <span data-ttu-id="cce6b-111">Para obtener un ejemplo de una función de Visual Basic basado en cero, considere la `Split` función.</span><span class="sxs-lookup"><span data-stu-id="cce6b-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="cce6b-112">Divide una cadena y devuelve una matriz que contiene las subcadenas.</span><span class="sxs-lookup"><span data-stu-id="cce6b-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="cce6b-113">El <xref:System.String.Split%2A?displayProperty=nameWithType> método .NET Framework también divide una cadena y devuelve una matriz que contiene las subcadenas.</span><span class="sxs-lookup"><span data-stu-id="cce6b-113">The .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="cce6b-114">Dado que la `Split` función y el <xref:System.String.Split%2A> método devuelven .NET Framework matrices, deben ser de base cero.</span><span class="sxs-lookup"><span data-stu-id="cce6b-114">Because the `Split` function and <xref:System.String.Split%2A> method return .NET Framework arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cce6b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cce6b-115">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [<span data-ttu-id="cce6b-116">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cce6b-116">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
