---
title: Se esperaba el fin de instrucción
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 7b91d13cbcb9d211d4ca18c8e48c7494bf6eccc6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588085"
---
# <a name="end-of-statement-expected"></a><span data-ttu-id="d1108-102">Se esperaba el fin de instrucción</span><span class="sxs-lookup"><span data-stu-id="d1108-102">End of statement expected</span></span>
<span data-ttu-id="d1108-103">La instrucción es sintácticamente completa, pero un elemento de programación adicional sigue al elemento que se completa la instrucción.</span><span class="sxs-lookup"><span data-stu-id="d1108-103">The statement is syntactically complete, but an additional programming element follows the element that completes the statement.</span></span> <span data-ttu-id="d1108-104">Tiene un terminador de línea al final de cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="d1108-104">A line terminator is required at the end of every statement.</span></span>
  
 <span data-ttu-id="d1108-105">Un terminador de línea divide los caracteres de un archivo de código fuente de Visual Basic en líneas.</span><span class="sxs-lookup"><span data-stu-id="d1108-105">A line terminator divides the characters of a Visual Basic source file into lines.</span></span> <span data-ttu-id="d1108-106">Algunos ejemplos de terminadores de línea son el Unicode carro devuelto carácter (& HD), el Unicode avance de línea carácter (& HA), y seguido del carácter de avance de línea de Unicode del carácter de retorno de carro de Unicode.</span><span class="sxs-lookup"><span data-stu-id="d1108-106">Examples of line terminators are the Unicode carriage return character (&HD), the Unicode linefeed character (&HA), and the Unicode carriage return character followed by the Unicode linefeed character.</span></span> <span data-ttu-id="d1108-107">Para obtener más información acerca de los terminadores de línea, consulte el [especificación del lenguaje Visual Basic](../../../visual-basic/reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="d1108-107">For more information about line terminators, see the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification/index.md).</span></span>
  
 <span data-ttu-id="d1108-108">**Id. de error:** BC30205</span><span class="sxs-lookup"><span data-stu-id="d1108-108">**Error ID:** BC30205</span></span>
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d1108-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d1108-109">To correct this error</span></span>
  
1.  <span data-ttu-id="d1108-110">Comprueba si dos instrucciones diferentes inadvertidamente se han colocado en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="d1108-110">Check to see if two different statements have inadvertently been put on the same line.</span></span>
  
2.  <span data-ttu-id="d1108-111">Inserte un terminador de línea después del elemento que se completa la instrucción.</span><span class="sxs-lookup"><span data-stu-id="d1108-111">Insert a line terminator after the element that completes the statement.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d1108-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1108-112">See Also</span></span>  
 [<span data-ttu-id="d1108-113">Interrumpir y combinar instrucciones en código</span><span class="sxs-lookup"><span data-stu-id="d1108-113">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 [<span data-ttu-id="d1108-114">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="d1108-114">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
