---
title: Fundamentos de la herencia (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76813bb36c0bcf75791932a0fec081f0fc1958e3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="inheritance-basics-visual-basic"></a><span data-ttu-id="a9f25-102">Fundamentos de la herencia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9f25-102">Inheritance Basics (Visual Basic)</span></span>
<span data-ttu-id="a9f25-103">El `Inherits` instrucción se utiliza para declarar una nueva clase, denominada una *clase derivada*, en función de una clase existente, conocida como un *clase base*.</span><span class="sxs-lookup"><span data-stu-id="a9f25-103">The `Inherits` statement is used to declare a new class, called a *derived class*, based on an existing class, known as a *base class*.</span></span> <span data-ttu-id="a9f25-104">Las clases derivadas heredan y pueden extender, las propiedades, métodos, eventos, campos y constantes definidas en la clase base.</span><span class="sxs-lookup"><span data-stu-id="a9f25-104">Derived classes inherit, and can extend, the properties, methods, events, fields, and constants defined in the base class.</span></span> <span data-ttu-id="a9f25-105">En la siguiente sección se describe algunas de las reglas de herencia, y los modificadores que puede utilizar para cambiar las clases de manera heredan o son heredados:</span><span class="sxs-lookup"><span data-stu-id="a9f25-105">The following section describes some of the rules for inheritance, and the modifiers you can use to change the way classes inherit or are inherited:</span></span>  
  
-   <span data-ttu-id="a9f25-106">De forma predeterminada, todas las clases son heredables a menos que se marca con el `NotInheritable` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="a9f25-106">By default, all classes are inheritable unless marked with the `NotInheritable` keyword.</span></span> <span data-ttu-id="a9f25-107">Las clases pueden heredar de otras clases en el proyecto o de clases en otros ensamblados a los que hace referencia el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a9f25-107">Classes can inherit from other classes in your project or from classes in other assemblies that your project references.</span></span>  
  
-   <span data-ttu-id="a9f25-108">A diferencia de los lenguajes que permiten herencia múltiple, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] permite herencia única solo en las clases; es decir, las clases derivadas pueden tener sólo una clase base.</span><span class="sxs-lookup"><span data-stu-id="a9f25-108">Unlike languages that allow multiple inheritance, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] allows only single inheritance in classes; that is, derived classes can have only one base class.</span></span> <span data-ttu-id="a9f25-109">Aunque no se permite la herencia múltiple de clases, las clases pueden implementar varias interfaces, que se pueden lograr de manera eficaz los mismos fines.</span><span class="sxs-lookup"><span data-stu-id="a9f25-109">Although multiple inheritance is not allowed in classes, classes can implement multiple interfaces, which can effectively accomplish the same ends.</span></span>  
  
-   <span data-ttu-id="a9f25-110">Para evitar la exposición de elementos restringidos en una clase base, el tipo de acceso de una clase derivada debe ser igual o más restrictivo que su clase base.</span><span class="sxs-lookup"><span data-stu-id="a9f25-110">To prevent exposing restricted items in a base class, the access type of a derived class must be equal to or more restrictive than its base class.</span></span> <span data-ttu-id="a9f25-111">Por ejemplo, un `Public` clase no puede heredar una `Friend` o un `Private` (clase) y un `Friend` clase no puede heredar un `Private` clase.</span><span class="sxs-lookup"><span data-stu-id="a9f25-111">For example, a `Public` class cannot inherit a `Friend` or a `Private` class, and a `Friend` class cannot inherit a `Private` class.</span></span>  
  
## <a name="inheritance-modifiers"></a><span data-ttu-id="a9f25-112">Modificadores de herencia</span><span class="sxs-lookup"><span data-stu-id="a9f25-112">Inheritance Modifiers</span></span>  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="a9f25-113">presenta las siguientes instrucciones de nivel de clase y los modificadores para admitir la herencia:</span><span class="sxs-lookup"><span data-stu-id="a9f25-113"> introduces the following class-level statements and modifiers to support inheritance:</span></span>  
  
-   <span data-ttu-id="a9f25-114">`Inherits`instrucción: especifica la clase base.</span><span class="sxs-lookup"><span data-stu-id="a9f25-114">`Inherits` statement — Specifies the base class.</span></span>  
  
-   <span data-ttu-id="a9f25-115">`NotInheritable`modificador: impide que los programadores utilicen la clase como una clase base.</span><span class="sxs-lookup"><span data-stu-id="a9f25-115">`NotInheritable` modifier — Prevents programmers from using the class as a base class.</span></span>  
  
-   <span data-ttu-id="a9f25-116">`MustInherit`modificador: Especifica que la clase está diseñada para su uso como clase base.</span><span class="sxs-lookup"><span data-stu-id="a9f25-116">`MustInherit` modifier — Specifies that the class is intended for use as a base class only.</span></span> <span data-ttu-id="a9f25-117">Instancias de `MustInherit` clases no se pueden crear directamente; solo se pueden crear instancias de clases como base de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="a9f25-117">Instances of `MustInherit` classes cannot be created directly; they can only be created as base class instances of a derived class.</span></span> <span data-ttu-id="a9f25-118">(Otros lenguajes de programación, como C++ y C#, usan el término *clase abstracta* para describir esta clase.)</span><span class="sxs-lookup"><span data-stu-id="a9f25-118">(Other programming languages, such as C++ and C#, use the term *abstract class* to describe such a class.)</span></span>  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a><span data-ttu-id="a9f25-119">Reemplazar propiedades y métodos en clases derivadas</span><span class="sxs-lookup"><span data-stu-id="a9f25-119">Overriding Properties and Methods in Derived Classes</span></span>  
 <span data-ttu-id="a9f25-120">De forma predeterminada, una clase derivada hereda las propiedades y métodos de la clase base.</span><span class="sxs-lookup"><span data-stu-id="a9f25-120">By default, a derived class inherits properties and methods from its base class.</span></span> <span data-ttu-id="a9f25-121">Si una propiedad o método heredado debe comportarse de manera diferente en la clase derivada puede ser *se reemplaza*.</span><span class="sxs-lookup"><span data-stu-id="a9f25-121">If an inherited property or method has to behave differently in the derived class it can be *overridden*.</span></span> <span data-ttu-id="a9f25-122">Es decir, puede definir una nueva implementación del método en la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="a9f25-122">That is, you can define a new implementation of the method in the derived class.</span></span> <span data-ttu-id="a9f25-123">Los siguientes modificadores se utilizan para controlar cómo se reemplazan propiedades y métodos:</span><span class="sxs-lookup"><span data-stu-id="a9f25-123">The following modifiers are used to control how properties and methods are overridden:</span></span>  
  
-   <span data-ttu-id="a9f25-124">`Overridable`Permite un método o propiedad en una clase para que se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="a9f25-124">`Overridable` — Allows a property or method in a class to be overridden in a derived class.</span></span>  
  
-   <span data-ttu-id="a9f25-125">`Overrides`: Invalida un `Overridable` propiedad o un método definido en la clase base.</span><span class="sxs-lookup"><span data-stu-id="a9f25-125">`Overrides` — Overrides an `Overridable` property or method defined in the base class.</span></span>  
  
-   <span data-ttu-id="a9f25-126">`NotOverridable`: Impide que una propiedad o método se invalide en una clase heredera.</span><span class="sxs-lookup"><span data-stu-id="a9f25-126">`NotOverridable` — Prevents a property or method from being overridden in an inheriting class.</span></span> <span data-ttu-id="a9f25-127">De forma predeterminada, `Public` métodos son `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="a9f25-127">By default, `Public` methods are `NotOverridable`.</span></span>  
  
-   <span data-ttu-id="a9f25-128">`MustOverride`: Requiere que una clase derivada invalide la propiedad o método.</span><span class="sxs-lookup"><span data-stu-id="a9f25-128">`MustOverride` — Requires that a derived class override the property or method.</span></span> <span data-ttu-id="a9f25-129">Cuando el `MustOverride` se utiliza la palabra clave, formada por la definición de método simplemente el `Sub`, `Function`, o `Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="a9f25-129">When the `MustOverride` keyword is used, the method definition consists of just the `Sub`, `Function`, or `Property` statement.</span></span> <span data-ttu-id="a9f25-130">Se permite ninguna otra instrucción y, específicamente no hay ningún `End Sub` o `End Function` instrucción.</span><span class="sxs-lookup"><span data-stu-id="a9f25-130">No other statements are allowed, and specifically there is no `End Sub` or `End Function` statement.</span></span> <span data-ttu-id="a9f25-131">`MustOverride`los métodos se deben declarar en `MustInherit` clases.</span><span class="sxs-lookup"><span data-stu-id="a9f25-131">`MustOverride` methods must be declared in `MustInherit` classes.</span></span>  
  
 <span data-ttu-id="a9f25-132">Suponga que desea definir clases para controlar la nómina.</span><span class="sxs-lookup"><span data-stu-id="a9f25-132">Suppose you want to define classes to handle payroll.</span></span> <span data-ttu-id="a9f25-133">Puede definir un tipo genérico `Payroll` clase que contiene un `RunPayroll` método calcular la nómina de una semana típica.</span><span class="sxs-lookup"><span data-stu-id="a9f25-133">You could define a generic `Payroll` class that contains a `RunPayroll` method that calculates payroll for a typical week.</span></span> <span data-ttu-id="a9f25-134">A continuación, podría utilizar `Payroll` como una clase base para una más especializado `BonusPayroll` (clase), que se pueda usar durante la distribución de bonificaciones de empleado.</span><span class="sxs-lookup"><span data-stu-id="a9f25-134">You could then use `Payroll` as a base class for a more specialized `BonusPayroll` class, which could be used when distributing employee bonuses.</span></span>  
  
 <span data-ttu-id="a9f25-135">El `BonusPayroll` clase puede heredar y reemplazar, el `PayEmployee` método definido en la base de `Payroll` clase.</span><span class="sxs-lookup"><span data-stu-id="a9f25-135">The `BonusPayroll` class can inherit, and override, the `PayEmployee` method defined in the base `Payroll` class.</span></span>  
  
 <span data-ttu-id="a9f25-136">En el ejemplo siguiente se define una clase base, `Payroll,` y una clase derivada, `BonusPayroll`, que reemplaza un método heredado, `PayEmployee`.</span><span class="sxs-lookup"><span data-stu-id="a9f25-136">The following example defines a base class, `Payroll,` and a derived class, `BonusPayroll`, which overrides an inherited method, `PayEmployee`.</span></span> <span data-ttu-id="a9f25-137">Un procedimiento, `RunPayroll`, crea y, a continuación, pasa una `Payroll` objeto y un `BonusPayroll` objeto a una función, `Pay`, que se ejecuta el `PayEmployee` método de ambos objetos.</span><span class="sxs-lookup"><span data-stu-id="a9f25-137">A procedure, `RunPayroll`, creates and then passes a `Payroll` object and a `BonusPayroll` object to a function, `Pay`, that executes the `PayEmployee` method of both objects.</span></span>  
  
 [!code-vb[VbVbalrOOP#28](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]  
  
## <a name="the-mybase-keyword"></a><span data-ttu-id="a9f25-138">La palabra clave MyBase</span><span class="sxs-lookup"><span data-stu-id="a9f25-138">The MyBase Keyword</span></span>  
 <span data-ttu-id="a9f25-139">El `MyBase` palabra clave se comporta como una variable de objeto que hace referencia a la clase base de la instancia actual de una clase.</span><span class="sxs-lookup"><span data-stu-id="a9f25-139">The `MyBase` keyword behaves like an object variable that refers to the base class of the current instance of a class.</span></span> <span data-ttu-id="a9f25-140">`MyBase`se suele utilizar para tener acceso a miembros de clase base que se reemplazan o se sombrean en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="a9f25-140">`MyBase` is frequently used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="a9f25-141">En concreto, `MyBase.New` se utiliza para llamar explícitamente a un constructor de clase base desde un constructor de clase derivada.</span><span class="sxs-lookup"><span data-stu-id="a9f25-141">In particular, `MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
 <span data-ttu-id="a9f25-142">Por ejemplo, suponga que está diseñando una clase derivada que reemplaza un método heredado de la clase base.</span><span class="sxs-lookup"><span data-stu-id="a9f25-142">For example, suppose you are designing a derived class that overrides a method inherited from the base class.</span></span> <span data-ttu-id="a9f25-143">El método invalidado puede llamar al método en la clase base y modificar el valor devuelto como se muestra en el siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="a9f25-143">The overridden method can call the method in the base class and modify the return value as shown in the following code fragment:</span></span>  
  
 [!code-vb[VbVbalrOOP#109](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]  
  
 <span data-ttu-id="a9f25-144">La siguiente lista describe las restricciones sobre el uso de `MyBase`:</span><span class="sxs-lookup"><span data-stu-id="a9f25-144">The following list describes restrictions on using `MyBase`:</span></span>  
  
-   <span data-ttu-id="a9f25-145">`MyBase`hace referencia a la clase base inmediata y a sus miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="a9f25-145">`MyBase` refers to the immediate base class and its inherited members.</span></span> <span data-ttu-id="a9f25-146">No se puede usar para tener acceso a `Private` los miembros de la clase.</span><span class="sxs-lookup"><span data-stu-id="a9f25-146">It cannot be used to access `Private` members in the class.</span></span>  
  
-   <span data-ttu-id="a9f25-147">`MyBase`es una palabra clave, no un objeto real.</span><span class="sxs-lookup"><span data-stu-id="a9f25-147">`MyBase` is a keyword, not a real object.</span></span> <span data-ttu-id="a9f25-148">`MyBase`no se asigna a una variable, pasar a los procedimientos o utilizar en una `Is` comparación.</span><span class="sxs-lookup"><span data-stu-id="a9f25-148">`MyBase` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="a9f25-149">El método que `MyBase` se consideran no tienen que definirse en la clase base inmediata; en su lugar puede definirse en una clase base heredada indirectamente.</span><span class="sxs-lookup"><span data-stu-id="a9f25-149">The method that `MyBase` qualifies does not have to be defined in the immediate base class; it may instead be defined in an indirectly inherited base class.</span></span> <span data-ttu-id="a9f25-150">En orden para una referencia calificada mediante `MyBase` para compilar correctamente, alguna clase base debe contener un método correspondiente al nombre y los tipos de parámetros que aparecen en la llamada.</span><span class="sxs-lookup"><span data-stu-id="a9f25-150">In order for a reference qualified by `MyBase` to compile correctly, some base class must contain a method matching the name and types of parameters that appear in the call.</span></span>  
  
-   <span data-ttu-id="a9f25-151">No se puede utilizar `MyBase` para llamar a `MustOverride` métodos de la clase de base.</span><span class="sxs-lookup"><span data-stu-id="a9f25-151">You cannot use `MyBase` to call `MustOverride` base class methods.</span></span>  
  
-   <span data-ttu-id="a9f25-152">`MyBase`no se puede utilizar para calificarse a sí misma.</span><span class="sxs-lookup"><span data-stu-id="a9f25-152">`MyBase` cannot be used to qualify itself.</span></span> <span data-ttu-id="a9f25-153">Por lo tanto, el código siguiente no es válido:</span><span class="sxs-lookup"><span data-stu-id="a9f25-153">Therefore, the following code is not valid:</span></span>  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   <span data-ttu-id="a9f25-154">`MyBase`no se puede utilizar en módulos.</span><span class="sxs-lookup"><span data-stu-id="a9f25-154">`MyBase` cannot be used in modules.</span></span>  
  
-   <span data-ttu-id="a9f25-155">`MyBase`no se puede usar para tener acceso a los miembros de clase base que están marcados como `Friend` si la clase base está en un ensamblado diferente.</span><span class="sxs-lookup"><span data-stu-id="a9f25-155">`MyBase` cannot be used to access base class members that are marked as `Friend` if the base class is in a different assembly.</span></span>  
  
 <span data-ttu-id="a9f25-156">Para obtener más información y otro ejemplo, vea [Cómo: obtener acceso a una Variable oculta una clase derivada](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span><span class="sxs-lookup"><span data-stu-id="a9f25-156">For more information and another example, see [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).</span></span>  
  
## <a name="the-myclass-keyword"></a><span data-ttu-id="a9f25-157">La palabra clave MyClass</span><span class="sxs-lookup"><span data-stu-id="a9f25-157">The MyClass Keyword</span></span>  
 <span data-ttu-id="a9f25-158">El `MyClass` palabra clave se comporta como una variable de objeto que hace referencia a la instancia actual de una clase como se implementaron originalmente.</span><span class="sxs-lookup"><span data-stu-id="a9f25-158">The `MyClass` keyword behaves like an object variable that refers to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="a9f25-159">`MyClass`es similar a `Me`, pero llama cada método y propiedad en `MyClass` se trata como si fuera el método o propiedad [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span><span class="sxs-lookup"><span data-stu-id="a9f25-159">`MyClass` resembles `Me`, but every method and property call on `MyClass` is treated as if the method or property were [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md).</span></span> <span data-ttu-id="a9f25-160">Por lo tanto, el método o propiedad no se ve afectado por el reemplazo de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="a9f25-160">Therefore, the method or property is not affected by overriding in a derived class.</span></span>  
  
-   <span data-ttu-id="a9f25-161">`MyClass`es una palabra clave, no un objeto real.</span><span class="sxs-lookup"><span data-stu-id="a9f25-161">`MyClass` is a keyword, not a real object.</span></span> <span data-ttu-id="a9f25-162">`MyClass`no se asigna a una variable, pasar a los procedimientos o utilizar en una `Is` comparación.</span><span class="sxs-lookup"><span data-stu-id="a9f25-162">`MyClass` cannot be assigned to a variable, passed to procedures, or used in an `Is` comparison.</span></span>  
  
-   <span data-ttu-id="a9f25-163">`MyClass`hace referencia a la clase contenedora y a sus miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="a9f25-163">`MyClass` refers to the containing class and its inherited members.</span></span>  
  
-   <span data-ttu-id="a9f25-164">`MyClass`se pueden usar como un calificador para `Shared` miembros.</span><span class="sxs-lookup"><span data-stu-id="a9f25-164">`MyClass` can be used as a qualifier for `Shared` members.</span></span>  
  
-   <span data-ttu-id="a9f25-165">`MyClass`no se puede usar dentro de un `Shared` (método), pero se puede usar dentro de un método de instancia para tener acceso a un miembro compartido de una clase.</span><span class="sxs-lookup"><span data-stu-id="a9f25-165">`MyClass` cannot be used inside a `Shared` method, but can be used inside an instance method to access a shared member of a class.</span></span>  
  
-   <span data-ttu-id="a9f25-166">`MyClass`no se puede utilizar en módulos estándares.</span><span class="sxs-lookup"><span data-stu-id="a9f25-166">`MyClass` cannot be used in standard modules.</span></span>  
  
-   <span data-ttu-id="a9f25-167">`MyClass`puede utilizarse para calificar un método que se define en una clase base y que no tiene ninguna implementación del método proporcionado en esa clase.</span><span class="sxs-lookup"><span data-stu-id="a9f25-167">`MyClass` can be used to qualify a method that is defined in a base class and that has no implementation of the method provided in that class.</span></span> <span data-ttu-id="a9f25-168">Este tipo de referencia tiene el mismo significado que `MyBase.` *método*.</span><span class="sxs-lookup"><span data-stu-id="a9f25-168">Such a reference has the same meaning as `MyBase.`*Method*.</span></span>  
  
 <span data-ttu-id="a9f25-169">En el ejemplo siguiente se comparan `Me` y `MyClass`.</span><span class="sxs-lookup"><span data-stu-id="a9f25-169">The following example compares `Me` and `MyClass`.</span></span>  
  
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
  
 <span data-ttu-id="a9f25-170">Aunque `derivedClass` invalida `testMethod`, `MyClass` palabra clave en `useMyClass` anula el efecto del reemplazo y el compilador resuelve la llamada a la versión de la clase base de `testMethod`.</span><span class="sxs-lookup"><span data-stu-id="a9f25-170">Even though `derivedClass` overrides `testMethod`, the `MyClass` keyword in `useMyClass` nullifies the effects of overriding, and the compiler resolves the call to the base class version of `testMethod`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9f25-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9f25-171">See Also</span></span>  
 [<span data-ttu-id="a9f25-172">Inherits (instrucción)</span><span class="sxs-lookup"><span data-stu-id="a9f25-172">Inherits Statement</span></span>](../../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="a9f25-173">Me, My, MyBase y MyClass</span><span class="sxs-lookup"><span data-stu-id="a9f25-173">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
