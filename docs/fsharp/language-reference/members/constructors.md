---
title: Constructores
description: Obtenga información sobre cómo definir y usar constructores F# en para crear e inicializar objetos de clase y estructura.
ms.date: 05/16/2016
ms.openlocfilehash: ef5dc134ad98179b6a365c4c34a9eca22fe5f7f6
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364359"
---
# <a name="constructors"></a><span data-ttu-id="11da7-103">Constructores</span><span class="sxs-lookup"><span data-stu-id="11da7-103">Constructors</span></span>

<span data-ttu-id="11da7-104">En este tema se describe cómo definir y usar constructores para crear e inicializar objetos de clase y estructura.</span><span class="sxs-lookup"><span data-stu-id="11da7-104">This topic describes how to define and use constructors to create and initialize class and structure objects.</span></span>

## <a name="construction-of-class-objects"></a><span data-ttu-id="11da7-105">Construcción de objetos de clase</span><span class="sxs-lookup"><span data-stu-id="11da7-105">Construction of Class Objects</span></span>

<span data-ttu-id="11da7-106">Los objetos de tipos de clase tienen constructores.</span><span class="sxs-lookup"><span data-stu-id="11da7-106">Objects of class types have constructors.</span></span> <span data-ttu-id="11da7-107">Hay dos tipos de constructores.</span><span class="sxs-lookup"><span data-stu-id="11da7-107">There are two kinds of constructors.</span></span> <span data-ttu-id="11da7-108">Uno es el constructor principal, cuyos parámetros aparecen entre paréntesis justo después del nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="11da7-108">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="11da7-109">Especifique otros constructores adicionales opcionales mediante la `new` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="11da7-109">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="11da7-110">Cualquier constructor adicional de este tipo debe llamar al constructor principal.</span><span class="sxs-lookup"><span data-stu-id="11da7-110">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="11da7-111">El constructor principal contiene `let` enlaces `do` y que aparecen al principio de la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="11da7-111">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="11da7-112">Un `let` enlace declara los campos y métodos privados de la clase; un `do` enlace ejecuta código.</span><span class="sxs-lookup"><span data-stu-id="11da7-112">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="11da7-113">Para obtener más información `let` sobre los enlaces de los constructores de clase, vea [ `let` enlaces en clases](let-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="11da7-113">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="11da7-114">Para obtener más información `do` sobre los enlaces en constructores, vea [ `do` enlaces en clases](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="11da7-114">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="11da7-115">Independientemente de si el constructor al que desea llamar es un constructor principal o un constructor adicional, puede crear objetos mediante una `new` expresión, con o sin la palabra clave opcional. `new`</span><span class="sxs-lookup"><span data-stu-id="11da7-115">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="11da7-116">Los objetos se inicializan junto con los argumentos del constructor, ya sea mediante una lista de los argumentos en orden y se separan mediante comas y entre paréntesis, o usando argumentos y valores con nombre entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="11da7-116">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="11da7-117">También puede establecer las propiedades de un objeto durante la construcción del objeto utilizando los nombres de propiedad y asignando valores de la misma forma que se usan los argumentos del constructor con nombre.</span><span class="sxs-lookup"><span data-stu-id="11da7-117">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="11da7-118">En el código siguiente se muestra una clase que tiene un constructor y varias maneras de crear objetos.</span><span class="sxs-lookup"><span data-stu-id="11da7-118">The following code illustrates a class that has a constructor and various ways of creating objects.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="11da7-119">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="11da7-119">The output is as follows.</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="11da7-120">Construcción de estructuras</span><span class="sxs-lookup"><span data-stu-id="11da7-120">Construction of Structures</span></span>

<span data-ttu-id="11da7-121">Las estructuras siguen todas las reglas de las clases.</span><span class="sxs-lookup"><span data-stu-id="11da7-121">Structures follow all the rules of classes.</span></span> <span data-ttu-id="11da7-122">Por lo tanto, puede tener un constructor principal y puede proporcionar constructores `new`adicionales mediante.</span><span class="sxs-lookup"><span data-stu-id="11da7-122">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="11da7-123">Sin embargo, hay una diferencia importante entre las estructuras y las clases: las estructuras pueden tener un constructor sin parámetros (es decir, uno sin argumentos) aunque no se haya definido ningún constructor principal.</span><span class="sxs-lookup"><span data-stu-id="11da7-123">However, there is one important difference between structures and classes: structures can have a parameterless constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="11da7-124">El constructor sin parámetros inicializa todos los campos en el valor predeterminado de ese tipo, normalmente cero o su equivalente.</span><span class="sxs-lookup"><span data-stu-id="11da7-124">The parameterless constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="11da7-125">Los constructores que defina para las estructuras deben tener al menos un argumento para que no entren en conflicto con el constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="11da7-125">Any constructors that you define for structures must have at least one argument so that they do not conflict with the default constructor.</span></span>

<span data-ttu-id="11da7-126">Además, las estructuras suelen tener campos que se crean mediante la `val` palabra clave; las clases también pueden tener estos campos.</span><span class="sxs-lookup"><span data-stu-id="11da7-126">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="11da7-127">Las estructuras y las clases que tienen campos definidos mediante `val` la palabra clave también se pueden inicializar en constructores adicionales mediante el uso de expresiones de registro, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="11da7-127">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="11da7-128">Para obtener más información, [vea campos explícitos: `val` Palabra clave](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="11da7-128">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>

## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="11da7-129">Ejecutar efectos secundarios en constructores</span><span class="sxs-lookup"><span data-stu-id="11da7-129">Executing Side Effects in Constructors</span></span>

<span data-ttu-id="11da7-130">Un constructor principal de una clase puede ejecutar código en un `do` enlace.</span><span class="sxs-lookup"><span data-stu-id="11da7-130">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="11da7-131">Sin embargo, ¿qué ocurre si tiene que ejecutar código en un constructor adicional, `do` sin un enlace?</span><span class="sxs-lookup"><span data-stu-id="11da7-131">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="11da7-132">Para ello, use la `then` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="11da7-132">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="11da7-133">Los efectos secundarios del constructor principal todavía se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="11da7-133">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="11da7-134">Por lo tanto, el resultado es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="11da7-134">Therefore, the output is as follows.</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="11da7-135">Identificadores propios en constructores</span><span class="sxs-lookup"><span data-stu-id="11da7-135">Self Identifiers in Constructors</span></span>

<span data-ttu-id="11da7-136">En otros miembros, se proporciona un nombre para el objeto actual en la definición de cada miembro.</span><span class="sxs-lookup"><span data-stu-id="11da7-136">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="11da7-137">También puede colocar el identificador propio en la primera línea de la definición de clase mediante la `as` palabra clave inmediatamente después de los parámetros del constructor.</span><span class="sxs-lookup"><span data-stu-id="11da7-137">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="11da7-138">En el ejemplo siguiente se muestra esta sintaxis.</span><span class="sxs-lookup"><span data-stu-id="11da7-138">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="11da7-139">En los constructores adicionales, también puede definir un identificador propio colocando la `as` cláusula justo después de los parámetros del constructor.</span><span class="sxs-lookup"><span data-stu-id="11da7-139">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="11da7-140">En el ejemplo siguiente se muestra esta sintaxis.</span><span class="sxs-lookup"><span data-stu-id="11da7-140">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="11da7-141">Pueden producirse problemas al intentar usar un objeto antes de que se defina por completo.</span><span class="sxs-lookup"><span data-stu-id="11da7-141">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="11da7-142">Por lo tanto, los usos del propio identificador pueden hacer que el compilador emita una advertencia e inserte comprobaciones adicionales para asegurarse de que no se tiene acceso a los miembros de un objeto antes de que se inicialice el objeto.</span><span class="sxs-lookup"><span data-stu-id="11da7-142">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="11da7-143">Solo se debe usar el identificador propio en los `do` enlaces del constructor principal o después de la `then` palabra clave en constructores adicionales.</span><span class="sxs-lookup"><span data-stu-id="11da7-143">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="11da7-144">No es necesario que el nombre del propio identificador sea `this`.</span><span class="sxs-lookup"><span data-stu-id="11da7-144">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="11da7-145">Puede ser cualquier identificador válido.</span><span class="sxs-lookup"><span data-stu-id="11da7-145">It can be any valid identifier.</span></span>

## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="11da7-146">Asignar valores a propiedades en la inicialización</span><span class="sxs-lookup"><span data-stu-id="11da7-146">Assigning Values to Properties at Initialization</span></span>

<span data-ttu-id="11da7-147">Puede asignar valores a las propiedades de un objeto de clase en el código de inicialización anexando una lista de asignaciones del formulario `property = value` a la lista de argumentos de un constructor.</span><span class="sxs-lookup"><span data-stu-id="11da7-147">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="11da7-148">Esto se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="11da7-148">This is shown in the following code example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="11da7-149">La siguiente versión del código anterior muestra la combinación de argumentos ordinarios, argumentos opcionales y valores de propiedades en una llamada a un constructor.</span><span class="sxs-lookup"><span data-stu-id="11da7-149">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a><span data-ttu-id="11da7-150">Constructores en la clase heredada</span><span class="sxs-lookup"><span data-stu-id="11da7-150">Constructors in inherited class</span></span>

<span data-ttu-id="11da7-151">Al heredar de una clase base que tiene un constructor, debe especificar sus argumentos en la cláusula inherit.</span><span class="sxs-lookup"><span data-stu-id="11da7-151">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="11da7-152">Para obtener más información, vea [constructores y herencia](../inheritance.md#constructors-and-inheritance).</span><span class="sxs-lookup"><span data-stu-id="11da7-152">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="11da7-153">Constructores estáticos o constructores de tipo</span><span class="sxs-lookup"><span data-stu-id="11da7-153">Static Constructors or Type Constructors</span></span>

<span data-ttu-id="11da7-154">Además de especificar el código para crear objetos, se pueden `let` crear `do` enlaces estáticos y en tipos de clase que se ejecutan antes de que el tipo se use por primera vez para realizar la inicialización en el nivel de tipo.</span><span class="sxs-lookup"><span data-stu-id="11da7-154">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="11da7-155">Para obtener más información, vea [ `let` enlaces en clases](let-bindings-in-classes.md) y [ `do` enlaces en clases](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="11da7-155">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="11da7-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="11da7-156">See also</span></span>

- [<span data-ttu-id="11da7-157">Miembros</span><span class="sxs-lookup"><span data-stu-id="11da7-157">Members</span></span>](index.md)
