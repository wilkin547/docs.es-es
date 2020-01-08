---
title: 'Cómo: buscar en una cadena'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: 655f746e4e496e1935afcd2a9f9fe36d9e3a2564
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348427"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="28316-102">Cómo: buscar en una cadena (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28316-102">How to: search within a string (Visual Basic)</span></span>

<span data-ttu-id="28316-103">En este artículo se muestra un ejemplo de cómo buscar dentro de una cadena en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="28316-103">This article shows an example of how to search within a string in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="28316-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="28316-104">Example</span></span>

<span data-ttu-id="28316-105">En este ejemplo se llama al método <xref:System.String.IndexOf%2A> en un objeto <xref:System.String> para notificar el índice de la primera aparición de una subcadena:</span><span class="sxs-lookup"><span data-stu-id="28316-105">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring:</span></span>

 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]

## <a name="robust-programming"></a><span data-ttu-id="28316-106">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="28316-106">Robust programming</span></span>

<span data-ttu-id="28316-107">El método <xref:System.String.IndexOf%2A> devuelve la ubicación del primer carácter de la primera aparición de la subcadena.</span><span class="sxs-lookup"><span data-stu-id="28316-107">The <xref:System.String.IndexOf%2A> method returns the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="28316-108">El índice es de base 0, lo que significa que el primer carácter de una cadena tiene un índice de 0.</span><span class="sxs-lookup"><span data-stu-id="28316-108">The index is 0-based, which means the first character of a string has an index of 0.</span></span>

<span data-ttu-id="28316-109">Si <xref:System.String.IndexOf%2A> no encuentra la subcadena, devuelve-1.</span><span class="sxs-lookup"><span data-stu-id="28316-109">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>

<span data-ttu-id="28316-110">El método <xref:System.String.IndexOf%2A> distingue entre mayúsculas y minúsculas y utiliza la referencia cultural actual.</span><span class="sxs-lookup"><span data-stu-id="28316-110">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>

<span data-ttu-id="28316-111">Para un control de errores óptimo, es posible que desee incluir la búsqueda de cadenas en el bloque `Try` de una [instrucción try... Detectar... Construcción de la instrucción Finally](../../../language-reference/statements/try-catch-finally-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="28316-111">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../language-reference/statements/try-catch-finally-statement.md) construction.</span></span>

## <a name="see-also"></a><span data-ttu-id="28316-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="28316-112">See also</span></span>

- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="28316-113">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="28316-113">Try...Catch...Finally Statement</span></span>](../../../language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="28316-114">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="28316-114">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
- [<span data-ttu-id="28316-115">Cadenas</span><span class="sxs-lookup"><span data-stu-id="28316-115">Strings</span></span>](index.md)
