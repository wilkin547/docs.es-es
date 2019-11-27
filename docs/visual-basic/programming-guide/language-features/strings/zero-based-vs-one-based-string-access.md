---
title: Acceso de cadena basado en cero y basado en uno
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: 97e60038bc7ec0f030939d0980b786bffebcfb9a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354299"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="d5d30-102">Acceso de base cero y de base uno a a cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d5d30-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="d5d30-103">En este tema se compara cómo Visual Basic y el .NET Framework proporcionan acceso a los caracteres de una cadena.</span><span class="sxs-lookup"><span data-stu-id="d5d30-103">This topic compares how Visual Basic and the .NET Framework provide access to the characters in a string.</span></span> <span data-ttu-id="d5d30-104">El .NET Framework siempre proporciona acceso de base cero a los caracteres de una cadena, mientras que Visual Basic proporciona acceso basado en cero y basado en uno, en función de la función.</span><span class="sxs-lookup"><span data-stu-id="d5d30-104">The .NET Framework always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="d5d30-105">Basado en uno</span><span class="sxs-lookup"><span data-stu-id="d5d30-105">One-Based</span></span>  
 <span data-ttu-id="d5d30-106">Para obtener un ejemplo de una función de Visual Basic basada en uno, considere la función `Mid`.</span><span class="sxs-lookup"><span data-stu-id="d5d30-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="d5d30-107">Toma un argumento que indica la posición del carácter en el que comenzará la subcadena, comenzando por la posición 1.</span><span class="sxs-lookup"><span data-stu-id="d5d30-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="d5d30-108">El método <xref:System.String.Substring%2A?displayProperty=nameWithType> de .NET Framework toma un índice del carácter de la cadena en la que se va a iniciar la subcadena, empezando por la posición 0.</span><span class="sxs-lookup"><span data-stu-id="d5d30-108">The .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="d5d30-109">Por lo tanto, si tiene una cadena "ABCDe", los caracteres individuales se numeran de 1, 2, 3, 4, 5 para su uso con la función `Mid`, pero 0, 1, 2, 3, 4 para su uso con el método <xref:System.String.Substring%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d5d30-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="d5d30-110">Basado en cero</span><span class="sxs-lookup"><span data-stu-id="d5d30-110">Zero-Based</span></span>  
 <span data-ttu-id="d5d30-111">Para obtener un ejemplo de una función de Visual Basic basado en cero, considere la función `Split`.</span><span class="sxs-lookup"><span data-stu-id="d5d30-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="d5d30-112">Divide una cadena y devuelve una matriz que contiene las subcadenas.</span><span class="sxs-lookup"><span data-stu-id="d5d30-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="d5d30-113">El método .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> también divide una cadena y devuelve una matriz que contiene las subcadenas.</span><span class="sxs-lookup"><span data-stu-id="d5d30-113">The .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="d5d30-114">Dado que la función `Split` y <xref:System.String.Split%2A> método devuelven .NET Framework matrices, deben ser de base cero.</span><span class="sxs-lookup"><span data-stu-id="d5d30-114">Because the `Split` function and <xref:System.String.Split%2A> method return .NET Framework arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5d30-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5d30-115">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [<span data-ttu-id="d5d30-116">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d5d30-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
