---
title: Procedimiento Contracción y ocultación de secciones de código
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, code collapsing
- Visual Basic, code hiding
- Visual Basic code, collapsing and hiding
ms.assetid: b770e8f5-e07d-491a-ab4b-a977980f9ba2
ms.openlocfilehash: c11affe9c4dd4251ba8ff4b87029d314970b5fcb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404854"
---
# <a name="how-to-collapse-and-hide-sections-of-code-visual-basic"></a><span data-ttu-id="b6b8e-102">Cómo: Contraer y ocultar secciones de código (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b6b8e-102">How to: Collapse and Hide Sections of Code (Visual Basic)</span></span>

<span data-ttu-id="b6b8e-103">La `#Region` directiva permite contraer y ocultar secciones de código en archivos de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b6b8e-103">The `#Region` directive enables you to collapse and hide sections of code in Visual Basic files.</span></span> <span data-ttu-id="b6b8e-104">La `#Region` directiva permite especificar un bloque de código que se puede expandir o contraer cuando se usa el editor de código de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b6b8e-104">The `#Region` directive lets you specify a block of code that you can expand or collapse when using the Visual Studio code editor.</span></span> <span data-ttu-id="b6b8e-105">La capacidad de ocultar el código de forma selectiva facilita la administración y la lectura de los archivos.</span><span class="sxs-lookup"><span data-stu-id="b6b8e-105">The ability to hide code selectively makes your files more manageable and easier to read.</span></span> <span data-ttu-id="b6b8e-106">Para obtener más información, vea [Esquematización](/visualstudio/ide/outlining).</span><span class="sxs-lookup"><span data-stu-id="b6b8e-106">For more information, see [Outlining](/visualstudio/ide/outlining).</span></span>

<span data-ttu-id="b6b8e-107">`#Region`las directivas admiten la semántica de bloques de código como `#If...#End If` .</span><span class="sxs-lookup"><span data-stu-id="b6b8e-107">`#Region` directives support code block semantics such as `#If...#End If`.</span></span> <span data-ttu-id="b6b8e-108">Esto significa que no pueden comenzar en un bloque y finalizar en otro; el inicio y el final deben estar en el mismo bloque.</span><span class="sxs-lookup"><span data-stu-id="b6b8e-108">This means they cannot begin in one block and end in another; the start and end must be in the same block.</span></span> <span data-ttu-id="b6b8e-109">`#Region`no se admiten directivas en las funciones.</span><span class="sxs-lookup"><span data-stu-id="b6b8e-109">`#Region` directives are not supported within functions.</span></span>

## <a name="to-collapse-and-hide-a-section-of-code"></a><span data-ttu-id="b6b8e-110">Para contraer y ocultar una sección de código</span><span class="sxs-lookup"><span data-stu-id="b6b8e-110">To collapse and hide a section of code</span></span>

<span data-ttu-id="b6b8e-111">Coloque la sección de código entre las `#Region` `#End Region` instrucciones y, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b6b8e-111">Place the section of code between the `#Region` and `#End Region` statements, as in the following example:</span></span>

[!code-vb[VbVbalrConditionalComp#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#6)]

<span data-ttu-id="b6b8e-112">El `#Region` bloque se puede usar varias veces en un archivo de código; por lo tanto, los usuarios pueden definir sus propios bloques de procedimientos y clases que, a su vez, se pueden contraer.</span><span class="sxs-lookup"><span data-stu-id="b6b8e-112">The `#Region` block can be used multiple times in a code file; thus, users can define their own blocks of procedures and classes that can, in turn, be collapsed.</span></span> <span data-ttu-id="b6b8e-113">`#Region`los bloques también se pueden anidar dentro de otros `#Region` bloques.</span><span class="sxs-lookup"><span data-stu-id="b6b8e-113">`#Region` blocks can also be nested within other `#Region` blocks.</span></span>

> [!NOTE]
> <span data-ttu-id="b6b8e-114">Ocultar código no impide que se compile y no afecta a las `#If...#End If` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="b6b8e-114">Hiding code does not prevent it from being compiled and does not affect `#If...#End If` statements.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6b8e-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6b8e-115">See also</span></span>

- [<span data-ttu-id="b6b8e-116">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="b6b8e-116">Conditional Compilation</span></span>](conditional-compilation.md)
- [<span data-ttu-id="b6b8e-117">#Region (Directiva)</span><span class="sxs-lookup"><span data-stu-id="b6b8e-117">#Region Directive</span></span>](../../language-reference/directives/region-directive.md)
- [<span data-ttu-id="b6b8e-118">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="b6b8e-118">#If...Then...#Else Directives</span></span>](../../language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="b6b8e-119">esquematizar</span><span class="sxs-lookup"><span data-stu-id="b6b8e-119">Outlining</span></span>](/visualstudio/ide/outlining)
