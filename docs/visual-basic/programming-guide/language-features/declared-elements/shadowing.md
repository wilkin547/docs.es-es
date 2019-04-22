---
title: Sombrear en Visual Basic
ms.date: 07/20/2015
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
ms.openlocfilehash: 9ad992a53618fa2f410e0b0fb23886c30136384f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839397"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="62cc3-102">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62cc3-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="62cc3-103">Cuando dos elementos de programación comparten el mismo nombre, puede ocultar uno de ellos, o *sombra*, otro.</span><span class="sxs-lookup"><span data-stu-id="62cc3-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="62cc3-104">En esta situación, el elemento reemplazado no está disponible como referencia; en su lugar, cuando el código usa el nombre del elemento, el compilador de Visual Basic resuelve en el elemento reemplazado.</span><span class="sxs-lookup"><span data-stu-id="62cc3-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="62cc3-105">Finalidad</span><span class="sxs-lookup"><span data-stu-id="62cc3-105">Purpose</span></span>  
 <span data-ttu-id="62cc3-106">El propósito principal de sombrear es proteger la definición de los miembros de clase.</span><span class="sxs-lookup"><span data-stu-id="62cc3-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="62cc3-107">La clase base puede sufrir un cambio que se crea un elemento con el mismo nombre que ya ha definido.</span><span class="sxs-lookup"><span data-stu-id="62cc3-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="62cc3-108">Si esto ocurre, el `Shadows` modificador fuerza hace referencia a través de su clase se resuelvan en el miembro está definido, en lugar de para el nuevo elemento de la clase base.</span><span class="sxs-lookup"><span data-stu-id="62cc3-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="62cc3-109">Tipos de sombreado</span><span class="sxs-lookup"><span data-stu-id="62cc3-109">Types of Shadowing</span></span>  
 <span data-ttu-id="62cc3-110">Un elemento puede verse ocultado por otro elemento de dos maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="62cc3-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="62cc3-111">El elemento reemplazado puede declararse dentro de una subregión de la región que contiene el elemento sombreado, en el que se logra caso el sombreado *por ámbito*.</span><span class="sxs-lookup"><span data-stu-id="62cc3-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="62cc3-112">O una clase derivada puede volver a definir un miembro de una clase base, en cuyo caso el sombreado se consigue *mediante herencia*.</span><span class="sxs-lookup"><span data-stu-id="62cc3-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="62cc3-113">Sombreado por ámbito</span><span class="sxs-lookup"><span data-stu-id="62cc3-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="62cc3-114">Es posible para la programación de elementos en el mismo módulo, clase o estructura tengan el mismo nombre pero con un ámbito diferente.</span><span class="sxs-lookup"><span data-stu-id="62cc3-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="62cc3-115">Cuando se declaran dos elementos de esta manera y el código hace referencia al nombre que comparten, el elemento con el ámbito más restringido oculta o prevalece sobre el otro elemento (el ámbito de bloque es el más restringido).</span><span class="sxs-lookup"><span data-stu-id="62cc3-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="62cc3-116">Por ejemplo, un módulo puede definir un `Public` variable denominada `temp`, y un procedimiento en el módulo puede declarar una variable local denominada también `temp`.</span><span class="sxs-lookup"><span data-stu-id="62cc3-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="62cc3-117">Las referencias a `temp` desde el procedimiento, obtener acceso a la variable local, mientras que las referencias a `temp` desde fuera del procedimiento obtienen acceso a la `Public` variable.</span><span class="sxs-lookup"><span data-stu-id="62cc3-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="62cc3-118">En este caso, la variable de procedimiento `temp` oculta o prevalece sobre la variable de módulo `temp`.</span><span class="sxs-lookup"><span data-stu-id="62cc3-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="62cc3-119">La siguiente ilustración muestra dos variables, ambos denominados `temp`.</span><span class="sxs-lookup"><span data-stu-id="62cc3-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="62cc3-120">La variable local `temp` oculta o prevalece sobre la variable miembro `temp` al acceder desde dentro de su propio procedimiento `p`.</span><span class="sxs-lookup"><span data-stu-id="62cc3-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="62cc3-121">Sin embargo, el `MyClass` palabra clave omite el sombreado y tiene acceso a la variable de miembro.</span><span class="sxs-lookup"><span data-stu-id="62cc3-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 ![Gráfico que muestra sombreado por ámbito.](./media/shadowing/shadow-scope-diagram.gif)
  
 <span data-ttu-id="62cc3-123">Para obtener un ejemplo de sombreado por ámbito, consulte [Cómo: Ocultar una Variable con el mismo nombre que la Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span><span class="sxs-lookup"><span data-stu-id="62cc3-123">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="62cc3-124">Sombreado por herencia</span><span class="sxs-lookup"><span data-stu-id="62cc3-124">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="62cc3-125">Si una clase derivada, se vuelve a definir un elemento de programación que se hereda de una clase base, el elemento que redefine oculta o prevalece sobre el elemento original.</span><span class="sxs-lookup"><span data-stu-id="62cc3-125">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="62cc3-126">Puede ocultar cualquier tipo de elemento declarado o conjunto de elementos sobrecargados, con cualquier otro tipo.</span><span class="sxs-lookup"><span data-stu-id="62cc3-126">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="62cc3-127">Por ejemplo, un `Integer` variable puede sombrear un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="62cc3-127">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="62cc3-128">Si sombrea un procedimiento con otro, puede usar una lista de parámetros distinta y un tipo de valor devuelto diferente.</span><span class="sxs-lookup"><span data-stu-id="62cc3-128">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="62cc3-129">La siguiente ilustración muestra una clase base `b` y una clase derivada `d` que hereda de `b`.</span><span class="sxs-lookup"><span data-stu-id="62cc3-129">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="62cc3-130">La clase base define un procedimiento denominado `proc`, y la clase derivada lo reemplaza con otro procedimiento del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="62cc3-130">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="62cc3-131">La primera `Call` instrucción tiene acceso el sombreado `proc` en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="62cc3-131">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="62cc3-132">Sin embargo, el `MyBase` palabra clave omite el sombreado y tiene acceso al procedimiento sombreado en la clase base.</span><span class="sxs-lookup"><span data-stu-id="62cc3-132">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 ![Diagrama gráfico de sombreado por herencia](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 <span data-ttu-id="62cc3-134">Para obtener un ejemplo de sombreado por herencia, vea [Cómo: Ocultar una Variable con el mismo nombre que la Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) y [Cómo: Ocultar una Variable heredada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span><span class="sxs-lookup"><span data-stu-id="62cc3-134">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="62cc3-135">Sombreado y nivel de acceso</span><span class="sxs-lookup"><span data-stu-id="62cc3-135">Shadowing and Access Level</span></span>  
 <span data-ttu-id="62cc3-136">El elemento reemplazado no siempre es accesible desde el código que usa la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="62cc3-136">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="62cc3-137">Por ejemplo, podría declararse `Private`.</span><span class="sxs-lookup"><span data-stu-id="62cc3-137">For example, it might be declared `Private`.</span></span> <span data-ttu-id="62cc3-138">En tal caso, se rechaza el sombreado y el compilador resuelve cualquier referencia al mismo elemento tendría si no hubiera habido ningún sombreado.</span><span class="sxs-lookup"><span data-stu-id="62cc3-138">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="62cc3-139">Este es el elemento accesible menos derivación en sentido pasos hacia atrás desde la clase que sombrea.</span><span class="sxs-lookup"><span data-stu-id="62cc3-139">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="62cc3-140">Si el elemento sombreado es un procedimiento, la resolución es la versión más cercana accesible con el mismo nombre, la lista de parámetros y tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="62cc3-140">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="62cc3-141">El ejemplo siguiente muestra una jerarquía de herencia de tres clases.</span><span class="sxs-lookup"><span data-stu-id="62cc3-141">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="62cc3-142">Cada clase define un `Sub` procedimiento `display`, y cada clase derivada sombrea el `display` procedimiento en su clase base.</span><span class="sxs-lookup"><span data-stu-id="62cc3-142">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
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
  
 <span data-ttu-id="62cc3-143">En el ejemplo anterior, la clase derivada `secondClass` sombras `display` con un `Private` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="62cc3-143">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="62cc3-144">Al módulo `callDisplay` llamadas `display` en `secondClass`, el código de llamada está fuera de `secondClass` y, por tanto, no puede acceder a la privada `display` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="62cc3-144">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="62cc3-145">Se rechaza el sombreado y el compilador resuelve la referencia a la clase base `display` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="62cc3-145">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="62cc3-146">Sin embargo, la otra clase derivada `thirdClass` declara `display` como `Public`, por lo que el código en `callDisplay` puede tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="62cc3-146">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="62cc3-147">Sombrear y reemplazar</span><span class="sxs-lookup"><span data-stu-id="62cc3-147">Shadowing and Overriding</span></span>  
 <span data-ttu-id="62cc3-148">No confunda sombrear y reemplazar.</span><span class="sxs-lookup"><span data-stu-id="62cc3-148">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="62cc3-149">Ambos se usan cuando una clase derivada hereda de una clase base, y ambos vuelven a definir un elemento declarado con otro.</span><span class="sxs-lookup"><span data-stu-id="62cc3-149">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="62cc3-150">Sin embargo, hay diferencias significativas entre los dos.</span><span class="sxs-lookup"><span data-stu-id="62cc3-150">But there are significant differences between the two.</span></span> <span data-ttu-id="62cc3-151">Para obtener una comparación, consulte [diferencias entre sombrear y Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span><span class="sxs-lookup"><span data-stu-id="62cc3-151">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="62cc3-152">Sombreado y sobrecarga</span><span class="sxs-lookup"><span data-stu-id="62cc3-152">Shadowing and Overloading</span></span>  
 <span data-ttu-id="62cc3-153">Si sombrea el mismo elemento de la clase base con más de un elemento en la clase derivada, los elementos sombreados se convierten en las versiones sobrecargadas de ese elemento.</span><span class="sxs-lookup"><span data-stu-id="62cc3-153">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="62cc3-154">Para obtener más información, consulta [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="62cc3-154">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="62cc3-155">Obtener acceso a un elemento reemplazado</span><span class="sxs-lookup"><span data-stu-id="62cc3-155">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="62cc3-156">Cuando tenga acceso a un elemento de una clase derivada, normalmente se logra a través de la instancia actual de dicha clase derivada, calificando el nombre del elemento con el `Me` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="62cc3-156">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="62cc3-157">Si la clase derivada oculta o prevalece sobre el elemento de la clase base, puede tener acceso al elemento de clase base mediante su calificación con la `MyBase` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="62cc3-157">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="62cc3-158">Para obtener un ejemplo de acceso a un elemento reemplazado, vea [Cómo: Obtener acceso a una Variable que oculta una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="62cc3-158">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="62cc3-159">Declaración de la Variable de objeto</span><span class="sxs-lookup"><span data-stu-id="62cc3-159">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="62cc3-160">Cómo crear la variable de objeto también puede afectar a si la clase derivada, obtiene acceso a un elemento reemplazado o el elemento sombreado.</span><span class="sxs-lookup"><span data-stu-id="62cc3-160">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="62cc3-161">El ejemplo siguiente crea dos objetos desde una clase derivada, pero se declara un objeto como la clase base y el otro como la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="62cc3-161">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
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
  
 <span data-ttu-id="62cc3-162">En el ejemplo anterior, la variable `basObj` se declara como clase base.</span><span class="sxs-lookup"><span data-stu-id="62cc3-162">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="62cc3-163">Asignar un `dervCls` objeto constituye una conversión de ampliación y, por tanto, es válida.</span><span class="sxs-lookup"><span data-stu-id="62cc3-163">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="62cc3-164">Sin embargo, la clase base no puede acceder a la versión de la variable de sombreado `z` en la clase derivada, por lo que el compilador resuelve `basObj.z` con el valor de la clase base original.</span><span class="sxs-lookup"><span data-stu-id="62cc3-164">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62cc3-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="62cc3-165">See also</span></span>

- [<span data-ttu-id="62cc3-166">Referencias a elementos declarados</span><span class="sxs-lookup"><span data-stu-id="62cc3-166">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="62cc3-167">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="62cc3-167">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="62cc3-168">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="62cc3-168">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="62cc3-169">Shadows</span><span class="sxs-lookup"><span data-stu-id="62cc3-169">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="62cc3-170">Overrides</span><span class="sxs-lookup"><span data-stu-id="62cc3-170">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="62cc3-171">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="62cc3-171">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="62cc3-172">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="62cc3-172">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
