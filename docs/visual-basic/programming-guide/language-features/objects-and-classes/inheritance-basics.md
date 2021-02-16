---
description: 'Más información acerca de: conceptos básicos de herencia (Visual Basic)'
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
ms.openlocfilehash: facaa9a21fe3f99fc6e923ecb59dd977d72275ad
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100485749"
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="554ff-103">Fundamentos de la herencia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="554ff-103">Inheritance Basics (Visual Basic)</span></span>

<span data-ttu-id="554ff-104">La `Inherits` instrucción se utiliza para declarar una nueva clase, denominada *clase derivada*, basada en una clase existente, conocida como *clase base*.</span><span class="sxs-lookup"><span data-stu-id="554ff-104">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="554ff-105">Las clases derivadas heredan y pueden extender las propiedades, los métodos, los eventos, los campos y las constantes definidos en la clase base.</span><span class="sxs-lookup"><span data-stu-id="554ff-105">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="554ff-106">En la sección siguiente se describen algunas de las reglas de herencia y los modificadores que se pueden usar para cambiar la forma en que las clases heredan o se heredan:</span><span class="sxs-lookup"><span data-stu-id="554ff-106">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>

- <span data-ttu-id="554ff-107">De forma predeterminada, todas las clases se pueden heredar a menos que estén marcadas con la `NotInheritable` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="554ff-107">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="554ff-108">Las clases pueden heredar de otras clases del proyecto o de clases de otros ensamblados a los que hace referencia el proyecto.</span><span class="sxs-lookup"><span data-stu-id="554ff-108">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>

- <span data-ttu-id="554ff-109">A diferencia de los lenguajes que permiten la herencia múltiple, Visual Basic solo permite la herencia única en las clases; es decir, las clases derivadas solo pueden tener una clase base.</span><span class="sxs-lookup"><span data-stu-id="554ff-109">Unlike languages that allow multiple inheritance, Visual Basic allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="554ff-110">Aunque no se permite la herencia múltiple en las clases, las clases pueden implementar varias interfaces, lo que puede lograr de forma eficaz los mismos extremos.</span><span class="sxs-lookup"><span data-stu-id="554ff-110">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>

- <span data-ttu-id="554ff-111">Para evitar la exposición de elementos restringidos en una clase base, el tipo de acceso de una clase derivada debe ser igual o más restrictivo que su clase base.</span><span class="sxs-lookup"><span data-stu-id="554ff-111">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="554ff-112">Por ejemplo, una `Public` clase no puede heredar una `Friend` `Private` clase o, y una `Friend` clase no puede heredar una `Private` clase.</span><span class="sxs-lookup"><span data-stu-id="554ff-112">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>

## <a name="inheritance-modifiers"></a><span data-ttu-id="554ff-113">Modificadores de herencia</span><span class="sxs-lookup"><span data-stu-id="554ff-113">Inheritance Modifiers</span></span>

<span data-ttu-id="554ff-114">Visual Basic presenta las siguientes instrucciones y modificadores de nivel de clase para admitir la herencia:</span><span class="sxs-lookup"><span data-stu-id="554ff-114">Visual Basic introduces the following class-level statements and modifiers to support inheritance:</span></span>

- <span data-ttu-id="554ff-115">`Inherits` instrucción: especifica la clase base.</span><span class="sxs-lookup"><span data-stu-id="554ff-115">`Inherits` statement — Specifies the base class.</span></span>

- <span data-ttu-id="554ff-116">`NotInheritable` modificador: impide que los programadores usen la clase como clase base.</span><span class="sxs-lookup"><span data-stu-id="554ff-116">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>

- <span data-ttu-id="554ff-117">`MustInherit` modificador: especifica que la clase está pensada para usarse solo como una clase base.</span><span class="sxs-lookup"><span data-stu-id="554ff-117">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="554ff-118">Las instancias de `MustInherit` clases no se pueden crear directamente; solo se pueden crear como instancias de clase base de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="554ff-118">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="554ff-119">(Otros lenguajes de programación, como C++ y C#, usan el término *clase abstracta* para describir una clase de este tipo).</span><span class="sxs-lookup"><span data-stu-id="554ff-119">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>

## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="554ff-120">Reemplazar propiedades y métodos en clases derivadas</span><span class="sxs-lookup"><span data-stu-id="554ff-120">Overriding Properties and Methods in Derived Classes</span></span>

<span data-ttu-id="554ff-121">De forma predeterminada, una clase derivada hereda propiedades y métodos de su clase base.</span><span class="sxs-lookup"><span data-stu-id="554ff-121">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="554ff-122">Si una propiedad o un método heredado tienen que comportarse de forma diferente en la clase derivada, se puede *invalidar*.</span><span class="sxs-lookup"><span data-stu-id="554ff-122">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="554ff-123">Es decir, puede definir una nueva implementación del método en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="554ff-123">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="554ff-124">Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:</span><span class="sxs-lookup"><span data-stu-id="554ff-124">The following modifiers are used to control how properties and methods are overridden:</span></span>

- <span data-ttu-id="554ff-125">`Overridable` : Permite que una propiedad o un método de una clase se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="554ff-125">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>

- <span data-ttu-id="554ff-126">`Overrides` : Reemplaza una `Overridable` propiedad o un método definidos en la clase base.</span><span class="sxs-lookup"><span data-stu-id="554ff-126">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>

- <span data-ttu-id="554ff-127">`NotOverridable` : Impide que una propiedad o un método se invalide en una clase heredada.</span><span class="sxs-lookup"><span data-stu-id="554ff-127">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="554ff-128">De forma predeterminada, `Public` los métodos son `NotOverridable` .</span><span class="sxs-lookup"><span data-stu-id="554ff-128">By default, `Public` methods are `NotOverridable`.</span></span>

- <span data-ttu-id="554ff-129">`MustOverride` : Requiere que una clase derivada invalide la propiedad o el método.</span><span class="sxs-lookup"><span data-stu-id="554ff-129">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="554ff-130">Cuando `MustOverride` se usa la palabra clave, la definición del método consta únicamente de la `Sub` `Function` instrucción, o `Property` .</span><span class="sxs-lookup"><span data-stu-id="554ff-130">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="554ff-131">No se permiten otras instrucciones y, en concreto, no hay ninguna `End Sub` `End Function` instrucción o.</span><span class="sxs-lookup"><span data-stu-id="554ff-131">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="554ff-132">`MustOverride` los métodos deben declararse en `MustInherit` clases.</span><span class="sxs-lookup"><span data-stu-id="554ff-132">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>

<span data-ttu-id="554ff-133">Supongamos que desea definir clases para controlar la nómina.</span><span class="sxs-lookup"><span data-stu-id="554ff-133">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="554ff-134">Podría definir una clase genérica `Payroll` que contiene un `RunPayroll` método que calcula la nómina para una semana típica.</span><span class="sxs-lookup"><span data-stu-id="554ff-134">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="554ff-135">Después, puede usar `Payroll` como clase base para una clase más especializada `BonusPayroll` , que podría usarse al distribuir las bonificaciones de empleado.</span><span class="sxs-lookup"><span data-stu-id="554ff-135">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>

<span data-ttu-id="554ff-136">La `BonusPayroll` clase puede heredar e invalidar el `PayEmployee` método definido en la `Payroll` clase base.</span><span class="sxs-lookup"><span data-stu-id="554ff-136">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>

<span data-ttu-id="554ff-137">En el ejemplo siguiente se define una clase base `Payroll,` y una clase derivada, `BonusPayroll` , que invalida un método heredado, `PayEmployee` .</span><span class="sxs-lookup"><span data-stu-id="554ff-137">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="554ff-138">Un procedimiento, `RunPayroll` , crea y, a continuación, pasa un `Payroll` objeto y un `BonusPayroll` objeto a una función, `Pay` , que ejecuta el `PayEmployee` método de ambos objetos.</span><span class="sxs-lookup"><span data-stu-id="554ff-138">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a><span data-ttu-id="554ff-139">La palabra clave MyBase</span><span class="sxs-lookup"><span data-stu-id="554ff-139">The MyBase Keyword</span></span>

<span data-ttu-id="554ff-140">La `MyBase` palabra clave se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase.</span><span class="sxs-lookup"><span data-stu-id="554ff-140">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="554ff-141">`MyBase` se usa con frecuencia para tener acceso a los miembros de clase base que se invalidan o se sombrean en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="554ff-141">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="554ff-142">En concreto, `MyBase.New` se usa para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="554ff-142">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>

<span data-ttu-id="554ff-143">Por ejemplo, supongamos que está diseñando una clase derivada que reemplaza un método heredado de la clase base.</span><span class="sxs-lookup"><span data-stu-id="554ff-143">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="554ff-144">El método invalidado puede llamar al método de la clase base y modificar el valor devuelto como se muestra en el siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="554ff-144">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

<span data-ttu-id="554ff-145">En la lista siguiente se describen las restricciones en el uso de `MyBase` :</span><span class="sxs-lookup"><span data-stu-id="554ff-145">The following list describes restrictions on using `MyBase`:</span></span>

- <span data-ttu-id="554ff-146">`MyBase` hace referencia a la clase base inmediata y a sus miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="554ff-146">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="554ff-147">No se puede usar para tener acceso a `Private` los miembros de la clase.</span><span class="sxs-lookup"><span data-stu-id="554ff-147">It cannot be used to access `Private` members in the class.</span></span>

- <span data-ttu-id="554ff-148">`MyBase` es una palabra clave, no un objeto real.</span><span class="sxs-lookup"><span data-stu-id="554ff-148">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="554ff-149">`MyBase` no se puede asignar a una variable, pasar a procedimientos ni usar en una `Is` comparación.</span><span class="sxs-lookup"><span data-stu-id="554ff-149">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="554ff-150">No es necesario definir el método que `MyBase` califica en la clase base inmediata; en su lugar, se puede definir en una clase base heredada indirectamente.</span><span class="sxs-lookup"><span data-stu-id="554ff-150">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="554ff-151">Para que una referencia calificada por `MyBase` se compile correctamente, alguna clase base debe contener un método que coincida con el nombre y los tipos de parámetros que aparecen en la llamada.</span><span class="sxs-lookup"><span data-stu-id="554ff-151">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>

- <span data-ttu-id="554ff-152">No se puede usar `MyBase` para llamar a `MustOverride` métodos de clase base.</span><span class="sxs-lookup"><span data-stu-id="554ff-152">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>

- <span data-ttu-id="554ff-153">`MyBase` no se puede usar para calificarse a sí mismo.</span><span class="sxs-lookup"><span data-stu-id="554ff-153">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="554ff-154">Por lo tanto, el código siguiente no es válido:</span><span class="sxs-lookup"><span data-stu-id="554ff-154">Therefore, the following code is not valid:</span></span>

  `MyBase.MyBase.BtnOK_Click()`

- <span data-ttu-id="554ff-155">`MyBase` no se puede usar en módulos.</span><span class="sxs-lookup"><span data-stu-id="554ff-155">`MyBase` cannot be used in modules.</span></span>

- <span data-ttu-id="554ff-156">`MyBase` no se puede usar para tener acceso a los miembros de clase base marcados como `Friend` si la clase base se encuentra en un ensamblado diferente.</span><span class="sxs-lookup"><span data-stu-id="554ff-156">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>

<span data-ttu-id="554ff-157">Para obtener más información y otro ejemplo, vea [Cómo: obtener acceso a una variable oculta por una clase derivada](../declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="554ff-157">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>

## <a name="the-myclass-keyword"></a><span data-ttu-id="554ff-158">La palabra clave MyClass</span><span class="sxs-lookup"><span data-stu-id="554ff-158">The MyClass Keyword</span></span>

<span data-ttu-id="554ff-159">La `MyClass` palabra clave se comporta como una variable de objeto que hace referencia a la instancia actual de una clase tal y como se implementó originalmente.</span><span class="sxs-lookup"><span data-stu-id="554ff-159">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="554ff-160">`MyClass` se parece a `Me` , pero todas las llamadas de método y propiedad en `MyClass` se tratan como si el método o la propiedad fueran [NotOverridable](../../../language-reference/modifiers/notoverridable.md).</span><span class="sxs-lookup"><span data-stu-id="554ff-160">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="554ff-161">Por lo tanto, el método o la propiedad no se ven afectados por el reemplazo en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="554ff-161">Therefore, the method or property is not affected by overriding in a derived class.</span></span>

- <span data-ttu-id="554ff-162">`MyClass` es una palabra clave, no un objeto real.</span><span class="sxs-lookup"><span data-stu-id="554ff-162">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="554ff-163">`MyClass` no se puede asignar a una variable, pasar a procedimientos ni usar en una `Is` comparación.</span><span class="sxs-lookup"><span data-stu-id="554ff-163">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>

- <span data-ttu-id="554ff-164">`MyClass` hace referencia a la clase contenedora y a sus miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="554ff-164">`MyClass` refers to the containing class and its inherited members.</span></span>

- <span data-ttu-id="554ff-165">`MyClass` se puede utilizar como calificador para `Shared` los miembros.</span><span class="sxs-lookup"><span data-stu-id="554ff-165">`MyClass` can be used as a qualifier for `Shared` members.</span></span>

- <span data-ttu-id="554ff-166">`MyClass` no se puede usar dentro de un `Shared` método, pero se puede usar dentro de un método de instancia para tener acceso a un miembro compartido de una clase.</span><span class="sxs-lookup"><span data-stu-id="554ff-166">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>

- <span data-ttu-id="554ff-167">`MyClass` no se puede usar en módulos estándar.</span><span class="sxs-lookup"><span data-stu-id="554ff-167">`MyClass` cannot be used in standard modules.</span></span>

- <span data-ttu-id="554ff-168">`MyClass` se puede usar para calificar un método que se define en una clase base y que no tiene ninguna implementación del método proporcionado en esa clase.</span><span class="sxs-lookup"><span data-stu-id="554ff-168">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="554ff-169">Este tipo de referencia tiene el mismo significado que el `MyBase.` *método*.</span><span class="sxs-lookup"><span data-stu-id="554ff-169">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>

<span data-ttu-id="554ff-170">En el ejemplo siguiente se comparan `Me` y `MyClass` .</span><span class="sxs-lookup"><span data-stu-id="554ff-170">The following example compares `Me` and `MyClass`.</span></span>

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

<span data-ttu-id="554ff-171">Aunque `derivedClass` invalida `testMethod` , la `MyClass` palabra clave en anula `useMyClass` los efectos de la invalidación, y el compilador resuelve la llamada a la versión de la clase base de `testMethod` .</span><span class="sxs-lookup"><span data-stu-id="554ff-171">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>

## <a name="see-also"></a><span data-ttu-id="554ff-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="554ff-172">See also</span></span>

- [<span data-ttu-id="554ff-173">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="554ff-173">Inherits Statement</span></span>](../../../language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="554ff-174">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="554ff-174">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
