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
ms.openlocfilehash: 8c0aece749edf144fdd5c8ede9ec7e2e4c96ad54
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58823394"
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="1c070-102">#If...Then...#Else (Directivas)</span><span class="sxs-lookup"><span data-stu-id="1c070-102">#If...Then...#Else Directives</span></span>
<span data-ttu-id="1c070-103">Compila condicionalmente bloques seleccionados de código de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1c070-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c070-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c070-104">Syntax</span></span>  
  
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
  
## <a name="parts"></a><span data-ttu-id="1c070-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="1c070-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="1c070-106">Necesario para `#If` y `#ElseIf` instrucciones, opcionales en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="1c070-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="1c070-107">Cualquier expresión, que consta únicamente de uno o más constantes de compilación condicional, literales y operadores, que se evalúa como `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="1c070-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>  
  
 `statements`  
 <span data-ttu-id="1c070-108">Necesario para `#If` bloque de instrucción en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="1c070-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="1c070-109">Líneas de programa de Visual Basic o directivas de compilación que se compilan si la expresión asociada se evalúa como `True`.</span><span class="sxs-lookup"><span data-stu-id="1c070-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>  
  
 `#End If`  
 <span data-ttu-id="1c070-110">Finaliza el `#If` bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="1c070-110">Terminates the `#If` statement block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c070-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c070-111">Remarks</span></span>  
 <span data-ttu-id="1c070-112">En la superficie, el comportamiento de la `#If...Then...#Else` Else es el mismo que el de la `If...Then...Else` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="1c070-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="1c070-113">Sin embargo, el `#If...Then...#Else` directivas evaluación qué está compilado por el compilador, mientras que el `If...Then...Else` condiciones evalúan instrucciones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1c070-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>  
  
 <span data-ttu-id="1c070-114">Compilación condicional se utiliza normalmente para compilar el mismo programa para diferentes plataformas.</span><span class="sxs-lookup"><span data-stu-id="1c070-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="1c070-115">También se utiliza para evitar que código de depuración aparezca en un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="1c070-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="1c070-116">Código durante el proceso de compilación condicional se omite completamente en el archivo ejecutable final, por lo que no tiene ningún efecto en el tamaño o rendimiento.</span><span class="sxs-lookup"><span data-stu-id="1c070-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>  
  
 <span data-ttu-id="1c070-117">Independientemente del resultado de la evaluación, todas las expresiones se evalúan mediante `Option Compare Binary`.</span><span class="sxs-lookup"><span data-stu-id="1c070-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="1c070-118">El `Option Compare` instrucción no afecta a las expresiones de `#If` y `#ElseIf` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="1c070-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c070-119">No hay forma de una línea de la `#If`, `#Else`, `#ElseIf`, y `#End If` directivas existe.</span><span class="sxs-lookup"><span data-stu-id="1c070-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="1c070-120">Ningún otro código puede aparecer en la misma línea que ninguna de las directivas.</span><span class="sxs-lookup"><span data-stu-id="1c070-120">No other code can appear on the same line as any of the directives.</span></span> 

<span data-ttu-id="1c070-121">Las instrucciones dentro de un bloque de compilación condicional deben ser completa lógico.</span><span class="sxs-lookup"><span data-stu-id="1c070-121">The statements within a conditional compilation block must be complete logical statements.</span></span> <span data-ttu-id="1c070-122">Por ejemplo, no se puede compilar condicionalmente solo los atributos de una función, pero condicionalmente puede declarar la función junto con sus atributos:</span><span class="sxs-lookup"><span data-stu-id="1c070-122">For example, you cannot conditionally compile only the attributes of a function, but you can conditionally declare the function along with its attributes:</span></span>

```vb
   #If DEBUG Then
   <WebMethod()>
   Public Function SomeFunction() As String
   #Else
   <WebMethod(CacheDuration:=86400)>
   Public Function SomeFunction() As String
   #End If
```

## <a name="example"></a><span data-ttu-id="1c070-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1c070-123">Example</span></span>
 <span data-ttu-id="1c070-124">Este ejemplo se usa el `#If...Then...#Else` construcción para determinar si se debe compilar ciertas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="1c070-124">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1c070-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c070-125">See also</span></span>

- [<span data-ttu-id="1c070-126">#Const (directiva)</span><span class="sxs-lookup"><span data-stu-id="1c070-126">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)
- [<span data-ttu-id="1c070-127">If...Then...Else (instrucción)</span><span class="sxs-lookup"><span data-stu-id="1c070-127">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="1c070-128">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="1c070-128">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
