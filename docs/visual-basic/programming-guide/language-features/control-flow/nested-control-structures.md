---
title: Estructuras de control anidadas (Visual Basic)
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
ms.openlocfilehash: ec3d4d477290480cdfa0f5b1c88aa82c81040d11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648078"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="c9dde-102">Estructuras de control anidadas (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9dde-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="c9dde-103">Puede colocar instrucciones de control dentro de otras instrucciones de control, por ejemplo un `If...Then...Else` bloquear dentro de un `For...Next` bucle.</span><span class="sxs-lookup"><span data-stu-id="c9dde-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="c9dde-104">Cuando una instrucción de control que se coloca dentro de otra instrucción de control se dice *anidada*.</span><span class="sxs-lookup"><span data-stu-id="c9dde-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="c9dde-105">Niveles de anidamiento</span><span class="sxs-lookup"><span data-stu-id="c9dde-105">Nesting Levels</span></span>  
 <span data-ttu-id="c9dde-106">Estructuras de control en Visual Basic se pueden anidar a tantos niveles como desee.</span><span class="sxs-lookup"><span data-stu-id="c9dde-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="c9dde-107">Es una práctica habitual que las estructuras anidadas sean más legibles aplicar sangría al cuerpo de cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="c9dde-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="c9dde-108">El editor de desarrollo integrado (IDE) de entorno lo hace automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c9dde-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="c9dde-109">En el ejemplo siguiente, el procedimiento `sumRows` suma los elementos positivos de cada fila de la matriz.</span><span class="sxs-lookup"><span data-stu-id="c9dde-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
```  
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
  
 <span data-ttu-id="c9dde-110">En el ejemplo anterior, la primera `Next` instrucción cierra interna `For` bucle y el último `Next` instrucción cierra el exterior `For` bucle.</span><span class="sxs-lookup"><span data-stu-id="c9dde-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="c9dde-111">Del mismo modo, en anidados `If` instrucciones, el `End If` instrucciones se aplican automáticamente al más cercano antes `If` instrucción.</span><span class="sxs-lookup"><span data-stu-id="c9dde-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="c9dde-112">Anidar `Do` bucles funcionan de manera similar, con la más interna `Loop` instrucción coincidencia interior `Do` instrucción.</span><span class="sxs-lookup"><span data-stu-id="c9dde-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9dde-113">Para muchas de las estructuras de control, al hacer clic en una palabra clave, se resaltan todas las palabras clave en la estructura.</span><span class="sxs-lookup"><span data-stu-id="c9dde-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="c9dde-114">Por ejemplo, al hacer clic en `If` en un `If...Then...Else` construcción, todas las instancias de `If`, `Then`, `ElseIf`, `Else`, y `End If` se resaltan en la construcción.</span><span class="sxs-lookup"><span data-stu-id="c9dde-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="c9dde-115">Para mover a la palabra clave resaltada siguiente o anterior, presione CTRL + MAYÚS + flecha abajo o CTRL + MAYÚS + flecha arriba.</span><span class="sxs-lookup"><span data-stu-id="c9dde-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="c9dde-116">Anidar diferentes tipos de estructuras de Control</span><span class="sxs-lookup"><span data-stu-id="c9dde-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="c9dde-117">Puede anidar un tipo de estructura de control dentro de otro tipo.</span><span class="sxs-lookup"><span data-stu-id="c9dde-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="c9dde-118">En el ejemplo siguiente se usa un `With` bloquear dentro de un `For Each` bucle y anidar `If` bloques dentro de la `With` bloque.</span><span class="sxs-lookup"><span data-stu-id="c9dde-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
```  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="c9dde-119">Estructuras de Control superpuestas</span><span class="sxs-lookup"><span data-stu-id="c9dde-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="c9dde-120">No se puede superponer estructuras de control.</span><span class="sxs-lookup"><span data-stu-id="c9dde-120">You cannot overlap control structures.</span></span> <span data-ttu-id="c9dde-121">Esto significa que cualquier estructura anidada debe estar completamente dentro de la siguiente estructura más interna.</span><span class="sxs-lookup"><span data-stu-id="c9dde-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="c9dde-122">Por ejemplo, la organización siguiente no es válida porque la `For` bucle finaliza antes interna `With` finaliza el bloque.</span><span class="sxs-lookup"><span data-stu-id="c9dde-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 <span data-ttu-id="c9dde-123">![Diagrama gráfico de anidación no válida](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span><span class="sxs-lookup"><span data-stu-id="c9dde-123">![Graphic diagram of invalid nesting](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")</span></span>  
<span data-ttu-id="c9dde-124">Anidamiento no válido de estructuras For y With</span><span class="sxs-lookup"><span data-stu-id="c9dde-124">Invalid nesting of For and With structures</span></span>  
  
 <span data-ttu-id="c9dde-125">El compilador de Visual Basic detecta estas estructuras de control superpuestas y señala un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="c9dde-125">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9dde-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9dde-126">See Also</span></span>  
 [<span data-ttu-id="c9dde-127">Flujo de control</span><span class="sxs-lookup"><span data-stu-id="c9dde-127">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="c9dde-128">Estructuras de decisión</span><span class="sxs-lookup"><span data-stu-id="c9dde-128">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="c9dde-129">Estructuras de bucle</span><span class="sxs-lookup"><span data-stu-id="c9dde-129">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="c9dde-130">Estructuras de control adicionales</span><span class="sxs-lookup"><span data-stu-id="c9dde-130">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
