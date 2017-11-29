---
title: "REM (Instrucción, Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d64ce970e3e74437f5e8c63c8a4d578900902192
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="27ae7-102">REM (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="27ae7-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="27ae7-103">Se usa para incluir notas explicativas en el código fuente de un programa.</span><span class="sxs-lookup"><span data-stu-id="27ae7-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27ae7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27ae7-104">Syntax</span></span>  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="27ae7-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="27ae7-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="27ae7-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="27ae7-106">Optional.</span></span> <span data-ttu-id="27ae7-107">El texto de cualquier comentario que desee incluir.</span><span class="sxs-lookup"><span data-stu-id="27ae7-107">The text of any comment you want to include.</span></span> <span data-ttu-id="27ae7-108">Se requiere un espacio entre el `REM` palabra clave y `comment`.</span><span class="sxs-lookup"><span data-stu-id="27ae7-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27ae7-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="27ae7-109">Remarks</span></span>  
 <span data-ttu-id="27ae7-110">Puede colocar una `REM` instrucción aislada en una línea o puede colocar en una línea después de otra instrucción.</span><span class="sxs-lookup"><span data-stu-id="27ae7-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="27ae7-111">El `REM` instrucción debe ser la última instrucción en la línea.</span><span class="sxs-lookup"><span data-stu-id="27ae7-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="27ae7-112">Si sigue otra instrucción, la `REM` debe estar separada de esa instrucción por un espacio.</span><span class="sxs-lookup"><span data-stu-id="27ae7-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="27ae7-113">Puede utilizar una comilla simple (`'`) en lugar de `REM`.</span><span class="sxs-lookup"><span data-stu-id="27ae7-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="27ae7-114">Esto es cierto si el comentario sigue a otra instrucción en la misma línea o se encuentra sola en una línea.</span><span class="sxs-lookup"><span data-stu-id="27ae7-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27ae7-115">No se puede continuar una `REM` instrucción mediante una secuencia de continuación de línea (`_`).</span><span class="sxs-lookup"><span data-stu-id="27ae7-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="27ae7-116">Una vez que inicia un comentario, el compilador no examina los caracteres de un significado especial.</span><span class="sxs-lookup"><span data-stu-id="27ae7-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="27ae7-117">Para un comentario ocupe varias líneas, usar otra `REM` instrucción o un símbolo de comentario (`'`) en cada línea.</span><span class="sxs-lookup"><span data-stu-id="27ae7-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27ae7-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="27ae7-118">Example</span></span>  
 <span data-ttu-id="27ae7-119">En el ejemplo siguiente se muestra el `REM` instrucción, que se usa para incluir notas explicativas en un programa.</span><span class="sxs-lookup"><span data-stu-id="27ae7-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="27ae7-120">También muestra la alternativa de utilizar el carácter de comilla simple (`'`) en lugar de `REM`.</span><span class="sxs-lookup"><span data-stu-id="27ae7-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="27ae7-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="27ae7-121">See Also</span></span>  
 [<span data-ttu-id="27ae7-122">Comentarios en código</span><span class="sxs-lookup"><span data-stu-id="27ae7-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 [<span data-ttu-id="27ae7-123">Interrumpir y combinar instrucciones en código</span><span class="sxs-lookup"><span data-stu-id="27ae7-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
