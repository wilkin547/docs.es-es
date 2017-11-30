---
title: Sombrear en Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- inheritance [Visual Basic], shadowing
- overriding, and shadowing
- shadowing
- duplicate names [Visual Basic]
- shadowing, by inheritance
- declared elements [Visual Basic], referencing
- shadowing, by scope
- declared elements [Visual Basic], hiding
- naming conflicts, shadowing
- declared elements [Visual Basic], shadowing
- shadowing, and overriding
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic], about
- objects [Visual Basic], names
- names [Visual Basic], shadowing
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cbfce3edc122ca875552b2d41ba876fe5cfcfc4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="40a6e-102">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="40a6e-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="40a6e-103">Si dos elementos de programación comparten el mismo nombre, uno de ellos puede ocultar, o *instantáneas*, el otro se.</span><span class="sxs-lookup"><span data-stu-id="40a6e-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="40a6e-104">En esta situación, el elemento sombreado no está disponible como referencia; en su lugar, cuando el código utiliza el nombre del elemento, el [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compilador lo resuelve como el elemento reemplazado.</span><span class="sxs-lookup"><span data-stu-id="40a6e-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="40a6e-105">Finalidad</span><span class="sxs-lookup"><span data-stu-id="40a6e-105">Purpose</span></span>  
 <span data-ttu-id="40a6e-106">El propósito principal de sombrear es proteger la definición de los miembros de clase.</span><span class="sxs-lookup"><span data-stu-id="40a6e-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="40a6e-107">La clase base puede sufrir un cambio que se crea un elemento con el mismo nombre que ya se ha definido.</span><span class="sxs-lookup"><span data-stu-id="40a6e-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="40a6e-108">Si esto ocurre, el `Shadows` modificador fuerza referencias a través de la clase para que se resuelvan en el miembro definido, en lugar de en el nuevo elemento de clase base.</span><span class="sxs-lookup"><span data-stu-id="40a6e-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="40a6e-109">Tipos de sombreado</span><span class="sxs-lookup"><span data-stu-id="40a6e-109">Types of Shadowing</span></span>  
 <span data-ttu-id="40a6e-110">Un elemento puede prevalecer sobre otro elemento de dos maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="40a6e-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="40a6e-111">El elemento que sombrea puede declararse dentro de una subregión de la región que contiene el elemento sombreado, en el que se consigue caso el sombreado *a través de ámbito*.</span><span class="sxs-lookup"><span data-stu-id="40a6e-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="40a6e-112">O una clase derivada puede volver a definir un miembro de una clase base, en cuyo caso el sombreado se consigue *a través de la herencia*.</span><span class="sxs-lookup"><span data-stu-id="40a6e-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="40a6e-113">Sombreado por ámbito</span><span class="sxs-lookup"><span data-stu-id="40a6e-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="40a6e-114">Es posible para la programación de elementos en el mismo módulo, clase o estructura tengan el mismo nombre pero con un ámbito diferente.</span><span class="sxs-lookup"><span data-stu-id="40a6e-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="40a6e-115">Cuando dos elementos se declaran de esta manera y el código hace referencia al nombre que comparten, el elemento con el ámbito más restringido oculta al otro elemento (el ámbito de bloque es el más restringido).</span><span class="sxs-lookup"><span data-stu-id="40a6e-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="40a6e-116">Por ejemplo, un módulo puede definir una `Public` variable denominada `temp`, y un procedimiento en el módulo puede declarar una variable local denominada también `temp`.</span><span class="sxs-lookup"><span data-stu-id="40a6e-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="40a6e-117">Las referencias a `temp` desde el procedimiento, tener acceso a la variable local, mientras que las referencias a `temp` desde fuera del procedimiento obtienen acceso a la `Public` variable.</span><span class="sxs-lookup"><span data-stu-id="40a6e-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="40a6e-118">En este caso, la variable de procedimiento `temp` prevalece sobre la variable de módulo `temp`.</span><span class="sxs-lookup"><span data-stu-id="40a6e-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="40a6e-119">La ilustración siguiente muestra dos variables, ambos denominados `temp`.</span><span class="sxs-lookup"><span data-stu-id="40a6e-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="40a6e-120">La variable local `temp` prevalece sobre la variable miembro `temp` cuando se tiene acceso desde dentro de su propio procedimiento `p`.</span><span class="sxs-lookup"><span data-stu-id="40a6e-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="40a6e-121">Sin embargo, la `MyClass` palabra clave omite el sombreado y tiene acceso a la variable miembro.</span><span class="sxs-lookup"><span data-stu-id="40a6e-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 <span data-ttu-id="40a6e-122">![Diagrama gráfico de sombreado por ámbito](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")</span><span class="sxs-lookup"><span data-stu-id="40a6e-122">![Graphic diagram of shadowing through scope](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")</span></span>  
<span data-ttu-id="40a6e-123">Sombreado por ámbito</span><span class="sxs-lookup"><span data-stu-id="40a6e-123">Shadowing through scope</span></span>  
  
 <span data-ttu-id="40a6e-124">Para obtener un ejemplo de sombreado por ámbito, consulte [Cómo: ocultar una Variable con el mismo nombre que la Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span><span class="sxs-lookup"><span data-stu-id="40a6e-124">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="40a6e-125">Sombreado por herencia</span><span class="sxs-lookup"><span data-stu-id="40a6e-125">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="40a6e-126">Si una clase derivada vuelve a definir un elemento de programación que se hereda de una clase base, el elemento que redefine ensombrece al elemento original.</span><span class="sxs-lookup"><span data-stu-id="40a6e-126">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="40a6e-127">Puede reemplazar cualquier tipo de elemento declarado o conjunto de elementos sobrecargados, con cualquier otro tipo.</span><span class="sxs-lookup"><span data-stu-id="40a6e-127">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="40a6e-128">Por ejemplo, un `Integer` variable puede reemplazar un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="40a6e-128">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="40a6e-129">Si sombrea un procedimiento con otro, puede utilizar una lista de parámetros distinta y un tipo de valor devuelto distinto.</span><span class="sxs-lookup"><span data-stu-id="40a6e-129">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="40a6e-130">La ilustración siguiente muestra una clase base `b` y una clase derivada `d` que hereda de `b`.</span><span class="sxs-lookup"><span data-stu-id="40a6e-130">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="40a6e-131">La clase base define un procedimiento denominado `proc`, y la clase derivada lo sombrea con otro procedimiento con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="40a6e-131">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="40a6e-132">La primera `Call` instrucción accede al sombreado `proc` en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="40a6e-132">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="40a6e-133">Sin embargo, la `MyBase` palabra clave omite el sombreado y tiene acceso al procedimiento sombreado en la clase base.</span><span class="sxs-lookup"><span data-stu-id="40a6e-133">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 <span data-ttu-id="40a6e-134">![Diagrama gráfico de sombreado por herencia](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")</span><span class="sxs-lookup"><span data-stu-id="40a6e-134">![Graphic diagram of shadowing through inheritance](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")</span></span>  
<span data-ttu-id="40a6e-135">Sombreado por herencia</span><span class="sxs-lookup"><span data-stu-id="40a6e-135">Shadowing through inheritance</span></span>  
  
 <span data-ttu-id="40a6e-136">Para obtener un ejemplo de sombreado por herencia, consulte [Cómo: ocultar una Variable con el mismo nombre que la Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) y [Cómo: ocultar una Variable heredada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span><span class="sxs-lookup"><span data-stu-id="40a6e-136">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="40a6e-137">El sombreado y el nivel de acceso</span><span class="sxs-lookup"><span data-stu-id="40a6e-137">Shadowing and Access Level</span></span>  
 <span data-ttu-id="40a6e-138">El elemento reemplazado no siempre es accesible desde el código que utiliza la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="40a6e-138">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="40a6e-139">Por ejemplo, podría declararse `Private`.</span><span class="sxs-lookup"><span data-stu-id="40a6e-139">For example, it might be declared `Private`.</span></span> <span data-ttu-id="40a6e-140">En tal caso, se rechaza el sombreado y el compilador resuelve cualquier referencia al mismo elemento tendría si no hubiera habido ningún sombreado.</span><span class="sxs-lookup"><span data-stu-id="40a6e-140">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="40a6e-141">Este elemento es el elemento accesible menos derivación en sentido pasos hacia atrás desde la clase que sombrea.</span><span class="sxs-lookup"><span data-stu-id="40a6e-141">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="40a6e-142">Si el elemento sombreado es un procedimiento, la resolución es la versión accesible más próxima con el mismo nombre, lista de parámetros y tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="40a6e-142">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="40a6e-143">En el ejemplo siguiente se muestra una jerarquía de herencia de tres clases.</span><span class="sxs-lookup"><span data-stu-id="40a6e-143">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="40a6e-144">Cada clase define un `Sub` procedimiento `display`, y cada clase derivada sombrea el `display` procedimiento en su clase base.</span><span class="sxs-lookup"><span data-stu-id="40a6e-144">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
```  
Public Class firstClass  
    Public Sub display()  
        MsgBox("This is firstClass")  
    End Sub  
End Class  
Public Class secondClass  
    Inherits firstClass  
    Private Shadows Sub display()  
        MsgBox("This is secondClass")  
    End Sub  
End Class  
Public Class thirdClass  
    Inherits secondClass  
    Public Shadows Sub display()  
        MsgBox("This is thirdClass")  
    End Sub  
End Class  
Module callDisplay  
    Dim first As New firstClass  
    Dim second As New secondClass  
    Dim third As New thirdClass  
    Public Sub callDisplayProcedures()  
        ' The following statement displays "This is firstClass".  
        first.display()  
        ' The following statement displays "This is firstClass".  
        second.display()  
        ' The following statement displays "This is thirdClass".  
        third.display()  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="40a6e-145">En el ejemplo anterior, la clase derivada `secondClass` sombras `display` con un `Private` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="40a6e-145">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="40a6e-146">Al módulo `callDisplay` llamadas `display` en `secondClass`, el código que realiza la llamada está fuera de `secondClass` y, por tanto, no se puede obtener acceso a la privada `display` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="40a6e-146">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="40a6e-147">Se rechaza el sombreado y el compilador resuelve la referencia a la clase base `display` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="40a6e-147">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="40a6e-148">Sin embargo, la otra clase derivada `thirdClass` declara `display` como `Public`, por lo que el código en `callDisplay` puede tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="40a6e-148">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="40a6e-149">Sombrear y reemplazar</span><span class="sxs-lookup"><span data-stu-id="40a6e-149">Shadowing and Overriding</span></span>  
 <span data-ttu-id="40a6e-150">No confunda sombrear y reemplazar.</span><span class="sxs-lookup"><span data-stu-id="40a6e-150">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="40a6e-151">Ambos se usan cuando una clase derivada hereda de una clase base y ambos vuelven a definir un elemento declarado con otro.</span><span class="sxs-lookup"><span data-stu-id="40a6e-151">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="40a6e-152">Pero hay diferencias significativas entre los dos.</span><span class="sxs-lookup"><span data-stu-id="40a6e-152">But there are significant differences between the two.</span></span> <span data-ttu-id="40a6e-153">Para obtener una comparación, consulte [diferencias entre sombrear y reemplazando](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span><span class="sxs-lookup"><span data-stu-id="40a6e-153">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="40a6e-154">Sombreado y sobrecarga</span><span class="sxs-lookup"><span data-stu-id="40a6e-154">Shadowing and Overloading</span></span>  
 <span data-ttu-id="40a6e-155">Si sombrea el mismo elemento de clase base con más de un elemento de la clase derivada, los elementos sombreados se convierten en las versiones sobrecargadas de ese elemento.</span><span class="sxs-lookup"><span data-stu-id="40a6e-155">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="40a6e-156">Para obtener más información, consulte [sobrecarga de procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="40a6e-156">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="40a6e-157">Obtener acceso a un elemento sombreado</span><span class="sxs-lookup"><span data-stu-id="40a6e-157">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="40a6e-158">Cuando tiene acceso a un elemento de una clase derivada, normalmente se logra a través de la instancia actual de dicha clase derivada, calificando el nombre del elemento con el `Me` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="40a6e-158">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="40a6e-159">Si la clase derivada ensombrece al elemento de la clase base, puede tener acceso al elemento de clase base mediante su calificación con la `MyBase` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="40a6e-159">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="40a6e-160">Para obtener un ejemplo de obtener acceso a un elemento reemplazado, consulte [Cómo: obtener acceso a una Variable oculta una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="40a6e-160">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="40a6e-161">Declaración de la Variable de objeto</span><span class="sxs-lookup"><span data-stu-id="40a6e-161">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="40a6e-162">Cómo crear la variable de objeto también puede afectar a si la clase derivada tiene acceso a un elemento de sombreado o el elemento sombreado.</span><span class="sxs-lookup"><span data-stu-id="40a6e-162">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="40a6e-163">En el ejemplo siguiente se crea dos objetos de una clase derivada, pero un objeto se declara como la clase base y el otro como la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="40a6e-163">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
```  
Public Class baseCls  
    ' The following statement declares the element that is to be shadowed.  
    Public z As Integer = 100  
End Class  
Public Class dervCls  
    Inherits baseCls  
    ' The following statement declares the shadowing element.  
    Public Shadows z As String = "*"  
End Class  
Public Class useClasses  
    ' The following statement creates the object declared as the base class.  
    Dim basObj As baseCls = New dervCls()  
    ' Note that dervCls widens to its base class baseCls.  
    ' The following statement creates the object declared as the derived class.  
    Dim derObj As dervCls = New dervCls()  
    Public Sub showZ()   
    ' The following statement outputs 100 (the shadowed element).  
        MsgBox("Accessed through base class: " & basObj.z)  
    ' The following statement outputs "*" (the shadowing element).  
        MsgBox("Accessed through derived class: " & derObj.z)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="40a6e-164">En el ejemplo anterior, la variable `basObj` se declara como clase base.</span><span class="sxs-lookup"><span data-stu-id="40a6e-164">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="40a6e-165">Asignar un `dervCls` objeto constituye una conversión de ampliación y, por tanto, es válida.</span><span class="sxs-lookup"><span data-stu-id="40a6e-165">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="40a6e-166">Sin embargo, la clase base no puede obtener acceso a la versión de sombreado de la variable `z` en la clase derivada, por lo que el compilador resuelve `basObj.z` para el valor original de la clase base.</span><span class="sxs-lookup"><span data-stu-id="40a6e-166">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40a6e-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="40a6e-167">See Also</span></span>  
 [<span data-ttu-id="40a6e-168">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="40a6e-168">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="40a6e-169">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="40a6e-169">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [<span data-ttu-id="40a6e-170">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="40a6e-170">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="40a6e-171">Shadows</span><span class="sxs-lookup"><span data-stu-id="40a6e-171">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="40a6e-172">Overrides</span><span class="sxs-lookup"><span data-stu-id="40a6e-172">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [<span data-ttu-id="40a6e-173">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="40a6e-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="40a6e-174">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="40a6e-174">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
