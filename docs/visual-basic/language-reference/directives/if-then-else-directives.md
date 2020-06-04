---
title: '#Directivas If...Then...#Else'
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
ms.openlocfilehash: 7054a6ada4583c5d89e020437eb622a59d3eb17a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410015"
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="fdff0-102">#If...Then...#Else (Directivas)</span><span class="sxs-lookup"><span data-stu-id="fdff0-102">#If...Then...#Else Directives</span></span>

<span data-ttu-id="fdff0-103">Compila condicionalmente bloques seleccionados de código Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fdff0-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>

## <a name="syntax"></a><span data-ttu-id="fdff0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdff0-104">Syntax</span></span>

```vb
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

## <a name="parts"></a><span data-ttu-id="fdff0-105">Partes</span><span class="sxs-lookup"><span data-stu-id="fdff0-105">Parts</span></span>

`expression`  
<span data-ttu-id="fdff0-106">Necesario para `#If` las `#ElseIf` instrucciones y, opcional en cualquier otro lugar.</span><span class="sxs-lookup"><span data-stu-id="fdff0-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="fdff0-107">Cualquier expresión, que consta exclusivamente de una o varias constantes, literales y operadores del compilador condicionales, que se evalúa como `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="fdff0-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>

`statements`  
<span data-ttu-id="fdff0-108">Requerido para el `#If` bloque de instrucciones, opcional en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="fdff0-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="fdff0-109">Visual Basic líneas de programa o directivas de compilador que se compilan si la expresión asociada se evalúa como `True` .</span><span class="sxs-lookup"><span data-stu-id="fdff0-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>

`#End If`  
<span data-ttu-id="fdff0-110">Finaliza el `#If` bloque de instrucciones.</span><span class="sxs-lookup"><span data-stu-id="fdff0-110">Terminates the `#If` statement block.</span></span>

## <a name="remarks"></a><span data-ttu-id="fdff0-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fdff0-111">Remarks</span></span>

<span data-ttu-id="fdff0-112">En la superficie, el comportamiento de las `#If...Then...#Else` directivas aparece igual que el de las `If...Then...Else` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="fdff0-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="fdff0-113">Sin embargo, las `#If...Then...#Else` directivas evalúan lo que compila el compilador, mientras que las `If...Then...Else` instrucciones evalúan las condiciones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fdff0-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>

<span data-ttu-id="fdff0-114">La compilación condicional se usa normalmente para compilar el mismo programa para distintas plataformas.</span><span class="sxs-lookup"><span data-stu-id="fdff0-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="fdff0-115">También se usa para evitar que el código de depuración aparezca en un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="fdff0-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="fdff0-116">El código excluido durante la compilación condicional se omite completamente del archivo ejecutable final, por lo que no tiene ningún efecto en el tamaño o el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fdff0-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>

<span data-ttu-id="fdff0-117">Independientemente del resultado de cualquier evaluación, todas las expresiones se evalúan utilizando `Option Compare Binary` .</span><span class="sxs-lookup"><span data-stu-id="fdff0-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="fdff0-118">La `Option Compare` instrucción no afecta a las expresiones de las `#If` `#ElseIf` instrucciones y.</span><span class="sxs-lookup"><span data-stu-id="fdff0-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>

> [!NOTE]
> <span data-ttu-id="fdff0-119">No existe ninguna forma de una línea de las `#If` `#Else` directivas,, `#ElseIf` y `#End If` .</span><span class="sxs-lookup"><span data-stu-id="fdff0-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="fdff0-120">No puede aparecer ningún otro código en la misma línea que ninguna de las directivas.</span><span class="sxs-lookup"><span data-stu-id="fdff0-120">No other code can appear on the same line as any of the directives.</span></span>

<span data-ttu-id="fdff0-121">Las instrucciones de un bloque de compilación condicional deben ser instrucciones lógicas completas.</span><span class="sxs-lookup"><span data-stu-id="fdff0-121">The statements within a conditional compilation block must be complete logical statements.</span></span> <span data-ttu-id="fdff0-122">Por ejemplo, no puede compilar condicionalmente solo los atributos de una función, pero puede declarar condicionalmente la función junto con sus atributos:</span><span class="sxs-lookup"><span data-stu-id="fdff0-122">For example, you cannot conditionally compile only the attributes of a function, but you can conditionally declare the function along with its attributes:</span></span>

```vb
#If DEBUG Then
<WebMethod()>
Public Function SomeFunction() As String
#Else
<WebMethod(CacheDuration:=86400)>
Public Function SomeFunction() As String
#End If
```

## <a name="example"></a><span data-ttu-id="fdff0-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdff0-123">Example</span></span>

<span data-ttu-id="fdff0-124">En este ejemplo se usa la `#If...Then...#Else` construcción para determinar si se deben compilar ciertas instrucciones.</span><span class="sxs-lookup"><span data-stu-id="fdff0-124">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>

[!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]

## <a name="see-also"></a><span data-ttu-id="fdff0-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fdff0-125">See also</span></span>

- [<span data-ttu-id="fdff0-126">#Const (directiva)</span><span class="sxs-lookup"><span data-stu-id="fdff0-126">#Const Directive</span></span>](const-directive.md)
- [<span data-ttu-id="fdff0-127">Instrucción If...Then...Else</span><span class="sxs-lookup"><span data-stu-id="fdff0-127">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
- [<span data-ttu-id="fdff0-128">Compilación condicional</span><span class="sxs-lookup"><span data-stu-id="fdff0-128">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
