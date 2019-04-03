---
title: Filtrar Etiqueta instrucciones (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 69ec8c7625410f140c59ba8dd492dca76857eb96
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828646"
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="5ba55-102">Filtrar Etiqueta instrucciones (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ba55-102">How to: Label Statements (Visual Basic)</span></span>
<span data-ttu-id="5ba55-103">Bloques de instrucciones se componen de líneas de código delimitadas por signos de dos puntos.</span><span class="sxs-lookup"><span data-stu-id="5ba55-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="5ba55-104">Líneas de código precedido de un entero o cadena de identificación se consideran *con la etiqueta*.</span><span class="sxs-lookup"><span data-stu-id="5ba55-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="5ba55-105">Las etiquetas de instrucciones se usan para marcar una línea de código para identificarla para su uso con instrucciones como `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="5ba55-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 <span data-ttu-id="5ba55-106">Las etiquetas pueden ser identificadores Visual Basic válidos, como las que identifican elementos de programación, o literales enteros.</span><span class="sxs-lookup"><span data-stu-id="5ba55-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="5ba55-107">Una etiqueta debe aparecer al principio de una línea de código fuente y debe ir seguida por dos puntos, independientemente de si está seguida por una instrucción en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="5ba55-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>  
  
 <span data-ttu-id="5ba55-108">El compilador identifica las etiquetas mediante la comprobación de si el principio de la línea coincide con cualquier identificador ya definido.</span><span class="sxs-lookup"><span data-stu-id="5ba55-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="5ba55-109">Si no es así, el compilador supone que es una etiqueta.</span><span class="sxs-lookup"><span data-stu-id="5ba55-109">If it does not, the compiler assumes it is a label.</span></span>  
  
 <span data-ttu-id="5ba55-110">Las etiquetas tienen su propio espacio de declaración y no interfieren con otros identificadores.</span><span class="sxs-lookup"><span data-stu-id="5ba55-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="5ba55-111">Ámbito de una etiqueta es el cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="5ba55-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="5ba55-112">Declaración de la etiqueta tiene prioridad en cualquier situación ambigua.</span><span class="sxs-lookup"><span data-stu-id="5ba55-112">Label declaration takes precedence in any ambiguous situation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ba55-113">Etiquetas se pueden usar únicamente en las instrucciones ejecutables dentro de los métodos.</span><span class="sxs-lookup"><span data-stu-id="5ba55-113">Labels can be used only on executable statements inside methods.</span></span>  
  
### <a name="to-label-a-line-of-code"></a><span data-ttu-id="5ba55-114">Para etiquetar una línea de código</span><span class="sxs-lookup"><span data-stu-id="5ba55-114">To label a line of code</span></span>  
  
-   <span data-ttu-id="5ba55-115">Coloque un identificador, seguido de dos puntos, al principio de la línea de código fuente.</span><span class="sxs-lookup"><span data-stu-id="5ba55-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>  
  
     <span data-ttu-id="5ba55-116">Por ejemplo, las siguientes líneas de código se etiquetan con `Jump` y `120`, respectivamente:</span><span class="sxs-lookup"><span data-stu-id="5ba55-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>  
  
     [!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]  
  
## <a name="see-also"></a><span data-ttu-id="5ba55-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ba55-117">See also</span></span>

- [<span data-ttu-id="5ba55-118">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="5ba55-118">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="5ba55-119">Nombres de elementos declarados</span><span class="sxs-lookup"><span data-stu-id="5ba55-119">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="5ba55-120">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="5ba55-120">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
