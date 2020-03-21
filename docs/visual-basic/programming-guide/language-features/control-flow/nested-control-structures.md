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
ms.openlocfilehash: b696c79cd3cada4416b3f4b6cdf96f00b89a5a0a
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266929"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="2592d-102">Estructuras de control anidadas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2592d-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="2592d-103">Puede colocar instrucciones de control dentro de otras `If...Then...Else` instrucciones `For...Next` de control, por ejemplo, un bloque dentro de un bucle.</span><span class="sxs-lookup"><span data-stu-id="2592d-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="2592d-104">Se dice que una instrucción de control colocada dentro de otra instrucción de control está *anidada.*</span><span class="sxs-lookup"><span data-stu-id="2592d-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="2592d-105">Niveles de anidación</span><span class="sxs-lookup"><span data-stu-id="2592d-105">Nesting Levels</span></span>  
 <span data-ttu-id="2592d-106">Las estructuras de control de Visual Basic se pueden anidar en tantos niveles como desee.</span><span class="sxs-lookup"><span data-stu-id="2592d-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="2592d-107">Es una práctica común hacer que las estructuras anidadas sean más legibles mediante la sangría del cuerpo de cada una.</span><span class="sxs-lookup"><span data-stu-id="2592d-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="2592d-108">El editor de entorno de desarrollo integrado (IDE) lo hace automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2592d-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="2592d-109">En el ejemplo siguiente, el procedimiento `sumRows` suma los elementos positivos de cada fila de la matriz.</span><span class="sxs-lookup"><span data-stu-id="2592d-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="2592d-110">En el ejemplo anterior, `Next` la primera `For` instrucción cierra `Next` el bucle `For` interno y la última instrucción cierra el bucle externo.</span><span class="sxs-lookup"><span data-stu-id="2592d-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="2592d-111">Del mismo modo, en las instrucciones anidadas, `If` las `End If` instrucciones se aplican automáticamente a la instrucción anterior `If` más cercana.</span><span class="sxs-lookup"><span data-stu-id="2592d-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="2592d-112">Los `Do` bucles anidados funcionan de forma `Loop` similar, con `Do` la instrucción más interna que coincide con la instrucción más interna.</span><span class="sxs-lookup"><span data-stu-id="2592d-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2592d-113">Para muchas estructuras de control, al hacer clic en una palabra clave, se resaltan todas las palabras clave de la estructura.</span><span class="sxs-lookup"><span data-stu-id="2592d-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="2592d-114">Por ejemplo, al `If` hacer `If...Then...Else` clic en una `If` `Then`construcción, se resaltan todas las instancias de , , `ElseIf` `Else`, y `End If` en la construcción.</span><span class="sxs-lookup"><span data-stu-id="2592d-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="2592d-115">Para pasar a la palabra clave resaltada siguiente o anterior, presione CTRL+MAYO+FLECHA ABAJO o CTRL+MAYO+FLECHA ARRIBA.</span><span class="sxs-lookup"><span data-stu-id="2592d-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="2592d-116">Anidar diferentes tipos de estructuras de control</span><span class="sxs-lookup"><span data-stu-id="2592d-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="2592d-117">Puede anidar un tipo de estructura de control dentro de otro tipo.</span><span class="sxs-lookup"><span data-stu-id="2592d-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="2592d-118">En el ejemplo `With` siguiente `For Each` se utiliza `If` un `With` bloque dentro de un bucle y bloques anidados dentro del bloque.</span><span class="sxs-lookup"><span data-stu-id="2592d-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="2592d-119">Estructuras de control superpuestas</span><span class="sxs-lookup"><span data-stu-id="2592d-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="2592d-120">No se pueden superponer estructuras de control.</span><span class="sxs-lookup"><span data-stu-id="2592d-120">You cannot overlap control structures.</span></span> <span data-ttu-id="2592d-121">Esto significa que cualquier estructura anidada debe estar completamente contenida dentro de la siguiente estructura más interna.</span><span class="sxs-lookup"><span data-stu-id="2592d-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="2592d-122">Por ejemplo, la siguiente disposición no es válida porque el `For` bucle finaliza antes de que finalice el bloque interno. `With`</span><span class="sxs-lookup"><span data-stu-id="2592d-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![Diagrama que muestra un ejemplo de anidamiento no válido.](./media/nested-control-structures/example-invalid-nesting.gif)
  
 <span data-ttu-id="2592d-124">El compilador de Visual Basic detecta estas estructuras de control superpuestas y señala un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="2592d-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2592d-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2592d-125">See also</span></span>

- [<span data-ttu-id="2592d-126">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="2592d-126">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="2592d-127">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="2592d-127">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="2592d-128">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="2592d-128">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="2592d-129">Estructuras de control adicionales</span><span class="sxs-lookup"><span data-stu-id="2592d-129">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
