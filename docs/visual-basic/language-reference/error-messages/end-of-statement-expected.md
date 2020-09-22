---
title: Se esperaba el fin de instrucción
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 9141400afc651629df381e0a655e2d7b9da2e45d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874419"
---
# <a name="end-of-statement-expected"></a><span data-ttu-id="5c8c9-102">Se esperaba el fin de instrucción</span><span class="sxs-lookup"><span data-stu-id="5c8c9-102">End of statement expected</span></span>

<span data-ttu-id="5c8c9-103">La instrucción se completa sintácticamente, pero un elemento de programación adicional sigue el elemento que completa la instrucción.</span><span class="sxs-lookup"><span data-stu-id="5c8c9-103">The statement is syntactically complete, but an additional programming element follows the element that completes the statement.</span></span> <span data-ttu-id="5c8c9-104">Se requiere un terminador de línea al final de cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="5c8c9-104">A line terminator is required at the end of every statement.</span></span>
  
 <span data-ttu-id="5c8c9-105">Un terminador de línea divide los caracteres de un archivo de origen de Visual Basic en líneas.</span><span class="sxs-lookup"><span data-stu-id="5c8c9-105">A line terminator divides the characters of a Visual Basic source file into lines.</span></span> <span data-ttu-id="5c8c9-106">Los ejemplos de terminadores de línea son el carácter de retorno de carro Unicode (&HD), el carácter de avance de línea Unicode (&HA) y el carácter de retorno de carro Unicode seguido del carácter de avance de línea Unicode.</span><span class="sxs-lookup"><span data-stu-id="5c8c9-106">Examples of line terminators are the Unicode carriage return character (&HD), the Unicode linefeed character (&HA), and the Unicode carriage return character followed by the Unicode linefeed character.</span></span> <span data-ttu-id="5c8c9-107">Para obtener más información sobre los terminadores de línea, vea la [especificación del lenguaje Visual Basic](~/_vblang/spec/lexical-grammar.md#line-terminators).</span><span class="sxs-lookup"><span data-stu-id="5c8c9-107">For more information about line terminators, see the [Visual Basic Language Specification](~/_vblang/spec/lexical-grammar.md#line-terminators).</span></span>
  
 <span data-ttu-id="5c8c9-108">**Identificador de error:** BC30205</span><span class="sxs-lookup"><span data-stu-id="5c8c9-108">**Error ID:** BC30205</span></span>
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5c8c9-109">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="5c8c9-109">To correct this error</span></span>
  
1. <span data-ttu-id="5c8c9-110">Compruebe si dos instrucciones diferentes se han colocado involuntariamente en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="5c8c9-110">Check to see if two different statements have inadvertently been put on the same line.</span></span>
  
2. <span data-ttu-id="5c8c9-111">Inserte un terminador de línea después del elemento que completa la instrucción.</span><span class="sxs-lookup"><span data-stu-id="5c8c9-111">Insert a line terminator after the element that completes the statement.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5c8c9-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5c8c9-112">See also</span></span>

- [<span data-ttu-id="5c8c9-113">Procedimiento Interrupción y combinación de instrucciones en código</span><span class="sxs-lookup"><span data-stu-id="5c8c9-113">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [<span data-ttu-id="5c8c9-114">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="5c8c9-114">Statements</span></span>](../../programming-guide/language-features/statements.md)
