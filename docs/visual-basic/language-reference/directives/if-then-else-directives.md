---
title: '#<a name="ifthenelse-directives"></a>If... Then... #Else directivas'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 77757e441ae937aa86122f237e839d1005644409
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="c68f3-102">#If...Then...#Else (Directivas)</span><span class="sxs-lookup"><span data-stu-id="c68f3-102">#If...Then...#Else Directives</span></span>
<span data-ttu-id="c68f3-103">Compila condicionalmente bloques de código de Visual Basic seleccionados.</span><span class="sxs-lookup"><span data-stu-id="c68f3-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c68f3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c68f3-104">Syntax</span></span>  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## <a name="parts"></a><span data-ttu-id="c68f3-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="c68f3-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="c68f3-106">Necesario para `#If` y `#ElseIf` instrucciones, opcionales en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="c68f3-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="c68f3-107">Cualquier expresión, que consta únicamente de una o más constantes de compilación condicional, literales y operadores, que se evalúa como `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="c68f3-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>  
  
 `statements`  
 <span data-ttu-id="c68f3-108">Necesario para `#If` bloque de instrucción, opcional en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="c68f3-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="c68f3-109">Líneas de programa de Visual Basic o directivas de compilación que se compilan si la expresión asociada se evalúa como `True`.</span><span class="sxs-lookup"><span data-stu-id="c68f3-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>  
  
 `#End If`  
 <span data-ttu-id="c68f3-110">Finaliza el `#If` bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="c68f3-110">Terminates the `#If` statement block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c68f3-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c68f3-111">Remarks</span></span>  
 <span data-ttu-id="c68f3-112">En la superficie, el comportamiento de la `#If...Then...#Else` Else es el mismo que el de la `If...Then...Else` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="c68f3-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="c68f3-113">Sin embargo, el `#If...Then...#Else` Else evalúan lo que compila el compilador, mientras que la `If...Then...Else` instrucciones evalúan las condiciones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c68f3-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>  
  
 <span data-ttu-id="c68f3-114">Compilación condicional se utiliza normalmente para compilar el mismo programa para diferentes plataformas.</span><span class="sxs-lookup"><span data-stu-id="c68f3-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="c68f3-115">También se utiliza para evitar que código de depuración aparezca en un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="c68f3-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="c68f3-116">Código excluido durante la compilación condicional se omite por completo desde el archivo ejecutable final, por lo que no tiene ningún efecto en el tamaño o el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="c68f3-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>  
  
 <span data-ttu-id="c68f3-117">Independientemente del resultado de la evaluación, todas las expresiones se evalúan utilizando `Option Compare Binary`.</span><span class="sxs-lookup"><span data-stu-id="c68f3-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="c68f3-118">El `Option Compare` instrucción no afecta a las expresiones en `#If` y `#ElseIf` las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="c68f3-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c68f3-119">No hay ningún formulario de línea de la `#If`, `#Else`, `#ElseIf`, y `#End If` directivas existe.</span><span class="sxs-lookup"><span data-stu-id="c68f3-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="c68f3-120">Ningún otro código puede aparecer en la misma línea que cualquiera de las directivas.</span><span class="sxs-lookup"><span data-stu-id="c68f3-120">No other code can appear on the same line as any of the directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c68f3-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c68f3-121">Example</span></span>  
 <span data-ttu-id="c68f3-122">Este ejemplo se utiliza la `#If...Then...#Else` construcción para determinar si se compilan ciertas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="c68f3-122">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c68f3-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c68f3-123">See Also</span></span>  
 [<span data-ttu-id="c68f3-124">#Const (directiva)</span><span class="sxs-lookup"><span data-stu-id="c68f3-124">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
 [<span data-ttu-id="c68f3-125">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="c68f3-125">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="c68f3-126">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="c68f3-126">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
