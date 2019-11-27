---
title: Estructuras de control anidadas
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
ms.openlocfilehash: 5818b13661fb4415c6f531b741b8a963a80bd2b8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348150"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="3d0cd-102">Estructuras de control anidadas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d0cd-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="3d0cd-103">Puede colocar instrucciones de control dentro de otras instrucciones de control, por ejemplo, un bloque `If...Then...Else` dentro de un bucle `For...Next`.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="3d0cd-104">Una instrucción de control colocada dentro de otra instrucción de control se dice que está *anidada*.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="3d0cd-105">Niveles de anidamiento</span><span class="sxs-lookup"><span data-stu-id="3d0cd-105">Nesting Levels</span></span>  
 <span data-ttu-id="3d0cd-106">Las estructuras de control de Visual Basic se pueden anidar hasta tantos niveles como se desee.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="3d0cd-107">Es habitual que las estructuras anidadas sean más legibles mediante la sangría del cuerpo de cada una.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="3d0cd-108">El editor del entorno de desarrollo integrado (IDE) lo hace automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="3d0cd-109">En el ejemplo siguiente, el procedimiento `sumRows` agrega juntos los elementos positivos de cada fila de la matriz.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
```vb
Public Sub sumRows(ByVal a(,) As Double, ByRef r() As Double)  
    Dim i, j As Integer  
    For i = 0 To UBound(a, 1)  
        r(i) = 0  
        For j = 0 To UBound(a, 2)  
            If a(i, j) > 0 Then  
                r(i) = r(i) + a(i, j)  
            End If  
        Next j  
    Next i  
End Sub  
```  
  
 <span data-ttu-id="3d0cd-110">En el ejemplo anterior, la primera instrucción `Next` cierra el bucle de `For` interno y la última instrucción `Next` cierra el bucle de `For` externo.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="3d0cd-111">Del mismo modo, en las instrucciones `If` anidadas, las instrucciones de `End If` se aplican automáticamente a la instrucción de `If` anterior más cercana.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="3d0cd-112">Los bucles `Do` anidados funcionan de manera similar, con la instrucción de `Loop` más interna que coincide con la instrucción de `Do` más interna.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d0cd-113">En el caso de muchas estructuras de control, al hacer clic en una palabra clave, se resaltan todas las palabras clave de la estructura.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="3d0cd-114">Por ejemplo, al hacer clic en `If` en una construcción de `If...Then...Else`, se resaltan todas las instancias de `If`, `Then`, `ElseIf`, `Else`y `End If` de la construcción.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="3d0cd-115">Para desplazarse a la palabra clave resaltada siguiente o anterior, presione CTRL + MAYÚS + flecha abajo o CTRL + MAYÚS + flecha arriba.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="3d0cd-116">Anidar distintos tipos de estructuras de control</span><span class="sxs-lookup"><span data-stu-id="3d0cd-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="3d0cd-117">Puede anidar un tipo de estructura de control dentro de otro tipo.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="3d0cd-118">En el ejemplo siguiente se usa un bloque `With` dentro de un bucle de `For Each` y bloques de `If` anidados dentro del bloque de `With`.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
```vb
For Each ctl As System.Windows.Forms.Control In Me.Controls  
    With ctl  
        .BackColor = System.Drawing.Color.Yellow  
        .ForeColor = System.Drawing.Color.Black  
        If .CanFocus Then  
            .Text = "Colors changed"  
            If Not .Focus() Then  
                ' Insert code to process failed focus.  
            End If  
        End If  
    End With  
Next ctl  
```  
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="3d0cd-119">Estructuras de control superpuestas</span><span class="sxs-lookup"><span data-stu-id="3d0cd-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="3d0cd-120">No se pueden superponer estructuras de control.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-120">You cannot overlap control structures.</span></span> <span data-ttu-id="3d0cd-121">Esto significa que cualquier estructura anidada debe estar contenida completamente dentro de la siguiente estructura más interna.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="3d0cd-122">Por ejemplo, la siguiente disposición no es válida porque el bucle `For` finaliza antes de que finalice el bloque de `With` interno.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![Diagrama que muestra un ejemplo de anidación no válida.](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 <span data-ttu-id="3d0cd-124">El compilador Visual Basic detecta esas estructuras de control superpuestas y señala un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="3d0cd-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d0cd-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d0cd-125">See also</span></span>

- [<span data-ttu-id="3d0cd-126">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="3d0cd-126">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="3d0cd-127">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="3d0cd-127">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="3d0cd-128">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="3d0cd-128">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="3d0cd-129">Estructuras de control adicionales</span><span class="sxs-lookup"><span data-stu-id="3d0cd-129">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
