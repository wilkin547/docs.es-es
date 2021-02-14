---
description: 'Más información sobre: Cómo: etiquetar instrucciones (Visual Basic)'
title: Procedimiento Instrucciones de etiquetas
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 4efb320dad7d52f6e9b94f6e6f81730f94b5966b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433257"
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="7f417-103">Cómo: Aplicar etiquetas a las instrucciones (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f417-103">How to: Label Statements (Visual Basic)</span></span>

<span data-ttu-id="7f417-104">Los bloques de instrucciones se componen de líneas de código delimitadas por dos puntos.</span><span class="sxs-lookup"><span data-stu-id="7f417-104">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="7f417-105">Se dice que las líneas de código precedidas de una cadena o un entero de identificación están *etiquetadas*.</span><span class="sxs-lookup"><span data-stu-id="7f417-105">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="7f417-106">Las etiquetas de instrucción se usan para marcar una línea de código para identificarla para su uso con instrucciones como `On Error Goto` .</span><span class="sxs-lookup"><span data-stu-id="7f417-106">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>

<span data-ttu-id="7f417-107">Las etiquetas pueden ser válidas Visual Basic identificadores, como los que identifican elementos de programación, o literales enteros.</span><span class="sxs-lookup"><span data-stu-id="7f417-107">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="7f417-108">Una etiqueta debe aparecer al principio de una línea de código fuente y debe ir seguida de dos puntos, independientemente de si va seguido de una instrucción en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="7f417-108">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>

<span data-ttu-id="7f417-109">El compilador identifica las etiquetas comprobando si el principio de la línea coincide con cualquier identificador ya definido.</span><span class="sxs-lookup"><span data-stu-id="7f417-109">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="7f417-110">Si no es así, el compilador supone que es una etiqueta.</span><span class="sxs-lookup"><span data-stu-id="7f417-110">If it does not, the compiler assumes it is a label.</span></span>

<span data-ttu-id="7f417-111">Las etiquetas tienen su propio espacio de declaración y no interfieren con otros identificadores.</span><span class="sxs-lookup"><span data-stu-id="7f417-111">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="7f417-112">El ámbito de una etiqueta es el cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="7f417-112">A label's scope is the body of the method.</span></span> <span data-ttu-id="7f417-113">La declaración de etiqueta tiene prioridad en cualquier situación ambigua.</span><span class="sxs-lookup"><span data-stu-id="7f417-113">Label declaration takes precedence in any ambiguous situation.</span></span>

> [!NOTE]
> <span data-ttu-id="7f417-114">Las etiquetas solo se pueden usar en instrucciones ejecutables dentro de métodos.</span><span class="sxs-lookup"><span data-stu-id="7f417-114">Labels can be used only on executable statements inside methods.</span></span>

## <a name="to-label-a-line-of-code"></a><span data-ttu-id="7f417-115">Para etiquetar una línea de código</span><span class="sxs-lookup"><span data-stu-id="7f417-115">To label a line of code</span></span>

<span data-ttu-id="7f417-116">Coloque un identificador seguido de un signo de dos puntos, al principio de la línea de código fuente.</span><span class="sxs-lookup"><span data-stu-id="7f417-116">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>

<span data-ttu-id="7f417-117">Por ejemplo, las siguientes líneas de código se etiquetan con `Jump` y `120` , respectivamente:</span><span class="sxs-lookup"><span data-stu-id="7f417-117">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>

[!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]

## <a name="see-also"></a><span data-ttu-id="7f417-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f417-118">See also</span></span>

- [<span data-ttu-id="7f417-119">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="7f417-119">Statements</span></span>](../language-features/statements.md)
- [<span data-ttu-id="7f417-120">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="7f417-120">Declared Element Names</span></span>](../language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="7f417-121">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="7f417-121">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
