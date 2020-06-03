---
title: Pruebas unitaria en .NET Core y .NET Standard
description: En este artículo se proporciona información general breve de las pruebas unitarias para los proyectos de .NET Core y .NET Standard.
author: ardalis
ms.author: wiwagn
ms.date: 05/18/2020
zone_pivot_groups: unit-testing-framework-set-one
ms.openlocfilehash: e15f80b173389cdff86c6e62013e9c0f21171dd6
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703104"
---
# <a name="unit-testing-in-net-core-and-net-standard"></a><span data-ttu-id="20597-103">Pruebas unitaria en .NET Core y .NET Standard</span><span class="sxs-lookup"><span data-stu-id="20597-103">Unit testing in .NET Core and .NET Standard</span></span>

<span data-ttu-id="20597-104">.NET Core facilita la creación de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="20597-104">.NET Core makes it easy to create unit tests.</span></span> <span data-ttu-id="20597-105">En este artículo se presentan las pruebas unitarias y se indican las diferencias con otros tipos de pruebas.</span><span class="sxs-lookup"><span data-stu-id="20597-105">This article introduces unit tests and illustrates how they differ from other kinds of tests.</span></span> <span data-ttu-id="20597-106">En los recursos vinculados al final de la página se muestra cómo agregar un proyecto de prueba a una solución.</span><span class="sxs-lookup"><span data-stu-id="20597-106">The linked resources near the bottom of the page show you how to add a test project to your solution.</span></span> <span data-ttu-id="20597-107">Una vez que haya configurado el proyecto de prueba, podrá ejecutar las pruebas unitarias con la línea de comandos o con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="20597-107">After you set up your test project, you will be able to run your unit tests using the command line or Visual Studio.</span></span>

<span data-ttu-id="20597-108">Si está realizando pruebas con un proyecto de **ASP.NET Core**, consulte [Pruebas de integración en ASP.NET Core](/aspnet/core/test/integration-tests#test-app-prerequisites).</span><span class="sxs-lookup"><span data-stu-id="20597-108">If you're testing an **ASP.NET Core** project, see [Integration tests in ASP.NET Core](/aspnet/core/test/integration-tests#test-app-prerequisites).</span></span>

<span data-ttu-id="20597-109">.NET Core 2.0 y versiones posteriores admiten [.NET Standard 2.0](../../standard/net-standard.md), cuyas bibliotecas usaremos para mostrar las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="20597-109">.NET Core 2.0 and later supports [.NET Standard 2.0](../../standard/net-standard.md), and we will use its libraries to demonstrate unit tests.</span></span>

<span data-ttu-id="20597-110">Puede usar plantillas de proyecto de prueba unitaria integradas de .NET Core 2.0 y versiones posteriores para C#, F# y Visual Basic como punto inicial para su proyecto personal.</span><span class="sxs-lookup"><span data-stu-id="20597-110">You are able to use built-in .NET Core 2.0 and later unit test project templates for C#, F# and Visual Basic as a starting point for your personal project.</span></span>

## <a name="what-are-unit-tests"></a><span data-ttu-id="20597-111">¿Qué son las pruebas unitarias?</span><span class="sxs-lookup"><span data-stu-id="20597-111">What are unit tests?</span></span>

<span data-ttu-id="20597-112">Automatizar pruebas es un método magnífico para asegurarse de que una aplicación de software hace lo que sus autores pretenden.</span><span class="sxs-lookup"><span data-stu-id="20597-112">Having automated tests is a great way to ensure a software application does what its authors intend it to do.</span></span> <span data-ttu-id="20597-113">Hay varios tipos de pruebas para aplicaciones de software.</span><span class="sxs-lookup"><span data-stu-id="20597-113">There are multiple types of tests for software applications.</span></span> <span data-ttu-id="20597-114">Estas incluyen pruebas de integración, pruebas web y pruebas de carga, entre otras.</span><span class="sxs-lookup"><span data-stu-id="20597-114">These include integration tests, web tests, load tests, and others.</span></span> <span data-ttu-id="20597-115">Con las **pruebas unitarias** se comprueban componentes y métodos de software individuales.</span><span class="sxs-lookup"><span data-stu-id="20597-115">**Unit tests** test individual software components and methods.</span></span> <span data-ttu-id="20597-116">Estas solo deberían probar código que pueda controlar el desarrollador.</span><span class="sxs-lookup"><span data-stu-id="20597-116">Unit tests should only test code within the developer’s control.</span></span> <span data-ttu-id="20597-117">No se deberían usar para comprobar problemas con la infraestructura.</span><span class="sxs-lookup"><span data-stu-id="20597-117">They should not test infrastructure concerns.</span></span> <span data-ttu-id="20597-118">Estos problemas incluyen los relacionados con bases de datos, el sistema de archivos o recursos de red.</span><span class="sxs-lookup"><span data-stu-id="20597-118">Infrastructure concerns include databases, file systems, and network resources.</span></span>

<span data-ttu-id="20597-119">Además, es recomendable que tenga en cuenta que hay procedimientos recomendados para la escritura de pruebas.</span><span class="sxs-lookup"><span data-stu-id="20597-119">Also, keep in mind there are best practices for writing tests.</span></span> <span data-ttu-id="20597-120">Por ejemplo, [Test Driven Development (TTD)](https://deviq.com/test-driven-development/) es un proceso en el que una prueba unitaria se escribe antes que el código que debería comprobar.</span><span class="sxs-lookup"><span data-stu-id="20597-120">For example, [Test Driven Development (TDD)](https://deviq.com/test-driven-development/) is when a unit test is written before the code it is meant to check.</span></span> <span data-ttu-id="20597-121">Este método se puede comparar a la creación del esquema de un libro antes de escribirlo.</span><span class="sxs-lookup"><span data-stu-id="20597-121">TDD is like creating an outline for a book before we write it.</span></span> <span data-ttu-id="20597-122">Está diseñado para ayudar a los desarrolladores a escribir código más simple, legible y eficaz.</span><span class="sxs-lookup"><span data-stu-id="20597-122">It is meant to help developers write simpler, more readable, and efficient code.</span></span>

> [!NOTE]
> <span data-ttu-id="20597-123">El equipo de ASP.NET sigue [estas convenciones](https://github.com/dotnet/aspnetcore/wiki/Engineering-guidelines#unit-tests-and-functional-tests) para ayudar a los desarrolladores a asignar buenos nombres a clases de prueba y métodos.</span><span class="sxs-lookup"><span data-stu-id="20597-123">The ASP.NET team follows [these conventions](https://github.com/dotnet/aspnetcore/wiki/Engineering-guidelines#unit-tests-and-functional-tests) to help developers come up with good names for test classes and methods.</span></span>

<span data-ttu-id="20597-124">No intente incluir dependencias en la infraestructura al escribir pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="20597-124">Try not to introduce dependencies on infrastructure when writing unit tests.</span></span> <span data-ttu-id="20597-125">Estas vuelven las pruebas lentas y frágiles, por lo que deberían reservarse para pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="20597-125">These make the tests slow and brittle, and should be reserved for integration tests.</span></span> <span data-ttu-id="20597-126">Puede evitar esas dependencias en su aplicación si sigue el [Explicit Dependencies Principle](https://deviq.com/explicit-dependencies-principle/) (Principio de dependencias explícitas) y usando la [Inserción de dependencias](/aspnet/core/fundamentals/dependency-injection).</span><span class="sxs-lookup"><span data-stu-id="20597-126">You can avoid these dependencies in your application by following the [Explicit Dependencies Principle](https://deviq.com/explicit-dependencies-principle/) and using [Dependency Injection](/aspnet/core/fundamentals/dependency-injection).</span></span> <span data-ttu-id="20597-127">También puede mantener las pruebas unitarias en un proyecto separado de las pruebas de integración.</span><span class="sxs-lookup"><span data-stu-id="20597-127">You can also keep your unit tests in a separate project from your integration tests.</span></span> <span data-ttu-id="20597-128">Esto asegurará que el proyecto de pruebas unitarias no tiene referencias a paquetes de infraestructura ni dependencias de estos.</span><span class="sxs-lookup"><span data-stu-id="20597-128">This ensures your unit test project doesn’t have references to or dependencies on infrastructure packages.</span></span>

## <a name="next-steps"></a><span data-ttu-id="20597-129">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="20597-129">Next steps</span></span>

<span data-ttu-id="20597-130">Puede encontrar más información sobre las pruebas unitarias en proyectos de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="20597-130">More information on unit testing in .NET Core projects:</span></span>

<span data-ttu-id="20597-131">Los proyectos de pruebas unitarias de .NET Core son compatibles con los siguientes lenguajes:</span><span class="sxs-lookup"><span data-stu-id="20597-131">.NET Core unit test projects are supported for:</span></span>

- [<span data-ttu-id="20597-132">C#</span><span class="sxs-lookup"><span data-stu-id="20597-132">C#</span></span>](../../csharp/index.yml)
- [<span data-ttu-id="20597-133">F#</span><span class="sxs-lookup"><span data-stu-id="20597-133">F#</span></span>](../../fsharp/index.yml)
- [<span data-ttu-id="20597-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20597-134">Visual Basic</span></span>](../../visual-basic/index.yml)

<span data-ttu-id="20597-135">También puede elegir entre varios marcos de pruebas unitarias:</span><span class="sxs-lookup"><span data-stu-id="20597-135">You can also choose between several unit test frameworks:</span></span>

- [<span data-ttu-id="20597-136">xUnit</span><span class="sxs-lookup"><span data-stu-id="20597-136">xUnit</span></span>](https://xunit.net/)
- [<span data-ttu-id="20597-137">NUnit</span><span class="sxs-lookup"><span data-stu-id="20597-137">NUnit</span></span>](https://nunit.org)
- [<span data-ttu-id="20597-138">MSTest</span><span class="sxs-lookup"><span data-stu-id="20597-138">MSTest</span></span>](https://github.com/Microsoft/testfx-docs)

<span data-ttu-id="20597-139">Puede obtener más información en los siguientes tutoriales:</span><span class="sxs-lookup"><span data-stu-id="20597-139">You can learn more in the following walkthroughs:</span></span>

:::zone pivot="mstest"

- <span data-ttu-id="20597-140">Cree pruebas unitarias mediante [*MSTest* y *C#* con la CLI de .NET Core](unit-testing-with-mstest.md).</span><span class="sxs-lookup"><span data-stu-id="20597-140">Create unit tests using [*MSTest* and *C#* with the .NET Core CLI](unit-testing-with-mstest.md).</span></span>
- <span data-ttu-id="20597-141">Cree pruebas unitarias mediante [*MSTest* y *F#* con la CLI de .NET Core](unit-testing-fsharp-with-mstest.md).</span><span class="sxs-lookup"><span data-stu-id="20597-141">Create unit tests using [*MSTest* and *F#* with the .NET Core CLI](unit-testing-fsharp-with-mstest.md).</span></span>
- <span data-ttu-id="20597-142">Cree pruebas unitarias mediante [*MSTest* y *Visual Basic* con la CLI de .NET Core](unit-testing-visual-basic-with-mstest.md).</span><span class="sxs-lookup"><span data-stu-id="20597-142">Create unit tests using [*MSTest* and *Visual Basic* with the .NET Core CLI](unit-testing-visual-basic-with-mstest.md).</span></span>

:::zone-end
:::zone pivot="xunit"

- <span data-ttu-id="20597-143">Cree pruebas unitarias mediante [*xUnit* y *C#* con la CLI de .NET Core](unit-testing-with-dotnet-test.md).</span><span class="sxs-lookup"><span data-stu-id="20597-143">Create unit tests using [*xUnit* and *C#* with the .NET Core CLI](unit-testing-with-dotnet-test.md).</span></span>
- <span data-ttu-id="20597-144">Cree pruebas unitarias mediante [*xUnit* y *F#* con la CLI de .NET Core](unit-testing-fsharp-with-dotnet-test.md).</span><span class="sxs-lookup"><span data-stu-id="20597-144">Create unit tests using [*xUnit* and *F#* with the .NET Core CLI](unit-testing-fsharp-with-dotnet-test.md).</span></span>
- <span data-ttu-id="20597-145">Cree pruebas unitarias mediante [*xUnit* y *Visual Basic* con la CLI de .NET Core](unit-testing-visual-basic-with-dotnet-test.md).</span><span class="sxs-lookup"><span data-stu-id="20597-145">Create unit tests using [*xUnit* and *Visual Basic* with the .NET Core CLI](unit-testing-visual-basic-with-dotnet-test.md).</span></span>

:::zone-end
:::zone pivot="nunit"

- <span data-ttu-id="20597-146">Cree pruebas unitarias mediante [*NUnit* y *C#* con la CLI de .NET Core](unit-testing-with-nunit.md).</span><span class="sxs-lookup"><span data-stu-id="20597-146">Create unit tests using [*NUnit* and *C#* with the .NET Core CLI](unit-testing-with-nunit.md).</span></span>
- <span data-ttu-id="20597-147">Cree pruebas unitarias mediante [*NUnit* y *F#* con la CLI de .NET Core](unit-testing-fsharp-with-nunit.md).</span><span class="sxs-lookup"><span data-stu-id="20597-147">Create unit tests using [*NUnit* and *F#* with the .NET Core CLI](unit-testing-fsharp-with-nunit.md).</span></span>
- <span data-ttu-id="20597-148">Cree pruebas unitarias mediante [*NUnit* y *Visual Basic* con la CLI de .NET Core](unit-testing-visual-basic-with-nunit.md).</span><span class="sxs-lookup"><span data-stu-id="20597-148">Create unit tests using [*NUnit* and *Visual Basic* with the .NET Core CLI](unit-testing-visual-basic-with-nunit.md).</span></span>

:::zone-end

<span data-ttu-id="20597-149">Puede obtener más información en los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="20597-149">You can learn more in the following articles:</span></span>

- <span data-ttu-id="20597-150">Visual Studio Enterprise proporciona herramientas de pruebas fantásticas para .NET Core.</span><span class="sxs-lookup"><span data-stu-id="20597-150">Visual Studio Enterprise offers great testing tools for .NET Core.</span></span> <span data-ttu-id="20597-151">Consulte [Live Unit Testing](/visualstudio/test/live-unit-testing) o [Cobertura de código](https://github.com/Microsoft/vstest-docs/blob/master/docs/analyze.md#working-with-code-coverage) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="20597-151">Check out [Live Unit Testing](/visualstudio/test/live-unit-testing) or [code coverage](https://github.com/Microsoft/vstest-docs/blob/master/docs/analyze.md#working-with-code-coverage) to learn more.</span></span>
- <span data-ttu-id="20597-152">Para obtener más información sobre cómo ejecutar pruebas unitarias, vea [Ejecución de pruebas unitarias selectivas](selective-unit-tests.md) o [Incluir y excluir proyectos de prueba y métodos de prueba](/visualstudio/test/live-unit-testing#include-and-exclude-test-projects-and-test-methods).</span><span class="sxs-lookup"><span data-stu-id="20597-152">For more information on how to run selective unit tests, see [Running selective unit tests](selective-unit-tests.md), or [including and excluding tests with Visual Studio](/visualstudio/test/live-unit-testing#include-and-exclude-test-projects-and-test-methods).</span></span>
- <span data-ttu-id="20597-153">[Cómo usar xUnit con .NET Core y Visual Studio](https://xunit.github.io/docs/getting-started-dotnet-core.html).</span><span class="sxs-lookup"><span data-stu-id="20597-153">[How to use xUnit with .NET Core and Visual Studio](https://xunit.github.io/docs/getting-started-dotnet-core.html).</span></span>
