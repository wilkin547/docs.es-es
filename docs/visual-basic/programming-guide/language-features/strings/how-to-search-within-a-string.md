---
description: 'Más información acerca de cómo: buscar dentro de una cadena (Visual Basic)'
title: 'Cómo: buscar en una cadena'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: dab9faf91eef2e6d845805693227e1a6735ec796
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429734"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="ef847-103">Cómo: buscar en una cadena (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef847-103">How to: search within a string (Visual Basic)</span></span>

<span data-ttu-id="ef847-104">En este artículo se muestra un ejemplo de cómo buscar dentro de una cadena en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ef847-104">This article shows an example of how to search within a string in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="ef847-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ef847-105">Example</span></span>

<span data-ttu-id="ef847-106">En este ejemplo se llama al <xref:System.String.IndexOf%2A> método en un <xref:System.String> objeto para notificar el índice de la primera aparición de una subcadena:</span><span class="sxs-lookup"><span data-stu-id="ef847-106">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring:</span></span>

 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]

## <a name="robust-programming"></a><span data-ttu-id="ef847-107">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="ef847-107">Robust programming</span></span>

<span data-ttu-id="ef847-108">El <xref:System.String.IndexOf%2A> método devuelve la ubicación del primer carácter de la primera aparición de la subcadena.</span><span class="sxs-lookup"><span data-stu-id="ef847-108">The <xref:System.String.IndexOf%2A> method returns the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="ef847-109">El índice es de base 0, lo que significa que el primer carácter de una cadena tiene un índice de 0.</span><span class="sxs-lookup"><span data-stu-id="ef847-109">The index is 0-based, which means the first character of a string has an index of 0.</span></span>

<span data-ttu-id="ef847-110">Si <xref:System.String.IndexOf%2A> no encuentra la subcadena, devuelve-1.</span><span class="sxs-lookup"><span data-stu-id="ef847-110">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>

<span data-ttu-id="ef847-111">El <xref:System.String.IndexOf%2A> método distingue entre mayúsculas y minúsculas y usa la referencia cultural actual.</span><span class="sxs-lookup"><span data-stu-id="ef847-111">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>

<span data-ttu-id="ef847-112">Para un control de errores óptimo, es posible que desee incluir la búsqueda de cadenas en el `Try` bloque de una [instrucción try... Detectar... Construcción de la instrucción Finally](../../../language-reference/statements/try-catch-finally-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="ef847-112">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../language-reference/statements/try-catch-finally-statement.md) construction.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef847-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef847-113">See also</span></span>

- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="ef847-114">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="ef847-114">Try...Catch...Finally Statement</span></span>](../../../language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="ef847-115">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ef847-115">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
- [<span data-ttu-id="ef847-116">Cadenas</span><span class="sxs-lookup"><span data-stu-id="ef847-116">Strings</span></span>](index.md)
