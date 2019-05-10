---
title: Procedimiento Interrumpir y combinar instrucciones en código (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb._
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores [Visual Basic], in code
- statements [Visual Basic], line continuation in
- line breaks [Visual Basic], in code
- line-continuation character [Visual Basic]
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
ms.openlocfilehash: d3656b924ebaca67c90dc602701c4cef9ce088b4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648789"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="2c95f-102">Procedimiento Interrumpir y combinar instrucciones en código (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c95f-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>
<span data-ttu-id="2c95f-103">Al escribir el código, a veces puede crear instrucciones largas que requieren un desplazamiento horizontal en el Editor de código.</span><span class="sxs-lookup"><span data-stu-id="2c95f-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="2c95f-104">Aunque esto no afecta a la forma se ejecuta el código, resulta difícil para que usted u otra persona leer el código tal y como aparece en el monitor.</span><span class="sxs-lookup"><span data-stu-id="2c95f-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="2c95f-105">En tales casos, considere la posibilidad de dividir la única instrucción larga en varias líneas.</span><span class="sxs-lookup"><span data-stu-id="2c95f-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="2c95f-106">Para dividir una única instrucción en varias líneas</span><span class="sxs-lookup"><span data-stu-id="2c95f-106">To break a single statement into multiple lines</span></span>  
  
- <span data-ttu-id="2c95f-107">Usar el carácter de continuación de línea, que es un carácter de subrayado (`_`), en el punto en el que desea que el salto de línea.</span><span class="sxs-lookup"><span data-stu-id="2c95f-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="2c95f-108">El carácter de subrayado debe tener inmediatamente antes un espacio e inmediatamente después un terminador de línea (retorno de carro).</span><span class="sxs-lookup"><span data-stu-id="2c95f-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c95f-109">En algunos casos, si se omite el carácter de continuación de línea, el compilador de Visual Basic implícitamente continuará, en la siguiente línea de código, la instrucción.</span><span class="sxs-lookup"><span data-stu-id="2c95f-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="2c95f-110">Para obtener una lista de elementos de sintaxis para el que puede omitir el carácter de continuación de línea, vea "Continuación de línea implícita" en [instrucciones](../../../visual-basic/programming-guide/language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="2c95f-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
     <span data-ttu-id="2c95f-111">En el ejemplo siguiente, la instrucción se divide en cuatro líneas con caracteres de continuación de línea final de todas excepto la última línea.</span><span class="sxs-lookup"><span data-stu-id="2c95f-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>  
  
     [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]  
  
     <span data-ttu-id="2c95f-112">Con esta secuencia hace que el código más fácil de leer, tanto en línea como al imprimirlo.</span><span class="sxs-lookup"><span data-stu-id="2c95f-112">Using this sequence makes your code easier to read, both online and when printed.</span></span>  
  
     <span data-ttu-id="2c95f-113">El carácter de continuación de línea debe ser el último carácter de una línea.</span><span class="sxs-lookup"><span data-stu-id="2c95f-113">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="2c95f-114">No puede seguir con cualquier otra cosa en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="2c95f-114">You can't follow it with anything else on the same line.</span></span>  
  
     <span data-ttu-id="2c95f-115">Existen algunas limitaciones sobre dónde puede usar el carácter de continuación de línea; Por ejemplo, no puede usar en el medio de un nombre de argumento.</span><span class="sxs-lookup"><span data-stu-id="2c95f-115">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="2c95f-116">Puede interrumpir una lista de argumentos con el carácter de continuación de línea, pero los nombres individuales de los argumentos deben permanecer intactos.</span><span class="sxs-lookup"><span data-stu-id="2c95f-116">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>  
  
     <span data-ttu-id="2c95f-117">No puede continuar un comentario mediante el uso de un carácter de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="2c95f-117">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="2c95f-118">El compilador no examina los caracteres de un comentario para un significado especial.</span><span class="sxs-lookup"><span data-stu-id="2c95f-118">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="2c95f-119">Para un comentario de varias líneas, repita el símbolo de comentario (`'`) en cada línea.</span><span class="sxs-lookup"><span data-stu-id="2c95f-119">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>  
  
 <span data-ttu-id="2c95f-120">Aunque el método recomendado consiste en colocar cada instrucción en una línea independiente, Visual Basic también permite colocar varias instrucciones en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="2c95f-120">Although placing each statement on a separate line is the recommended method, Visual Basic also allows you to place multiple statements on the same line.</span></span>  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="2c95f-121">Colocar varias instrucciones en la misma línea</span><span class="sxs-lookup"><span data-stu-id="2c95f-121">To place multiple statements on the same line</span></span>  
  
- <span data-ttu-id="2c95f-122">Separe las instrucciones con un signo de dos puntos (`:`), como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2c95f-122">Separate the statements with a colon (`:`), as in the following example.</span></span>  
  
     [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="2c95f-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c95f-123">See also</span></span>

- [<span data-ttu-id="2c95f-124">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="2c95f-124">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="2c95f-125">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="2c95f-125">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
