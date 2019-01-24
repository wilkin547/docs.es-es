---
title: Procedimiento Buscar en una cadena (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: 6ac75c99270deb14e23691d32e8ebf4e8b0a91b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542556"
---
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="1bc9f-102">Procedimiento Buscar en una cadena (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1bc9f-102">How to: Search Within a String (Visual Basic)</span></span>
<span data-ttu-id="1bc9f-103">Este ejemplo llama a la <xref:System.String.IndexOf%2A> método en un <xref:System.String> objeto para informar del índice de la primera aparición de una subcadena.</span><span class="sxs-lookup"><span data-stu-id="1bc9f-103">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bc9f-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1bc9f-104">Example</span></span>  
 [!code-vb[VbVbalrStrings#71](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-search-within-a-string_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1bc9f-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="1bc9f-105">Compiling the Code</span></span>  
 <span data-ttu-id="1bc9f-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="1bc9f-106">This example requires:</span></span>  
  
-   <span data-ttu-id="1bc9f-107">Un `Imports` instrucción que especifica el <xref:System> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="1bc9f-107">An `Imports` statement specifying the <xref:System> namespace.</span></span> <span data-ttu-id="1bc9f-108">Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="1bc9f-108">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="1bc9f-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="1bc9f-109">Robust Programming</span></span>  
 <span data-ttu-id="1bc9f-110">El <xref:System.String.IndexOf%2A> método informa de la ubicación del primer carácter de la primera aparición de la subcadena.</span><span class="sxs-lookup"><span data-stu-id="1bc9f-110">The <xref:System.String.IndexOf%2A> method reports the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="1bc9f-111">El índice está basado en 0, lo que significa que el primer carácter de una cadena tiene un índice de 0.</span><span class="sxs-lookup"><span data-stu-id="1bc9f-111">The index is 0-based, which means the first character of a string has an index of 0.</span></span>  
  
 <span data-ttu-id="1bc9f-112">Si <xref:System.String.IndexOf%2A> no encuentra la subcadena, devuelve -1.</span><span class="sxs-lookup"><span data-stu-id="1bc9f-112">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>  
  
 <span data-ttu-id="1bc9f-113">El <xref:System.String.IndexOf%2A> método distingue mayúsculas de minúsculas y utiliza la referencia cultural actual.</span><span class="sxs-lookup"><span data-stu-id="1bc9f-113">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>  
  
 <span data-ttu-id="1bc9f-114">Para el control de errores óptimo, podría incluir la cadena de búsqueda en el `Try` block de un [intente... Catch... Finally (instrucción)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) construcción.</span><span class="sxs-lookup"><span data-stu-id="1bc9f-114">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) construction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bc9f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bc9f-115">See also</span></span>
- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="1bc9f-116">Try...Catch...Finally (instrucción)</span><span class="sxs-lookup"><span data-stu-id="1bc9f-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="1bc9f-117">Introducción a las cadenas en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1bc9f-117">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [<span data-ttu-id="1bc9f-118">Cadenas</span><span class="sxs-lookup"><span data-stu-id="1bc9f-118">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
