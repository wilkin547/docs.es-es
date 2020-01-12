---
title: Procedimientos recomendados para escribir pruebas unitarias
description: Obtenga información sobre los procedimientos recomendados para escribir pruebas unitarias que mejoren la calidad y la resistencia del código para proyectos de NET Core y .NET Standard.
author: jpreese
ms.author: wiwagn
ms.date: 07/28/2018
ms.openlocfilehash: 387d66bfeaf48359a27a532247a799c319f38caa
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714284"
---
# <a name="unit-testing-best-practices-with-net-core-and-net-standard"></a><span data-ttu-id="26550-103">Procedimientos recomendados de pruebas unitarias con .NET Core y .NET Standard</span><span class="sxs-lookup"><span data-stu-id="26550-103">Unit testing best practices with .NET Core and .NET Standard</span></span>

<span data-ttu-id="26550-104">La escritura de pruebas unitarias reporta muchos beneficios; las pruebas ayudan con la regresión, proporcionan documentación y facilitan un buen diseño.</span><span class="sxs-lookup"><span data-stu-id="26550-104">There are numerous benefits to writing unit tests; they help with regression, provide documentation, and facilitate good design.</span></span> <span data-ttu-id="26550-105">Pero también son difíciles de leer y, si son frágiles, pueden causar estragos en el código base.</span><span class="sxs-lookup"><span data-stu-id="26550-105">However, hard to read and brittle unit tests can wreak havoc on your code base.</span></span> <span data-ttu-id="26550-106">En este artículo se describen algunos procedimientos recomendados sobre el diseño de pruebas unitarias para proyectos de .NET Core y .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="26550-106">This article describes some best practices regarding unit test design for your .NET Core and .NET Standard projects.</span></span>

<span data-ttu-id="26550-107">En esta guía, aprenderá algunos procedimientos recomendados para escribir pruebas unitarias resistentes y fáciles de entender.</span><span class="sxs-lookup"><span data-stu-id="26550-107">In this guide, you'll learn some best practices when writing unit tests to keep your tests resilient and easy to understand.</span></span>

<span data-ttu-id="26550-108">De [John Reese](https://reese.dev), con agradecimientos especiales a [Roy Osherove](https://osherove.com/)</span><span class="sxs-lookup"><span data-stu-id="26550-108">By [John Reese](https://reese.dev) with special thanks to [Roy Osherove](https://osherove.com/)</span></span>

## <a name="why-unit-test"></a><span data-ttu-id="26550-109">El porqué de las pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="26550-109">Why unit test?</span></span>

### <a name="less-time-performing-functional-tests"></a><span data-ttu-id="26550-110">Menos tiempo para realizar pruebas funcionales</span><span class="sxs-lookup"><span data-stu-id="26550-110">Less time performing functional tests</span></span>
<span data-ttu-id="26550-111">Las pruebas funcionales son costosas.</span><span class="sxs-lookup"><span data-stu-id="26550-111">Functional tests are expensive.</span></span> <span data-ttu-id="26550-112">Normalmente implican la apertura de la aplicación y la realización de una serie de pasos que usted (u otro usuario) debe seguir para validar el comportamiento esperado.</span><span class="sxs-lookup"><span data-stu-id="26550-112">They typically involve opening up the application and performing a series of steps that you (or someone else), must follow in order to validate the expected behavior.</span></span> <span data-ttu-id="26550-113">Es posible que estos pasos no sean siempre conocidos para el evaluador, lo que significa tener que recurrir a alguien con más conocimientos en el tema para llevar a cabo la prueba.</span><span class="sxs-lookup"><span data-stu-id="26550-113">These steps may not always be known to the tester, which means they will have to reach out to someone more knowledgeable in the area in order to carry out the test.</span></span> <span data-ttu-id="26550-114">Las pruebas en sí mismas podrían llevar segundos en el caso de cambios triviales, o minutos en el de cambios más importantes.</span><span class="sxs-lookup"><span data-stu-id="26550-114">Testing itself could take seconds for trivial changes, or minutes for larger changes.</span></span> <span data-ttu-id="26550-115">Por último, este proceso debe repetirse para cada cambio que se realice en el sistema.</span><span class="sxs-lookup"><span data-stu-id="26550-115">Lastly, this process must be repeated for every change that you make in the system.</span></span>

<span data-ttu-id="26550-116">Por otra parte, las pruebas unitarias duran milisegundos, se pueden ejecutar con solo presionar un botón y no exigen necesariamente ningún conocimiento del sistema en general.</span><span class="sxs-lookup"><span data-stu-id="26550-116">Unit tests, on the other hand, take milliseconds, can be run at the press of a button and do not necessarily require any knowledge of the system at large.</span></span> <span data-ttu-id="26550-117">El que la prueba se supere o no depende del ejecutor de pruebas, no del usuario.</span><span class="sxs-lookup"><span data-stu-id="26550-117">Whether or not the test passes or fails is up to the test runner, not the individual.</span></span>

### <a name="protection-against-regression"></a><span data-ttu-id="26550-118">Protección frente a regresión</span><span class="sxs-lookup"><span data-stu-id="26550-118">Protection against regression</span></span>
<span data-ttu-id="26550-119">Los defectos de regresión son aquellos que se presentan cuando se realiza un cambio en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="26550-119">Regression defects are defects that are introduced when a change is made to the application.</span></span> <span data-ttu-id="26550-120">Es habitual que los evaluadores no solo prueben una nueva característica, sino también las ya existentes con el fin de comprobar que siguen funcionando según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="26550-120">It is common for testers to not only test their new feature but also features that existed beforehand in order to verify that previously implemented features still function as expected.</span></span>

<span data-ttu-id="26550-121">Con las pruebas unitarias, es posible volver a ejecutar el conjunto completo de pruebas después de cada compilación o incluso después de cambiar una línea de código.</span><span class="sxs-lookup"><span data-stu-id="26550-121">With unit testing, it's possible to rerun your entire suite of tests after every build or even after you change a line of code.</span></span> <span data-ttu-id="26550-122">Eso da confianza en que el nuevo código no interrumpa la funcionalidad existente.</span><span class="sxs-lookup"><span data-stu-id="26550-122">Giving you confidence that your new code does not break existing functionality.</span></span>

### <a name="executable-documentation"></a><span data-ttu-id="26550-123">Documentación ejecutable</span><span class="sxs-lookup"><span data-stu-id="26550-123">Executable documentation</span></span>
<span data-ttu-id="26550-124">Es posible que no siempre sea evidente lo que hace un método determinado o cómo se comporta ante una acción concreta.</span><span class="sxs-lookup"><span data-stu-id="26550-124">It may not always be obvious what a particular method does or how it behaves given a certain input.</span></span> <span data-ttu-id="26550-125">Es posible que se pregunte: ¿cómo se comporta este método si se le pasa una cadena en blanco?</span><span class="sxs-lookup"><span data-stu-id="26550-125">You may ask yourself: How does this method behave if I pass it a blank string?</span></span> <span data-ttu-id="26550-126">¿Null?</span><span class="sxs-lookup"><span data-stu-id="26550-126">Null?</span></span>

<span data-ttu-id="26550-127">Si tiene un conjunto de pruebas unitarias con un nombre adecuado, cada prueba debe ser capaz de explicar con claridad el resultado esperado de una acción determinada.</span><span class="sxs-lookup"><span data-stu-id="26550-127">When you have a suite of well-named unit tests, each test should be able to clearly explain the expected output for a given input.</span></span> <span data-ttu-id="26550-128">Además, debe ser capaz de comprobar que funciona.</span><span class="sxs-lookup"><span data-stu-id="26550-128">In addition, it should be able to verify that it actually works.</span></span>

### <a name="less-coupled-code"></a><span data-ttu-id="26550-129">Menos código acoplado</span><span class="sxs-lookup"><span data-stu-id="26550-129">Less coupled code</span></span>
<span data-ttu-id="26550-130">Cuando el código está estrechamente acoplado, puede resultar difícil realizar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="26550-130">When code is tightly coupled, it can be difficult to unit test.</span></span> <span data-ttu-id="26550-131">Sin crear pruebas unitarias para el código que se está escribiendo, el acoplamiento puede ser menos evidente.</span><span class="sxs-lookup"><span data-stu-id="26550-131">Without creating unit tests for the code that you're writing, coupling may be less apparent.</span></span>

<span data-ttu-id="26550-132">Al escribir pruebas para el código, este se desacopla naturalmente, ya que, de otra forma, sería más difícil de probar.</span><span class="sxs-lookup"><span data-stu-id="26550-132">Writing tests for your code will naturally decouple your code, because it would be more difficult to test otherwise.</span></span>

## <a name="characteristics-of-a-good-unit-test"></a><span data-ttu-id="26550-133">Características de una buena prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="26550-133">Characteristics of a good unit test</span></span>

- <span data-ttu-id="26550-134">**Rápida**.</span><span class="sxs-lookup"><span data-stu-id="26550-134">**Fast**.</span></span> <span data-ttu-id="26550-135">No es infrecuente que los proyectos maduros tengan miles de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="26550-135">It is not uncommon for mature projects to have thousands of unit tests.</span></span> <span data-ttu-id="26550-136">Las pruebas unitarias deberían tardar muy poco tiempo en ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="26550-136">Unit tests should take very little time to run.</span></span> <span data-ttu-id="26550-137">Milisegundos.</span><span class="sxs-lookup"><span data-stu-id="26550-137">Milliseconds.</span></span>
- <span data-ttu-id="26550-138">**Aislada**.</span><span class="sxs-lookup"><span data-stu-id="26550-138">**Isolated**.</span></span> <span data-ttu-id="26550-139">Las pruebas unitarias son independientes, se pueden ejecutar de forma aislada y no tienen ninguna dependencia en ningún factor externo, como sistemas de archivos o bases de datos.</span><span class="sxs-lookup"><span data-stu-id="26550-139">Unit tests are standalone, can be run in isolation, and have no dependencies on any outside factors such as a file system or database.</span></span>
- <span data-ttu-id="26550-140">**Reiterativa**.</span><span class="sxs-lookup"><span data-stu-id="26550-140">**Repeatable**.</span></span> <span data-ttu-id="26550-141">La ejecución de una prueba unitaria debe ser coherente con sus resultados, es decir, devolver siempre el mismo resultado si no cambia nada entre ejecuciones.</span><span class="sxs-lookup"><span data-stu-id="26550-141">Running a unit test should be consistent with its results, that is, it always returns the same result if you do not change anything in between runs.</span></span>
- <span data-ttu-id="26550-142">**Autocomprobada**.</span><span class="sxs-lookup"><span data-stu-id="26550-142">**Self-Checking**.</span></span> <span data-ttu-id="26550-143">La prueba debe ser capaz de detectar automáticamente si el resultado ha sido correcto o incorrecto sin necesidad de intervención humana.</span><span class="sxs-lookup"><span data-stu-id="26550-143">The test should be able to automatically detect if it passed or failed without any human interaction.</span></span>
- <span data-ttu-id="26550-144">**Oportuna**.</span><span class="sxs-lookup"><span data-stu-id="26550-144">**Timely**.</span></span> <span data-ttu-id="26550-145">Una prueba unitaria no debe tardar un tiempo desproporcionado en escribirse en comparación con el código que se va a probar.</span><span class="sxs-lookup"><span data-stu-id="26550-145">A unit test should not take a disproportionately long time to write compared to the code being tested.</span></span> <span data-ttu-id="26550-146">Si observa que la prueba del código tarda mucho en comparación con su escritura, considere un diseño más fácil de probar.</span><span class="sxs-lookup"><span data-stu-id="26550-146">If you find testing the code taking a large amount of time compared to writing the code, consider a design that is more testable.</span></span>

## <a name="lets-speak-the-same-language"></a><span data-ttu-id="26550-147">Vamos a hablar el mismo idioma</span><span class="sxs-lookup"><span data-stu-id="26550-147">Let's speak the same language</span></span>
<span data-ttu-id="26550-148">El término *ficticio* desafortunadamente se emplea muy mal cuando se habla sobre las pruebas.</span><span class="sxs-lookup"><span data-stu-id="26550-148">The term *mock* is unfortunately very misused when talking about testing.</span></span> <span data-ttu-id="26550-149">A continuación se definen los tipos más comunes de *emulaciones* al escribir pruebas unitarias:</span><span class="sxs-lookup"><span data-stu-id="26550-149">The following defines the most common types of *fakes* when writing unit tests:</span></span>

<span data-ttu-id="26550-150">*Emulación*: una emulación es un término genérico que se puede usar para describir un stub o un objeto ficticio.</span><span class="sxs-lookup"><span data-stu-id="26550-150">*Fake* - A fake is a generic term which can be used to describe either a stub or a mock object.</span></span> <span data-ttu-id="26550-151">Si es un stub o un objeto ficticio depende del contexto en el que se use.</span><span class="sxs-lookup"><span data-stu-id="26550-151">Whether it is a stub or a mock depends on the context in which it's used.</span></span> <span data-ttu-id="26550-152">Es decir, una emulación puede ser un stub o un objeto ficticio.</span><span class="sxs-lookup"><span data-stu-id="26550-152">So in other words, a fake can be a stub or a mock.</span></span>

<span data-ttu-id="26550-153">*Objeto ficticio*: un objeto ficticio es una emulación del sistema que decide si una prueba unitaria se ha superado o no.</span><span class="sxs-lookup"><span data-stu-id="26550-153">*Mock* - A mock object is a fake object in the system that decides whether or not a unit test has passed or failed.</span></span> <span data-ttu-id="26550-154">Un objeto ficticio comienza como una emulación hasta que se declara en ella.</span><span class="sxs-lookup"><span data-stu-id="26550-154">A mock starts out as a Fake until it is asserted against.</span></span>

<span data-ttu-id="26550-155">*Stub*: un stub es un reemplazo controlable para una dependencia existente (o colaborador) en el sistema.</span><span class="sxs-lookup"><span data-stu-id="26550-155">*Stub* - A stub is a controllable replacement for an existing dependency (or collaborator) in the system.</span></span> <span data-ttu-id="26550-156">Con un stub, puede probar el código sin tratar directamente con la dependencia.</span><span class="sxs-lookup"><span data-stu-id="26550-156">By using a stub, you can test your code without dealing with the dependency directly.</span></span> <span data-ttu-id="26550-157">De forma predeterminada, una emulación empieza como un stub.</span><span class="sxs-lookup"><span data-stu-id="26550-157">By default, a fake starts out as a stub.</span></span>

<span data-ttu-id="26550-158">Tenga en cuenta el fragmento de código siguiente:</span><span class="sxs-lookup"><span data-stu-id="26550-158">Consider the following code snippet:</span></span>

```csharp
var mockOrder = new MockOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

<span data-ttu-id="26550-159">Es un ejemplo de stub al que se hace referencia como un objeto ficticio.</span><span class="sxs-lookup"><span data-stu-id="26550-159">This would be an example of stub being referred to as a mock.</span></span> <span data-ttu-id="26550-160">En este caso, es un stub.</span><span class="sxs-lookup"><span data-stu-id="26550-160">In this case, it is a stub.</span></span> <span data-ttu-id="26550-161">Simplemente está pasando el pedido para poder crear una instancia de `Purchase` (el sistema sometido a prueba).</span><span class="sxs-lookup"><span data-stu-id="26550-161">You're just passing in the Order as a means to be able to instantiate `Purchase` (the system under test).</span></span> <span data-ttu-id="26550-162">El nombre `MockOrder` también es muy confuso porque, una vez más, el pedido no es un objeto ficticio.</span><span class="sxs-lookup"><span data-stu-id="26550-162">The name `MockOrder` is also very misleading because again, the order is not a mock.</span></span>

<span data-ttu-id="26550-163">Un mejor enfoque sería</span><span class="sxs-lookup"><span data-stu-id="26550-163">A better approach would be</span></span>

```csharp
var stubOrder = new FakeOrder();
var purchase = new Purchase(stubOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

<span data-ttu-id="26550-164">Al cambiar el nombre de la clase `FakeOrder`, la ha convertido en mucho más genérica, con lo que puede usarse como objeto ficticio o stub.</span><span class="sxs-lookup"><span data-stu-id="26550-164">By renaming the class to `FakeOrder`, you've made the class a lot more generic, the class can be used as a mock or a stub.</span></span> <span data-ttu-id="26550-165">Lo que sea mejor para el caso de prueba.</span><span class="sxs-lookup"><span data-stu-id="26550-165">Whichever is better for the test case.</span></span> <span data-ttu-id="26550-166">En el ejemplo anterior, `FakeOrder` se usa como un stub.</span><span class="sxs-lookup"><span data-stu-id="26550-166">In the above example, `FakeOrder` is used as a stub.</span></span> <span data-ttu-id="26550-167">No usa `FakeOrder` de ninguna forma durante la aserción.</span><span class="sxs-lookup"><span data-stu-id="26550-167">You're not using the `FakeOrder` in any shape or form during the assert.</span></span> <span data-ttu-id="26550-168">`FakeOrder` simplemente se ha pasado a la clase `Purchase` para satisfacer los requisitos del constructor.</span><span class="sxs-lookup"><span data-stu-id="26550-168">`FakeOrder` was just passed into the `Purchase` class to satisfy the requirements of the constructor.</span></span>

<span data-ttu-id="26550-169">Para usarlo como un objeto ficticio, podría hacer algo parecido a esto:</span><span class="sxs-lookup"><span data-stu-id="26550-169">To use it as a Mock, you could do something like this</span></span>

```csharp
var mockOrder = new FakeOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(mockOrder.Validated);
```

<span data-ttu-id="26550-170">En este caso, va a registrar una propiedad en la emulación (la declara en ella), por lo que en el fragmento de código anterior, `mockOrder` es un objeto simulado.</span><span class="sxs-lookup"><span data-stu-id="26550-170">In this case, you are checking a property on the Fake (asserting against it), so in the above code snippet, the `mockOrder` is a Mock.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26550-171">Es importante tener clara esta terminología.</span><span class="sxs-lookup"><span data-stu-id="26550-171">It's important to get this terminology correct.</span></span> <span data-ttu-id="26550-172">Si se denomina a los stubs "objetos ficticios", los demás desarrolladores van a realizar suposiciones falsas sobre su intención.</span><span class="sxs-lookup"><span data-stu-id="26550-172">If you call your stubs "mocks", other developers are going to make false assumptions about your intent.</span></span>

<span data-ttu-id="26550-173">Lo principal que debe recordar sobre los objetos ficticios frente a los stubs es que los objetos ficticios son como los stubs, pero se declara en el objeto ficticio, y no en un stub.</span><span class="sxs-lookup"><span data-stu-id="26550-173">The main thing to remember about mocks versus stubs is that mocks are just like stubs, but you assert against the mock object, whereas you do not assert against a stub.</span></span>

## <a name="best-practices"></a><span data-ttu-id="26550-174">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="26550-174">Best practices</span></span>

### <a name="naming-your-tests"></a><span data-ttu-id="26550-175">Asignar nombre a las pruebas</span><span class="sxs-lookup"><span data-stu-id="26550-175">Naming your tests</span></span>
<span data-ttu-id="26550-176">El nombre de la prueba debe constar de tres partes:</span><span class="sxs-lookup"><span data-stu-id="26550-176">The name of your test should consist of three parts:</span></span>

- <span data-ttu-id="26550-177">Nombre del método que se va a probar.</span><span class="sxs-lookup"><span data-stu-id="26550-177">The name of the method being tested.</span></span>
- <span data-ttu-id="26550-178">Escenario en el que se está probando.</span><span class="sxs-lookup"><span data-stu-id="26550-178">The scenario under which it's being tested.</span></span>
- <span data-ttu-id="26550-179">Comportamiento esperado al invocar al escenario.</span><span class="sxs-lookup"><span data-stu-id="26550-179">The expected behavior when the scenario is invoked.</span></span>

#### <a name="why"></a><span data-ttu-id="26550-180">¿Por qué?</span><span class="sxs-lookup"><span data-stu-id="26550-180">Why?</span></span>

- <span data-ttu-id="26550-181">Los estándares de nomenclatura son importantes porque expresan de forma explícita la intención de la prueba.</span><span class="sxs-lookup"><span data-stu-id="26550-181">Naming standards are important because they explicitly express the intent of the test.</span></span>

<span data-ttu-id="26550-182">Las pruebas van más allá de garantizar que el código funciona, también proporcionan documentación.</span><span class="sxs-lookup"><span data-stu-id="26550-182">Tests are more than just making sure your code works, they also provide documentation.</span></span> <span data-ttu-id="26550-183">Con solo mirar el conjunto de pruebas unitarias, debe ser capaz de deducir el comportamiento del código sin ni siquiera mirar el propio código.</span><span class="sxs-lookup"><span data-stu-id="26550-183">Just by looking at the suite of unit tests, you should be able to infer the behavior of your code without even looking at the code itself.</span></span> <span data-ttu-id="26550-184">Además, cuando no se superan las pruebas, puede ver exactamente qué escenarios no cumplen las expectativas.</span><span class="sxs-lookup"><span data-stu-id="26550-184">Additionally, when tests fail, you can see exactly which scenarios do not meet your expectations.</span></span>

#### <a name="bad"></a><span data-ttu-id="26550-185">Malo:</span><span class="sxs-lookup"><span data-stu-id="26550-185">Bad:</span></span>
[!code-csharp[BeforeNaming](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeNaming)]

#### <a name="better"></a><span data-ttu-id="26550-186">Mejor:</span><span class="sxs-lookup"><span data-stu-id="26550-186">Better:</span></span>
[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="arranging-your-tests"></a><span data-ttu-id="26550-187">Organizar las pruebas</span><span class="sxs-lookup"><span data-stu-id="26550-187">Arranging your tests</span></span>
<span data-ttu-id="26550-188">**Organizar, actuar, declarar** es un patrón común al realizar pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="26550-188">**Arrange, Act, Assert** is a common pattern when unit testing.</span></span> <span data-ttu-id="26550-189">Como el propio nombre implica, consta de tres acciones principales:</span><span class="sxs-lookup"><span data-stu-id="26550-189">As the name implies, it consists of three main actions:</span></span>

- <span data-ttu-id="26550-190">*Organizar* los objetos, crearlos y configurarlos según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="26550-190">*Arrange* your objects, creating and setting them up as necessary.</span></span>
- <span data-ttu-id="26550-191">*Actuar* en un objeto.</span><span class="sxs-lookup"><span data-stu-id="26550-191">*Act* on an object.</span></span>
- <span data-ttu-id="26550-192">*Declarar* que algo es como se espera.</span><span class="sxs-lookup"><span data-stu-id="26550-192">*Assert* that something is as expected.</span></span>

#### <a name="why"></a><span data-ttu-id="26550-193">¿Por qué?</span><span class="sxs-lookup"><span data-stu-id="26550-193">Why?</span></span>

- <span data-ttu-id="26550-194">Separa claramente lo que se está probando de los pasos *organizar* y *declarar*.</span><span class="sxs-lookup"><span data-stu-id="26550-194">Clearly separates what is being tested from the *arrange* and *assert* steps.</span></span>
- <span data-ttu-id="26550-195">Menos posibilidad de mezclar aserciones con el código para "actuar".</span><span class="sxs-lookup"><span data-stu-id="26550-195">Less chance to intermix assertions with "Act" code.</span></span>

<span data-ttu-id="26550-196">La legibilidad es uno de los aspectos más importantes a la hora de escribir una prueba.</span><span class="sxs-lookup"><span data-stu-id="26550-196">Readability is one of the most important aspects when writing a test.</span></span> <span data-ttu-id="26550-197">Al separar cada una de estas acciones dentro de la prueba, se resaltan claramente las dependencias necesarias para llamar al código, la forma de llamarlo y lo que se intenta declarar.</span><span class="sxs-lookup"><span data-stu-id="26550-197">Separating each of these actions within the test clearly highlight the dependencies required to call your code, how your code is being called, and what you are trying to assert.</span></span> <span data-ttu-id="26550-198">Aunque es posible combinar algunos pasos y reducir el tamaño de la prueba, el objetivo principal es que sea lo más legible posible.</span><span class="sxs-lookup"><span data-stu-id="26550-198">While it may be possible to combine some steps and reduce the size of your test, the primary goal is to make the test as readable as possible.</span></span>

#### <a name="bad"></a><span data-ttu-id="26550-199">Malo:</span><span class="sxs-lookup"><span data-stu-id="26550-199">Bad:</span></span>
[!code-csharp[BeforeArranging](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeArranging)]

#### <a name="better"></a><span data-ttu-id="26550-200">Mejor:</span><span class="sxs-lookup"><span data-stu-id="26550-200">Better:</span></span>
[!code-csharp[AfterArranging](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterArranging)]

### <a name="write-minimally-passing-tests"></a><span data-ttu-id="26550-201">Escribir pruebas correctas lo más sencillas posible</span><span class="sxs-lookup"><span data-stu-id="26550-201">Write minimally passing tests</span></span>
<span data-ttu-id="26550-202">La entrada que se use en una prueba unitaria debe ser lo más sencilla posible para comprobar el comportamiento que se está probando.</span><span class="sxs-lookup"><span data-stu-id="26550-202">The input to be used in a unit test should be the simplest possible in order to verify the behavior that you are currently testing.</span></span>

#### <a name="why"></a><span data-ttu-id="26550-203">¿Por qué?</span><span class="sxs-lookup"><span data-stu-id="26550-203">Why?</span></span>

- <span data-ttu-id="26550-204">Las pruebas se hacen más resistentes a los cambios futuros en el código base.</span><span class="sxs-lookup"><span data-stu-id="26550-204">Tests become more resilient to future changes in the codebase.</span></span>
- <span data-ttu-id="26550-205">Más cercano al comportamiento de prueba que a la implementación.</span><span class="sxs-lookup"><span data-stu-id="26550-205">Closer to testing behavior over implementation.</span></span>

<span data-ttu-id="26550-206">Las pruebas que incluyen más información de la necesaria para superarse tienen una mayor posibilidad de incorporar errores en la prueba y pueden hacer confusa su intención.</span><span class="sxs-lookup"><span data-stu-id="26550-206">Tests that include more information than required to pass the test have a higher chance of introducing errors into the test and can make the intent of the test less clear.</span></span> <span data-ttu-id="26550-207">Al escribir pruebas, el usuario quiere centrarse en el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="26550-207">When writing tests you want to focus on the behavior.</span></span> <span data-ttu-id="26550-208">El establecimiento de propiedades adicionales en los modelos o el empleo de valores distintos de cero cuando no es necesario solo resta de lo que se quiere probar.</span><span class="sxs-lookup"><span data-stu-id="26550-208">Setting extra properties on models or using non-zero values when not required, only detracts from what you are trying to prove.</span></span>

#### <a name="bad"></a><span data-ttu-id="26550-209">Malo:</span><span class="sxs-lookup"><span data-stu-id="26550-209">Bad:</span></span>
[!code-csharp[BeforeMinimallyPassing](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeMinimallyPassing)]

#### <a name="better"></a><span data-ttu-id="26550-210">Mejor:</span><span class="sxs-lookup"><span data-stu-id="26550-210">Better:</span></span>
[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="avoid-magic-strings"></a><span data-ttu-id="26550-211">Evitar cadenas mágicas</span><span class="sxs-lookup"><span data-stu-id="26550-211">Avoid magic strings</span></span>
<span data-ttu-id="26550-212">La asignación de nombres a las variables de las pruebas unitarias es tan importante, si no más, que la asignación de nombres a las variables del código de producción.</span><span class="sxs-lookup"><span data-stu-id="26550-212">Naming variables in unit tests is as important, if not more important, than naming variables in production code.</span></span> <span data-ttu-id="26550-213">Las pruebas unitarias no deben contener cadenas mágicas.</span><span class="sxs-lookup"><span data-stu-id="26550-213">Unit tests should not contain magic strings.</span></span>

#### <a name="why"></a><span data-ttu-id="26550-214">¿Por qué?</span><span class="sxs-lookup"><span data-stu-id="26550-214">Why?</span></span>

- <span data-ttu-id="26550-215">Evita la necesidad de que el lector de la prueba inspeccione el código de producción con el fin de averiguar lo que hace que el valor sea especial.</span><span class="sxs-lookup"><span data-stu-id="26550-215">Prevents the need for the reader of the test to inspect the production code in order to figure out what makes the value special.</span></span>
- <span data-ttu-id="26550-216">Muestra explícitamente lo que se intenta *probar*, en lugar de lo que se intenta *lograr*.</span><span class="sxs-lookup"><span data-stu-id="26550-216">Explicitly shows what you're trying to *prove* rather than trying to *accomplish*.</span></span>

<span data-ttu-id="26550-217">Las cadenas mágicas pueden provocar confusión al lector de las pruebas.</span><span class="sxs-lookup"><span data-stu-id="26550-217">Magic strings can cause confusion to the reader of your tests.</span></span> <span data-ttu-id="26550-218">Si una cadena tiene un aspecto fuera de lo normal, puede preguntarse por qué se ha elegido un determinado valor para un parámetro o valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="26550-218">If a string looks out of the ordinary, they may wonder why a certain value was chosen for a parameter or return value.</span></span> <span data-ttu-id="26550-219">Esto puede dar lugar a un vistazo más detallado a los detalles de implementación, en lugar de centrarse en la prueba.</span><span class="sxs-lookup"><span data-stu-id="26550-219">This may lead them to take a closer look at the implementation details, rather than focus on the test.</span></span>

> [!TIP] 
> <span data-ttu-id="26550-220">Al escribir pruebas, su objetivo debe ser expresar tanta intención como sea posible.</span><span class="sxs-lookup"><span data-stu-id="26550-220">When writing tests, you should aim to express as much intent as possible.</span></span> <span data-ttu-id="26550-221">En el caso de las cadenas mágicas, un buen enfoque es asignar estos valores a constantes.</span><span class="sxs-lookup"><span data-stu-id="26550-221">In the case of magic strings, a good approach is to assign these values to constants.</span></span>

#### <a name="bad"></a><span data-ttu-id="26550-222">Malo:</span><span class="sxs-lookup"><span data-stu-id="26550-222">Bad:</span></span>
[!code-csharp[BeforeMagicString](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeMagicString)]

#### <a name="better"></a><span data-ttu-id="26550-223">Mejor:</span><span class="sxs-lookup"><span data-stu-id="26550-223">Better:</span></span>
[!code-csharp[AfterMagicString](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterMagicString)]

### <a name="avoid-logic-in-tests"></a><span data-ttu-id="26550-224">Evitar la lógica en las pruebas</span><span class="sxs-lookup"><span data-stu-id="26550-224">Avoid logic in tests</span></span>
<span data-ttu-id="26550-225">Al escribir las pruebas unitarias, evite la concatenación de cadenas manual y las condiciones lógicas como `if`, `while`, `for`, `switch`, etc.</span><span class="sxs-lookup"><span data-stu-id="26550-225">When writing your unit tests avoid manual string concatenation and logical conditions such as `if`, `while`, `for`, `switch`, etc.</span></span>

#### <a name="why"></a><span data-ttu-id="26550-226">¿Por qué?</span><span class="sxs-lookup"><span data-stu-id="26550-226">Why?</span></span>

- <span data-ttu-id="26550-227">Menos posibilidad de incorporar un error a las pruebas.</span><span class="sxs-lookup"><span data-stu-id="26550-227">Less chance to introduce a bug inside of your tests.</span></span>
- <span data-ttu-id="26550-228">El foco está en el resultado final, en lugar de en los detalles de implementación.</span><span class="sxs-lookup"><span data-stu-id="26550-228">Focus on the end result, rather than implementation details.</span></span>

<span data-ttu-id="26550-229">Al incorporar lógica al conjunto de pruebas, aumenta considerablemente la posibilidad de agregar un error.</span><span class="sxs-lookup"><span data-stu-id="26550-229">When you introduce logic into your test suite, the chance of introducing a bug into it increases dramatically.</span></span> <span data-ttu-id="26550-230">El último lugar en el que se quiere encontrar un error es el conjunto de pruebas.</span><span class="sxs-lookup"><span data-stu-id="26550-230">The last place that you want to find a bug is within your test suite.</span></span> <span data-ttu-id="26550-231">Debe tener mucha confianza en que las pruebas funcionan, de lo contrario, no confiará en ellas.</span><span class="sxs-lookup"><span data-stu-id="26550-231">You should have a high level of confidence that your tests work, otherwise, you will not trust them.</span></span> <span data-ttu-id="26550-232">Las pruebas en las que no se confía, no proporcionan ningún valor.</span><span class="sxs-lookup"><span data-stu-id="26550-232">Tests that you do not trust, do not provide any value.</span></span> <span data-ttu-id="26550-233">Cuando se produce un error en una prueba, quiere saber que algo va mal realmente con el código y que no se puede omitir.</span><span class="sxs-lookup"><span data-stu-id="26550-233">When a test fails, you want to have a sense that something is actually wrong with your code and that it cannot be ignored.</span></span>

> [!TIP]
> <span data-ttu-id="26550-234">Si la lógica en la prueba parece inevitable, considere la posibilidad de dividirla en dos o más pruebas diferentes.</span><span class="sxs-lookup"><span data-stu-id="26550-234">If logic in your test seems unavoidable, consider splitting the test up into two or more different tests.</span></span>

#### <a name="bad"></a><span data-ttu-id="26550-235">Malo:</span><span class="sxs-lookup"><span data-stu-id="26550-235">Bad:</span></span>
[!code-csharp[LogicInTests](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#LogicInTests)]

#### <a name="better"></a><span data-ttu-id="26550-236">Mejor:</span><span class="sxs-lookup"><span data-stu-id="26550-236">Better:</span></span>
[!code-csharp[AfterTestLogic](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterTestLogic)]

### <a name="prefer-helper-methods-to-setup-and-teardown"></a><span data-ttu-id="26550-237">Se prefieren métodos auxiliares a la instalación y el desmontaje</span><span class="sxs-lookup"><span data-stu-id="26550-237">Prefer helper methods to setup and teardown</span></span>
<span data-ttu-id="26550-238">Si necesita un objeto o un estado similares para las pruebas, se prefiere un método auxiliar al aprovechamiento de los atributos de instalación y desmontaje, si existen.</span><span class="sxs-lookup"><span data-stu-id="26550-238">If you require a similar object or state for your tests, prefer a helper method than leveraging Setup and Teardown attributes if they exist.</span></span>

#### <a name="why"></a><span data-ttu-id="26550-239">¿Por qué?</span><span class="sxs-lookup"><span data-stu-id="26550-239">Why?</span></span>

- <span data-ttu-id="26550-240">Menos confusión al leer las pruebas, puesto que todo el código es visible desde dentro de cada prueba.</span><span class="sxs-lookup"><span data-stu-id="26550-240">Less confusion when reading the tests since all of the code is visible from within each test.</span></span>
- <span data-ttu-id="26550-241">Menor posibilidad de configurar demasiado o muy poco para la prueba.</span><span class="sxs-lookup"><span data-stu-id="26550-241">Less chance of setting up too much or too little for the given test.</span></span>
- <span data-ttu-id="26550-242">Menor posibilidad de compartir el estado entre las pruebas, lo que crea dependencias no deseadas entre ellas.</span><span class="sxs-lookup"><span data-stu-id="26550-242">Less chance of sharing state between tests which creates unwanted dependencies between them.</span></span>

<span data-ttu-id="26550-243">En los marcos de trabajo de pruebas unitarias, se llama a `Setup` antes de cada prueba unitaria del conjunto de pruebas.</span><span class="sxs-lookup"><span data-stu-id="26550-243">In unit testing frameworks, `Setup` is called before each and every unit test within your test suite.</span></span> <span data-ttu-id="26550-244">Aunque algunos puedan verlo como una herramienta útil, por lo general termina por dar lugar a pruebas recargadas y difíciles de leer.</span><span class="sxs-lookup"><span data-stu-id="26550-244">While some may see this as a useful tool, it generally ends up leading to bloated and hard to read tests.</span></span> <span data-ttu-id="26550-245">Cada prueba normalmente tendrá requisitos diferentes para funcionar y ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="26550-245">Each test will generally have different requirements in order to get the test up and running.</span></span> <span data-ttu-id="26550-246">Por desgracia, `Setup` obliga a usar los mismos requisitos para cada prueba.</span><span class="sxs-lookup"><span data-stu-id="26550-246">Unfortunately, `Setup` forces you to use the exact same requirements for each test.</span></span>

> [!NOTE] 
> <span data-ttu-id="26550-247">xUnit ha quitado la instalación y el desmontaje a partir de la versión 2.x</span><span class="sxs-lookup"><span data-stu-id="26550-247">xUnit has removed both SetUp and TearDown as of version 2.x</span></span>

#### <a name="bad"></a><span data-ttu-id="26550-248">Malo:</span><span class="sxs-lookup"><span data-stu-id="26550-248">Bad:</span></span>
[!code-csharp[BeforeSetup](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeSetup)]

```csharp
// more tests...
```

[!code-csharp[BeforeHelperMethod](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeHelperMethod)]

#### <a name="better"></a><span data-ttu-id="26550-249">Mejor:</span><span class="sxs-lookup"><span data-stu-id="26550-249">Better:</span></span>
[!code-csharp[AfterHelperMethod](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterHelperMethod)]

```csharp
// more tests...
```

[!code-csharp[AfterSetup](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterSetup)]

### <a name="avoid-multiple-asserts"></a><span data-ttu-id="26550-250">Evitar varias aserciones</span><span class="sxs-lookup"><span data-stu-id="26550-250">Avoid multiple asserts</span></span>
<span data-ttu-id="26550-251">Al escribir las pruebas, intente incluir solo una aserción por prueba.</span><span class="sxs-lookup"><span data-stu-id="26550-251">When writing your tests, try to only include one Assert per test.</span></span> <span data-ttu-id="26550-252">Los enfoques comunes para usar solo una aserción incluyen:</span><span class="sxs-lookup"><span data-stu-id="26550-252">Common approaches to using only one assert include:</span></span>

- <span data-ttu-id="26550-253">Crear una prueba independiente para cada aserción.</span><span class="sxs-lookup"><span data-stu-id="26550-253">Create a separate test for each assert.</span></span>
- <span data-ttu-id="26550-254">Usar pruebas con parámetros.</span><span class="sxs-lookup"><span data-stu-id="26550-254">Use parameterized tests.</span></span>

#### <a name="why"></a><span data-ttu-id="26550-255">¿Por qué?</span><span class="sxs-lookup"><span data-stu-id="26550-255">Why?</span></span>

- <span data-ttu-id="26550-256">Si se produce un error en una aserción, no se evalúan las aserciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="26550-256">If one Assert fails, the subsequent Asserts will not be evaluated.</span></span>
- <span data-ttu-id="26550-257">Garantiza que no se estén declarando varios casos en las pruebas.</span><span class="sxs-lookup"><span data-stu-id="26550-257">Ensures you are not asserting multiple cases in your tests.</span></span>
- <span data-ttu-id="26550-258">Proporciona la imagen completa de por qué se producen errores en las pruebas.</span><span class="sxs-lookup"><span data-stu-id="26550-258">Gives you the entire picture as to why your tests are failing.</span></span> 

<span data-ttu-id="26550-259">Al incorporar varias aserciones en un caso de prueba, no se garantiza que se ejecuten todas.</span><span class="sxs-lookup"><span data-stu-id="26550-259">When introducing multiple asserts into a test case, it is not guaranteed that all of the asserts will be executed.</span></span> <span data-ttu-id="26550-260">En la mayoría de los marcos de trabajo de pruebas unitarias, una vez que se produce un error en una aserción de una prueba unitaria, las pruebas siguientes se consideran erróneas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="26550-260">In most unit testing frameworks, once an assertion fails in a unit test, the proceeding tests are automatically considered to be failing.</span></span> <span data-ttu-id="26550-261">Esto puede ser confuso, ya que funciones que realmente están funcionando se muestran como erróneas.</span><span class="sxs-lookup"><span data-stu-id="26550-261">This can be confusing as functionality that is actually working, will be shown as failing.</span></span>

> [!NOTE]
> <span data-ttu-id="26550-262">Una excepción común a esta regla es cuando se declara en un objeto.</span><span class="sxs-lookup"><span data-stu-id="26550-262">A common exception to this rule is when asserting against an object.</span></span> <span data-ttu-id="26550-263">En este caso, suele ser aceptable que haya varias aserciones en cada propiedad para asegurarse de que el objeto está en el estado que se espera que esté.</span><span class="sxs-lookup"><span data-stu-id="26550-263">In this case, it is generally acceptable to have multiple asserts against each property to ensure the object is in the state that you expect it to be in.</span></span>

#### <a name="bad"></a><span data-ttu-id="26550-264">Malo:</span><span class="sxs-lookup"><span data-stu-id="26550-264">Bad:</span></span>
[!code-csharp[BeforeMultipleAsserts](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeMultipleAsserts)]

#### <a name="better"></a><span data-ttu-id="26550-265">Mejor:</span><span class="sxs-lookup"><span data-stu-id="26550-265">Better:</span></span>
[!code-csharp[AfterMultipleAsserts](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterMultipleAsserts)]

### <a name="validate-private-methods-by-unit-testing-public-methods"></a><span data-ttu-id="26550-266">Validar métodos privados mediante la prueba unitaria de métodos públicos</span><span class="sxs-lookup"><span data-stu-id="26550-266">Validate private methods by unit testing public methods</span></span>
<span data-ttu-id="26550-267">En la mayoría de los casos, no debería haber necesidad de probar un método privado.</span><span class="sxs-lookup"><span data-stu-id="26550-267">In most cases, there should not be a need to test a private method.</span></span> <span data-ttu-id="26550-268">Los métodos privados son un detalle de implementación.</span><span class="sxs-lookup"><span data-stu-id="26550-268">Private methods are an implementation detail.</span></span> <span data-ttu-id="26550-269">Se puede considerar de esta forma: los métodos privados nunca existen de forma aislada.</span><span class="sxs-lookup"><span data-stu-id="26550-269">You can think of it this way: private methods never exist in isolation.</span></span> <span data-ttu-id="26550-270">En algún momento, va a haber un método público que llame al método privado como parte de su implementación.</span><span class="sxs-lookup"><span data-stu-id="26550-270">At some point, there is going to be a public facing method that calls the private method as part of its implementation.</span></span> <span data-ttu-id="26550-271">Lo que debería importarle es el resultado final del método público que llama al privado.</span><span class="sxs-lookup"><span data-stu-id="26550-271">What you should care about is the end result of the public method that calls into the private one.</span></span> 

<span data-ttu-id="26550-272">Considere el caso siguiente</span><span class="sxs-lookup"><span data-stu-id="26550-272">Consider the following case</span></span>

```csharp
public string ParseLogLine(string input)
{
    var sanitizedInput = TrimInput(input);
    return sanitizedInput;
}

private string TrimInput(string input)
{
    return input.Trim();
}
```

<span data-ttu-id="26550-273">Su primera reacción puede ser empezar a escribir una prueba para `TrimInput` porque quiere asegurarse de que el método funciona según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="26550-273">Your first reaction may be to start writing a test for `TrimInput` because you want to make sure that the method is working as expected.</span></span> <span data-ttu-id="26550-274">Pero es muy posible que `ParseLogLine` manipule a `sanitizedInput` de una forma totalmente imprevista, con lo que una prueba en `TrimInput` sería inútil.</span><span class="sxs-lookup"><span data-stu-id="26550-274">However, it is entirely possible that `ParseLogLine` manipulates `sanitizedInput` in such a way that you do not expect, rendering a test against `TrimInput` useless.</span></span> 

<span data-ttu-id="26550-275">La prueba real debe realizarse en el método público `ParseLogLine`, porque eso es lo debe importarle en última instancia.</span><span class="sxs-lookup"><span data-stu-id="26550-275">The real test should be done against the public facing method `ParseLogLine` because that is what you should ultimately care about.</span></span> 

```csharp
public void ParseLogLine_ByDefault_ReturnsTrimmedResult()
{
    var parser = new Parser();

    var result = parser.ParseLogLine(" a ");

    Assert.Equals("a", result);
}
```

<span data-ttu-id="26550-276">Con este punto de vista, si ve un método privado, busque el método público y escriba las pruebas en ese método.</span><span class="sxs-lookup"><span data-stu-id="26550-276">With this viewpoint, if you see a private method, find the public method and write your tests against that method.</span></span> <span data-ttu-id="26550-277">Simplemente porque un método privado devuelva el resultado esperado, no significa que el sistema que finalmente llama al método privado use el resultado correctamente.</span><span class="sxs-lookup"><span data-stu-id="26550-277">Just because a private method returns the expected result, does not mean the system that eventually calls the private method uses the result correctly.</span></span>

### <a name="stub-static-references"></a><span data-ttu-id="26550-278">Referencias estáticas de stub</span><span class="sxs-lookup"><span data-stu-id="26550-278">Stub static references</span></span>
<span data-ttu-id="26550-279">Uno de los principios de una prueba unitaria es que debe tener control total del sistema sometido a prueba.</span><span class="sxs-lookup"><span data-stu-id="26550-279">One of the principles of a unit test is that it must have full control of the system under test.</span></span> <span data-ttu-id="26550-280">Esto puede ser problemático cuando el código de producción incluye llamadas a referencias estáticas (por ejemplo, `DateTime.Now`).</span><span class="sxs-lookup"><span data-stu-id="26550-280">This can be problematic when production code includes calls to static references (e.g. `DateTime.Now`).</span></span> <span data-ttu-id="26550-281">Considere el código siguiente</span><span class="sxs-lookup"><span data-stu-id="26550-281">Consider the following code</span></span>

```csharp
public int GetDiscountedPrice(int price)
{
    if(DateTime.Now.DayOfWeek == DayOfWeek.Tuesday) 
    {
        return price / 2;
    }
    else 
    {
        return price;
    }
}
```

<span data-ttu-id="26550-282">¿Cómo se podrían realizar pruebas unitarias de este código?</span><span class="sxs-lookup"><span data-stu-id="26550-282">How can this code possibly be unit tested?</span></span> <span data-ttu-id="26550-283">Puede probar un enfoque como</span><span class="sxs-lookup"><span data-stu-id="26550-283">You may try an approach such as</span></span>

```csharp
public void GetDiscountedPrice_ByDefault_ReturnsFullPrice()
{
    var priceCalculator = new PriceCalculator();

    var actual = priceCalculator.GetDiscountedPrice(2);

    Assert.Equals(2, actual)
}

public void GetDiscountedPrice_OnTuesday_ReturnsHalfPrice()
{
    var priceCalculator = new PriceCalculator();

    var actual = priceCalculator.GetDiscountedPrice(2);

    Assert.Equals(1, actual);
}
```

<span data-ttu-id="26550-284">Lamentablemente, pronto comprobará que hay un par de problemas con las pruebas.</span><span class="sxs-lookup"><span data-stu-id="26550-284">Unfortunately, you will quickly realize that there are a couple problems with your tests.</span></span> 

- <span data-ttu-id="26550-285">Si el conjunto de pruebas se ejecuta un martes, se superará la segunda prueba, pero se producirá un error en la primera.</span><span class="sxs-lookup"><span data-stu-id="26550-285">If the test suite is run on a Tuesday, the second test will pass, but the first test will fail.</span></span>
- <span data-ttu-id="26550-286">Si el conjunto de pruebas se ejecuta otro día, se superará la primera prueba, pero se producirá un error en la segunda.</span><span class="sxs-lookup"><span data-stu-id="26550-286">If the test suite is run on any other day, the first test will pass, but the second test will fail.</span></span>

<span data-ttu-id="26550-287">Para solucionar estos problemas, debe incorporar un *arreglo* en el código de producción.</span><span class="sxs-lookup"><span data-stu-id="26550-287">To solve these problems, you'll need to introduce a *seam* into your production code.</span></span> <span data-ttu-id="26550-288">Un enfoque consiste en encapsular el código que necesita controlar en una interfaz y hacer que el código de producción dependa de esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="26550-288">One approach is to wrap the code that you need to control in an interface and have the production code depend on that interface.</span></span>

```csharp
public interface IDateTimeProvider
{
    DayOfWeek DayOfWeek();
}

public int GetDiscountedPrice(int price, IDateTimeProvider dateTimeProvider)
{
    if(dateTimeProvider.DayOfWeek() == DayOfWeek.Tuesday) 
    {
        return price / 2;
    }
    else 
    {
        return price;
    }
}
```

<span data-ttu-id="26550-289">El conjunto de pruebas ahora se convierte</span><span class="sxs-lookup"><span data-stu-id="26550-289">Your test suite now becomes</span></span>

```csharp
public void GetDiscountedPrice_ByDefault_ReturnsFullPrice()
{
    var priceCalculator = new PriceCalculator();
    var dateTimeProviderStub = new Mock<IDateTimeProvider>();
    dateTimeProviderStub.Setup(dtp => dtp.DayOfWeek()).Returns(DayOfWeek.Monday);

    var actual = priceCalculator.GetDiscountedPrice(2, dateTimeProviderStub);

    Assert.Equals(2, actual);
}

public void GetDiscountedPrice_OnTuesday_ReturnsHalfPrice()
{
    var priceCalculator = new PriceCalculator();
    var dateTimeProviderStub = new Mock<IDateTimeProvider>();
    dateTimeProviderStub.Setup(dtp => dtp.DayOfWeek()).Returns(DayOfWeek.Tuesday);

    var actual = priceCalculator.GetDiscountedPrice(2, dateTimeProviderStub);

    Assert.Equals(1, actual);
}
```

<span data-ttu-id="26550-290">Ahora el conjunto de pruebas tiene control total sobre `DateTime.Now` y puede convertir en stub cualquier valor al llamar al método.</span><span class="sxs-lookup"><span data-stu-id="26550-290">Now the test suite has full control over `DateTime.Now` and can stub any value when calling into the method.</span></span>
