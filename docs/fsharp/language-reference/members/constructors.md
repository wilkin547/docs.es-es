---
title: Constructores
description: 'Obtenga información sobre cómo definir y usar constructores en F # para crear e inicializar objetos de clase y estructura.'
ms.date: 05/16/2016
ms.openlocfilehash: be8fc3f1d82a9a7c778a6d094139f14150a28813
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303444"
---
# <a name="constructors"></a><span data-ttu-id="dc094-103">Constructores</span><span class="sxs-lookup"><span data-stu-id="dc094-103">Constructors</span></span>

<span data-ttu-id="dc094-104">En este artículo se describe cómo definir y usar constructores para crear e inicializar objetos de clase y estructura.</span><span class="sxs-lookup"><span data-stu-id="dc094-104">This article describes how to define and use constructors to create and initialize class and structure objects.</span></span>

## <a name="construction-of-class-objects"></a><span data-ttu-id="dc094-105">Construcción de objetos de clase</span><span class="sxs-lookup"><span data-stu-id="dc094-105">Construction of class objects</span></span>

<span data-ttu-id="dc094-106">Los objetos de tipos de clase tienen constructores.</span><span class="sxs-lookup"><span data-stu-id="dc094-106">Objects of class types have constructors.</span></span> <span data-ttu-id="dc094-107">Hay dos tipos de constructores.</span><span class="sxs-lookup"><span data-stu-id="dc094-107">There are two kinds of constructors.</span></span> <span data-ttu-id="dc094-108">Uno es el constructor principal, cuyos parámetros aparecen entre paréntesis justo después del nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="dc094-108">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="dc094-109">Especifique otros constructores adicionales opcionales mediante la `new` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="dc094-109">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="dc094-110">Cualquier constructor adicional de este tipo debe llamar al constructor principal.</span><span class="sxs-lookup"><span data-stu-id="dc094-110">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="dc094-111">El constructor principal contiene `let` `do` enlaces y que aparecen al principio de la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="dc094-111">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="dc094-112">Un `let` enlace declara los campos y métodos privados de la clase; un `do` enlace ejecuta código.</span><span class="sxs-lookup"><span data-stu-id="dc094-112">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="dc094-113">Para obtener más información sobre los `let` enlaces de los constructores de clase, vea [ `let` enlaces en clases](let-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="dc094-113">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="dc094-114">Para obtener más información sobre los `do` enlaces en constructores, vea [ `do` enlaces en clases](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="dc094-114">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="dc094-115">Independientemente de si el constructor al que desea llamar es un constructor principal o un constructor adicional, puede crear objetos mediante una `new` expresión, con o sin la `new` palabra clave opcional.</span><span class="sxs-lookup"><span data-stu-id="dc094-115">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="dc094-116">Los objetos se inicializan junto con los argumentos del constructor, ya sea mediante una lista de los argumentos en orden y se separan mediante comas y entre paréntesis, o usando argumentos y valores con nombre entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="dc094-116">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="dc094-117">También puede establecer las propiedades de un objeto durante la construcción del objeto utilizando los nombres de propiedad y asignando valores de la misma forma que se usan los argumentos del constructor con nombre.</span><span class="sxs-lookup"><span data-stu-id="dc094-117">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="dc094-118">En el código siguiente se muestra una clase que tiene un constructor y varias maneras de crear objetos:</span><span class="sxs-lookup"><span data-stu-id="dc094-118">The following code illustrates a class that has a constructor and various ways of creating objects:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="dc094-119">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="dc094-119">The output is as follows:</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="dc094-120">Construcción de estructuras</span><span class="sxs-lookup"><span data-stu-id="dc094-120">Construction of structures</span></span>

<span data-ttu-id="dc094-121">Las estructuras siguen todas las reglas de las clases.</span><span class="sxs-lookup"><span data-stu-id="dc094-121">Structures follow all the rules of classes.</span></span> <span data-ttu-id="dc094-122">Por lo tanto, puede tener un constructor principal y puede proporcionar constructores adicionales mediante `new` .</span><span class="sxs-lookup"><span data-stu-id="dc094-122">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="dc094-123">Sin embargo, hay una diferencia importante entre las estructuras y las clases: las estructuras pueden tener un constructor sin parámetros (es decir, uno sin argumentos) aunque no se haya definido ningún constructor principal.</span><span class="sxs-lookup"><span data-stu-id="dc094-123">However, there is one important difference between structures and classes: structures can have a parameterless constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="dc094-124">El constructor sin parámetros inicializa todos los campos en el valor predeterminado de ese tipo, normalmente cero o su equivalente.</span><span class="sxs-lookup"><span data-stu-id="dc094-124">The parameterless constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="dc094-125">Los constructores que defina para las estructuras deben tener al menos un argumento para que no entren en conflicto con el constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="dc094-125">Any constructors that you define for structures must have at least one argument so that they do not conflict with the parameterless constructor.</span></span>

<span data-ttu-id="dc094-126">Además, las estructuras suelen tener campos que se crean mediante la `val` palabra clave; las clases también pueden tener estos campos.</span><span class="sxs-lookup"><span data-stu-id="dc094-126">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="dc094-127">Las estructuras y las clases que tienen campos definidos mediante la `val` palabra clave también se pueden inicializar en constructores adicionales mediante el uso de expresiones de registro, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="dc094-127">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="dc094-128">Para obtener más información, vea [campos explícitos: la `val` palabra clave](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="dc094-128">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>

## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="dc094-129">Ejecutar efectos secundarios en constructores</span><span class="sxs-lookup"><span data-stu-id="dc094-129">Executing side effects in constructors</span></span>

<span data-ttu-id="dc094-130">Un constructor principal de una clase puede ejecutar código en un `do` enlace.</span><span class="sxs-lookup"><span data-stu-id="dc094-130">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="dc094-131">Sin embargo, ¿qué ocurre si tiene que ejecutar código en un constructor adicional, sin un `do` enlace?</span><span class="sxs-lookup"><span data-stu-id="dc094-131">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="dc094-132">Para ello, use la `then` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="dc094-132">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="dc094-133">Los efectos secundarios del constructor principal todavía se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="dc094-133">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="dc094-134">Por lo tanto, la salida es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="dc094-134">Therefore, the output is as follows:</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

<span data-ttu-id="dc094-135">La razón por la `then` que se requiere, en lugar de otra, `do` es que la `do` palabra clave tiene su significado estándar para delimitar una `unit` expresión de devolución cuando está presente en el cuerpo de un constructor adicional.</span><span class="sxs-lookup"><span data-stu-id="dc094-135">The reason why `then` is required instead of another `do` is that the `do` keyword has its standard meaning of delimiting a `unit`-returning expression when present in the body of an additional constructor.</span></span> <span data-ttu-id="dc094-136">Solo tiene un significado especial en el contexto de los constructores principales.</span><span class="sxs-lookup"><span data-stu-id="dc094-136">It only has special meaning in the context of primary constructors.</span></span>

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="dc094-137">Identificadores propios en constructores</span><span class="sxs-lookup"><span data-stu-id="dc094-137">Self identifiers in constructors</span></span>

<span data-ttu-id="dc094-138">En otros miembros, se proporciona un nombre para el objeto actual en la definición de cada miembro.</span><span class="sxs-lookup"><span data-stu-id="dc094-138">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="dc094-139">También puede colocar el identificador propio en la primera línea de la definición de clase mediante la `as` palabra clave inmediatamente después de los parámetros del constructor.</span><span class="sxs-lookup"><span data-stu-id="dc094-139">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="dc094-140">En el ejemplo siguiente se muestra esta sintaxis.</span><span class="sxs-lookup"><span data-stu-id="dc094-140">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="dc094-141">En los constructores adicionales, también puede definir un identificador propio colocando la `as` cláusula justo después de los parámetros del constructor.</span><span class="sxs-lookup"><span data-stu-id="dc094-141">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="dc094-142">En el ejemplo siguiente se muestra esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="dc094-142">The following example illustrates this syntax:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="dc094-143">Pueden producirse problemas al intentar usar un objeto antes de que se defina por completo.</span><span class="sxs-lookup"><span data-stu-id="dc094-143">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="dc094-144">Por lo tanto, los usos del propio identificador pueden hacer que el compilador emita una advertencia e inserte comprobaciones adicionales para asegurarse de que no se tiene acceso a los miembros de un objeto antes de que se inicialice el objeto.</span><span class="sxs-lookup"><span data-stu-id="dc094-144">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="dc094-145">Solo se debe usar el identificador propio en los `do` enlaces del constructor principal o después de la `then` palabra clave en constructores adicionales.</span><span class="sxs-lookup"><span data-stu-id="dc094-145">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="dc094-146">No es necesario que el nombre del propio identificador sea `this` .</span><span class="sxs-lookup"><span data-stu-id="dc094-146">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="dc094-147">Puede ser cualquier identificador válido.</span><span class="sxs-lookup"><span data-stu-id="dc094-147">It can be any valid identifier.</span></span>

## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="dc094-148">Asignar valores a propiedades en la inicialización</span><span class="sxs-lookup"><span data-stu-id="dc094-148">Assigning values to properties at initialization</span></span>

<span data-ttu-id="dc094-149">Puede asignar valores a las propiedades de un objeto de clase en el código de inicialización anexando una lista de asignaciones del formulario `property = value` a la lista de argumentos de un constructor.</span><span class="sxs-lookup"><span data-stu-id="dc094-149">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="dc094-150">Esto se muestra en el ejemplo de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="dc094-150">This is shown in the following code example:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="dc094-151">La siguiente versión del código anterior muestra la combinación de argumentos ordinarios, argumentos opcionales y valores de propiedad en una llamada de constructor:</span><span class="sxs-lookup"><span data-stu-id="dc094-151">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a><span data-ttu-id="dc094-152">Constructores en la clase heredada</span><span class="sxs-lookup"><span data-stu-id="dc094-152">Constructors in inherited class</span></span>

<span data-ttu-id="dc094-153">Al heredar de una clase base que tiene un constructor, debe especificar sus argumentos en la cláusula inherit.</span><span class="sxs-lookup"><span data-stu-id="dc094-153">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="dc094-154">Para obtener más información, vea [constructores y herencia](../inheritance.md#constructors-and-inheritance).</span><span class="sxs-lookup"><span data-stu-id="dc094-154">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="dc094-155">Constructores estáticos o constructores de tipo</span><span class="sxs-lookup"><span data-stu-id="dc094-155">Static constructors or type constructors</span></span>

<span data-ttu-id="dc094-156">Además de especificar el código para crear objetos, `let` se pueden crear enlaces estáticos y `do` en tipos de clase que se ejecutan antes de que el tipo se use por primera vez para realizar la inicialización en el nivel de tipo.</span><span class="sxs-lookup"><span data-stu-id="dc094-156">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="dc094-157">Para obtener más información, vea [ `let` enlaces en clases](let-bindings-in-classes.md) y [ `do` enlaces en clases](do-bindings-in-classes.md).</span><span class="sxs-lookup"><span data-stu-id="dc094-157">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dc094-158">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dc094-158">See also</span></span>

- [<span data-ttu-id="dc094-159">Miembros</span><span class="sxs-lookup"><span data-stu-id="dc094-159">Members</span></span>](index.md)
