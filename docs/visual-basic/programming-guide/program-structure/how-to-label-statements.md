---
title: Procedimiento Instrucciones de etiquetas
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 8f04d592c51b6a0630bfe623fd3574555aef9ff8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403218"
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="d5cfa-102">Cómo: Aplicar etiquetas a las instrucciones (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5cfa-102">How to: Label Statements (Visual Basic)</span></span>

<span data-ttu-id="d5cfa-103">Los bloques de instrucciones se componen de líneas de código delimitadas por dos puntos.</span><span class="sxs-lookup"><span data-stu-id="d5cfa-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="d5cfa-104">Se dice que las líneas de código precedidas de una cadena o un entero de identificación están *etiquetadas*.</span><span class="sxs-lookup"><span data-stu-id="d5cfa-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="d5cfa-105">Las etiquetas de instrucción se usan para marcar una línea de código para identificarla para su uso con instrucciones como `On Error Goto` .</span><span class="sxs-lookup"><span data-stu-id="d5cfa-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>

<span data-ttu-id="d5cfa-106">Las etiquetas pueden ser válidas Visual Basic identificadores, como los que identifican elementos de programación, o literales enteros.</span><span class="sxs-lookup"><span data-stu-id="d5cfa-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="d5cfa-107">Una etiqueta debe aparecer al principio de una línea de código fuente y debe ir seguida de dos puntos, independientemente de si va seguido de una instrucción en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="d5cfa-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>

<span data-ttu-id="d5cfa-108">El compilador identifica las etiquetas comprobando si el principio de la línea coincide con cualquier identificador ya definido.</span><span class="sxs-lookup"><span data-stu-id="d5cfa-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="d5cfa-109">Si no es así, el compilador supone que es una etiqueta.</span><span class="sxs-lookup"><span data-stu-id="d5cfa-109">If it does not, the compiler assumes it is a label.</span></span>

<span data-ttu-id="d5cfa-110">Las etiquetas tienen su propio espacio de declaración y no interfieren con otros identificadores.</span><span class="sxs-lookup"><span data-stu-id="d5cfa-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="d5cfa-111">El ámbito de una etiqueta es el cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="d5cfa-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="d5cfa-112">La declaración de etiqueta tiene prioridad en cualquier situación ambigua.</span><span class="sxs-lookup"><span data-stu-id="d5cfa-112">Label declaration takes precedence in any ambiguous situation.</span></span>

> [!NOTE]
> <span data-ttu-id="d5cfa-113">Las etiquetas solo se pueden usar en instrucciones ejecutables dentro de métodos.</span><span class="sxs-lookup"><span data-stu-id="d5cfa-113">Labels can be used only on executable statements inside methods.</span></span>

## <a name="to-label-a-line-of-code"></a><span data-ttu-id="d5cfa-114">Para etiquetar una línea de código</span><span class="sxs-lookup"><span data-stu-id="d5cfa-114">To label a line of code</span></span>

<span data-ttu-id="d5cfa-115">Coloque un identificador seguido de un signo de dos puntos, al principio de la línea de código fuente.</span><span class="sxs-lookup"><span data-stu-id="d5cfa-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>

<span data-ttu-id="d5cfa-116">Por ejemplo, las siguientes líneas de código se etiquetan con `Jump` y `120` , respectivamente:</span><span class="sxs-lookup"><span data-stu-id="d5cfa-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>

[!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]

## <a name="see-also"></a><span data-ttu-id="d5cfa-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5cfa-117">See also</span></span>

- [<span data-ttu-id="d5cfa-118">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="d5cfa-118">Statements</span></span>](../language-features/statements.md)
- [<span data-ttu-id="d5cfa-119">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="d5cfa-119">Declared Element Names</span></span>](../language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="d5cfa-120">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="d5cfa-120">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
