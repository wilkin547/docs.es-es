---
title: 'Tutorial: Algoritmos de compilación con coincidencia de patrones'
description: En este tutorial avanzado se muestra cómo usar técnicas de coincidencia de patrones para crear una funcionalidad con datos y algoritmos creados por separado.
ms.date: 10/06/2020
ms.technology: csharp-whats-new
ms.custom: contperf-fy21q1
ms.openlocfilehash: be1c330973859df62cd4706e5f6f9ca4326fb221
ms.sourcegitcommit: 4d5e25a46aa7cd0d29b4b9227b92987354d444c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98794816"
---
# <a name="tutorial-use-pattern-matching-to-build-type-driven-and-data-driven-algorithms"></a><span data-ttu-id="951eb-103">Tutorial: Uso de la coincidencia de patrones para compilar algoritmos basados en tipos y basados en datos.</span><span class="sxs-lookup"><span data-stu-id="951eb-103">Tutorial: Use pattern matching to build type-driven and data-driven algorithms.</span></span>

<span data-ttu-id="951eb-104">C# 7 introdujo las características básicas de coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="951eb-104">C# 7 introduced basic pattern matching features.</span></span> <span data-ttu-id="951eb-105">Esas características se han ampliado en C# 8 y C# 9 con nuevas expresiones y patrones.</span><span class="sxs-lookup"><span data-stu-id="951eb-105">Those features are extended in C# 8 and C# 9 with new expressions and patterns.</span></span> <span data-ttu-id="951eb-106">Puede escribir una funcionalidad que se comporta como si se hubiesen ampliado tipos que pueden estar en otras bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="951eb-106">You can write functionality that behaves as though you extended types that may be in other libraries.</span></span> <span data-ttu-id="951eb-107">Los patrones también se usan para crear una funcionalidad que la aplicación requiere y que no es una característica fundamental del tipo que se está ampliando.</span><span class="sxs-lookup"><span data-stu-id="951eb-107">Another use for patterns is to create functionality your application requires that isn't a fundamental feature of the type being extended.</span></span>

<span data-ttu-id="951eb-108">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="951eb-108">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="951eb-109">Reconocer situaciones donde se debe usar la coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="951eb-109">Recognize situations where pattern matching should be used.</span></span>
> - <span data-ttu-id="951eb-110">Usar las expresiones de coincidencia de patrones para implementar un comportamiento en función de los tipos y los valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="951eb-110">Use pattern matching expressions to implement behavior based on types and property values.</span></span>
> - <span data-ttu-id="951eb-111">Combinar la coincidencia de patrones con otras técnicas para crear algoritmos completos.</span><span class="sxs-lookup"><span data-stu-id="951eb-111">Combine pattern matching with other techniques to create complete algorithms.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="951eb-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="951eb-112">Prerequisites</span></span>

<span data-ttu-id="951eb-113">Tendrá que configurar el equipo para ejecutar .NET 5, que incluye el compilador de C# 9.</span><span class="sxs-lookup"><span data-stu-id="951eb-113">You'll need to set up your machine to run .NET 5, which includes the C# 9 compiler.</span></span> <span data-ttu-id="951eb-114">El compilador de C# 9 está disponible a partir de [Visual Studio 2019, versión 16.9 Preview 1](https://visualstudio.microsoft.com/vs/preview/) o del [SDK de .NET 5.0](https://dot.net/get-dotnet5).</span><span class="sxs-lookup"><span data-stu-id="951eb-114">The C# 9 compiler is available starting with [Visual Studio 2019 version 16.9 preview 1](https://visualstudio.microsoft.com/vs/preview/) or [.NET 5.0 SDK](https://dot.net/get-dotnet5).</span></span>

<span data-ttu-id="951eb-115">En este tutorial se da por supuesto que está familiarizado con C# y. NET, incluidos Visual Studio o la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="951eb-115">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="scenarios-for-pattern-matching"></a><span data-ttu-id="951eb-116">Escenarios para la coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="951eb-116">Scenarios for pattern matching</span></span>

<span data-ttu-id="951eb-117">Con frecuencia, el desarrollo moderno incluye integrar datos desde varios orígenes y presentar información y perspectivas a partir de esos datos en una sola aplicación cohesiva.</span><span class="sxs-lookup"><span data-stu-id="951eb-117">Modern development often includes integrating data from multiple sources and presenting information and insights from that data in a single cohesive application.</span></span> <span data-ttu-id="951eb-118">Ni usted ni su equipo tendrán control ni acceso para todos los tipos que representan los datos entrantes.</span><span class="sxs-lookup"><span data-stu-id="951eb-118">You and your team won't have control or access for all the types that represent the incoming data.</span></span>

<span data-ttu-id="951eb-119">El diseño clásico orientado a objetos llamaría a la creación de tipos en la aplicación que representen cada tipo de datos de esos orígenes de datos múltiples.</span><span class="sxs-lookup"><span data-stu-id="951eb-119">The classic object-oriented design would call for creating types in your application that represent each data type from those multiple data sources.</span></span> <span data-ttu-id="951eb-120">Luego, la aplicación podría trabajar con esos tipos nuevos, crear jerarquías de herencia, crear métodos virtuales e implementar abstracciones.</span><span class="sxs-lookup"><span data-stu-id="951eb-120">Then, your application would work with those new types, build inheritance hierarchies, create virtual methods, and implement abstractions.</span></span> <span data-ttu-id="951eb-121">Esas técnicas funcionan y son a veces las mejores herramientas.</span><span class="sxs-lookup"><span data-stu-id="951eb-121">Those techniques work, and sometimes they are the best tools.</span></span> <span data-ttu-id="951eb-122">En otras ocasiones, puede escribir menos código.</span><span class="sxs-lookup"><span data-stu-id="951eb-122">Other times you can write less code.</span></span> <span data-ttu-id="951eb-123">Puede escribir código más claro con técnicas que separan los datos de las operaciones que manipulan esos datos.</span><span class="sxs-lookup"><span data-stu-id="951eb-123">You can write more clear code using techniques that separate the data from the operations that manipulate that data.</span></span>

<span data-ttu-id="951eb-124">En este tutorial, creará y explorará una aplicación que toma datos entrantes de varios orígenes externos para un solo escenario.</span><span class="sxs-lookup"><span data-stu-id="951eb-124">In this tutorial, you'll create and explore an application that takes incoming data from several external sources for a single scenario.</span></span> <span data-ttu-id="951eb-125">Verá cómo la **coincidencia de patrones** proporciona una forma eficaz de consumir y procesar esos datos de maneras que no formaban parte del sistema original.</span><span class="sxs-lookup"><span data-stu-id="951eb-125">You'll see how **pattern matching** provides an efficient way to consume and process that data in ways that weren't part of the original system.</span></span>

<span data-ttu-id="951eb-126">Considere un área metropolitana importante que usa peajes y precios estipulados para las horas de mayor actividad con el fin de administrar el tráfico.</span><span class="sxs-lookup"><span data-stu-id="951eb-126">Consider a major metropolitan area that is using tolls and peak time pricing to manage traffic.</span></span> <span data-ttu-id="951eb-127">Puede escribir una aplicación que calcule los peajes de un vehículo en función de su tipo.</span><span class="sxs-lookup"><span data-stu-id="951eb-127">You write an application that calculates tolls for a vehicle based on its type.</span></span> <span data-ttu-id="951eb-128">Mejoras posteriores incorporan precios basados en la cantidad de ocupantes del vehículo.</span><span class="sxs-lookup"><span data-stu-id="951eb-128">Later enhancements incorporate pricing based on the number of occupants in the vehicle.</span></span> <span data-ttu-id="951eb-129">Otras mejoras agregan precios según la hora y el día de la semana.</span><span class="sxs-lookup"><span data-stu-id="951eb-129">Further enhancements add pricing based on the time and the day of the week.</span></span>

<span data-ttu-id="951eb-130">Desde esa descripción breve, puede haber esbozado rápidamente una jerarquía de objetos para modelar este sistema.</span><span class="sxs-lookup"><span data-stu-id="951eb-130">From that brief description, you may have quickly sketched out an object hierarchy to model this system.</span></span> <span data-ttu-id="951eb-131">Sin embargo, los datos provienen de varios orígenes, como otros sistemas de administración de registros de vehículos.</span><span class="sxs-lookup"><span data-stu-id="951eb-131">However, your data is coming from multiple sources like other vehicle registration management systems.</span></span> <span data-ttu-id="951eb-132">Estos sistemas ofrecen distintas clases para modelar esos datos y no se tiene un modelo de objetos único que puede usar.</span><span class="sxs-lookup"><span data-stu-id="951eb-132">These systems provide different classes to model that data and you don't have a single object model you can use.</span></span> <span data-ttu-id="951eb-133">En este tutorial, usará estas clases simplificadas para modelar los datos del vehículo desde dichos sistemas externos, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="951eb-133">In this tutorial, you'll use these simplified classes to model for the vehicle data from these external systems, as shown in the following code:</span></span>

[!code-csharp[ExternalSystems](~/samples/snippets/csharp/tutorials/patterns/start/toll-calculator/ExternalSystems.cs)]

<span data-ttu-id="951eb-134">Puede descargar el código de inicio del repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) de GitHub.</span><span class="sxs-lookup"><span data-stu-id="951eb-134">You can download the starter code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) GitHub repository.</span></span> <span data-ttu-id="951eb-135">Puede ver que las clases de vehículo provienen de distintos sistemas y que están en distintos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="951eb-135">You can see that the vehicle classes are from different systems, and are in different namespaces.</span></span> <span data-ttu-id="951eb-136">No se puede aprovechar ninguna clase base común distinta de `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="951eb-136">No common base class, other than `System.Object` can be leveraged.</span></span>

## <a name="pattern-matching-designs"></a><span data-ttu-id="951eb-137">Diseños de coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="951eb-137">Pattern matching designs</span></span>

<span data-ttu-id="951eb-138">En el escenario que se usa en este tutorial se resaltan los tipos de problemas en los que resulta adecuado usar la coincidencia de patrones para resolver lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="951eb-138">The scenario used in this tutorial highlights the kinds of problems that pattern matching is well suited to solve:</span></span>

- <span data-ttu-id="951eb-139">Los objetos con los que necesita trabajar no están en una jerarquía de objetos que coincida con sus objetivos.</span><span class="sxs-lookup"><span data-stu-id="951eb-139">The objects you need to work with aren't in an object hierarchy that matches your goals.</span></span> <span data-ttu-id="951eb-140">Es posible que trabaje con clases que forman parte de sistemas no relacionados.</span><span class="sxs-lookup"><span data-stu-id="951eb-140">You may be working with classes that are part of unrelated systems.</span></span>
- <span data-ttu-id="951eb-141">La funcionalidad que agrega no forma parte de la abstracción central de estas clases.</span><span class="sxs-lookup"><span data-stu-id="951eb-141">The functionality you're adding isn't part of the core abstraction for these classes.</span></span> <span data-ttu-id="951eb-142">El peaje que paga un vehículo *cambia* según los distintos tipos de vehículos, pero el peaje no es una función central del vehículo.</span><span class="sxs-lookup"><span data-stu-id="951eb-142">The toll paid by a vehicle *changes* for different types of vehicles, but the toll isn't a core function of the vehicle.</span></span>

<span data-ttu-id="951eb-143">Cuando la *forma* de los datos y las *operaciones* que se realizan en esos datos no se describen en conjunto, las características de coincidencia de patrones de C# permiten que sea más fácil trabajar con ellos.</span><span class="sxs-lookup"><span data-stu-id="951eb-143">When the *shape* of the data and the *operations* on that data are not described together, the pattern matching features in C# make it easier to work with.</span></span>

## <a name="implement-the-basic-toll-calculations"></a><span data-ttu-id="951eb-144">Implementación de cálculos de peajes básicos</span><span class="sxs-lookup"><span data-stu-id="951eb-144">Implement the basic toll calculations</span></span>

<span data-ttu-id="951eb-145">El cálculo de peaje más básico solo se basa en el tipo de vehículo:</span><span class="sxs-lookup"><span data-stu-id="951eb-145">The most basic toll calculation relies only on the vehicle type:</span></span>

- <span data-ttu-id="951eb-146">Un `Car` es USD 2,00.</span><span class="sxs-lookup"><span data-stu-id="951eb-146">A `Car` is $2.00.</span></span>
- <span data-ttu-id="951eb-147">Un `Taxi` es USD 3,50.</span><span class="sxs-lookup"><span data-stu-id="951eb-147">A `Taxi` is $3.50.</span></span>
- <span data-ttu-id="951eb-148">Un `Bus` es USD 5,00.</span><span class="sxs-lookup"><span data-stu-id="951eb-148">A `Bus` is $5.00.</span></span>
- <span data-ttu-id="951eb-149">Un `DeliveryTruck` es USD 10,00</span><span class="sxs-lookup"><span data-stu-id="951eb-149">A `DeliveryTruck` is $10.00</span></span>

<span data-ttu-id="951eb-150">Cree una clase `TollCalculator` nueva e implemente la coincidencia de patrones en el tipo de vehículo para obtener el importe del peaje.</span><span class="sxs-lookup"><span data-stu-id="951eb-150">Create a new `TollCalculator` class, and implement pattern matching on the vehicle type to get the toll amount.</span></span> <span data-ttu-id="951eb-151">En el siguiente código se muestra la implementación inicial de `TollCalculator`.</span><span class="sxs-lookup"><span data-stu-id="951eb-151">The following code shows the initial implementation of the `TollCalculator`.</span></span>

```csharp
using System;
using CommercialRegistration;
using ConsumerVehicleRegistration;
using LiveryRegistration;

namespace toll_calculator
{
    public class TollCalculator
    {
        public decimal CalculateToll(object vehicle) =>
            vehicle switch
        {
            Car c           => 2.00m,
            Taxi t          => 3.50m,
            Bus b           => 5.00m,
            DeliveryTruck t => 10.00m,
            { }             => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
            null            => throw new ArgumentNullException(nameof(vehicle))
        };
    }
}
```

<span data-ttu-id="951eb-152">El código anterior usa una **expresión switch** (que no es la misma que en una instrucción [`switch`](../language-reference/keywords/switch.md)) que prueba el **patrón de tipo**.</span><span class="sxs-lookup"><span data-stu-id="951eb-152">The preceding code uses a **switch expression** (not the same as a [`switch`](../language-reference/keywords/switch.md) statement) that tests the **type pattern**.</span></span> <span data-ttu-id="951eb-153">Una **expresión switch** comienza por la variable, `vehicle` en el código anterior, seguida de la palabra clave `switch`.</span><span class="sxs-lookup"><span data-stu-id="951eb-153">A **switch expression** begins with the variable, `vehicle` in the preceding code, followed by the `switch` keyword.</span></span> <span data-ttu-id="951eb-154">A continuación, todos los **segmentos modificadores** aparecen entre llaves.</span><span class="sxs-lookup"><span data-stu-id="951eb-154">Next comes all the **switch arms** inside curly braces.</span></span> <span data-ttu-id="951eb-155">La expresión `switch` lleva a cabo otras mejoras en la sintaxis que rodea la instrucción `switch`.</span><span class="sxs-lookup"><span data-stu-id="951eb-155">The `switch` expression makes other refinements to the syntax that surrounds the `switch` statement.</span></span> <span data-ttu-id="951eb-156">La palabra clave `case` se omite y el resultado de cada segmento es una expresión.</span><span class="sxs-lookup"><span data-stu-id="951eb-156">The `case` keyword is omitted, and the result of each arm is an expression.</span></span> <span data-ttu-id="951eb-157">Los dos últimos segmentos muestran una característica de lenguaje nueva.</span><span class="sxs-lookup"><span data-stu-id="951eb-157">The last two arms show a new language feature.</span></span> <span data-ttu-id="951eb-158">El caso `{ }` coincide con cualquier objeto no nulo que no coincidía con ningún segmento anterior.</span><span class="sxs-lookup"><span data-stu-id="951eb-158">The `{ }` case matches any non-null object that didn't match an earlier arm.</span></span> <span data-ttu-id="951eb-159">Este segmento detecta todo tipo incorrecto que se pasa a este método.</span><span class="sxs-lookup"><span data-stu-id="951eb-159">This arm catches any incorrect types passed to this method.</span></span>  <span data-ttu-id="951eb-160">El caso `{ }` debe seguir los casos de cada tipo de vehículo.</span><span class="sxs-lookup"><span data-stu-id="951eb-160">The `{ }` case must follow the cases for each vehicle type.</span></span> <span data-ttu-id="951eb-161">Si se invierte el orden, el caso `{ }` tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="951eb-161">If the order were reversed, the `{ }` case would take precedence.</span></span> <span data-ttu-id="951eb-162">Por último, el patrón `null` detecta si se pasa `null` a este método.</span><span class="sxs-lookup"><span data-stu-id="951eb-162">Finally, the `null` pattern detects when a `null` is passed to this method.</span></span> <span data-ttu-id="951eb-163">El patrón `null` puede ser el último porque los otros patrones de tipos solo coinciden con un objeto no nulo del tipo correcto.</span><span class="sxs-lookup"><span data-stu-id="951eb-163">The `null` pattern can be last because the other type patterns match only a non-null object of the correct type.</span></span>

<span data-ttu-id="951eb-164">Puede probar este código con el código siguiente en `Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="951eb-164">You can test this code using the following code in `Program.cs`:</span></span>

```csharp
using System;
using CommercialRegistration;
using ConsumerVehicleRegistration;
using LiveryRegistration;

namespace toll_calculator
{
    class Program
    {
        static void Main(string[] args)
        {
            var tollCalc = new TollCalculator();

            var car = new Car();
            var taxi = new Taxi();
            var bus = new Bus();
            var truck = new DeliveryTruck();

            Console.WriteLine($"The toll for a car is {tollCalc.CalculateToll(car)}");
            Console.WriteLine($"The toll for a taxi is {tollCalc.CalculateToll(taxi)}");
            Console.WriteLine($"The toll for a bus is {tollCalc.CalculateToll(bus)}");
            Console.WriteLine($"The toll for a truck is {tollCalc.CalculateToll(truck)}");

            try
            {
                tollCalc.CalculateToll("this will fail");
            }
            catch (ArgumentException e)
            {
                Console.WriteLine("Caught an argument exception when using the wrong type");
            }
            try
            {
                tollCalc.CalculateToll(null!);
            }
            catch (ArgumentNullException e)
            {
                Console.WriteLine("Caught an argument exception when using null");
            }
        }
    }
}
```

<span data-ttu-id="951eb-165">Ese código se incluye en el proyecto de inicio, pero se marca como comentario. Quite los comentarios y podrá probar lo que escribió.</span><span class="sxs-lookup"><span data-stu-id="951eb-165">That code is included in the starter project, but is commented out. Remove the comments, and you can test what you've written.</span></span>

<span data-ttu-id="951eb-166">Empezará a ver cómo los patrones pueden ayudarlo a crear algoritmos cuando el código y los datos están separados.</span><span class="sxs-lookup"><span data-stu-id="951eb-166">You're starting to see how patterns can help you create algorithms where the code and the data are separate.</span></span> <span data-ttu-id="951eb-167">La expresión `switch` prueba el tipo y genera valores distintos en función de los resultados.</span><span class="sxs-lookup"><span data-stu-id="951eb-167">The `switch` expression tests the type and produces different values based on the results.</span></span> <span data-ttu-id="951eb-168">Eso es solo el principio.</span><span class="sxs-lookup"><span data-stu-id="951eb-168">That's only the beginning.</span></span>

## <a name="add-occupancy-pricing"></a><span data-ttu-id="951eb-169">Incorporación de precios por ocupación</span><span class="sxs-lookup"><span data-stu-id="951eb-169">Add occupancy pricing</span></span>

<span data-ttu-id="951eb-170">La autoridad encargada de los peajes quiere incentivar que los vehículos viajen a plena capacidad.</span><span class="sxs-lookup"><span data-stu-id="951eb-170">The toll authority wants to encourage vehicles to travel at maximum capacity.</span></span> <span data-ttu-id="951eb-171">Se decidió cobrar más cuando los vehículos circulan con menos pasajeros y se incentiva que los vehículos vayan llenos al ofrecer precios más bajos:</span><span class="sxs-lookup"><span data-stu-id="951eb-171">They've decided to charge more when vehicles have fewer passengers, and encourage full vehicles by offering lower pricing:</span></span>

- <span data-ttu-id="951eb-172">Los automóviles y taxis sin pasajeros pagan USD 0,50 adicionales.</span><span class="sxs-lookup"><span data-stu-id="951eb-172">Cars and taxis with no passengers pay an extra $0.50.</span></span>
- <span data-ttu-id="951eb-173">Los automóviles y taxis con dos pasajeros tienen un descuento de USD 0,50.</span><span class="sxs-lookup"><span data-stu-id="951eb-173">Cars and taxis with two passengers get a $0.50 discount.</span></span>
- <span data-ttu-id="951eb-174">Los automóviles y taxis con tres o más pasajeros tienen un descuento de USD 1.</span><span class="sxs-lookup"><span data-stu-id="951eb-174">Cars and taxis with three or more passengers get a $1.00 discount.</span></span>
- <span data-ttu-id="951eb-175">Los buses que viajan con menos del 50 % de su capacidad pagan USD 2 adicionales.</span><span class="sxs-lookup"><span data-stu-id="951eb-175">Buses that are less than 50% full pay an extra $2.00.</span></span>
- <span data-ttu-id="951eb-176">Los buses que viajan con más del 90 % de su capacidad tienen un descuento de USD 1.</span><span class="sxs-lookup"><span data-stu-id="951eb-176">Buses that are more than 90% full get a $1.00 discount.</span></span>

<span data-ttu-id="951eb-177">Estas reglas se pueden implementar con el **patrón de propiedad** en la misma expresión switch.</span><span class="sxs-lookup"><span data-stu-id="951eb-177">These rules can be implemented using the **property pattern** in the same switch expression.</span></span> <span data-ttu-id="951eb-178">Un patrón de propiedades es una cláusula `when` que compara un valor de propiedad con un valor constante.</span><span class="sxs-lookup"><span data-stu-id="951eb-178">A property pattern is a `when` clause that compares a property value to a constant value.</span></span> <span data-ttu-id="951eb-179">El patrón de propiedad examina las propiedades del objeto una vez que se determina el tipo.</span><span class="sxs-lookup"><span data-stu-id="951eb-179">The property pattern examines properties of the object once the type has been determined.</span></span> <span data-ttu-id="951eb-180">El caso único de `Car` se amplía a cuatro casos distintos:</span><span class="sxs-lookup"><span data-stu-id="951eb-180">The single case for a `Car` expands to four different cases:</span></span>

```csharp
vehicle switch
{
    Car {Passengers: 0}        => 2.00m + 0.50m,
    Car {Passengers: 1}        => 2.0m,
    Car {Passengers: 2}        => 2.0m - 0.50m,
    Car c                      => 2.00m - 1.0m,

    // ...
};
```

<span data-ttu-id="951eb-181">Los primeros tres casos prueban el tipo como `Car` y luego comprueban el valor de la propiedad `Passengers`.</span><span class="sxs-lookup"><span data-stu-id="951eb-181">The first three cases test the type as a `Car`, then check the value of the `Passengers` property.</span></span> <span data-ttu-id="951eb-182">Si ambos coinciden, esa expresión se evalúa y devuelve.</span><span class="sxs-lookup"><span data-stu-id="951eb-182">If both match, that expression is evaluated and returned.</span></span>

<span data-ttu-id="951eb-183">También podría expandir los casos para los taxis de manera similar:</span><span class="sxs-lookup"><span data-stu-id="951eb-183">You would also expand the cases for taxis in a similar manner:</span></span>

```csharp
vehicle switch
{
    // ...

    Taxi {Fares: 0}  => 3.50m + 1.00m,
    Taxi {Fares: 1}  => 3.50m,
    Taxi {Fares: 2}  => 3.50m - 0.50m,
    Taxi t           => 3.50m - 1.00m,

    // ...
};
```

<span data-ttu-id="951eb-184">En el ejemplo anterior, la cláusula `when` se omitía en el caso final.</span><span class="sxs-lookup"><span data-stu-id="951eb-184">In the preceding example, the `when` clause was omitted on the final case.</span></span>

<span data-ttu-id="951eb-185">A continuación, implemente las reglas de ocupación mediante la expansión de los casos para los buses, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="951eb-185">Next, implement the occupancy rules by expanding the cases for buses, as shown in the following example:</span></span>

```csharp
vehicle switch
{
    // ...

    Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
    Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
    Bus b => 5.00m,

    // ...
};
```

<span data-ttu-id="951eb-186">A la autoridad encargada de los peajes no le preocupa el número de pasajeros en los camiones de reparto.</span><span class="sxs-lookup"><span data-stu-id="951eb-186">The toll authority isn't concerned with the number of passengers in the delivery trucks.</span></span> <span data-ttu-id="951eb-187">Alternativamente, ajustan el importe del peaje en base a la clase de peso de los camiones, como sigue:</span><span class="sxs-lookup"><span data-stu-id="951eb-187">Instead, they adjust the toll amount based on the weight class of the trucks as follows:</span></span>

- <span data-ttu-id="951eb-188">A los camiones de más de 2268 kilos se les cobran USD 5 adicionales.</span><span class="sxs-lookup"><span data-stu-id="951eb-188">Trucks over 5000 lbs are charged an extra $5.00.</span></span>
- <span data-ttu-id="951eb-189">Los camiones livianos, por debajo de los 1360 kilos, tienen un descuento de 2 USD.</span><span class="sxs-lookup"><span data-stu-id="951eb-189">Light trucks under 3000 lbs are given a $2.00 discount.</span></span>

<span data-ttu-id="951eb-190">Esta regla se implementa con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="951eb-190">That rule is implemented with the following code:</span></span>

```csharp
vehicle switch
{
    // ...

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,
};
```

<span data-ttu-id="951eb-191">En el código anterior se muestra la cláusula `when` de un segmento modificador.</span><span class="sxs-lookup"><span data-stu-id="951eb-191">The preceding code shows the `when` clause of a switch arm.</span></span> <span data-ttu-id="951eb-192">Puede usar la cláusula `when` para probar condiciones distintas de la igualdad de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="951eb-192">You use the `when` clause to test conditions other than equality on a property.</span></span> <span data-ttu-id="951eb-193">Cuando haya terminado, tendrá un método muy similar al código siguiente:</span><span class="sxs-lookup"><span data-stu-id="951eb-193">When you've finished, you'll have a method that looks much like the following code:</span></span>

```csharp
vehicle switch
{
    Car {Passengers: 0}        => 2.00m + 0.50m,
    Car {Passengers: 1}        => 2.0m,
    Car {Passengers: 2}        => 2.0m - 0.50m,
    Car c                      => 2.00m - 1.0m,

    Taxi {Fares: 0}  => 3.50m + 1.00m,
    Taxi {Fares: 1}  => 3.50m,
    Taxi {Fares: 2}  => 3.50m - 0.50m,
    Taxi t           => 3.50m - 1.00m,

    Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
    Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
    Bus b => 5.00m,

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,

    { }     => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
    null    => throw new ArgumentNullException(nameof(vehicle))
};
```

<span data-ttu-id="951eb-194">Muchos de estos segmentos modificadores son ejemplos de **patrones recursivos**.</span><span class="sxs-lookup"><span data-stu-id="951eb-194">Many of these switch arms are examples of **recursive patterns**.</span></span> <span data-ttu-id="951eb-195">Por ejemplo, `Car { Passengers: 1}` muestra un patrón constante dentro de un patrón de propiedad.</span><span class="sxs-lookup"><span data-stu-id="951eb-195">For example, `Car { Passengers: 1}` shows a constant pattern inside a property pattern.</span></span>

<span data-ttu-id="951eb-196">Puede usar modificadores anidados para que este código sea menos repetitivo.</span><span class="sxs-lookup"><span data-stu-id="951eb-196">You can make this code less repetitive by using nested switches.</span></span> <span data-ttu-id="951eb-197">Tanto `Car` como `Taxi` tienen cuatro segmentos distintos en los ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="951eb-197">The `Car` and `Taxi` both have four different arms in the preceding examples.</span></span> <span data-ttu-id="951eb-198">En ambos casos, puede crear un patrón de tipo que se agrega a un patrón de propiedad.</span><span class="sxs-lookup"><span data-stu-id="951eb-198">In both cases, you can create a type pattern that feeds into a property pattern.</span></span> <span data-ttu-id="951eb-199">Esta técnica se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="951eb-199">This technique is shown in the following code:</span></span>

```csharp
public decimal CalculateToll(object vehicle) =>
    vehicle switch
    {
        Car c => c.Passengers switch
        {
            0 => 2.00m + 0.5m,
            1 => 2.0m,
            2 => 2.0m - 0.5m,
            _ => 2.00m - 1.0m
        },

        Taxi t => t.Fares switch
        {
            0 => 3.50m + 1.00m,
            1 => 3.50m,
            2 => 3.50m - 0.50m,
            _ => 3.50m - 1.00m
        },

        Bus b when ((double)b.Riders / (double)b.Capacity) < 0.50 => 5.00m + 2.00m,
        Bus b when ((double)b.Riders / (double)b.Capacity) > 0.90 => 5.00m - 1.00m,
        Bus b => 5.00m,

        DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
        DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
        DeliveryTruck t => 10.00m,

        { }  => throw new ArgumentException(message: "Not a known vehicle type", paramName: nameof(vehicle)),
        null => throw new ArgumentNullException(nameof(vehicle))
    };
```

<span data-ttu-id="951eb-200">En el ejemplo anterior, el uso de una expresión recursiva significa que no repite los segmentos `Car` y `Taxi` que contienen segmentos secundarios que prueban el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="951eb-200">In the preceding sample, using a recursive expression means you don't repeat the `Car` and `Taxi` arms containing child arms that test the property value.</span></span> <span data-ttu-id="951eb-201">Esta técnica no se usa para los segmentos `Bus` y `DeliveryTruck`, porque esos segmentos prueban intervalos para la propiedad, no valores discretos.</span><span class="sxs-lookup"><span data-stu-id="951eb-201">This technique isn't used for the `Bus` and `DeliveryTruck` arms because those arms are testing ranges for the property, not discrete values.</span></span>

## <a name="add-peak-pricing"></a><span data-ttu-id="951eb-202">Incorporación de precio en horas punta</span><span class="sxs-lookup"><span data-stu-id="951eb-202">Add peak pricing</span></span>

<span data-ttu-id="951eb-203">Para la característica final, la autoridad encargada de los peajes quiere agregar precios en función de las horas punta.</span><span class="sxs-lookup"><span data-stu-id="951eb-203">For the final feature, the toll authority wants to add time sensitive peak pricing.</span></span> <span data-ttu-id="951eb-204">En las horas de mayor afluencia durante mañana y tarde, el valor de los peajes se dobla.</span><span class="sxs-lookup"><span data-stu-id="951eb-204">During the morning and evening rush hours, the tolls are doubled.</span></span> <span data-ttu-id="951eb-205">Esa regla solo afecta el tráfico en una dirección: hacia la ciudad en la mañana y desde la ciudad en la tarde.</span><span class="sxs-lookup"><span data-stu-id="951eb-205">That rule only affects traffic in one direction: inbound to the city in the morning, and outbound in the evening rush hour.</span></span> <span data-ttu-id="951eb-206">En otros momentos durante la jornada laboral, los peajes aumentan en un 50 %.</span><span class="sxs-lookup"><span data-stu-id="951eb-206">During other times during the workday, tolls increase by 50%.</span></span> <span data-ttu-id="951eb-207">Tarde por la noche y temprano en la mañana, disminuyen en un 25 %.</span><span class="sxs-lookup"><span data-stu-id="951eb-207">Late night and early morning, tolls are reduced by 25%.</span></span> <span data-ttu-id="951eb-208">Durante el fin de semana, la tarifa es normal independientemente de la hora.</span><span class="sxs-lookup"><span data-stu-id="951eb-208">During the weekend, it's the normal rate, regardless of the time.</span></span> <span data-ttu-id="951eb-209">Puede usar una serie de instrucciones `if` y `else` para expresar esto mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="951eb-209">You could use a series if `if` and `else` statements to express this using the following code:</span></span>

[!code-csharp[FullTuplePattern](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#SnippetPremiumWithoutPattern)]

<span data-ttu-id="951eb-210">El código anterior funciona correctamente, pero no es legible.</span><span class="sxs-lookup"><span data-stu-id="951eb-210">The preceding code does work correctly, but isn't readable.</span></span> <span data-ttu-id="951eb-211">Para que el código tenga sentido, tiene que encadenar todos los casos de entrada y las instrucciones `if` anidadas.</span><span class="sxs-lookup"><span data-stu-id="951eb-211">You have to chain through all the input cases and the nested `if` statements to reason about the code.</span></span> <span data-ttu-id="951eb-212">En su lugar, usará la coincidencia de patrones para esta característica, pero la integrará con otras técnicas.</span><span class="sxs-lookup"><span data-stu-id="951eb-212">Instead, you'll use pattern matching for this feature, but you'll integrate it with other techniques.</span></span> <span data-ttu-id="951eb-213">Podría crear una expresión de coincidencia de patrones única que consideraría todas las combinaciones de dirección, día de la semana y hora.</span><span class="sxs-lookup"><span data-stu-id="951eb-213">You could build a single pattern match expression that would account for all the combinations of direction, day of the week, and time.</span></span> <span data-ttu-id="951eb-214">El resultado sería una expresión complicada.</span><span class="sxs-lookup"><span data-stu-id="951eb-214">The result would be a complicated expression.</span></span> <span data-ttu-id="951eb-215">Podría ser difícil de leer y de comprender.</span><span class="sxs-lookup"><span data-stu-id="951eb-215">It would be hard to read and difficult to understand.</span></span> <span data-ttu-id="951eb-216">Esto implica que es difícil garantizar su exactitud.</span><span class="sxs-lookup"><span data-stu-id="951eb-216">That makes it hard to ensure correctness.</span></span> <span data-ttu-id="951eb-217">En su lugar, combine esos método para crear una tupla de valores que describa de manera concisa todos esos estados.</span><span class="sxs-lookup"><span data-stu-id="951eb-217">Instead, combine those methods to build a tuple of values that concisely describes all those states.</span></span> <span data-ttu-id="951eb-218">Luego, use la coincidencia de patrones para calcular un multiplicador para el peaje.</span><span class="sxs-lookup"><span data-stu-id="951eb-218">Then use pattern matching to calculate a multiplier for the toll.</span></span> <span data-ttu-id="951eb-219">La tupla contiene tres condiciones discretas:</span><span class="sxs-lookup"><span data-stu-id="951eb-219">The tuple contains three discrete conditions:</span></span>

- <span data-ttu-id="951eb-220">El día es un día laborable o fin de semana.</span><span class="sxs-lookup"><span data-stu-id="951eb-220">The day is either a weekday or a weekend.</span></span>
- <span data-ttu-id="951eb-221">La banda de tiempo cuando se cobra el peaje.</span><span class="sxs-lookup"><span data-stu-id="951eb-221">The band of time when the toll is collected.</span></span>
- <span data-ttu-id="951eb-222">La dirección si va hacia la ciudad o desde la ciudad.</span><span class="sxs-lookup"><span data-stu-id="951eb-222">The direction is into the city or out of the city</span></span>

<span data-ttu-id="951eb-223">En la tabla siguiente se muestran las combinaciones de valores de entrada y el multiplicador de precio en horas punta:</span><span class="sxs-lookup"><span data-stu-id="951eb-223">The following table shows the combinations of input values and the peak pricing multiplier:</span></span>

| <span data-ttu-id="951eb-224">Día</span><span class="sxs-lookup"><span data-stu-id="951eb-224">Day</span></span>        | <span data-ttu-id="951eb-225">Time</span><span class="sxs-lookup"><span data-stu-id="951eb-225">Time</span></span>         | <span data-ttu-id="951eb-226">Dirección</span><span class="sxs-lookup"><span data-stu-id="951eb-226">Direction</span></span> | <span data-ttu-id="951eb-227">Premium</span><span class="sxs-lookup"><span data-stu-id="951eb-227">Premium</span></span> |
| ---------- | ------------ | --------- |--------:|
| <span data-ttu-id="951eb-228">Día de la semana</span><span class="sxs-lookup"><span data-stu-id="951eb-228">Weekday</span></span>    | <span data-ttu-id="951eb-229">hora punta de la mañana</span><span class="sxs-lookup"><span data-stu-id="951eb-229">morning rush</span></span> | <span data-ttu-id="951eb-230">hacia la ciudad</span><span class="sxs-lookup"><span data-stu-id="951eb-230">inbound</span></span>   | <span data-ttu-id="951eb-231">x 2,00</span><span class="sxs-lookup"><span data-stu-id="951eb-231">x 2.00</span></span>  |
| <span data-ttu-id="951eb-232">Día de la semana</span><span class="sxs-lookup"><span data-stu-id="951eb-232">Weekday</span></span>    | <span data-ttu-id="951eb-233">hora punta de la mañana</span><span class="sxs-lookup"><span data-stu-id="951eb-233">morning rush</span></span> | <span data-ttu-id="951eb-234">desde la ciudad</span><span class="sxs-lookup"><span data-stu-id="951eb-234">outbound</span></span>  | <span data-ttu-id="951eb-235">x 1,00</span><span class="sxs-lookup"><span data-stu-id="951eb-235">x 1.00</span></span>  |
| <span data-ttu-id="951eb-236">Día de la semana</span><span class="sxs-lookup"><span data-stu-id="951eb-236">Weekday</span></span>    | <span data-ttu-id="951eb-237">día</span><span class="sxs-lookup"><span data-stu-id="951eb-237">daytime</span></span>      | <span data-ttu-id="951eb-238">hacia la ciudad</span><span class="sxs-lookup"><span data-stu-id="951eb-238">inbound</span></span>   | <span data-ttu-id="951eb-239">x 1,50</span><span class="sxs-lookup"><span data-stu-id="951eb-239">x 1.50</span></span>  |
| <span data-ttu-id="951eb-240">Día de la semana</span><span class="sxs-lookup"><span data-stu-id="951eb-240">Weekday</span></span>    | <span data-ttu-id="951eb-241">día</span><span class="sxs-lookup"><span data-stu-id="951eb-241">daytime</span></span>      | <span data-ttu-id="951eb-242">desde la ciudad</span><span class="sxs-lookup"><span data-stu-id="951eb-242">outbound</span></span>  | <span data-ttu-id="951eb-243">x 1,50</span><span class="sxs-lookup"><span data-stu-id="951eb-243">x 1.50</span></span>  |
| <span data-ttu-id="951eb-244">Día de la semana</span><span class="sxs-lookup"><span data-stu-id="951eb-244">Weekday</span></span>    | <span data-ttu-id="951eb-245">hora punta de la tarde</span><span class="sxs-lookup"><span data-stu-id="951eb-245">evening rush</span></span> | <span data-ttu-id="951eb-246">hacia la ciudad</span><span class="sxs-lookup"><span data-stu-id="951eb-246">inbound</span></span>   | <span data-ttu-id="951eb-247">x 1,00</span><span class="sxs-lookup"><span data-stu-id="951eb-247">x 1.00</span></span>  |
| <span data-ttu-id="951eb-248">Día de la semana</span><span class="sxs-lookup"><span data-stu-id="951eb-248">Weekday</span></span>    | <span data-ttu-id="951eb-249">hora punta de la tarde</span><span class="sxs-lookup"><span data-stu-id="951eb-249">evening rush</span></span> | <span data-ttu-id="951eb-250">desde la ciudad</span><span class="sxs-lookup"><span data-stu-id="951eb-250">outbound</span></span>  | <span data-ttu-id="951eb-251">x 2,00</span><span class="sxs-lookup"><span data-stu-id="951eb-251">x 2.00</span></span>  |
| <span data-ttu-id="951eb-252">Día de la semana</span><span class="sxs-lookup"><span data-stu-id="951eb-252">Weekday</span></span>    | <span data-ttu-id="951eb-253">noche</span><span class="sxs-lookup"><span data-stu-id="951eb-253">overnight</span></span>    | <span data-ttu-id="951eb-254">hacia la ciudad</span><span class="sxs-lookup"><span data-stu-id="951eb-254">inbound</span></span>   | <span data-ttu-id="951eb-255">x 0,75</span><span class="sxs-lookup"><span data-stu-id="951eb-255">x 0.75</span></span>  |
| <span data-ttu-id="951eb-256">Día de la semana</span><span class="sxs-lookup"><span data-stu-id="951eb-256">Weekday</span></span>    | <span data-ttu-id="951eb-257">noche</span><span class="sxs-lookup"><span data-stu-id="951eb-257">overnight</span></span>    | <span data-ttu-id="951eb-258">desde la ciudad</span><span class="sxs-lookup"><span data-stu-id="951eb-258">outbound</span></span>  | <span data-ttu-id="951eb-259">x 0,75</span><span class="sxs-lookup"><span data-stu-id="951eb-259">x 0.75</span></span>  |
| <span data-ttu-id="951eb-260">Fin de semana</span><span class="sxs-lookup"><span data-stu-id="951eb-260">Weekend</span></span>    | <span data-ttu-id="951eb-261">hora punta de la mañana</span><span class="sxs-lookup"><span data-stu-id="951eb-261">morning rush</span></span> | <span data-ttu-id="951eb-262">hacia la ciudad</span><span class="sxs-lookup"><span data-stu-id="951eb-262">inbound</span></span>   | <span data-ttu-id="951eb-263">x 1,00</span><span class="sxs-lookup"><span data-stu-id="951eb-263">x 1.00</span></span>  |
| <span data-ttu-id="951eb-264">Fin de semana</span><span class="sxs-lookup"><span data-stu-id="951eb-264">Weekend</span></span>    | <span data-ttu-id="951eb-265">hora punta de la mañana</span><span class="sxs-lookup"><span data-stu-id="951eb-265">morning rush</span></span> | <span data-ttu-id="951eb-266">desde la ciudad</span><span class="sxs-lookup"><span data-stu-id="951eb-266">outbound</span></span>  | <span data-ttu-id="951eb-267">x 1,00</span><span class="sxs-lookup"><span data-stu-id="951eb-267">x 1.00</span></span>  |
| <span data-ttu-id="951eb-268">Fin de semana</span><span class="sxs-lookup"><span data-stu-id="951eb-268">Weekend</span></span>    | <span data-ttu-id="951eb-269">día</span><span class="sxs-lookup"><span data-stu-id="951eb-269">daytime</span></span>      | <span data-ttu-id="951eb-270">hacia la ciudad</span><span class="sxs-lookup"><span data-stu-id="951eb-270">inbound</span></span>   | <span data-ttu-id="951eb-271">x 1,00</span><span class="sxs-lookup"><span data-stu-id="951eb-271">x 1.00</span></span>  |
| <span data-ttu-id="951eb-272">Fin de semana</span><span class="sxs-lookup"><span data-stu-id="951eb-272">Weekend</span></span>    | <span data-ttu-id="951eb-273">día</span><span class="sxs-lookup"><span data-stu-id="951eb-273">daytime</span></span>      | <span data-ttu-id="951eb-274">desde la ciudad</span><span class="sxs-lookup"><span data-stu-id="951eb-274">outbound</span></span>  | <span data-ttu-id="951eb-275">x 1,00</span><span class="sxs-lookup"><span data-stu-id="951eb-275">x 1.00</span></span>  |
| <span data-ttu-id="951eb-276">Fin de semana</span><span class="sxs-lookup"><span data-stu-id="951eb-276">Weekend</span></span>    | <span data-ttu-id="951eb-277">hora punta de la tarde</span><span class="sxs-lookup"><span data-stu-id="951eb-277">evening rush</span></span> | <span data-ttu-id="951eb-278">hacia la ciudad</span><span class="sxs-lookup"><span data-stu-id="951eb-278">inbound</span></span>   | <span data-ttu-id="951eb-279">x 1,00</span><span class="sxs-lookup"><span data-stu-id="951eb-279">x 1.00</span></span>  |
| <span data-ttu-id="951eb-280">Fin de semana</span><span class="sxs-lookup"><span data-stu-id="951eb-280">Weekend</span></span>    | <span data-ttu-id="951eb-281">hora punta de la tarde</span><span class="sxs-lookup"><span data-stu-id="951eb-281">evening rush</span></span> | <span data-ttu-id="951eb-282">desde la ciudad</span><span class="sxs-lookup"><span data-stu-id="951eb-282">outbound</span></span>  | <span data-ttu-id="951eb-283">x 1,00</span><span class="sxs-lookup"><span data-stu-id="951eb-283">x 1.00</span></span>  |
| <span data-ttu-id="951eb-284">Fin de semana</span><span class="sxs-lookup"><span data-stu-id="951eb-284">Weekend</span></span>    | <span data-ttu-id="951eb-285">noche</span><span class="sxs-lookup"><span data-stu-id="951eb-285">overnight</span></span>    | <span data-ttu-id="951eb-286">hacia la ciudad</span><span class="sxs-lookup"><span data-stu-id="951eb-286">inbound</span></span>   | <span data-ttu-id="951eb-287">x 1,00</span><span class="sxs-lookup"><span data-stu-id="951eb-287">x 1.00</span></span>  |
| <span data-ttu-id="951eb-288">Fin de semana</span><span class="sxs-lookup"><span data-stu-id="951eb-288">Weekend</span></span>    | <span data-ttu-id="951eb-289">noche</span><span class="sxs-lookup"><span data-stu-id="951eb-289">overnight</span></span>    | <span data-ttu-id="951eb-290">desde la ciudad</span><span class="sxs-lookup"><span data-stu-id="951eb-290">outbound</span></span>  | <span data-ttu-id="951eb-291">x 1,00</span><span class="sxs-lookup"><span data-stu-id="951eb-291">x 1.00</span></span>  |

<span data-ttu-id="951eb-292">Hay 16 combinaciones distintas de las tres variables.</span><span class="sxs-lookup"><span data-stu-id="951eb-292">There are 16 different combinations of the three variables.</span></span> <span data-ttu-id="951eb-293">Mediante la combinación de algunas de las condiciones, simplificará la expresión switch final.</span><span class="sxs-lookup"><span data-stu-id="951eb-293">By combining some of the conditions, you'll simplify the final switch expression.</span></span>

<span data-ttu-id="951eb-294">El sistema que cobra los peajes usa una estructura <xref:System.DateTime> para la hora en que se cobró el peaje.</span><span class="sxs-lookup"><span data-stu-id="951eb-294">The system that collects the tolls uses a <xref:System.DateTime> structure for the time when the toll was collected.</span></span> <span data-ttu-id="951eb-295">Genere métodos de miembro que creen las variables a partir de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="951eb-295">Build member methods that create the variables from the preceding table.</span></span> <span data-ttu-id="951eb-296">La función siguiente usa una expresión switch de coincidencia de patrones para expresar si la estructura <xref:System.DateTime> representa un día laborable o un fin de semana:</span><span class="sxs-lookup"><span data-stu-id="951eb-296">The following function uses a pattern matching switch expression to express whether a <xref:System.DateTime> represents a weekend or a weekday:</span></span>

```csharp
private static bool IsWeekDay(DateTime timeOfToll) =>
    timeOfToll.DayOfWeek switch
    {
        DayOfWeek.Monday    => true,
        DayOfWeek.Tuesday   => true,
        DayOfWeek.Wednesday => true,
        DayOfWeek.Thursday  => true,
        DayOfWeek.Friday    => true,
        DayOfWeek.Saturday  => false,
        DayOfWeek.Sunday    => false
    };
```

<span data-ttu-id="951eb-297">Ese método es correcto, pero es redundante.</span><span class="sxs-lookup"><span data-stu-id="951eb-297">That method is correct, but it's repetitious.</span></span> <span data-ttu-id="951eb-298">Puede simplificarlo tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="951eb-298">You can simplify it, as shown in the following code:</span></span>

[!code-csharp[IsWeekDay](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#IsWeekDay)]

<span data-ttu-id="951eb-299">A continuación, agregue una función similar para categorizar la hora en los bloques:</span><span class="sxs-lookup"><span data-stu-id="951eb-299">Next, add a similar function to categorize the time into the blocks:</span></span>

[!code-csharp[GetTimeBand](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#GetTimeBand)]

<span data-ttu-id="951eb-300">Agregue un elemento `enum` privado para convertir cada intervalo de tiempo en un valor discreto.</span><span class="sxs-lookup"><span data-stu-id="951eb-300">You add a private `enum` to convert each range of time to a discrete value.</span></span> <span data-ttu-id="951eb-301">Después, el método `GetTimeBand` usa *patrones relacionales* y *patrones OR conjuntivos*, ambos agregados en C# 9.0.</span><span class="sxs-lookup"><span data-stu-id="951eb-301">Then, the `GetTimeBand` method uses *relational patterns*, and *conjunctive or patterns*, both added in C# 9.0.</span></span> <span data-ttu-id="951eb-302">El patrón relacional permite probar un valor numérico mediante `<`, `>`, `<=` o `>=`.</span><span class="sxs-lookup"><span data-stu-id="951eb-302">The relational pattern lets you test a numeric value using `<`, `>`, `<=`, or `>=`.</span></span> <span data-ttu-id="951eb-303">El patrón `or` comprueba si una expresión coincide con uno o más patrones.</span><span class="sxs-lookup"><span data-stu-id="951eb-303">The `or` pattern tests if an expression matches one or more patterns.</span></span> <span data-ttu-id="951eb-304">También puede usar un patrón `and` para asegurarse de que una expresión coincide con dos patrones distintos, y un patrón `not` para probar que una expresión no coincide con un patrón.</span><span class="sxs-lookup"><span data-stu-id="951eb-304">You can also use an `and` pattern to ensure that an expression matches two distinct patterns, and a `not` pattern to test that an expression doesn't match a pattern.</span></span>

<span data-ttu-id="951eb-305">Después de usar esos métodos, puede usar otra expresión `switch` con el **patrón de tuplas** para calcular el recargo en los precios.</span><span class="sxs-lookup"><span data-stu-id="951eb-305">After you create those methods, you can use another `switch` expression with the **tuple pattern** to calculate the pricing premium.</span></span> <span data-ttu-id="951eb-306">Puede crear una expresión `switch` con los 16 segmentos:</span><span class="sxs-lookup"><span data-stu-id="951eb-306">You could build a `switch` expression with all 16 arms:</span></span>

[!code-csharp[FullTuplePattern](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#TuplePatternOne)]

<span data-ttu-id="951eb-307">El código anterior funciona, pero se puede simplificar.</span><span class="sxs-lookup"><span data-stu-id="951eb-307">The above code works, but it can be simplified.</span></span> <span data-ttu-id="951eb-308">Las ocho combinaciones para el fin de semana tienen el mismo peaje.</span><span class="sxs-lookup"><span data-stu-id="951eb-308">All eight combinations for the weekend have the same toll.</span></span> <span data-ttu-id="951eb-309">Puede reemplazar las ocho por la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="951eb-309">You can replace all eight with the following line:</span></span>

```csharp
(false, _, _) => 1.0m,
```

<span data-ttu-id="951eb-310">Tanto el tráfico hacia la ciudad como el tráfico desde la ciudad tienen el mismo multiplicador durante el día y la noche de los fines de semana.</span><span class="sxs-lookup"><span data-stu-id="951eb-310">Both inbound and outbound traffic have the same multiplier during the weekday daytime and overnight hours.</span></span> <span data-ttu-id="951eb-311">Esos cuatro segmentos modificadores se pueden reemplazar por las dos líneas siguientes:</span><span class="sxs-lookup"><span data-stu-id="951eb-311">Those four switch arms can be replaced with the following two lines:</span></span>

```csharp
(true, TimeBand.Overnight, _) => 0.75m,
(true, TimeBand.Daytime, _)   => 1.5m,
```

<span data-ttu-id="951eb-312">El código debe ser similar al código siguiente después de esos dos cambios:</span><span class="sxs-lookup"><span data-stu-id="951eb-312">The code should look like the following code after those two changes:</span></span>

```csharp
public decimal PeakTimePremium(DateTime timeOfToll, bool inbound) =>
    (IsWeekDay(timeOfToll), GetTimeBand(timeOfToll), inbound) switch
    {
        (true, TimeBand.MorningRush, true)  => 2.00m,
        (true, TimeBand.MorningRush, false) => 1.00m,
        (true, TimeBand.Daytime,     _)     => 1.50m,
        (true, TimeBand.EveningRush, true)  => 1.00m,
        (true, TimeBand.EveningRush, false) => 2.00m,
        (true, TimeBand.Overnight,   _)     => 0.75m,
        (false, _,                   _)     => 1.00m,
    };
```

<span data-ttu-id="951eb-313">Por último, puede quitar las dos horas punta en que se paga el precio regular.</span><span class="sxs-lookup"><span data-stu-id="951eb-313">Finally, you can remove the two rush hour times that pay the regular price.</span></span> <span data-ttu-id="951eb-314">Cuando quite esos segmentos, puede reemplazar `false` por un descarte (`_`) en el segmento modificador final.</span><span class="sxs-lookup"><span data-stu-id="951eb-314">Once you remove those arms, you can replace the `false` with a discard (`_`) in the final switch arm.</span></span> <span data-ttu-id="951eb-315">Tendrá el siguiente método finalizado:</span><span class="sxs-lookup"><span data-stu-id="951eb-315">You'll have the following finished method:</span></span>

[!code-csharp[SimplifiedTuplePattern](../../../samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#FinalTuplePattern)]

<span data-ttu-id="951eb-316">En este ejemplo se resalta una de las ventajas de la coincidencia de patrones: las ramas del patrón se evalúan en orden.</span><span class="sxs-lookup"><span data-stu-id="951eb-316">This example highlights one of the advantages of pattern matching: the pattern branches are evaluated in order.</span></span> <span data-ttu-id="951eb-317">Si vuelve a ordenarlas para que una rama anterior controle uno de los últimos casos, el compilador genera una advertencia sobre el código inaccesible.</span><span class="sxs-lookup"><span data-stu-id="951eb-317">If you rearrange them so that an earlier branch handles one of your later cases, the compiler warns you about the unreachable code.</span></span> <span data-ttu-id="951eb-318">Esas reglas de lenguaje facilitan la realización de las simplificaciones anteriores con la confianza de que el código no cambió.</span><span class="sxs-lookup"><span data-stu-id="951eb-318">Those language rules made it easier to do the preceding simplifications with confidence that the code didn't change.</span></span>

<span data-ttu-id="951eb-319">La coincidencia de patrones hace que algunos tipos de código sean más legibles y ofrece una alternativa a las técnicas orientadas a objetos cuando no se puede agregar código a las clases.</span><span class="sxs-lookup"><span data-stu-id="951eb-319">Pattern matching makes some types of code more readable and offers an alternative to object-oriented techniques when you can't add code to your classes.</span></span> <span data-ttu-id="951eb-320">La nube hace que los datos y la funcionalidad residan por separado.</span><span class="sxs-lookup"><span data-stu-id="951eb-320">The cloud is causing data and functionality to live apart.</span></span> <span data-ttu-id="951eb-321">La *forma* de los datos y las *operaciones* que se realizan en ellos no necesariamente se describen en conjunto.</span><span class="sxs-lookup"><span data-stu-id="951eb-321">The *shape* of the data and the *operations* on it aren't necessarily described together.</span></span> <span data-ttu-id="951eb-322">En este tutorial, consumió datos existentes de maneras totalmente distintas de su función original.</span><span class="sxs-lookup"><span data-stu-id="951eb-322">In this tutorial, you consumed existing data in entirely different ways from its original function.</span></span> <span data-ttu-id="951eb-323">La coincidencia de patrones le ha brindado la capacidad de escribir una funcionalidad que reemplazase a esos tipos, aunque no le permitía extenderlos.</span><span class="sxs-lookup"><span data-stu-id="951eb-323">Pattern matching gave you the ability to write functionality that overrode those types, even though you couldn't extend them.</span></span>

## <a name="next-steps"></a><span data-ttu-id="951eb-324">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="951eb-324">Next steps</span></span>

<span data-ttu-id="951eb-325">Puede descargar el código finalizado del repositorio GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished).</span><span class="sxs-lookup"><span data-stu-id="951eb-325">You can download the finished code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished) GitHub repository.</span></span> <span data-ttu-id="951eb-326">Explore los patrones por su cuenta y agregue esta técnica a sus actividades habituales de codificación.</span><span class="sxs-lookup"><span data-stu-id="951eb-326">Explore patterns on your own and add this technique into your regular coding activities.</span></span> <span data-ttu-id="951eb-327">Aprender estas técnicas le permite contar con otra forma de enfocar los problemas y crear una funcionalidad nueva.</span><span class="sxs-lookup"><span data-stu-id="951eb-327">Learning these techniques gives you another way to approach problems and create new functionality.</span></span>
