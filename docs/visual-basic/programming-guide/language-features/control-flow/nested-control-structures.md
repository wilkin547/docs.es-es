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
ms.openlocfilehash: 539ad639320615c1e53176fe47e5468864aa21d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414394"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="4b76a-102">Estructuras de control anidadas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b76a-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="4b76a-103">Puede colocar instrucciones de control dentro de otras instrucciones de control, por ejemplo, un `If...Then...Else` bloque dentro de un `For...Next` bucle.</span><span class="sxs-lookup"><span data-stu-id="4b76a-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="4b76a-104">Una instrucción de control colocada dentro de otra instrucción de control se dice que está *anidada*.</span><span class="sxs-lookup"><span data-stu-id="4b76a-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="4b76a-105">Niveles de anidamiento</span><span class="sxs-lookup"><span data-stu-id="4b76a-105">Nesting Levels</span></span>  
 <span data-ttu-id="4b76a-106">Las estructuras de control de Visual Basic se pueden anidar hasta tantos niveles como se desee.</span><span class="sxs-lookup"><span data-stu-id="4b76a-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="4b76a-107">Es habitual que las estructuras anidadas sean más legibles mediante la sangría del cuerpo de cada una.</span><span class="sxs-lookup"><span data-stu-id="4b76a-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="4b76a-108">El editor del entorno de desarrollo integrado (IDE) lo hace automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4b76a-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="4b76a-109">En el ejemplo siguiente, el procedimiento `sumRows` suma los elementos positivos de cada fila de la matriz.</span><span class="sxs-lookup"><span data-stu-id="4b76a-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="4b76a-110">En el ejemplo anterior, la primera `Next` instrucción cierra el bucle interno `For` y la última `Next` instrucción cierra el `For` bucle externo.</span><span class="sxs-lookup"><span data-stu-id="4b76a-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="4b76a-111">Del mismo modo, en `If` las instrucciones anidadas, las `End If` instrucciones se aplican automáticamente a la instrucción anterior más cercana `If` .</span><span class="sxs-lookup"><span data-stu-id="4b76a-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="4b76a-112">`Do`Los bucles anidados funcionan de manera similar, con la instrucción más interna `Loop` que coincide con la instrucción más interna `Do` .</span><span class="sxs-lookup"><span data-stu-id="4b76a-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b76a-113">En el caso de muchas estructuras de control, al hacer clic en una palabra clave, se resaltan todas las palabras clave de la estructura.</span><span class="sxs-lookup"><span data-stu-id="4b76a-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="4b76a-114">Por ejemplo, al hacer clic `If` en en una `If...Then...Else` construcción, `If` se resaltan todas las instancias de,,, `Then` `ElseIf` `Else` y `End If` en la construcción.</span><span class="sxs-lookup"><span data-stu-id="4b76a-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="4b76a-115">Para desplazarse a la palabra clave resaltada siguiente o anterior, presione CTRL + MAYÚS + flecha abajo o CTRL + MAYÚS + flecha arriba.</span><span class="sxs-lookup"><span data-stu-id="4b76a-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="4b76a-116">Anidar distintos tipos de estructuras de control</span><span class="sxs-lookup"><span data-stu-id="4b76a-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="4b76a-117">Puede anidar un tipo de estructura de control dentro de otro tipo.</span><span class="sxs-lookup"><span data-stu-id="4b76a-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="4b76a-118">En el ejemplo siguiente se usa un `With` bloque dentro de un `For Each` bucle y bloques anidados `If` dentro del `With` bloque.</span><span class="sxs-lookup"><span data-stu-id="4b76a-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="4b76a-119">Estructuras de control superpuestas</span><span class="sxs-lookup"><span data-stu-id="4b76a-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="4b76a-120">No se pueden superponer estructuras de control.</span><span class="sxs-lookup"><span data-stu-id="4b76a-120">You cannot overlap control structures.</span></span> <span data-ttu-id="4b76a-121">Esto significa que cualquier estructura anidada debe estar contenida completamente dentro de la siguiente estructura más interna.</span><span class="sxs-lookup"><span data-stu-id="4b76a-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="4b76a-122">Por ejemplo, la siguiente disposición no es válida porque el `For` bucle finaliza antes de que `With` finalice el bloque interno.</span><span class="sxs-lookup"><span data-stu-id="4b76a-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![Diagrama que muestra un ejemplo de anidación no válida.](./media/nested-control-structures/example-invalid-nesting.gif)
  
 <span data-ttu-id="4b76a-124">El compilador Visual Basic detecta esas estructuras de control superpuestas y señala un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="4b76a-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b76a-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4b76a-125">See also</span></span>

- [<span data-ttu-id="4b76a-126">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="4b76a-126">Control Flow</span></span>](index.md)
- [<span data-ttu-id="4b76a-127">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="4b76a-127">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="4b76a-128">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="4b76a-128">Loop Structures</span></span>](loop-structures.md)
- [<span data-ttu-id="4b76a-129">Estructuras de control adicionales</span><span class="sxs-lookup"><span data-stu-id="4b76a-129">Other Control Structures</span></span>](other-control-structures.md)
