---
title: Procedimiento Interrupción y combinación de instrucciones en código
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
ms.openlocfilehash: c78cbeaa5c2df2d4f2e3cce2b5b3fb8048ff3388
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403257"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a><span data-ttu-id="8d8ee-102">Cómo: Interrumpir y combinar instrucciones en código (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8d8ee-102">How to: Break and Combine Statements in Code (Visual Basic)</span></span>

<span data-ttu-id="8d8ee-103">Al escribir el código, puede crear a veces instrucciones largas que requieren un desplazamiento horizontal en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="8d8ee-103">When writing your code, you might at times create lengthy statements that necessitate horizontal scrolling in the Code Editor.</span></span> <span data-ttu-id="8d8ee-104">Aunque esto no afecta al modo en que se ejecuta el código, dificulta la lectura del código tal y como aparece en el monitor.</span><span class="sxs-lookup"><span data-stu-id="8d8ee-104">Although this doesn't affect the way your code runs, it makes it difficult for you or anyone else to read the code as it appears on the monitor.</span></span> <span data-ttu-id="8d8ee-105">En tales casos, debería considerar la posibilidad de dividir la única instrucción larga en varias líneas.</span><span class="sxs-lookup"><span data-stu-id="8d8ee-105">In such cases, you should consider breaking the single long statement into several lines.</span></span>

## <a name="to-break-a-single-statement-into-multiple-lines"></a><span data-ttu-id="8d8ee-106">Para dividir una sola instrucción en varias líneas</span><span class="sxs-lookup"><span data-stu-id="8d8ee-106">To break a single statement into multiple lines</span></span>

<span data-ttu-id="8d8ee-107">Use el carácter de continuación de línea, que es un carácter de subrayado ( `_` ), en el punto en el que desea que se interrumpa la línea.</span><span class="sxs-lookup"><span data-stu-id="8d8ee-107">Use the line-continuation character, which is an underscore (`_`), at the point at which you want the line to break.</span></span> <span data-ttu-id="8d8ee-108">El carácter de subrayado debe ir inmediatamente precedido de un espacio y seguido inmediatamente de un terminador de línea (retorno de carro) o (a partir de la versión 16,0) un comentario seguido de un retorno de carro.</span><span class="sxs-lookup"><span data-stu-id="8d8ee-108">The underscore must be immediately preceded by a space and immediately followed by a line terminator (carriage return) or (starting with version 16.0) a comment followed by a carriage return.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8d8ee-109">En algunos casos, si se omite el carácter de continuación de línea, el compilador Visual Basic continuará implícitamente la instrucción en la siguiente línea de código.</span><span class="sxs-lookup"><span data-stu-id="8d8ee-109">In some cases, if you omit the line-continuation character, the Visual Basic compiler will implicitly continue the statement on the next line of code.</span></span> <span data-ttu-id="8d8ee-110">Para obtener una lista de los elementos de sintaxis para los que puede omitir el carácter de continuación de línea, vea "continuación de línea implícita" en las [instrucciones](../language-features/statements.md).</span><span class="sxs-lookup"><span data-stu-id="8d8ee-110">For a list of syntax elements for which you can omit the line-continuation character, see "Implicit Line Continuation" in [Statements](../language-features/statements.md).</span></span>

  <span data-ttu-id="8d8ee-111">En el ejemplo siguiente, la instrucción se divide en cuatro líneas con caracteres de continuación de línea que terminan todo excepto la última línea.</span><span class="sxs-lookup"><span data-stu-id="8d8ee-111">In the following example, the statement is broken into four lines with line-continuation characters terminating all but the last line.</span></span>

  [!code-vb[VbVbcnConventions#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#20)]

  <span data-ttu-id="8d8ee-112">El uso de esta secuencia hace que el código sea más fácil de leer, tanto en línea como en el momento de su impresión.</span><span class="sxs-lookup"><span data-stu-id="8d8ee-112">Using this sequence makes your code easier to read, both online and when printed.</span></span>

  <span data-ttu-id="8d8ee-113">El carácter de continuación de línea debe ser el último carácter de una línea.</span><span class="sxs-lookup"><span data-stu-id="8d8ee-113">The line-continuation character must be the last character on a line.</span></span> <span data-ttu-id="8d8ee-114">No puede seguirlo con nada más en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="8d8ee-114">You can't follow it with anything else on the same line.</span></span>

  <span data-ttu-id="8d8ee-115">Existen algunas limitaciones en cuanto a dónde se puede usar el carácter de continuación de línea; por ejemplo, no se puede utilizar en medio de un nombre de argumento.</span><span class="sxs-lookup"><span data-stu-id="8d8ee-115">Some limitations exist as to where you can use the line-continuation character; for example, you can't use it in the middle of an argument name.</span></span> <span data-ttu-id="8d8ee-116">Puede dividir una lista de argumentos con el carácter de continuación de línea, pero los nombres individuales de los argumentos deben permanecer intactos.</span><span class="sxs-lookup"><span data-stu-id="8d8ee-116">You can break an argument list with the line-continuation character, but the individual names of the arguments must remain intact.</span></span>

  <span data-ttu-id="8d8ee-117">No se puede continuar un comentario mediante un carácter de continuación de línea.</span><span class="sxs-lookup"><span data-stu-id="8d8ee-117">You can't continue a comment by using a line-continuation character.</span></span> <span data-ttu-id="8d8ee-118">El compilador no examina los caracteres de un comentario para obtener un significado especial.</span><span class="sxs-lookup"><span data-stu-id="8d8ee-118">The compiler doesn't examine the characters in a comment for special meaning.</span></span> <span data-ttu-id="8d8ee-119">Para un Comentario de varias líneas, repita el símbolo de comentario ( `'` ) en cada línea.</span><span class="sxs-lookup"><span data-stu-id="8d8ee-119">For a multiple-line comment, repeat the comment symbol (`'`) on each line.</span></span>

 <span data-ttu-id="8d8ee-120">Aunque la colocación de cada instrucción en una línea independiente es el método recomendado, Visual Basic también permite colocar varias instrucciones en la misma línea.</span><span class="sxs-lookup"><span data-stu-id="8d8ee-120">Although placing each statement on a separate line is the recommended method, Visual Basic also allows you to place multiple statements on the same line.</span></span>

## <a name="to-place-multiple-statements-on-the-same-line"></a><span data-ttu-id="8d8ee-121">Para colocar varias instrucciones en la misma línea</span><span class="sxs-lookup"><span data-stu-id="8d8ee-121">To place multiple statements on the same line</span></span>

<span data-ttu-id="8d8ee-122">Separe las instrucciones con dos puntos ( `:` ), como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8d8ee-122">Separate the statements with a colon (`:`), as in the following example:</span></span>

  [!code-vb[VbVbcnConventions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#10)]

## <a name="see-also"></a><span data-ttu-id="8d8ee-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d8ee-123">See also</span></span>

- [<span data-ttu-id="8d8ee-124">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="8d8ee-124">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="8d8ee-125">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="8d8ee-125">Statements</span></span>](../language-features/statements.md)
