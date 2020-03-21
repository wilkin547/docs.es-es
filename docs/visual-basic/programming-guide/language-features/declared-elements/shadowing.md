---
title: Sombreado
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
ms.openlocfilehash: 20a33478f622fca6d3183772f53dcb3e72f79409
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266890"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="01050-102">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="01050-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="01050-103">Cuando dos elementos de programación comparten el mismo nombre, uno de ellos puede ocultar, o *sombra,* el otro.</span><span class="sxs-lookup"><span data-stu-id="01050-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="01050-104">En tal situación, el elemento sombreado no está disponible como referencia; en su lugar, cuando el código usa el nombre del elemento, el compilador de Visual Basic lo resuelve en el elemento de sombreado.</span><span class="sxs-lookup"><span data-stu-id="01050-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="01050-105">Propósito</span><span class="sxs-lookup"><span data-stu-id="01050-105">Purpose</span></span>  
 <span data-ttu-id="01050-106">El propósito principal del sombreado es proteger la definición de los miembros de la clase.</span><span class="sxs-lookup"><span data-stu-id="01050-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="01050-107">La clase base puede sufrir un cambio que crea un elemento con el mismo nombre que ya ha definido.</span><span class="sxs-lookup"><span data-stu-id="01050-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="01050-108">Si esto sucede, el `Shadows` modificador fuerza las referencias a través de la clase para que se resuelvan en el miembro que definió, en lugar del nuevo elemento de clase base.</span><span class="sxs-lookup"><span data-stu-id="01050-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="01050-109">Tipos de Sombras</span><span class="sxs-lookup"><span data-stu-id="01050-109">Types of Shadowing</span></span>  
 <span data-ttu-id="01050-110">Un elemento puede sombrear otro elemento de dos maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="01050-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="01050-111">El elemento de sombreado se puede declarar dentro de una subregión de la región que contiene el elemento sombreado, en cuyo caso el sombreado se realiza *a través*del ámbito .</span><span class="sxs-lookup"><span data-stu-id="01050-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="01050-112">O una clase derivada puede redefinir un miembro de una clase base, en cuyo caso el sombreado se realiza *a través*de la herencia.</span><span class="sxs-lookup"><span data-stu-id="01050-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="01050-113">Sombreado a través del alcance</span><span class="sxs-lookup"><span data-stu-id="01050-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="01050-114">Es posible que los elementos de programación del mismo módulo, clase o estructura tengan el mismo nombre pero un ámbito diferente.</span><span class="sxs-lookup"><span data-stu-id="01050-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="01050-115">Cuando se declaran dos elementos de esta manera y el código hace referencia al nombre que comparten, el elemento con el ámbito más estrecho sombrea el otro elemento (el ámbito de bloque es el más estrecho).</span><span class="sxs-lookup"><span data-stu-id="01050-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="01050-116">Por ejemplo, un módulo `Public` puede `temp`definir una variable denominada , y un `temp`procedimiento dentro del módulo puede declarar una variable local también denominada .</span><span class="sxs-lookup"><span data-stu-id="01050-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="01050-117">Las `temp` referencias desde dentro del procedimiento tienen `temp` acceso a la `Public` variable local, mientras que las referencias desde fuera del procedimiento tienen acceso a la variable.</span><span class="sxs-lookup"><span data-stu-id="01050-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="01050-118">En este caso, `temp` la variable `temp`de procedimiento sombrea la variable de módulo .</span><span class="sxs-lookup"><span data-stu-id="01050-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="01050-119">En la ilustración siguiente se `temp`muestran dos variables, ambas denominadas .</span><span class="sxs-lookup"><span data-stu-id="01050-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="01050-120">La variable `temp` local sombrea la variable `temp` `p`miembro cuando se accede desde su propio procedimiento.</span><span class="sxs-lookup"><span data-stu-id="01050-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="01050-121">Sin `MyClass` embargo, la palabra clave omite el sombreado y tiene acceso a la variable miembro.</span><span class="sxs-lookup"><span data-stu-id="01050-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 ![Gráfico que muestra sombras a través del ámbito.](./media/shadowing/shadow-scope-diagram.gif)
  
 <span data-ttu-id="01050-123">Para obtener un ejemplo de sombreado a través del ámbito, vea [Cómo: Ocultar una variable con el mismo nombre que](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)la variable .</span><span class="sxs-lookup"><span data-stu-id="01050-123">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="01050-124">Sombreado a través de la herencia</span><span class="sxs-lookup"><span data-stu-id="01050-124">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="01050-125">Si una clase derivada redefine un elemento de programación heredado de una clase base, el elemento de redefinición sombrea el elemento original.</span><span class="sxs-lookup"><span data-stu-id="01050-125">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="01050-126">Puede sombrear cualquier tipo de elemento declarado, o conjunto de elementos sobrecargados, con cualquier otro tipo.</span><span class="sxs-lookup"><span data-stu-id="01050-126">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="01050-127">Por ejemplo, `Integer` una variable `Function` puede sombrear un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="01050-127">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="01050-128">Si sombrea un procedimiento con otro procedimiento, puede utilizar una lista de parámetros diferente y un tipo de valor devuelto diferente.</span><span class="sxs-lookup"><span data-stu-id="01050-128">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="01050-129">En la ilustración `b` siguiente se muestra `d` una clase `b`base y una clase derivada que hereda de .</span><span class="sxs-lookup"><span data-stu-id="01050-129">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="01050-130">La clase base define `proc`un procedimiento denominado y la clase derivada lo sombrea con otro procedimiento del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="01050-130">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="01050-131">La `Call` primera instrucción tiene `proc` acceso al sombreado de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="01050-131">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="01050-132">Sin `MyBase` embargo, la palabra clave omite el sombreado y tiene acceso al procedimiento sombreado en la clase base.</span><span class="sxs-lookup"><span data-stu-id="01050-132">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 ![Diagrama gráfico de sombreado por herencia](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 <span data-ttu-id="01050-134">Para obtener un ejemplo de sombreado a través de la herencia, vea [Cómo: Ocultar una variable con el mismo nombre que](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) la variable y [Cómo: Ocultar una variable heredada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span><span class="sxs-lookup"><span data-stu-id="01050-134">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="01050-135">Sombreado y nivel de acceso</span><span class="sxs-lookup"><span data-stu-id="01050-135">Shadowing and Access Level</span></span>  
 <span data-ttu-id="01050-136">El elemento de sombreado no siempre es accesible desde el código mediante la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="01050-136">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="01050-137">Por ejemplo, podría `Private`declararse .</span><span class="sxs-lookup"><span data-stu-id="01050-137">For example, it might be declared `Private`.</span></span> <span data-ttu-id="01050-138">En tal caso, se derrota el sombreado y el compilador resuelve cualquier referencia al mismo elemento que tendría si no hubiera habido ninguna sombra.</span><span class="sxs-lookup"><span data-stu-id="01050-138">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="01050-139">Este elemento es el elemento accesible el menor número de pasos derivacionales hacia atrás desde la clase de sombreado.</span><span class="sxs-lookup"><span data-stu-id="01050-139">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="01050-140">Si el elemento sombreado es un procedimiento, la resolución es a la versión accesible más cercana con el mismo nombre, lista de parámetros y tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="01050-140">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="01050-141">En el ejemplo siguiente se muestra una jerarquía de herencia de tres clases.</span><span class="sxs-lookup"><span data-stu-id="01050-141">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="01050-142">Cada clase `Sub` define `display`un procedimiento y cada `display` clase derivada sombrea el procedimiento en su clase base.</span><span class="sxs-lookup"><span data-stu-id="01050-142">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
```vb  
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
  
 <span data-ttu-id="01050-143">En el ejemplo anterior, la `secondClass` `display` clase `Private` derivada se sombrea con un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="01050-143">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="01050-144">Cuando `callDisplay` el `display` `secondClass`módulo llama adentro, el código de llamada está fuera `secondClass` y, por lo tanto, no puede tener acceso al procedimiento privado. `display`</span><span class="sxs-lookup"><span data-stu-id="01050-144">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="01050-145">Se derrota el sombreado y el compilador resuelve la `display` referencia al procedimiento de clase base.</span><span class="sxs-lookup"><span data-stu-id="01050-145">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="01050-146">Sin embargo, la `thirdClass` clase `display` `Public`derivada adicional declara `callDisplay` como , por lo que el código en puede tener acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="01050-146">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="01050-147">Sombra y anulación</span><span class="sxs-lookup"><span data-stu-id="01050-147">Shadowing and Overriding</span></span>  
 <span data-ttu-id="01050-148">No confunda las sombras con la invalidación.</span><span class="sxs-lookup"><span data-stu-id="01050-148">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="01050-149">Ambos se utilizan cuando una clase derivada hereda de una clase base y ambos redefinen un elemento declarado con otro.</span><span class="sxs-lookup"><span data-stu-id="01050-149">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="01050-150">Pero hay diferencias significativas entre los dos.</span><span class="sxs-lookup"><span data-stu-id="01050-150">But there are significant differences between the two.</span></span> <span data-ttu-id="01050-151">Para obtener una comparación, consulte [Diferencias entre sombreado y anulación](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span><span class="sxs-lookup"><span data-stu-id="01050-151">For a comparison, see [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="01050-152">Sombreado y sobrecarga</span><span class="sxs-lookup"><span data-stu-id="01050-152">Shadowing and Overloading</span></span>  
 <span data-ttu-id="01050-153">Si sombrea el mismo elemento de clase base con más de un elemento en la clase derivada, los elementos de sombreado se convierten en versiones sobrecargadas de ese elemento.</span><span class="sxs-lookup"><span data-stu-id="01050-153">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="01050-154">Para obtener más información, consulta [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="01050-154">For more information, see [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="01050-155">Acceso a un elemento sombreado</span><span class="sxs-lookup"><span data-stu-id="01050-155">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="01050-156">Cuando se tiene acceso a un elemento desde una clase derivada, normalmente se hace a través de la instancia actual de esa clase derivada, calificando el nombre del elemento con la `Me` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="01050-156">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="01050-157">Si la clase derivada sombrea el elemento de la clase base, puede `MyBase` tener acceso al elemento de clase base calificándolo con la palabra clave.</span><span class="sxs-lookup"><span data-stu-id="01050-157">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="01050-158">Para obtener un ejemplo de acceso a un elemento sombreado, vea [Cómo: obtener acceso a una variable oculta por una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="01050-158">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="01050-159">Declaración de la variable de objeto</span><span class="sxs-lookup"><span data-stu-id="01050-159">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="01050-160">La forma de crear la variable de objeto también puede afectar a si la clase derivada tiene acceso a un elemento de sombreado o al elemento sombreado.</span><span class="sxs-lookup"><span data-stu-id="01050-160">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="01050-161">En el ejemplo siguiente se crean dos objetos a partir de una clase derivada, pero un objeto se declara como la clase base y el otro como la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="01050-161">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
```vb  
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
  
 <span data-ttu-id="01050-162">En el ejemplo anterior, `basObj` la variable se declara como la clase base.</span><span class="sxs-lookup"><span data-stu-id="01050-162">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="01050-163">Asignarle `dervCls` un objeto constituye una conversión cada vez mayor y, por lo tanto, es válida.</span><span class="sxs-lookup"><span data-stu-id="01050-163">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="01050-164">Sin embargo, la clase base no `z` puede tener acceso a la versión de sombreado de la variable en la clase derivada, por lo que el compilador se resuelve `basObj.z` en el valor de clase base original.</span><span class="sxs-lookup"><span data-stu-id="01050-164">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01050-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01050-165">See also</span></span>

- [<span data-ttu-id="01050-166">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="01050-166">References to Declared Elements</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="01050-167">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="01050-167">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [<span data-ttu-id="01050-168">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="01050-168">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="01050-169">Shadows</span><span class="sxs-lookup"><span data-stu-id="01050-169">Shadows</span></span>](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="01050-170">Invalidaciones</span><span class="sxs-lookup"><span data-stu-id="01050-170">Overrides</span></span>](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [<span data-ttu-id="01050-171">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="01050-171">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="01050-172">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="01050-172">Inheritance Basics</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
