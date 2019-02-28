---
title: REM (Instrucción, Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: b25910f5215585914094b7bc4420f537a400934b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968012"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="f1db5-102">REM (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1db5-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="f1db5-103">Se usa para incluir notas explicativas en el código fuente de un programa.</span><span class="sxs-lookup"><span data-stu-id="f1db5-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1db5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1db5-104">Syntax</span></span>  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="f1db5-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="f1db5-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="f1db5-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="f1db5-106">Optional.</span></span> <span data-ttu-id="f1db5-107">El texto de cualquier comentario que desee incluir.</span><span class="sxs-lookup"><span data-stu-id="f1db5-107">The text of any comment you want to include.</span></span> <span data-ttu-id="f1db5-108">Se requiere un espacio entre el `REM` palabra clave y `comment`.</span><span class="sxs-lookup"><span data-stu-id="f1db5-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1db5-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f1db5-109">Remarks</span></span>  
 <span data-ttu-id="f1db5-110">Puede colocar un `REM` por sí solo en una línea o instrucción puede colocarlo en una línea después de otra instrucción.</span><span class="sxs-lookup"><span data-stu-id="f1db5-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="f1db5-111">El `REM` instrucción debe ser la última instrucción en la línea.</span><span class="sxs-lookup"><span data-stu-id="f1db5-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="f1db5-112">Si sigue otra instrucción, el `REM` deben estar separados de esa instrucción por un espacio.</span><span class="sxs-lookup"><span data-stu-id="f1db5-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="f1db5-113">Puede usar una comilla simple (`'`) en lugar de `REM`.</span><span class="sxs-lookup"><span data-stu-id="f1db5-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="f1db5-114">Esto es cierto si el comentario sigue otra instrucción en la misma línea o se encuentra solo en una línea.</span><span class="sxs-lookup"><span data-stu-id="f1db5-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1db5-115">No puede continuar una `REM` instrucción mediante el uso de una secuencia de continuación de línea (`_`).</span><span class="sxs-lookup"><span data-stu-id="f1db5-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="f1db5-116">Una vez que inicia un comentario, el compilador no examina los caracteres de un significado especial.</span><span class="sxs-lookup"><span data-stu-id="f1db5-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="f1db5-117">Para un comentario de varias líneas, use otro `REM` instrucción o un símbolo de comentario (`'`) en cada línea.</span><span class="sxs-lookup"><span data-stu-id="f1db5-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1db5-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f1db5-118">Example</span></span>  
 <span data-ttu-id="f1db5-119">El ejemplo siguiente ilustra la `REM` instrucción, que se usa para incluir notas explicativas en un programa.</span><span class="sxs-lookup"><span data-stu-id="f1db5-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="f1db5-120">También se muestra la alternativa de utilizar el carácter de comilla simple (`'`) en lugar de `REM`.</span><span class="sxs-lookup"><span data-stu-id="f1db5-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="f1db5-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1db5-121">See also</span></span>
- [<span data-ttu-id="f1db5-122">Comentarios en código</span><span class="sxs-lookup"><span data-stu-id="f1db5-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [<span data-ttu-id="f1db5-123">Cómo: Interrumpir y combinar instrucciones en código</span><span class="sxs-lookup"><span data-stu-id="f1db5-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
