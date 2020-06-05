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
ms.openlocfilehash: 7d76e2e7398c2f954ff4274f77ffa350efbd3617
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410752"
---
# <a name="shadowing-in-visual-basic"></a><span data-ttu-id="efa44-102">Sombrear en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="efa44-102">Shadowing in Visual Basic</span></span>
<span data-ttu-id="efa44-103">Cuando dos elementos de programación comparten el mismo nombre, uno de ellos puede ocultar, o *sombrear*, el otro.</span><span class="sxs-lookup"><span data-stu-id="efa44-103">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="efa44-104">En tal situación, el elemento sombreado no está disponible como referencia; en su lugar, cuando el código usa el nombre del elemento, el compilador Visual Basic lo resuelve en el elemento de sombreado.</span><span class="sxs-lookup"><span data-stu-id="efa44-104">In such a situation, the shadowed element is not available for reference; instead, when your code uses the element name, the Visual Basic compiler resolves it to the shadowing element.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="efa44-105">Propósito</span><span class="sxs-lookup"><span data-stu-id="efa44-105">Purpose</span></span>  
 <span data-ttu-id="efa44-106">El propósito principal de la sombra es proteger la definición de los miembros de clase.</span><span class="sxs-lookup"><span data-stu-id="efa44-106">The main purpose of shadowing is to protect the definition of your class members.</span></span> <span data-ttu-id="efa44-107">La clase base puede someterse a un cambio que crea un elemento con el mismo nombre que el que ya se ha definido.</span><span class="sxs-lookup"><span data-stu-id="efa44-107">The base class might undergo a change that creates an element with the same name as one you have already defined.</span></span> <span data-ttu-id="efa44-108">Si esto ocurre, el `Shadows` modificador fuerza las referencias a través de la clase para que se resuelvan en el miembro definido, en lugar de en el nuevo elemento de clase base.</span><span class="sxs-lookup"><span data-stu-id="efa44-108">If this happens, the `Shadows` modifier forces references through your class to be resolved to the member you defined, instead of to the new base class element.</span></span>  
  
## <a name="types-of-shadowing"></a><span data-ttu-id="efa44-109">Tipos de sombreado</span><span class="sxs-lookup"><span data-stu-id="efa44-109">Types of Shadowing</span></span>  
 <span data-ttu-id="efa44-110">Un elemento puede prevalecer sobre otro elemento de dos maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="efa44-110">An element can shadow another element in two different ways.</span></span> <span data-ttu-id="efa44-111">El elemento de sombreado se puede declarar dentro de una subregión de la región que contiene el elemento sombreado, en cuyo caso la sombra se logra *a través del ámbito*.</span><span class="sxs-lookup"><span data-stu-id="efa44-111">The shadowing element can be declared inside a subregion of the region containing the shadowed element, in which case the shadowing is accomplished *through scope*.</span></span> <span data-ttu-id="efa44-112">O una clase derivada puede volver a definir un miembro de una clase base, en cuyo caso la sombra se realiza *a través*de la herencia.</span><span class="sxs-lookup"><span data-stu-id="efa44-112">Or a deriving class can redefine a member of a base class, in which case the shadowing is done *through inheritance*.</span></span>  
  
### <a name="shadowing-through-scope"></a><span data-ttu-id="efa44-113">Sombreado a través del ámbito</span><span class="sxs-lookup"><span data-stu-id="efa44-113">Shadowing Through Scope</span></span>  
 <span data-ttu-id="efa44-114">Es posible que los elementos de programación del mismo módulo, clase o estructura tengan el mismo nombre pero con un ámbito diferente.</span><span class="sxs-lookup"><span data-stu-id="efa44-114">It is possible for programming elements in the same module, class, or structure to have the same name but different scope.</span></span> <span data-ttu-id="efa44-115">Cuando dos elementos se declaran de esta manera y el código hace referencia al nombre que comparten, el elemento con el ámbito más estrecho prevalece sobre el otro elemento (el ámbito de bloque es el más estrecho).</span><span class="sxs-lookup"><span data-stu-id="efa44-115">When two elements are declared in this manner and the code refers to the name they share, the element with the narrower scope shadows the other element (block scope is the narrowest).</span></span>  
  
 <span data-ttu-id="efa44-116">Por ejemplo, un módulo puede definir una `Public` variable denominada `temp` y un procedimiento dentro del módulo puede declarar una variable local denominada también `temp` .</span><span class="sxs-lookup"><span data-stu-id="efa44-116">For example, a module can define a `Public` variable named `temp`, and a procedure within the module can declare a local variable also named `temp`.</span></span> <span data-ttu-id="efa44-117">Las referencias a `temp` desde dentro del procedimiento obtienen acceso a la variable local, mientras que las referencias a `temp` desde fuera del procedimiento tienen acceso a la `Public` variable.</span><span class="sxs-lookup"><span data-stu-id="efa44-117">References to `temp` from within the procedure access the local variable, while references to `temp` from outside the procedure access the `Public` variable.</span></span> <span data-ttu-id="efa44-118">En este caso, la variable de procedimiento `temp` prevalece sobre la variable de módulo `temp` .</span><span class="sxs-lookup"><span data-stu-id="efa44-118">In this case, the procedure variable `temp` shadows the module variable `temp`.</span></span>  
  
 <span data-ttu-id="efa44-119">En la ilustración siguiente se muestran dos variables, denominadas `temp` .</span><span class="sxs-lookup"><span data-stu-id="efa44-119">The following illustration shows two variables, both named `temp`.</span></span> <span data-ttu-id="efa44-120">La variable local `temp` prevalece sobre la variable miembro `temp` cuando se tiene acceso a ella desde dentro de su propio procedimiento `p` .</span><span class="sxs-lookup"><span data-stu-id="efa44-120">The local variable `temp` shadows the member variable `temp` when accessed from within its own procedure `p`.</span></span> <span data-ttu-id="efa44-121">Sin embargo, la `MyClass` palabra clave omite el sombreado y obtiene acceso a la variable miembro.</span><span class="sxs-lookup"><span data-stu-id="efa44-121">However, the `MyClass` keyword bypasses the shadowing and accesses the member variable.</span></span>  
  
 ![Gráfico que muestra el sombreado en el ámbito.](./media/shadowing/shadow-scope-diagram.gif)
  
 <span data-ttu-id="efa44-123">Para obtener un ejemplo de sombreado a través del ámbito, consulte [Cómo: ocultar una variable con el mismo nombre que la variable](how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span><span class="sxs-lookup"><span data-stu-id="efa44-123">For an example of shadowing through scope, see [How to: Hide a Variable with the Same Name as Your Variable](how-to-hide-a-variable-with-the-same-name-as-your-variable.md).</span></span>  
  
### <a name="shadowing-through-inheritance"></a><span data-ttu-id="efa44-124">Sombrear a través de la herencia</span><span class="sxs-lookup"><span data-stu-id="efa44-124">Shadowing Through Inheritance</span></span>  
 <span data-ttu-id="efa44-125">Si una clase derivada vuelve a definir un elemento de programación heredado de una clase base, el elemento que se va a redefinir prevalecerá sobre el elemento original.</span><span class="sxs-lookup"><span data-stu-id="efa44-125">If a derived class redefines a programming element inherited from a base class, the redefining element shadows the original element.</span></span> <span data-ttu-id="efa44-126">Puede sombrear cualquier tipo de elemento declarado, o bien un conjunto de elementos sobrecargados, con cualquier otro tipo.</span><span class="sxs-lookup"><span data-stu-id="efa44-126">You can shadow any type of declared element, or set of overloaded elements, with any other type.</span></span> <span data-ttu-id="efa44-127">Por ejemplo, una `Integer` variable puede prevalecer sobre un `Function` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="efa44-127">For example, an `Integer` variable can shadow a `Function` procedure.</span></span> <span data-ttu-id="efa44-128">Si sombrea un procedimiento con otro procedimiento, puede usar una lista de parámetros diferente y un tipo de valor devuelto diferente.</span><span class="sxs-lookup"><span data-stu-id="efa44-128">If you shadow a procedure with another procedure, you can use a different parameter list and a different return type.</span></span>  
  
 <span data-ttu-id="efa44-129">En la ilustración siguiente se muestra una clase base `b` y una clase derivada `d` que hereda de `b` .</span><span class="sxs-lookup"><span data-stu-id="efa44-129">The following illustration shows a base class `b` and a derived class `d` that inherits from `b`.</span></span> <span data-ttu-id="efa44-130">La clase base define un procedimiento denominado `proc` y la clase derivada lo sombrea con otro procedimiento con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="efa44-130">The base class defines a procedure named `proc`, and the derived class shadows it with another procedure of the same name.</span></span> <span data-ttu-id="efa44-131">La primera `Call` instrucción tiene acceso al sombreado `proc` en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="efa44-131">The first `Call` statement accesses the shadowing `proc` in the derived class.</span></span> <span data-ttu-id="efa44-132">Sin embargo, la `MyBase` palabra clave omite el sombreado y obtiene acceso al procedimiento sombreado en la clase base.</span><span class="sxs-lookup"><span data-stu-id="efa44-132">However, the `MyBase` keyword bypasses the shadowing and accesses the shadowed procedure in the base class.</span></span>  
  
 ![Diagrama gráfico de sombreado por herencia](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 <span data-ttu-id="efa44-134">Para obtener un ejemplo de sombreado a través de la herencia, vea [Cómo: ocultar una variable con el mismo nombre que la variable](how-to-hide-a-variable-with-the-same-name-as-your-variable.md) y [Cómo: ocultar una variable heredada](how-to-hide-an-inherited-variable.md).</span><span class="sxs-lookup"><span data-stu-id="efa44-134">For an example of shadowing through inheritance, see [How to: Hide a Variable with the Same Name as Your Variable](how-to-hide-a-variable-with-the-same-name-as-your-variable.md) and [How to: Hide an Inherited Variable](how-to-hide-an-inherited-variable.md).</span></span>  
  
#### <a name="shadowing-and-access-level"></a><span data-ttu-id="efa44-135">Nivel de acceso y sombreado</span><span class="sxs-lookup"><span data-stu-id="efa44-135">Shadowing and Access Level</span></span>  
 <span data-ttu-id="efa44-136">No siempre se puede obtener acceso al elemento de sombreado desde el código mediante la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="efa44-136">The shadowing element is not always accessible from the code using the derived class.</span></span> <span data-ttu-id="efa44-137">Por ejemplo, podría declararse `Private` .</span><span class="sxs-lookup"><span data-stu-id="efa44-137">For example, it might be declared `Private`.</span></span> <span data-ttu-id="efa44-138">En tal caso, la sombra es derrotada y el compilador resuelve cualquier referencia al mismo elemento que tendría si no hubiese ninguna sombra.</span><span class="sxs-lookup"><span data-stu-id="efa44-138">In such a case, shadowing is defeated and the compiler resolves any reference to the same element it would have if there had been no shadowing.</span></span> <span data-ttu-id="efa44-139">Este elemento es el elemento accesible el menos pasos de derivación hacia atrás desde la clase de sombreado.</span><span class="sxs-lookup"><span data-stu-id="efa44-139">This element is the accessible element the fewest derivational steps backward from the shadowing class.</span></span> <span data-ttu-id="efa44-140">Si el elemento sombreado es un procedimiento, la resolución es a la versión accesible más cercana con el mismo nombre, lista de parámetros y tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="efa44-140">If the shadowed element is a procedure, the resolution is to the closest accessible version with the same name, parameter list, and return type.</span></span>  
  
 <span data-ttu-id="efa44-141">En el ejemplo siguiente se muestra una jerarquía de herencia de tres clases.</span><span class="sxs-lookup"><span data-stu-id="efa44-141">The following example shows an inheritance hierarchy of three classes.</span></span> <span data-ttu-id="efa44-142">Cada clase define un `Sub` procedimiento `display` y cada clase derivada sombrea el `display` procedimiento en su clase base.</span><span class="sxs-lookup"><span data-stu-id="efa44-142">Each class defines a `Sub` procedure `display`, and each derived class shadows the `display` procedure in its base class.</span></span>  
  
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
  
 <span data-ttu-id="efa44-143">En el ejemplo anterior, la clase derivada `secondClass` prevalece sobre `display` un `Private` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="efa44-143">In the preceding example, the derived class `secondClass` shadows `display` with a `Private` procedure.</span></span> <span data-ttu-id="efa44-144">Cuando `callDisplay` el módulo llama a `display` en `secondClass` , el código de llamada está fuera `secondClass` y, por tanto, no puede tener acceso al `display` procedimiento privado.</span><span class="sxs-lookup"><span data-stu-id="efa44-144">When module `callDisplay` calls `display` in `secondClass`, the calling code is outside `secondClass` and therefore cannot access the private `display` procedure.</span></span> <span data-ttu-id="efa44-145">La sombra es derrotada y el compilador resuelve la referencia al procedimiento de la clase base `display` .</span><span class="sxs-lookup"><span data-stu-id="efa44-145">Shadowing is defeated, and the compiler resolves the reference to the base class `display` procedure.</span></span>  
  
 <span data-ttu-id="efa44-146">Sin embargo, la clase derivada adicional `thirdClass` declara `display` como `Public` , por lo que el código de `callDisplay` puede tener acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="efa44-146">However, the further derived class `thirdClass` declares `display` as `Public`, so the code in `callDisplay` can access it.</span></span>  
  
## <a name="shadowing-and-overriding"></a><span data-ttu-id="efa44-147">Sombrear e invalidar</span><span class="sxs-lookup"><span data-stu-id="efa44-147">Shadowing and Overriding</span></span>  
 <span data-ttu-id="efa44-148">No confunda el sombreado con la invalidación.</span><span class="sxs-lookup"><span data-stu-id="efa44-148">Do not confuse shadowing with overriding.</span></span> <span data-ttu-id="efa44-149">Ambos se usan cuando una clase derivada hereda de una clase base y ambos vuelven a definir un elemento declarado con otro.</span><span class="sxs-lookup"><span data-stu-id="efa44-149">Both are used when a derived class inherits from a base class, and both redefine one declared element with another.</span></span> <span data-ttu-id="efa44-150">Pero hay diferencias significativas entre los dos.</span><span class="sxs-lookup"><span data-stu-id="efa44-150">But there are significant differences between the two.</span></span> <span data-ttu-id="efa44-151">Para obtener una comparación, vea [diferencias entre la sombra y el reemplazo](differences-between-shadowing-and-overriding.md).</span><span class="sxs-lookup"><span data-stu-id="efa44-151">For a comparison, see [Differences Between Shadowing and Overriding](differences-between-shadowing-and-overriding.md).</span></span>  
  
## <a name="shadowing-and-overloading"></a><span data-ttu-id="efa44-152">Sombreado y sobrecarga</span><span class="sxs-lookup"><span data-stu-id="efa44-152">Shadowing and Overloading</span></span>  
 <span data-ttu-id="efa44-153">Si sombrea el mismo elemento de clase base con más de un elemento en la clase derivada, los elementos de sombreado pasan a ser versiones sobrecargadas de ese elemento.</span><span class="sxs-lookup"><span data-stu-id="efa44-153">If you shadow the same base class element with more than one element in your derived class, the shadowing elements become overloaded versions of that element.</span></span> <span data-ttu-id="efa44-154">Para obtener más información, consulta [Procedure Overloading](../procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="efa44-154">For more information, see [Procedure Overloading](../procedures/procedure-overloading.md).</span></span>  
  
## <a name="accessing-a-shadowed-element"></a><span data-ttu-id="efa44-155">Obtener acceso a un elemento con sombra</span><span class="sxs-lookup"><span data-stu-id="efa44-155">Accessing a Shadowed Element</span></span>  
 <span data-ttu-id="efa44-156">Al tener acceso a un elemento desde una clase derivada, normalmente lo hace a través de la instancia actual de esa clase derivada, calificando el nombre del elemento con la `Me` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="efa44-156">When you access an element from a derived class, you normally do so through the current instance of that derived class, by qualifying the element name with the `Me` keyword.</span></span> <span data-ttu-id="efa44-157">Si la clase derivada sombrea el elemento en la clase base, puede tener acceso al elemento de clase base si lo califica con la `MyBase` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="efa44-157">If your derived class shadows the element in the base class, you can access the base class element by qualifying it with the `MyBase` keyword.</span></span>  
  
 <span data-ttu-id="efa44-158">Para obtener un ejemplo de acceso a un elemento con sombra, vea [Cómo: obtener acceso a una variable oculta por una clase derivada](how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="efa44-158">For an example of accessing a shadowed element, see [How to: Access a Variable Hidden by a Derived Class](how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
### <a name="declaration-of-the-object-variable"></a><span data-ttu-id="efa44-159">Declaración de la variable de objeto</span><span class="sxs-lookup"><span data-stu-id="efa44-159">Declaration of the Object Variable</span></span>  
 <span data-ttu-id="efa44-160">La forma de crear la variable de objeto también puede afectar a si la clase derivada tiene acceso a un elemento de sombreado o al elemento sombreado.</span><span class="sxs-lookup"><span data-stu-id="efa44-160">How you create the object variable can also affect whether the derived class accesses a shadowing element or the shadowed element.</span></span> <span data-ttu-id="efa44-161">En el ejemplo siguiente se crean dos objetos a partir de una clase derivada, pero un objeto se declara como la clase base y el otro como la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="efa44-161">The following example creates two objects from a derived class, but one object is declared as the base class and the other as the derived class.</span></span>  
  
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
  
 <span data-ttu-id="efa44-162">En el ejemplo anterior, la variable `basObj` se declara como la clase base.</span><span class="sxs-lookup"><span data-stu-id="efa44-162">In the preceding example, the variable `basObj` is declared as the base class.</span></span> <span data-ttu-id="efa44-163">Asignar un `dervCls` objeto a él constituye una conversión de ampliación y, por tanto, es válida.</span><span class="sxs-lookup"><span data-stu-id="efa44-163">Assigning a `dervCls` object to it constitutes a widening conversion and is therefore valid.</span></span> <span data-ttu-id="efa44-164">Sin embargo, la clase base no puede tener acceso a la versión de sombreado de la variable `z` en la clase derivada, por lo que el compilador se resuelve `basObj.z` en el valor de la clase base original.</span><span class="sxs-lookup"><span data-stu-id="efa44-164">However, the base class cannot access the shadowing version of the variable `z` in the derived class, so the compiler resolves `basObj.z` to the original base class value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa44-165">Consulte también</span><span class="sxs-lookup"><span data-stu-id="efa44-165">See also</span></span>

- [<span data-ttu-id="efa44-166">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="efa44-166">References to Declared Elements</span></span>](references-to-declared-elements.md)
- [<span data-ttu-id="efa44-167">Ámbito en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="efa44-167">Scope in Visual Basic</span></span>](scope.md)
- [<span data-ttu-id="efa44-168">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="efa44-168">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="efa44-169">Shadows</span><span class="sxs-lookup"><span data-stu-id="efa44-169">Shadows</span></span>](../../../language-reference/modifiers/shadows.md)
- [<span data-ttu-id="efa44-170">Invalidaciones</span><span class="sxs-lookup"><span data-stu-id="efa44-170">Overrides</span></span>](../../../language-reference/modifiers/overrides.md)
- [<span data-ttu-id="efa44-171">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="efa44-171">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="efa44-172">Fundamentos de la herencia</span><span class="sxs-lookup"><span data-stu-id="efa44-172">Inheritance Basics</span></span>](../objects-and-classes/inheritance-basics.md)
