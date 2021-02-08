---
description: 'Más información acerca de: BC30205: final de la instrucción esperada'
title: Se esperaba el fin de instrucción
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: a3f309a4674f6de34c0be8abfef31e293a10dec5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796553"
---
# <a name="bc30205-end-of-statement-expected"></a><span data-ttu-id="f3941-103">BC30205: se esperaba el final de la instrucción</span><span class="sxs-lookup"><span data-stu-id="f3941-103">BC30205: End of statement expected</span></span>

<span data-ttu-id="f3941-104">La instrucción se completa sintácticamente, pero un elemento de programación adicional sigue el elemento que completa la instrucción.</span><span class="sxs-lookup"><span data-stu-id="f3941-104">The statement is syntactically complete, but an additional programming element follows the element that completes the statement.</span></span> <span data-ttu-id="f3941-105">Se requiere un terminador de línea al final de cada instrucción.</span><span class="sxs-lookup"><span data-stu-id="f3941-105">A line terminator is required at the end of every statement.</span></span>

 <span data-ttu-id="f3941-106">Un terminador de línea divide los caracteres de un archivo de origen de Visual Basic en líneas.</span><span class="sxs-lookup"><span data-stu-id="f3941-106">A line terminator divides the characters of a Visual Basic source file into lines.</span></span> <span data-ttu-id="f3941-107">Los ejemplos de terminadores de línea son el carácter de retorno de carro Unicode (&HD), el carácter de avance de línea Unicode (&HA) y el carácter de retorno de carro Unicode seguido del carácter de avance de línea Unicode.</span><span class="sxs-lookup"><span data-stu-id="f3941-107">Examples of line terminators are the Unicode carriage return character (&HD), the Unicode linefeed character (&HA), and the Unicode carriage return character followed by the Unicode linefeed character.</span></span> <span data-ttu-id="f3941-108">Para obtener más información sobre los terminadores de línea, vea la [especificación del lenguaje Visual Basic](~/_vblang/spec/lexical-grammar.md#line-terminators).</span><span class="sxs-lookup"><span data-stu-id="f3941-108">For more information about line terminators, see the [Visual Basic Language Specification](~/_vblang/spec/lexical-grammar.md#line-terminators).</span></span>

 <span data-ttu-id="f3941-109">**Identificador de error:** BC30205</span><span class="sxs-lookup"><span data-stu-id="f3941-109">**Error ID:** BC30205</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="f3941-110">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="f3941-110">To correct this error</span></span>

1. <span data-ttu-id="f3941-111">Compruebe si dos instrucciones diferentes se han colocado involuntariamente en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="f3941-111">Check to see if two different statements have inadvertently been put on the same line.</span></span>

2. <span data-ttu-id="f3941-112">Inserte un terminador de línea después del elemento que completa la instrucción.</span><span class="sxs-lookup"><span data-stu-id="f3941-112">Insert a line terminator after the element that completes the statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3941-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3941-113">See also</span></span>

- [<span data-ttu-id="f3941-114">Procedimiento Interrupción y combinación de instrucciones en código</span><span class="sxs-lookup"><span data-stu-id="f3941-114">How to: Break and Combine Statements in Code</span></span>](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [<span data-ttu-id="f3941-115">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="f3941-115">Statements</span></span>](../../programming-guide/language-features/statements.md)
