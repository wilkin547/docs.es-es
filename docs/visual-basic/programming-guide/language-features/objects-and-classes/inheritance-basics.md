---
title: Fundamentos de la herencia (Visual Basic)
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
ms.openlocfilehash: 8a75b75ef9acb4c89f4c7d05f1410d4ca70e680b
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582747"
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="0446f-102">Fundamentos de la herencia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0446f-102">Inheritance Basics (Visual Basic)</span></span>

<span data-ttu-id="0446f-103">La instrucción `Inherits` se utiliza para declarar una nueva clase, denominada *clase derivada*, basada en una clase existente, conocida como *clase base*.</span><span class="sxs-lookup"><span data-stu-id="0446f-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="0446f-104">Las clases derivadas heredan y pueden extender las propiedades, los métodos, los eventos, los campos y las constantes definidos en la clase base.</span><span class="sxs-lookup"><span data-stu-id="0446f-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="0446f-105">En la sección siguiente se describen algunas de las reglas de herencia y los modificadores que se pueden usar para cambiar la forma en que las clases heredan o se heredan:</span><span class="sxs-lookup"><span data-stu-id="0446f-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>

- <span data-ttu-id="0446f-106">De forma predeterminada, todas las clases se pueden heredar a menos que estén marcadas con la palabra clave `NotInheritable`.</span><span class="sxs-lookup"><span data-stu-id="0446f-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="0446f-107">Las clases pueden heredar de otras clases del proyecto o de clases de otros ensamblados a los que hace referencia el proyecto.</span><span class="sxs-lookup"><span data-stu-id="0446f-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>

- <span data-ttu-id="0446f-108">A diferencia de los lenguajes que permiten la herencia múltiple, Visual Basic solo permite la herencia única en las clases; es decir, las clases derivadas solo pueden tener una clase base.</span><span class="sxs-lookup"><span data-stu-id="0446f-108">Unlike languages that allow multiple inheritance, Visual Basic allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="0446f-109">Aunque no se permite la herencia múltiple en las clases, las clases pueden implementar varias interfaces, lo que puede lograr de forma eficaz los mismos extremos.</span><span class="sxs-lookup"><span data-stu-id="0446f-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>

- <span data-ttu-id="0446f-110">Para evitar la exposición de elementos restringidos en una clase base, el tipo de acceso de una clase derivada debe ser igual o más restrictivo que su clase base.</span><span class="sxs-lookup"><span data-stu-id="0446f-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="0446f-111">Por ejemplo, una clase `Public` no puede heredar un `Friend` o una clase `Private`, y una clase `Friend` no puede heredar una clase `Private`.</span><span class="sxs-lookup"><span data-stu-id="0446f-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>

## <a name="inheritance-modifiers"></a><span data-ttu-id="0446f-112">Modificadores de herencia</span><span class="sxs-lookup"><span data-stu-id="0446f-112">Inheritance Modifiers</span></span>

<span data-ttu-id="0446f-113">Visual Basic presenta las siguientes instrucciones y modificadores de nivel de clase para admitir la herencia:</span><span class="sxs-lookup"><span data-stu-id="0446f-113">Visual Basic introduces the following class-level statements and modifiers to support inheritance:</span></span>

- <span data-ttu-id="0446f-114">instrucción `Inherits`: especifica la clase base.</span><span class="sxs-lookup"><span data-stu-id="0446f-114">`Inherits` statement — Specifies the base class.</span></span>

- <span data-ttu-id="0446f-115">`NotInheritable` modificador: impide que los programadores usen la clase como clase base.</span><span class="sxs-lookup"><span data-stu-id="0446f-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>

- <span data-ttu-id="0446f-116">`MustInherit` modificador: especifica que la clase está pensada para usarse solo como una clase base.</span><span class="sxs-lookup"><span data-stu-id="0446f-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="0446f-117">Las instancias de clases de `MustInherit` no se pueden crear directamente. solo se pueden crear como instancias de clase base de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="0446f-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="0446f-118">(Otros lenguajes de programación, C++ como C#y, usan el término *clase abstracta* para describir este tipo de clase).</span><span class="sxs-lookup"><span data-stu-id="0446f-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>

## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="0446f-119">Reemplazar propiedades y métodos en clases derivadas</span><span class="sxs-lookup"><span data-stu-id="0446f-119">Overriding Properties and Methods in Derived Classes</span></span>

<span data-ttu-id="0446f-120">De forma predeterminada, una clase derivada hereda propiedades y métodos de su clase base.</span><span class="sxs-lookup"><span data-stu-id="0446f-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="0446f-121">Si una propiedad o un método heredado tienen que comportarse de forma diferente en la clase derivada, se puede *invalidar*.</span><span class="sxs-lookup"><span data-stu-id="0446f-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="0446f-122">Es decir, puede definir una nueva implementación del método en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="0446f-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="0446f-123">Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:</span><span class="sxs-lookup"><span data-stu-id="0446f-123">The following modifiers are used to control how properties and methods are overridden:</span></span>

- <span data-ttu-id="0446f-124">`Overridable`: permite que una propiedad o un método de una clase se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="0446f-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>

- <span data-ttu-id="0446f-125">`Overrides`: reemplaza una propiedad de `Overridable` o un método definido en la clase base.</span><span class="sxs-lookup"><span data-stu-id="0446f-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>

- <span data-ttu-id="0446f-126">`NotOverridable`: impide que una propiedad o un método se invalide en una clase heredada.</span><span class="sxs-lookup"><span data-stu-id="0446f-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="0446f-127">De forma predeterminada, `Public` métodos son `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="0446f-127">By default, `Public` methods are `NotOverridable`.</span></span>

- <span data-ttu-id="0446f-128">`MustOverride`: requiere que una clase derivada invalide la propiedad o el método.</span><span class="sxs-lookup"><span data-stu-id="0446f-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="0446f-129">Cuando se usa la palabra clave `MustOverride`, la definición del método consta únicamente de la instrucción `Sub`, `Function` o `Property`.</span><span class="sxs-lookup"><span data-stu-id="0446f-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="0446f-130">No se permiten otras instrucciones y, en concreto, no hay ninguna instrucción `End Sub` o `End Function`.</span><span class="sxs-lookup"><span data-stu-id="0446f-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="0446f-131">`MustOverride` métodos deben declararse en clases `MustInherit`.</span><span class="sxs-lookup"><span data-stu-id="0446f-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>

<span data-ttu-id="0446f-132">Supongamos que desea definir clases para controlar la nómina.</span><span class="sxs-lookup"><span data-stu-id="0446f-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="0446f-133">Puede definir una clase `Payroll` genérica que contenga un método `RunPayroll` que calcule la nómina para una semana típica.</span><span class="sxs-lookup"><span data-stu-id="0446f-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="0446f-134">Después, podría utilizar `Payroll` como una clase base para una clase `BonusPayroll` más especializada, que podría usarse al distribuir las primas de los empleados.</span><span class="sxs-lookup"><span data-stu-id="0446f-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>

<span data-ttu-id="0446f-135">La clase `BonusPayroll` puede heredar, e invalidar, el método `PayEmployee` definido en la clase base `Payroll`.</span><span class="sxs-lookup"><span data-stu-id="0446f-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>

<span data-ttu-id="0446f-136">En el ejemplo siguiente se define una clase base, `Payroll,` y una clase derivada, `BonusPayroll`, que invalida un método heredado, `PayEmployee`.</span><span class="sxs-lookup"><span data-stu-id="0446f-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="0446f-137">Un procedimiento, `RunPayroll`, crea y, a continuación, pasa un objeto `Payroll` y un objeto `BonusPayroll` a una función, `Pay`, que ejecuta el método `PayEmployee` de ambos objetos.</span><span class="sxs-lookup"><span data-stu-id="0446f-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a><span data-ttu-id="0446f-138">La palabra clave MyBase</span><span class="sxs-lookup"><span data-stu-id="0446f-138">The MyBase Keyword</span></span>

<span data-ttu-id="0446f-139">La palabra clave `MyBase` se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase.</span><span class="sxs-lookup"><span data-stu-id="0446f-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="0446f-140">`MyBase` se usa con frecuencia para tener acceso a los miembros de clase base que se invalidan o se sombrean en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="0446f-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="0446f-141">En concreto, `MyBase.New` se usa para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="0446f-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>

<span data-ttu-id="0446f-142">Por ejemplo, supongamos que está diseñando una clase derivada que reemplaza un método heredado de la clase base.</span><span class="sxs-lookup"><span data-stu-id="0446f-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="0446f-143">El método invalidado puede llamar al método de la clase base y modificar el valor devuelto como se muestra en el siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="0446f-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

<span data-ttu-id="0446f-144">En la lista siguiente se describen las restricciones en el uso de `MyBase`:</span><span class="sxs-lookup"><span data-stu-id="0446f-144">The following list describes restrictions on using `MyBase`:</span></span>

- <span data-ttu-id="0446f-145">`MyBase` hace referencia a la clase base inmediata y a sus miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="0446f-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="0446f-146">No se puede usar para tener acceso a `Private` miembros en la clase.</span><span class="sxs-lookup"><span data-stu-id="0446f-146">It cannot be used to access `Private` members in the class.</span></span>

- <span data-ttu-id="0446f-147">`MyBase` es una palabra clave, no un objeto real.</span><span class="sxs-lookup"><span data-stu-id="0446f-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="0446f-148">`MyBase` no se puede asignar a una variable, se puede pasar a procedimientos o usarse en una comparación de `Is`.</span><span class="sxs-lookup"><span data-stu-id="0446f-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="0446f-149">No es necesario definir el método que `MyBase` califica en la clase base inmediata; en su lugar, se puede definir en una clase base heredada indirectamente.</span><span class="sxs-lookup"><span data-stu-id="0446f-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="0446f-150">Para que una referencia calificada por `MyBase` se compile correctamente, alguna clase base debe contener un método que coincida con el nombre y los tipos de parámetros que aparecen en la llamada.</span><span class="sxs-lookup"><span data-stu-id="0446f-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>

- <span data-ttu-id="0446f-151">No se puede usar `MyBase` para llamar a métodos de clase base `MustOverride`.</span><span class="sxs-lookup"><span data-stu-id="0446f-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>

- <span data-ttu-id="0446f-152">no se puede usar `MyBase` para calificarse a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="0446f-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="0446f-153">Por lo tanto, el código siguiente no es válido:</span><span class="sxs-lookup"><span data-stu-id="0446f-153">Therefore, the following code is not valid:</span></span>

  `MyBase.MyBase.BtnOK_Click()`

- <span data-ttu-id="0446f-154">no se puede usar `MyBase` en módulos.</span><span class="sxs-lookup"><span data-stu-id="0446f-154">`MyBase` cannot be used in modules.</span></span>

- <span data-ttu-id="0446f-155">no se puede usar `MyBase` para tener acceso a los miembros de clase base marcados como `Friend` si la clase base está en un ensamblado diferente.</span><span class="sxs-lookup"><span data-stu-id="0446f-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>

<span data-ttu-id="0446f-156">Para obtener más información y otro ejemplo, vea [Cómo: obtener acceso a una variable oculta por una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="0446f-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>

## <a name="the-myclass-keyword"></a><span data-ttu-id="0446f-157">La palabra clave MyClass</span><span class="sxs-lookup"><span data-stu-id="0446f-157">The MyClass Keyword</span></span>

<span data-ttu-id="0446f-158">La palabra clave `MyClass` se comporta como una variable de objeto que hace referencia a la instancia actual de una clase como se implementó originalmente.</span><span class="sxs-lookup"><span data-stu-id="0446f-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="0446f-159">`MyClass` es similar a `Me`, pero todas las llamadas de método y propiedad en `MyClass` se tratan como si el método o la propiedad fueran [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span><span class="sxs-lookup"><span data-stu-id="0446f-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="0446f-160">Por lo tanto, el método o la propiedad no se ven afectados por el reemplazo en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="0446f-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>

- <span data-ttu-id="0446f-161">`MyClass` es una palabra clave, no un objeto real.</span><span class="sxs-lookup"><span data-stu-id="0446f-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="0446f-162">`MyClass` no se puede asignar a una variable, se puede pasar a procedimientos o usarse en una comparación de `Is`.</span><span class="sxs-lookup"><span data-stu-id="0446f-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="0446f-163">`MyClass` hace referencia a la clase contenedora y a sus miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="0446f-163">`MyClass` refers to the containing class and its inherited members.</span></span>

- <span data-ttu-id="0446f-164">`MyClass` puede usarse como calificador para `Shared` miembros.</span><span class="sxs-lookup"><span data-stu-id="0446f-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>

- <span data-ttu-id="0446f-165">`MyClass` no se puede usar dentro de un método de `Shared`, pero se puede usar dentro de un método de instancia para tener acceso a un miembro compartido de una clase.</span><span class="sxs-lookup"><span data-stu-id="0446f-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>

- <span data-ttu-id="0446f-166">no se puede usar `MyClass` en módulos estándar.</span><span class="sxs-lookup"><span data-stu-id="0446f-166">`MyClass` cannot be used in standard modules.</span></span>

- <span data-ttu-id="0446f-167">`MyClass` puede usarse para calificar un método que se define en una clase base y que no tiene ninguna implementación del método proporcionado en esa clase.</span><span class="sxs-lookup"><span data-stu-id="0446f-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="0446f-168">Este tipo de referencia tiene el mismo significado que `MyBase.`*método*.</span><span class="sxs-lookup"><span data-stu-id="0446f-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>

<span data-ttu-id="0446f-169">En el ejemplo siguiente se comparan `Me` y `MyClass`.</span><span class="sxs-lookup"><span data-stu-id="0446f-169">The following example compares `Me` and `MyClass`.</span></span>

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

<span data-ttu-id="0446f-170">Aunque `derivedClass` invalidaciones `testMethod`, la palabra clave `MyClass` en `useMyClass` anula los efectos de la invalidación, y el compilador resuelve la llamada a la versión de la clase base de `testMethod`.</span><span class="sxs-lookup"><span data-stu-id="0446f-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0446f-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="0446f-171">See also</span></span>

- [<span data-ttu-id="0446f-172">Inherits (instrucción)</span><span class="sxs-lookup"><span data-stu-id="0446f-172">Inherits Statement</span></span>](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="0446f-173">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="0446f-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
