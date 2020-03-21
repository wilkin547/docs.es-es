---
title: Fundamentos de la herencia
ms.date: 07/20/2015
helpviewer_keywords:
- derived classes [Visual Basic], inheritance
- MyClass keyword [Visual Basic], using
- MyBase keyword [Visual Basic], using
- Inherits statement [Visual Basic], inheritance
- overriding, Overridable keyword
- MustInherit keyword [Visual Basic], using
- Overrides keyword [Visual Basic], using
- inheritance
- MustInherit classes [Visual Basic]
- MustOverride keyword [Visual Basic], using
- classes [Visual Basic], derived
- NotInheritable keyword [Visual Basic], using
- base classes [Visual Basic], extending properties and methods [Visual Basic]
- NotOverridable keyword [Visual Basic], using
- base classes [Visual Basic], inheritance
- abstract classes [Visual Basic], inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
ms.openlocfilehash: 89fcf2a14d8938d536aa72628218242811baa1a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401464"
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="32d86-102">Fundamentos de la herencia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32d86-102">Inheritance Basics (Visual Basic)</span></span>

<span data-ttu-id="32d86-103">La `Inherits` instrucción se utiliza para declarar una nueva clase, denominada *clase derivada*, basada en una clase existente, conocida como *clase base.*</span><span class="sxs-lookup"><span data-stu-id="32d86-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="32d86-104">Las clases derivadas heredan y pueden extender las propiedades, métodos, eventos, campos y constantes definidos en la clase base.</span><span class="sxs-lookup"><span data-stu-id="32d86-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="32d86-105">En la siguiente sección se describen algunas de las reglas de herencia y los modificadores que puede usar para cambiar la forma en que las clases heredan o se heredan:</span><span class="sxs-lookup"><span data-stu-id="32d86-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>

- <span data-ttu-id="32d86-106">De forma predeterminada, todas las clases son heredables a menos que estén marcadas con la `NotInheritable` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="32d86-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="32d86-107">Las clases pueden heredar de otras clases del proyecto o de clases de otros ensamblados a los que hace referencia el proyecto.</span><span class="sxs-lookup"><span data-stu-id="32d86-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>

- <span data-ttu-id="32d86-108">A diferencia de los lenguajes que permiten la herencia múltiple, Visual Basic solo permite la herencia única en las clases; es decir, las clases derivadas solo pueden tener una clase base.</span><span class="sxs-lookup"><span data-stu-id="32d86-108">Unlike languages that allow multiple inheritance, Visual Basic allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="32d86-109">Aunque no se permite la herencia múltiple en las clases, las clases pueden implementar varias interfaces, lo que puede lograr eficazmente los mismos fines.</span><span class="sxs-lookup"><span data-stu-id="32d86-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>

- <span data-ttu-id="32d86-110">Para evitar exponer elementos restringidos en una clase base, el tipo de acceso de una clase derivada debe ser igual o más restrictivo que su clase base.</span><span class="sxs-lookup"><span data-stu-id="32d86-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="32d86-111">Por ejemplo, `Public` una clase `Friend` no `Private` puede heredar una o una clase y una `Friend` clase no puede heredar una `Private` clase.</span><span class="sxs-lookup"><span data-stu-id="32d86-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>

## <a name="inheritance-modifiers"></a><span data-ttu-id="32d86-112">Modificadores de herencia</span><span class="sxs-lookup"><span data-stu-id="32d86-112">Inheritance Modifiers</span></span>

<span data-ttu-id="32d86-113">Visual Basic presenta las siguientes instrucciones y modificadores de nivel de clase para admitir la herencia:</span><span class="sxs-lookup"><span data-stu-id="32d86-113">Visual Basic introduces the following class-level statements and modifiers to support inheritance:</span></span>

- <span data-ttu-id="32d86-114">`Inherits`statement — Especifica la clase base.</span><span class="sxs-lookup"><span data-stu-id="32d86-114">`Inherits` statement — Specifies the base class.</span></span>

- <span data-ttu-id="32d86-115">`NotInheritable`modificador: impide que los programadores utilicen la clase como clase base.</span><span class="sxs-lookup"><span data-stu-id="32d86-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>

- <span data-ttu-id="32d86-116">`MustInherit`modificador: especifica que la clase está pensada para su uso únicamente como clase base.</span><span class="sxs-lookup"><span data-stu-id="32d86-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="32d86-117">Las instancias de `MustInherit` clases no se pueden crear directamente; solo se pueden crear como instancias de clase base de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="32d86-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="32d86-118">(Otros lenguajes de programación, como C++ y C, usan el término *clase abstracta* para describir dicha clase.)</span><span class="sxs-lookup"><span data-stu-id="32d86-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>

## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="32d86-119">Propiedades y métodos de invalidación en clases derivadas</span><span class="sxs-lookup"><span data-stu-id="32d86-119">Overriding Properties and Methods in Derived Classes</span></span>

<span data-ttu-id="32d86-120">De forma predeterminada, una clase derivada hereda propiedades y métodos de su clase base.</span><span class="sxs-lookup"><span data-stu-id="32d86-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="32d86-121">Si una propiedad o método heredado tiene que comportarse de forma diferente en la clase derivada, se puede *invalidar.*</span><span class="sxs-lookup"><span data-stu-id="32d86-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="32d86-122">Es decir, puede definir una nueva implementación del método en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="32d86-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="32d86-123">Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:</span><span class="sxs-lookup"><span data-stu-id="32d86-123">The following modifiers are used to control how properties and methods are overridden:</span></span>

- <span data-ttu-id="32d86-124">`Overridable`: permite que una propiedad o método de una clase se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="32d86-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>

- <span data-ttu-id="32d86-125">`Overrides`: reemplaza `Overridable` una propiedad o método definido en la clase base.</span><span class="sxs-lookup"><span data-stu-id="32d86-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>

- <span data-ttu-id="32d86-126">`NotOverridable`: impide que una propiedad o método se invalide en una clase heredada.</span><span class="sxs-lookup"><span data-stu-id="32d86-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="32d86-127">De forma `Public` predeterminada, los métodos son `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="32d86-127">By default, `Public` methods are `NotOverridable`.</span></span>

- <span data-ttu-id="32d86-128">`MustOverride`: requiere que una clase derivada invalide la propiedad o el método.</span><span class="sxs-lookup"><span data-stu-id="32d86-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="32d86-129">Cuando `MustOverride` se utiliza la palabra clave, `Sub`la `Function`definición del método consta solo de la instrucción , , o `Property` .</span><span class="sxs-lookup"><span data-stu-id="32d86-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="32d86-130">No se permiten otras declaraciones, y `End Sub` `End Function` específicamente no hay ninguna declaración o declaración.</span><span class="sxs-lookup"><span data-stu-id="32d86-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="32d86-131">`MustOverride`métodos deben `MustInherit` declararse en clases.</span><span class="sxs-lookup"><span data-stu-id="32d86-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>

<span data-ttu-id="32d86-132">Supongamos que desea definir clases para gestionar el cálculo de la nómina.</span><span class="sxs-lookup"><span data-stu-id="32d86-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="32d86-133">Puede definir una `Payroll` clase genérica `RunPayroll` que contenga un método que calcule el cálculo de la nómina para una semana típica.</span><span class="sxs-lookup"><span data-stu-id="32d86-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="32d86-134">A continuación, `Payroll` podría utilizar como clase `BonusPayroll` base para una clase más especializada, que podría utilizarse al distribuir bonificaciones de empleados.</span><span class="sxs-lookup"><span data-stu-id="32d86-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>

<span data-ttu-id="32d86-135">La `BonusPayroll` clase puede heredar `PayEmployee` e invalidar el `Payroll` método definido en la clase base.</span><span class="sxs-lookup"><span data-stu-id="32d86-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>

<span data-ttu-id="32d86-136">En el ejemplo siguiente `Payroll,` se define una `BonusPayroll`clase base y una `PayEmployee`clase derivada, , que reemplaza un método heredado, .</span><span class="sxs-lookup"><span data-stu-id="32d86-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="32d86-137">`RunPayroll`Un procedimiento, , crea y, a continuación, pasa un `Payroll` objeto y un `BonusPayroll` objeto a una función, `Pay`, que ejecuta el `PayEmployee` método de ambos objetos.</span><span class="sxs-lookup"><span data-stu-id="32d86-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a><span data-ttu-id="32d86-138">La palabra clave MyBase</span><span class="sxs-lookup"><span data-stu-id="32d86-138">The MyBase Keyword</span></span>

<span data-ttu-id="32d86-139">La `MyBase` palabra clave se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase.</span><span class="sxs-lookup"><span data-stu-id="32d86-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="32d86-140">`MyBase`se utiliza con frecuencia para tener acceso a los miembros de la clase base que se reemplazan o sombrean en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="32d86-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="32d86-141">En concreto, `MyBase.New` se utiliza para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="32d86-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>

<span data-ttu-id="32d86-142">Por ejemplo, supongamos que está diseñando una clase derivada que reemplaza un método heredado de la clase base.</span><span class="sxs-lookup"><span data-stu-id="32d86-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="32d86-143">El método invalidado puede llamar al método en la clase base y modificar el valor devuelto como se muestra en el siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="32d86-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

<span data-ttu-id="32d86-144">La siguiente lista describe las `MyBase`restricciones en el uso de:</span><span class="sxs-lookup"><span data-stu-id="32d86-144">The following list describes restrictions on using `MyBase`:</span></span>

- <span data-ttu-id="32d86-145">`MyBase`se refiere a la clase base inmediata y sus miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="32d86-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="32d86-146">No se puede `Private` usar para tener acceso a los miembros de la clase.</span><span class="sxs-lookup"><span data-stu-id="32d86-146">It cannot be used to access `Private` members in the class.</span></span>

- <span data-ttu-id="32d86-147">`MyBase`es una palabra clave, no un objeto real.</span><span class="sxs-lookup"><span data-stu-id="32d86-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="32d86-148">`MyBase`no se puede asignar a una variable, `Is` pasar a procedimientos o utilizarse en una comparación.</span><span class="sxs-lookup"><span data-stu-id="32d86-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="32d86-149">El método `MyBase` que califica no tiene que definirse en la clase base inmediata; en su lugar puede definirse en una clase base hereditaria indirectamente.</span><span class="sxs-lookup"><span data-stu-id="32d86-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="32d86-150">Para que una referencia `MyBase` calificada para compilar correctamente, alguna clase base debe contener un método que coincida con el nombre y los tipos de parámetros que aparecen en la llamada.</span><span class="sxs-lookup"><span data-stu-id="32d86-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>

- <span data-ttu-id="32d86-151">No se `MyBase` puede `MustOverride` utilizar para llamar a métodos de clase base.</span><span class="sxs-lookup"><span data-stu-id="32d86-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>

- <span data-ttu-id="32d86-152">`MyBase`no se puede utilizar para calificarse a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="32d86-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="32d86-153">Por lo tanto, el código siguiente no es válido:</span><span class="sxs-lookup"><span data-stu-id="32d86-153">Therefore, the following code is not valid:</span></span>

  `MyBase.MyBase.BtnOK_Click()`

- <span data-ttu-id="32d86-154">`MyBase`no se puede utilizar en módulos.</span><span class="sxs-lookup"><span data-stu-id="32d86-154">`MyBase` cannot be used in modules.</span></span>

- <span data-ttu-id="32d86-155">`MyBase`no se puede utilizar para tener `Friend` acceso a los miembros de la clase base que están marcados como si la clase base estuviera en un ensamblado diferente.</span><span class="sxs-lookup"><span data-stu-id="32d86-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>

<span data-ttu-id="32d86-156">Para obtener más información y otro ejemplo, vea [Cómo: obtener acceso a una variable oculta por una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="32d86-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>

## <a name="the-myclass-keyword"></a><span data-ttu-id="32d86-157">La palabra clave MyClass</span><span class="sxs-lookup"><span data-stu-id="32d86-157">The MyClass Keyword</span></span>

<span data-ttu-id="32d86-158">La `MyClass` palabra clave se comporta como una variable de objeto que hace referencia a la instancia actual de una clase como implementada originalmente.</span><span class="sxs-lookup"><span data-stu-id="32d86-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="32d86-159">`MyClass`se `Me`asemeja , pero cada `MyClass` método y propiedad en la que se llama se trata como si el método o la propiedad [fueraNotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span><span class="sxs-lookup"><span data-stu-id="32d86-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="32d86-160">Por lo tanto, el método o propiedad no se ve afectada por la invalidación en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="32d86-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>

- <span data-ttu-id="32d86-161">`MyClass`es una palabra clave, no un objeto real.</span><span class="sxs-lookup"><span data-stu-id="32d86-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="32d86-162">`MyClass`no se puede asignar a una variable, `Is` pasar a procedimientos o utilizarse en una comparación.</span><span class="sxs-lookup"><span data-stu-id="32d86-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="32d86-163">`MyClass`se refiere a la clase contenedora y sus miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="32d86-163">`MyClass` refers to the containing class and its inherited members.</span></span>

- <span data-ttu-id="32d86-164">`MyClass`se puede utilizar como `Shared` calificador para los miembros.</span><span class="sxs-lookup"><span data-stu-id="32d86-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>

- <span data-ttu-id="32d86-165">`MyClass`no se puede `Shared` utilizar dentro de un método, pero se puede utilizar dentro de un método de instancia para tener acceso a un miembro compartido de una clase.</span><span class="sxs-lookup"><span data-stu-id="32d86-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>

- <span data-ttu-id="32d86-166">`MyClass`no se puede utilizar en módulos estándar.</span><span class="sxs-lookup"><span data-stu-id="32d86-166">`MyClass` cannot be used in standard modules.</span></span>

- <span data-ttu-id="32d86-167">`MyClass`se puede usar para calificar un método que se define en una clase base y que no tiene ninguna implementación del método proporcionado en esa clase.</span><span class="sxs-lookup"><span data-stu-id="32d86-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="32d86-168">Dicha referencia tiene el `MyBase.`mismo significado que *Method*.</span><span class="sxs-lookup"><span data-stu-id="32d86-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>

<span data-ttu-id="32d86-169">En el ejemplo `Me` `MyClass`siguiente se comparan y .</span><span class="sxs-lookup"><span data-stu-id="32d86-169">The following example compares `Me` and `MyClass`.</span></span>

```vb
Class baseClass
    Public Overridable Sub testMethod()
        MsgBox("Base class string")
    End Sub
    Public Sub useMe()
        ' The following call uses the calling class's method, even if
        ' that method is an override.
        Me.testMethod()
    End Sub
    Public Sub useMyClass()
        ' The following call uses this instance's method and not any
        ' override.
        MyClass.testMethod()
    End Sub
End Class
Class derivedClass : Inherits baseClass
    Public Overrides Sub testMethod()
        MsgBox("Derived class string")
    End Sub
End Class
Class testClasses
    Sub startHere()
        Dim testObj As derivedClass = New derivedClass()
        ' The following call displays "Derived class string".
        testObj.useMe()
        ' The following call displays "Base class string".
        testObj.useMyClass()
    End Sub
End Class
```

<span data-ttu-id="32d86-170">Aunque `derivedClass` invalida `testMethod`, `MyClass` la `useMyClass` palabra clave en anula los efectos de invalidación y `testMethod`el compilador resuelve la llamada a la versión de clase base de .</span><span class="sxs-lookup"><span data-stu-id="32d86-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>

## <a name="see-also"></a><span data-ttu-id="32d86-171">Consulte también</span><span class="sxs-lookup"><span data-stu-id="32d86-171">See also</span></span>

- [<span data-ttu-id="32d86-172">Inherits (instrucción)</span><span class="sxs-lookup"><span data-stu-id="32d86-172">Inherits Statement</span></span>](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="32d86-173">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="32d86-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
