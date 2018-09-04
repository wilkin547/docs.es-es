---
title: '#If... Then... #Else directivas (Visual Basic)'
ms.date: 04/11/2018
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05aac9109e49897d1c4dbbad60d807eb3e47798d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43555136"
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="8601c-102">#If...Then...#Else (Directivas)</span><span class="sxs-lookup"><span data-stu-id="8601c-102">#If...Then...#Else Directives</span></span>
<span data-ttu-id="8601c-103">Compila condicionalmente bloques seleccionados de código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="8601c-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8601c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8601c-104">Syntax</span></span>  
  
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
  
## <a name="parts"></a><span data-ttu-id="8601c-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="8601c-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="8601c-106">Necesario para `#If` y `#ElseIf` instrucciones, opcionales en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="8601c-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="8601c-107">Cualquier expresión, que consta únicamente de uno o más constantes de compilación condicional, literales y operadores, que se evalúa como `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="8601c-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>  
  
 `statements`  
 <span data-ttu-id="8601c-108">Necesario para `#If` bloque de instrucción en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="8601c-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="8601c-109">Líneas de programa de Visual Basic o directivas de compilación que se compilan si la expresión asociada se evalúa como `True`.</span><span class="sxs-lookup"><span data-stu-id="8601c-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>  
  
 `#End If`  
 <span data-ttu-id="8601c-110">Finaliza el `#If` bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="8601c-110">Terminates the `#If` statement block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8601c-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8601c-111">Remarks</span></span>  
 <span data-ttu-id="8601c-112">En la superficie, el comportamiento de la `#If...Then...#Else` Else es el mismo que el de la `If...Then...Else` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="8601c-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="8601c-113">Sin embargo, el `#If...Then...#Else` directivas evaluación qué está compilado por el compilador, mientras que el `If...Then...Else` condiciones evalúan instrucciones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8601c-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>  
  
 <span data-ttu-id="8601c-114">Compilación condicional se utiliza normalmente para compilar el mismo programa para diferentes plataformas.</span><span class="sxs-lookup"><span data-stu-id="8601c-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="8601c-115">También se utiliza para evitar que código de depuración aparezca en un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="8601c-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="8601c-116">Código durante el proceso de compilación condicional se omite completamente en el archivo ejecutable final, por lo que no tiene ningún efecto en el tamaño o rendimiento.</span><span class="sxs-lookup"><span data-stu-id="8601c-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>  
  
 <span data-ttu-id="8601c-117">Independientemente del resultado de la evaluación, todas las expresiones se evalúan mediante `Option Compare Binary`.</span><span class="sxs-lookup"><span data-stu-id="8601c-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="8601c-118">El `Option Compare` instrucción no afecta a las expresiones de `#If` y `#ElseIf` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="8601c-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8601c-119">No hay forma de una línea de la `#If`, `#Else`, `#ElseIf`, y `#End If` directivas existe.</span><span class="sxs-lookup"><span data-stu-id="8601c-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="8601c-120">Ningún otro código puede aparecer en la misma línea que ninguna de las directivas.</span><span class="sxs-lookup"><span data-stu-id="8601c-120">No other code can appear on the same line as any of the directives.</span></span> 

<span data-ttu-id="8601c-121">Las instrucciones dentro de un bloque de compilación condicional deben ser completa lógico.</span><span class="sxs-lookup"><span data-stu-id="8601c-121">The statements within a conditional compilation block must be complete logical statements.</span></span> <span data-ttu-id="8601c-122">Por ejemplo, no se puede compilar condicionalmente solo los atributos de una función, pero condicionalmente puede declarar la función junto con sus atributos:</span><span class="sxs-lookup"><span data-stu-id="8601c-122">For example, you cannot conditionally compile only the attributes of a function, but you can conditionally declare the function along with its attributes:</span></span>

```vb
   #If DEBUG Then
   <WebMethod()>
   Public Function SomeFunction() As String
   #Else
   <WebMethod(CacheDuration:=86400)>
   Public Function SomeFunction() As String
   #End If
```

## <a name="example"></a><span data-ttu-id="8601c-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8601c-123">Example</span></span>
 <span data-ttu-id="8601c-124">Este ejemplo se usa el `#If...Then...#Else` construcción para determinar si se debe compilar ciertas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="8601c-124">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8601c-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="8601c-125">See Also</span></span>  
[<span data-ttu-id="8601c-126">#Const (directiva)</span><span class="sxs-lookup"><span data-stu-id="8601c-126">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
[<span data-ttu-id="8601c-127">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8601c-127">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
<span data-ttu-id="8601c-128">[Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span><span class="sxs-lookup"><span data-stu-id="8601c-128">[Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span></span>  
<xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>   


