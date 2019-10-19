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
ms.openlocfilehash: 729d0710d65c0cda750061e72309ced527bbcfe7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582058"
---
# <a name="rem-statement-visual-basic"></a><span data-ttu-id="629f9-102">REM (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="629f9-102">REM Statement (Visual Basic)</span></span>
<span data-ttu-id="629f9-103">Se usa para incluir comentarios explicativos en el código fuente de un programa.</span><span class="sxs-lookup"><span data-stu-id="629f9-103">Used to include explanatory remarks in the source code of a program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="629f9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="629f9-104">Syntax</span></span>  
  
```vb  
REM comment  
' comment  
```  
  
## <a name="parts"></a><span data-ttu-id="629f9-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="629f9-105">Parts</span></span>  
 `comment`  
 <span data-ttu-id="629f9-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="629f9-106">Optional.</span></span> <span data-ttu-id="629f9-107">Texto de cualquier comentario que desee incluir.</span><span class="sxs-lookup"><span data-stu-id="629f9-107">The text of any comment you want to include.</span></span> <span data-ttu-id="629f9-108">Se requiere un espacio entre la palabra clave `REM` y `comment`.</span><span class="sxs-lookup"><span data-stu-id="629f9-108">A space is required between the `REM` keyword and `comment`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="629f9-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="629f9-109">Remarks</span></span>  
 <span data-ttu-id="629f9-110">Puede colocar una instrucción `REM` sola en una línea o puede colocarla en una línea después de otra instrucción.</span><span class="sxs-lookup"><span data-stu-id="629f9-110">You can put a `REM` statement alone on a line, or you can put it on a line following another statement.</span></span> <span data-ttu-id="629f9-111">La instrucción `REM` debe ser la última instrucción de la línea.</span><span class="sxs-lookup"><span data-stu-id="629f9-111">The `REM` statement must be the last statement on the line.</span></span> <span data-ttu-id="629f9-112">Si sigue otra instrucción, el `REM` debe estar separado de la instrucción por un espacio.</span><span class="sxs-lookup"><span data-stu-id="629f9-112">If it follows another statement, the `REM` must be separated from that statement by a space.</span></span>  
  
 <span data-ttu-id="629f9-113">Puede usar una comilla simple (`'`) en lugar de `REM`.</span><span class="sxs-lookup"><span data-stu-id="629f9-113">You can use a single quotation mark (`'`) instead of `REM`.</span></span> <span data-ttu-id="629f9-114">Esto es así si el comentario sigue a otra instrucción en la misma línea o solo se coloca en una línea.</span><span class="sxs-lookup"><span data-stu-id="629f9-114">This is true whether your comment follows another statement on the same line or sits alone on a line.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="629f9-115">No se puede continuar una instrucción `REM` mediante una secuencia de continuación de línea (`_`).</span><span class="sxs-lookup"><span data-stu-id="629f9-115">You cannot continue a `REM` statement by using a line-continuation sequence (`_`).</span></span> <span data-ttu-id="629f9-116">Una vez que se inicia un comentario, el compilador no examina los caracteres para un significado especial.</span><span class="sxs-lookup"><span data-stu-id="629f9-116">Once a comment begins, the compiler does not examine the characters for special meaning.</span></span> <span data-ttu-id="629f9-117">Para un Comentario de varias líneas, use otra instrucción `REM` o un símbolo de comentario (`'`) en cada línea.</span><span class="sxs-lookup"><span data-stu-id="629f9-117">For a multiple-line comment, use another `REM` statement or a comment symbol (`'`) on each line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="629f9-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="629f9-118">Example</span></span>  
 <span data-ttu-id="629f9-119">En el ejemplo siguiente se muestra la instrucción `REM`, que se usa para incluir comentarios explicativos en un programa.</span><span class="sxs-lookup"><span data-stu-id="629f9-119">The following example illustrates the `REM` statement, which is used to include explanatory remarks in a program.</span></span> <span data-ttu-id="629f9-120">También se muestra la alternativa de usar el carácter de comilla simple (`'`) en lugar de `REM`.</span><span class="sxs-lookup"><span data-stu-id="629f9-120">It also shows the alternative of using the single quotation-mark character (`'`) instead of `REM`.</span></span>  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="629f9-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="629f9-121">See also</span></span>

- [<span data-ttu-id="629f9-122">Comentarios en código</span><span class="sxs-lookup"><span data-stu-id="629f9-122">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [<span data-ttu-id="629f9-123">Interrumpir y combinar instrucciones en código</span><span class="sxs-lookup"><span data-stu-id="629f9-123">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
