---
description: 'Más información sobre: estructuras de control anidadas (Visual Basic)'
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
ms.openlocfilehash: 086e1201cab3ea133b01a003de58f8d3e67bfc44
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100473607"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="906ff-103">Estructuras de control anidadas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="906ff-103">Nested Control Structures (Visual Basic)</span></span>

<span data-ttu-id="906ff-104">Puede colocar instrucciones de control dentro de otras instrucciones de control, por ejemplo, un `If...Then...Else` bloque dentro de un `For...Next` bucle.</span><span class="sxs-lookup"><span data-stu-id="906ff-104">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="906ff-105">Una instrucción de control colocada dentro de otra instrucción de control se dice que está *anidada*.</span><span class="sxs-lookup"><span data-stu-id="906ff-105">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="906ff-106">Niveles de anidamiento</span><span class="sxs-lookup"><span data-stu-id="906ff-106">Nesting Levels</span></span>  

 <span data-ttu-id="906ff-107">Las estructuras de control de Visual Basic se pueden anidar hasta tantos niveles como se desee.</span><span class="sxs-lookup"><span data-stu-id="906ff-107">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="906ff-108">Es habitual que las estructuras anidadas sean más legibles mediante la sangría del cuerpo de cada una.</span><span class="sxs-lookup"><span data-stu-id="906ff-108">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="906ff-109">El editor del entorno de desarrollo integrado (IDE) lo hace automáticamente.</span><span class="sxs-lookup"><span data-stu-id="906ff-109">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="906ff-110">En el ejemplo siguiente, el procedimiento `sumRows` suma los elementos positivos de cada fila de la matriz.</span><span class="sxs-lookup"><span data-stu-id="906ff-110">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="906ff-111">En el ejemplo anterior, la primera `Next` instrucción cierra el bucle interno `For` y la última `Next` instrucción cierra el `For` bucle externo.</span><span class="sxs-lookup"><span data-stu-id="906ff-111">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="906ff-112">Del mismo modo, en `If` las instrucciones anidadas, las `End If` instrucciones se aplican automáticamente a la instrucción anterior más cercana `If` .</span><span class="sxs-lookup"><span data-stu-id="906ff-112">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="906ff-113">`Do`Los bucles anidados funcionan de manera similar, con la instrucción más interna `Loop` que coincide con la instrucción más interna `Do` .</span><span class="sxs-lookup"><span data-stu-id="906ff-113">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="906ff-114">En el caso de muchas estructuras de control, al hacer clic en una palabra clave, se resaltan todas las palabras clave de la estructura.</span><span class="sxs-lookup"><span data-stu-id="906ff-114">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="906ff-115">Por ejemplo, al hacer clic `If` en en una `If...Then...Else` construcción, `If` se resaltan todas las instancias de,,, `Then` `ElseIf` `Else` y `End If` en la construcción.</span><span class="sxs-lookup"><span data-stu-id="906ff-115">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="906ff-116">Para desplazarse a la palabra clave resaltada siguiente o anterior, presione CTRL + MAYÚS + flecha abajo o CTRL + MAYÚS + flecha arriba.</span><span class="sxs-lookup"><span data-stu-id="906ff-116">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="906ff-117">Anidar distintos tipos de estructuras de control</span><span class="sxs-lookup"><span data-stu-id="906ff-117">Nesting Different Kinds of Control Structures</span></span>  

 <span data-ttu-id="906ff-118">Puede anidar un tipo de estructura de control dentro de otro tipo.</span><span class="sxs-lookup"><span data-stu-id="906ff-118">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="906ff-119">En el ejemplo siguiente se usa un `With` bloque dentro de un `For Each` bucle y bloques anidados `If` dentro del `With` bloque.</span><span class="sxs-lookup"><span data-stu-id="906ff-119">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="906ff-120">Estructuras de control superpuestas</span><span class="sxs-lookup"><span data-stu-id="906ff-120">Overlapping Control Structures</span></span>  

 <span data-ttu-id="906ff-121">No se pueden superponer estructuras de control.</span><span class="sxs-lookup"><span data-stu-id="906ff-121">You cannot overlap control structures.</span></span> <span data-ttu-id="906ff-122">Esto significa que cualquier estructura anidada debe estar contenida completamente dentro de la siguiente estructura más interna.</span><span class="sxs-lookup"><span data-stu-id="906ff-122">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="906ff-123">Por ejemplo, la siguiente disposición no es válida porque el `For` bucle finaliza antes de que `With` finalice el bloque interno.</span><span class="sxs-lookup"><span data-stu-id="906ff-123">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![Diagrama que muestra un ejemplo de anidación no válida.](./media/nested-control-structures/example-invalid-nesting.gif)
  
 <span data-ttu-id="906ff-125">El compilador Visual Basic detecta esas estructuras de control superpuestas y señala un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="906ff-125">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="906ff-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="906ff-126">See also</span></span>

- [<span data-ttu-id="906ff-127">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="906ff-127">Control Flow</span></span>](index.md)
- [<span data-ttu-id="906ff-128">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="906ff-128">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="906ff-129">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="906ff-129">Loop Structures</span></span>](loop-structures.md)
- [<span data-ttu-id="906ff-130">Estructuras de control adicionales</span><span class="sxs-lookup"><span data-stu-id="906ff-130">Other Control Structures</span></span>](other-control-structures.md)
