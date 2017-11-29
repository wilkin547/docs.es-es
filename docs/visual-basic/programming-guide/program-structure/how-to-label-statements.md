---
title: "Cómo: Aplicar etiquetas a las instrucciones (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 190ec9fc2392e6e4adae9b2b612edd69d73cedfd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-label-statements-visual-basic"></a><span data-ttu-id="8ff41-102">Cómo: Aplicar etiquetas a las instrucciones (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ff41-102">How to: Label Statements (Visual Basic)</span></span>
<span data-ttu-id="8ff41-103">Bloques de instrucciones se componen de líneas de código delimitadas por dos puntos.</span><span class="sxs-lookup"><span data-stu-id="8ff41-103">Statement blocks are made up of lines of code delimited by colons.</span></span> <span data-ttu-id="8ff41-104">Se dice que las líneas de código precedidas por una cadena o entero identificación *con la etiqueta*.</span><span class="sxs-lookup"><span data-stu-id="8ff41-104">Lines of code preceded by an identifying string or integer are said to be *labeled*.</span></span> <span data-ttu-id="8ff41-105">Las etiquetas de instrucciones se utilizan para marcar una línea de código que se identifique para su uso con instrucciones como `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="8ff41-105">Statement labels are used to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 <span data-ttu-id="8ff41-106">Las etiquetas pueden ser identificadores Visual Basic válidos, como las que identifican elementos de programación, o literales enteros.</span><span class="sxs-lookup"><span data-stu-id="8ff41-106">Labels may be either valid Visual Basic identifiers—such as those that identify programming elements—or integer literals.</span></span> <span data-ttu-id="8ff41-107">Una etiqueta debe aparecer al principio de una línea de código fuente y debe ir seguida por un signo de dos puntos, independientemente de si es seguida por una instrucción en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="8ff41-107">A label must appear at the beginning of a line of source code and must be followed by a colon, regardless of whether it is followed by a statement on the same line.</span></span>  
  
 <span data-ttu-id="8ff41-108">El compilador identifica las etiquetas comprobando si el principio de la línea coincide con cualquier identificador ya definido.</span><span class="sxs-lookup"><span data-stu-id="8ff41-108">The compiler identifies labels by checking whether the beginning of the line matches any already-defined identifier.</span></span> <span data-ttu-id="8ff41-109">Si no es así, el compilador supone que es una etiqueta.</span><span class="sxs-lookup"><span data-stu-id="8ff41-109">If it does not, the compiler assumes it is a label.</span></span>  
  
 <span data-ttu-id="8ff41-110">Las etiquetas tienen su propio espacio de declaración y no interfieren con otros identificadores.</span><span class="sxs-lookup"><span data-stu-id="8ff41-110">Labels have their own declaration space and do not interfere with other identifiers.</span></span> <span data-ttu-id="8ff41-111">Ámbito de una etiqueta es el cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="8ff41-111">A label's scope is the body of the method.</span></span> <span data-ttu-id="8ff41-112">Declaración de la etiqueta tiene prioridad en cualquier situación ambigua.</span><span class="sxs-lookup"><span data-stu-id="8ff41-112">Label declaration takes precedence in any ambiguous situation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ff41-113">Las etiquetas se pueden utilizar sólo en las instrucciones ejecutables dentro de métodos.</span><span class="sxs-lookup"><span data-stu-id="8ff41-113">Labels can be used only on executable statements inside methods.</span></span>  
  
### <a name="to-label-a-line-of-code"></a><span data-ttu-id="8ff41-114">Para etiquetar una línea de código</span><span class="sxs-lookup"><span data-stu-id="8ff41-114">To label a line of code</span></span>  
  
-   <span data-ttu-id="8ff41-115">Coloque un identificador, seguido de dos puntos, al principio de la línea de código fuente.</span><span class="sxs-lookup"><span data-stu-id="8ff41-115">Place an identifier, followed by a colon, at the beginning of the line of source code.</span></span>  
  
     <span data-ttu-id="8ff41-116">Por ejemplo, las siguientes líneas de código están etiquetadas con `Jump` y `120`, respectivamente:</span><span class="sxs-lookup"><span data-stu-id="8ff41-116">For example, the following lines of code are labeled with `Jump` and `120`, respectively:</span></span>  
  
     [!code-vb[VbVbalrStatements#708](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/how-to-label-statements_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8ff41-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ff41-117">See Also</span></span>  
 [<span data-ttu-id="8ff41-118">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="8ff41-118">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="8ff41-119">Nombres de elementos declarados</span><span class="sxs-lookup"><span data-stu-id="8ff41-119">Declared Element Names</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="8ff41-120">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="8ff41-120">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
