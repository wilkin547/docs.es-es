---
title: Uso de las características de coincidencia de patrones para ampliar los tipos de datos
description: En este tutorial avanzado se muestra cómo usar técnicas de coincidencia de patrones para crear una funcionalidad con datos y algoritmos creados por separado.
ms.date: 03/13/2019
ms-technology: csharp-whats-new
ms.custom: mvc
ms.openlocfilehash: df1054d8e0ec2b2539e6a1d00bf353d8ca927397
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79156537"
---
# <a name="tutorial-using-pattern-matching-features-to-extend-data-types"></a><span data-ttu-id="fdbb5-103">Tutorial: Uso de las características de coincidencia de patrones para ampliar los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="fdbb5-103">Tutorial: Using pattern matching features to extend data types</span></span>

<span data-ttu-id="fdbb5-104">C# 7 introdujo las características básicas de coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-104">C# 7 introduced basic pattern matching features.</span></span> <span data-ttu-id="fdbb5-105">Esas características se amplían en C# 8 con nuevas expresiones y patrones.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-105">Those features are extended in C# 8 with new expressions and patterns.</span></span> <span data-ttu-id="fdbb5-106">Puede escribir una funcionalidad que se comporta como si se hubiesen ampliado tipos que pueden estar en otras bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-106">You can write functionality that behaves as though you extended types that may be in other libraries.</span></span> <span data-ttu-id="fdbb5-107">Los patrones también se usan para crear una funcionalidad que la aplicación requiere y que no es una característica fundamental del tipo que se está ampliando.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-107">Another use for patterns is to create functionality your application requires that isn't a fundamental feature of the type being extended.</span></span>

<span data-ttu-id="fdbb5-108">En este tutorial aprenderá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-108">In this tutorial, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="fdbb5-109">Reconocer situaciones donde se debe usar la coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-109">Recognize situations where pattern matching should be used.</span></span>
> - <span data-ttu-id="fdbb5-110">Usar las expresiones de coincidencia de patrones para implementar un comportamiento en función de los tipos y los valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-110">Use pattern matching expressions to implement behavior based on types and property values.</span></span>
> - <span data-ttu-id="fdbb5-111">Combinar la coincidencia de patrones con otras técnicas para crear algoritmos completos.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-111">Combine pattern matching with other techniques to create complete algorithms.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fdbb5-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fdbb5-112">Prerequisites</span></span>

<span data-ttu-id="fdbb5-113">Deberá configurar la máquina para ejecutar .NET Core, incluido el compilador de C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-113">You’ll need to set up your machine to run .NET Core, including the C# 8.0 compiler.</span></span> <span data-ttu-id="fdbb5-114">El compilador de C# 8 está disponible a partir de la [versión 16.3 de Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o del [SDK de .NET Core 3.0](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="fdbb5-114">The C# 8 compiler is available starting with [Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) or [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="fdbb5-115">En este tutorial se da por supuesto que está familiarizado con C# y. NET, incluidos Visual Studio o la CLI de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-115">This tutorial assumes you're familiar with C# and .NET, including either Visual Studio or the .NET Core CLI.</span></span>

## <a name="scenarios-for-pattern-matching"></a><span data-ttu-id="fdbb5-116">Escenarios para la coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="fdbb5-116">Scenarios for pattern matching</span></span>

<span data-ttu-id="fdbb5-117">Con frecuencia, el desarrollo moderno incluye integrar datos desde varios orígenes y presentar información y perspectivas a partir de esos datos en una sola aplicación cohesiva.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-117">Modern development often includes integrating data from multiple sources and presenting information and insights from that data in a single cohesive application.</span></span> <span data-ttu-id="fdbb5-118">Ni usted ni su equipo tendrán control ni acceso para todos los tipos que representan los datos entrantes.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-118">You and your team won't have control or access for all the types that represent the incoming data.</span></span>

<span data-ttu-id="fdbb5-119">El diseño clásico orientado a objetos llamaría a la creación de tipos en la aplicación que representen cada tipo de datos de esos orígenes de datos múltiples.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-119">The classic object-oriented design would call for creating types in your application that represent each data type from those multiple data sources.</span></span> <span data-ttu-id="fdbb5-120">Luego, la aplicación podría trabajar con esos tipos nuevos, crear jerarquías de herencia, crear métodos virtuales e implementar abstracciones.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-120">Then, your application would work with those new types, build inheritance hierarchies, create virtual methods, and implement abstractions.</span></span> <span data-ttu-id="fdbb5-121">Esas técnicas funcionan y son a veces las mejores herramientas.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-121">Those techniques work, and sometimes they are the best tools.</span></span> <span data-ttu-id="fdbb5-122">En otras ocasiones, puede escribir menos código.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-122">Other times you can write less code.</span></span> <span data-ttu-id="fdbb5-123">Puede escribir código más claro con técnicas que separan los datos de las operaciones que manipulan esos datos.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-123">You can write more clear code using techniques that separate the data from the operations that manipulate that data.</span></span>

<span data-ttu-id="fdbb5-124">En este tutorial, creará y explorará una aplicación que toma datos entrantes de varios orígenes externos para un solo escenario.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-124">In this tutorial, you'll create and explore an application that takes incoming data from several external sources for a single scenario.</span></span> <span data-ttu-id="fdbb5-125">Verá cómo la **coincidencia de patrones** proporciona una forma eficaz de consumir y procesar esos datos de maneras que no formaban parte del sistema original.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-125">You'll see how **pattern matching** provides an efficient way to consume and process that data in ways that weren't part of the original system.</span></span>

<span data-ttu-id="fdbb5-126">Considere un área metropolitana importante que usa peajes y precios estipulados para las horas de mayor actividad con el fin de administrar el tráfico.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-126">Consider a major metropolitan area that is using tolls and peak time pricing to manage traffic.</span></span> <span data-ttu-id="fdbb5-127">Puede escribir una aplicación que calcule los peajes de un vehículo en función de su tipo.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-127">You write an application that calculates tolls for a vehicle based on its type.</span></span> <span data-ttu-id="fdbb5-128">Mejoras posteriores incorporan precios basados en la cantidad de ocupantes del vehículo.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-128">Later enhancements incorporate pricing based on the number of occupants in the vehicle.</span></span> <span data-ttu-id="fdbb5-129">Otras mejoras agregan precios según la hora y el día de la semana.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-129">Further enhancements add pricing based on the time and the day of the week.</span></span>

<span data-ttu-id="fdbb5-130">Desde esa descripción breve, puede haber esbozado rápidamente una jerarquía de objetos para modelar este sistema.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-130">From that brief description, you may have quickly sketched out an object hierarchy to model this system.</span></span> <span data-ttu-id="fdbb5-131">Sin embargo, los datos provienen de varios orígenes, como otros sistemas de administración de registros de vehículos.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-131">However, your data is coming from multiple sources like other vehicle registration management systems.</span></span> <span data-ttu-id="fdbb5-132">Estos sistemas ofrecen distintas clases para modelar esos datos y no se tiene un modelo de objetos único que puede usar.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-132">These systems provide different classes to model that data and you don't have a single object model you can use.</span></span> <span data-ttu-id="fdbb5-133">En este tutorial, usará estas clases simplificadas para modelar los datos del vehículo desde dichos sistemas externos, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-133">In this tutorial, you'll use these simplified classes to model for the vehicle data from these external systems, as shown in the following code:</span></span>

[!code-csharp[ExternalSystems](~/samples/snippets/csharp/tutorials/patterns/start/toll-calculator/ExternalSystems.cs)]

<span data-ttu-id="fdbb5-134">Puede descargar el código de inicio del repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) de GitHub.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-134">You can download the starter code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) GitHub repository.</span></span> <span data-ttu-id="fdbb5-135">Puede ver que las clases de vehículo provienen de distintos sistemas y que están en distintos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-135">You can see that the vehicle classes are from different systems, and are in different namespaces.</span></span> <span data-ttu-id="fdbb5-136">No se puede aprovechar ninguna clase base común distinta de `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-136">No common base class, other than `System.Object` can be leveraged.</span></span>

## <a name="pattern-matching-designs"></a><span data-ttu-id="fdbb5-137">Diseños de coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="fdbb5-137">Pattern matching designs</span></span>

<span data-ttu-id="fdbb5-138">En el escenario que se usa en este tutorial se resaltan los tipos de problemas en los que resulta adecuado usar la coincidencia de patrones para resolverlos:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-138">The scenario used in this tutorial highlights the kinds of problems that pattern matching is well-suited to solve:</span></span>

- <span data-ttu-id="fdbb5-139">Los objetos con los que necesita trabajar no están en una jerarquía de objetos que coincida con sus objetivos.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-139">The objects you need to work with aren't in an object hierarchy that matches your goals.</span></span> <span data-ttu-id="fdbb5-140">Es posible que trabaje con clases que forman parte de sistemas no relacionados.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-140">You may be working with classes that are part of unrelated systems.</span></span>
- <span data-ttu-id="fdbb5-141">La funcionalidad que agrega no forma parte de la abstracción central de estas clases.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-141">The functionality you're adding isn't part of the core abstraction for these classes.</span></span> <span data-ttu-id="fdbb5-142">El peaje que paga un vehículo *cambia* según los distintos tipos de vehículos, pero el peaje no es una función central del vehículo.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-142">The toll paid by a vehicle *changes* for different types of vehicles, but the toll isn't a core function of the vehicle.</span></span>

<span data-ttu-id="fdbb5-143">Cuando la *forma* de los datos y las *operaciones* que se realizan en esos datos no se describen en conjunto, las características de coincidencia de patrones de C# permiten que sea más fácil trabajar con ellos.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-143">When the *shape* of the data and the *operations* on that data are not described together, the pattern matching features in C# make it easier to work with.</span></span>

## <a name="implement-the-basic-toll-calculations"></a><span data-ttu-id="fdbb5-144">Implementación de cálculos de peajes básicos</span><span class="sxs-lookup"><span data-stu-id="fdbb5-144">Implement the basic toll calculations</span></span>

<span data-ttu-id="fdbb5-145">El cálculo de peaje más básico solo se basa en el tipo de vehículo:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-145">The most basic toll calculation relies only on the vehicle type:</span></span>

- <span data-ttu-id="fdbb5-146">Un `Car` es USD 2,00.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-146">A `Car` is $2.00.</span></span>
- <span data-ttu-id="fdbb5-147">Un `Taxi` es USD 3,50.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-147">A `Taxi` is $3.50.</span></span>
- <span data-ttu-id="fdbb5-148">Un `Bus` es USD 5,00.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-148">A `Bus` is $5.00.</span></span>
- <span data-ttu-id="fdbb5-149">Un `DeliveryTruck` es USD 10,00</span><span class="sxs-lookup"><span data-stu-id="fdbb5-149">A `DeliveryTruck` is $10.00</span></span>

<span data-ttu-id="fdbb5-150">Cree una clase `TollCalculator` nueva e implemente la coincidencia de patrones en el tipo de vehículo para obtener el importe del peaje.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-150">Create a new `TollCalculator` class, and implement pattern matching on the vehicle type to get the toll amount.</span></span> <span data-ttu-id="fdbb5-151">En el siguiente código se muestra la implementación inicial de `TollCalculator`.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-151">The following code shows the initial implementation of the `TollCalculator`.</span></span>

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

<span data-ttu-id="fdbb5-152">El código anterior usa una **expresión switch** (que no es la misma que en una instrucción [`switch`](../language-reference/keywords/switch.md)) que prueba el **patrón de tipo**.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-152">The preceding code uses a **switch expression** (not the same as a [`switch`](../language-reference/keywords/switch.md) statement) that tests the **type pattern**.</span></span> <span data-ttu-id="fdbb5-153">Una **expresión switch** comienza por la variable, `vehicle` en el código anterior, seguida de la palabra clave `switch`.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-153">A **switch expression** begins with the variable, `vehicle` in the preceding code, followed by the `switch` keyword.</span></span> <span data-ttu-id="fdbb5-154">A continuación, todos los **segmentos modificadores** aparecen entre llaves.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-154">Next comes all the **switch arms** inside curly braces.</span></span> <span data-ttu-id="fdbb5-155">La expresión `switch` lleva a cabo otras mejoras en la sintaxis que rodea la instrucción `switch`.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-155">The `switch` expression makes other refinements to the syntax that surrounds the `switch` statement.</span></span> <span data-ttu-id="fdbb5-156">La palabra clave `case` se omite y el resultado de cada segmento es una expresión.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-156">The `case` keyword is omitted, and the result of each arm is an expression.</span></span> <span data-ttu-id="fdbb5-157">Los dos últimos segmentos muestran una característica de lenguaje nueva.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-157">The last two arms show a new language feature.</span></span> <span data-ttu-id="fdbb5-158">El caso `{ }` coincide con cualquier objeto no nulo que no coincidía con ningún segmento anterior.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-158">The `{ }` case matches any non-null object that didn't match an earlier arm.</span></span> <span data-ttu-id="fdbb5-159">Este segmento detecta todo tipo incorrecto que se pasa a este método.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-159">This arm catches any incorrect types passed to this method.</span></span>  <span data-ttu-id="fdbb5-160">El caso `{ }` debe seguir los casos de cada tipo de vehículo.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-160">The `{ }` case must follow the cases for each vehicle type.</span></span> <span data-ttu-id="fdbb5-161">Si se invierte el orden, el caso `{ }` tendrá prioridad.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-161">If the order were reversed, the `{ }` case would take precedence.</span></span> <span data-ttu-id="fdbb5-162">Por último, el patrón `null` detecta si se pasa `null` a este método.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-162">Finally, the `null` pattern detects when a `null` is passed to this method.</span></span> <span data-ttu-id="fdbb5-163">El patrón `null` puede ser el último porque los otros patrones de tipos solo coinciden con un objeto no nulo del tipo correcto.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-163">The `null` pattern can be last because the other type patterns match only a non-null object of the correct type.</span></span>

<span data-ttu-id="fdbb5-164">Puede probar este código con el código siguiente en `Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-164">You can test this code using the following code in `Program.cs`:</span></span>

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
                tollCalc.CalculateToll(null);
            }
            catch (ArgumentNullException e)
            {
                Console.WriteLine("Caught an argument exception when using null");
            }
        }
    }
}
```

<span data-ttu-id="fdbb5-165">Ese código se incluye en el proyecto de inicio, pero se marca como comentario. Quite los comentarios y podrá probar lo que escribió.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-165">That code is included in the starter project, but is commented out. Remove the comments, and you can test what you've written.</span></span>

<span data-ttu-id="fdbb5-166">Empezará a ver cómo los patrones pueden ayudarlo a crear algoritmos cuando el código y los datos están separados.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-166">You're starting to see how patterns can help you create algorithms where the code and the data are separate.</span></span> <span data-ttu-id="fdbb5-167">La expresión `switch` prueba el tipo y genera valores distintos en función de los resultados.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-167">The `switch` expression tests the type and produces different values based on the results.</span></span> <span data-ttu-id="fdbb5-168">Eso es solo el principio.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-168">That's only the beginning.</span></span>

## <a name="add-occupancy-pricing"></a><span data-ttu-id="fdbb5-169">Incorporación de precios por ocupación</span><span class="sxs-lookup"><span data-stu-id="fdbb5-169">Add occupancy pricing</span></span>

<span data-ttu-id="fdbb5-170">La autoridad encargada de los peajes quiere incentivar que los vehículos viajen a plena capacidad.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-170">The toll authority wants to encourage vehicles to travel at maximum capacity.</span></span> <span data-ttu-id="fdbb5-171">Se decidió cobrar más cuando los vehículos circulan con menos pasajeros y se incentiva que los vehículos vayan llenos al ofrecer precios más bajos:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-171">They've decided to charge more when vehicles have fewer passengers, and encourage full vehicles by offering lower pricing:</span></span>

- <span data-ttu-id="fdbb5-172">Los automóviles y taxis sin pasajeros pagan USD 0,50 adicionales.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-172">Cars and taxis with no passengers pay an extra $0.50.</span></span>
- <span data-ttu-id="fdbb5-173">Los automóviles y taxis con dos pasajeros tienen un descuento de USD 0,50.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-173">Cars and taxis with two passengers get a $0.50 discount.</span></span>
- <span data-ttu-id="fdbb5-174">Los automóviles y taxis con tres o más pasajeros tienen un descuento de USD 1.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-174">Cars and taxis with three or more passengers get a $1.00 discount.</span></span>
- <span data-ttu-id="fdbb5-175">Los buses que viajan con menos del 50 % de su capacidad pagan USD 2 adicionales.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-175">Buses that are less than 50% full pay an extra $2.00.</span></span>
- <span data-ttu-id="fdbb5-176">Los buses que viajan con más del 90 % de su capacidad tienen un descuento de USD 1.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-176">Buses that are more than 90% full get a $1.00 discount.</span></span>

<span data-ttu-id="fdbb5-177">Estas reglas se pueden implementar con el **patrón de propiedad** en la misma expresión switch.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-177">These rules can be implemented using the **property pattern** in the same switch expression.</span></span> <span data-ttu-id="fdbb5-178">El patrón de propiedad examina las propiedades del objeto una vez que se determina el tipo.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-178">The property pattern examines properties of the object once the type has been determined.</span></span> <span data-ttu-id="fdbb5-179">El caso único de `Car` se amplía a cuatro casos distintos:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-179">The single case for a `Car` expands to four different cases:</span></span>

```csharp
vehicle switch
{
    Car { Passengers: 0}        => 2.00m + 0.50m,
    Car { Passengers: 1 }       => 2.0m,
    Car { Passengers: 2}        => 2.0m - 0.50m,
    Car c                       => 2.00m - 1.0m,

    // ...
};
```

<span data-ttu-id="fdbb5-180">Los primeros tres casos prueban el tipo como `Car` y luego comprueban el valor de la propiedad `Passengers`.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-180">The first three cases test the type as a `Car`, then check the value of the `Passengers` property.</span></span> <span data-ttu-id="fdbb5-181">Si ambos coinciden, esa expresión se evalúa y devuelve.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-181">If both match, that expression is evaluated and returned.</span></span>

<span data-ttu-id="fdbb5-182">También podría expandir los casos para los taxis de manera similar:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-182">You would also expand the cases for taxis in a similar manner:</span></span>

```csharp
vehicle switch
{
    // ...

    Taxi { Fares: 0}  => 3.50m + 1.00m,
    Taxi { Fares: 1 } => 3.50m,
    Taxi { Fares: 2}  => 3.50m - 0.50m,
    Taxi t            => 3.50m - 1.00m,

    // ...
};
```

<span data-ttu-id="fdbb5-183">En el ejemplo anterior, la cláusula `when` se omitía en el caso final.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-183">In the preceding example, the `when` clause was omitted on the final case.</span></span>

<span data-ttu-id="fdbb5-184">A continuación, implemente las reglas de ocupación mediante la expansión de los casos para los buses, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-184">Next, implement the occupancy rules by expanding the cases for buses, as shown in the following example:</span></span>

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

<span data-ttu-id="fdbb5-185">A la autoridad encargada de los peajes no le preocupa el número de pasajeros en los camiones de reparto.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-185">The toll authority isn't concerned with the number of passengers in the delivery trucks.</span></span> <span data-ttu-id="fdbb5-186">Alternativamente, ajustan el importe del peaje en base a la clase de peso de los camiones, como sigue:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-186">Instead, they adjust the toll amount based on the weight class of the trucks as follows:</span></span>

- <span data-ttu-id="fdbb5-187">A los camiones de más de 2268 kilos se les cobran USD 5 adicionales.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-187">Trucks over 5000 lbs are charged an extra $5.00.</span></span>
- <span data-ttu-id="fdbb5-188">Los camiones livianos, por debajo de los 1360 kilos, tienen un descuento de 2 USD.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-188">Light trucks under 3000 lbs are given a $2.00 discount.</span></span>

<span data-ttu-id="fdbb5-189">Esta regla se implementa con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-189">That rule is implemented with the following code:</span></span>

```csharp
vehicle switch
{
    // ...

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,
};
```

<span data-ttu-id="fdbb5-190">En el código anterior se muestra la cláusula `when` de un segmento modificador.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-190">The preceding code shows the `when` clause of a switch arm.</span></span> <span data-ttu-id="fdbb5-191">Puede usar la cláusula `when` para probar condiciones distintas de la igualdad de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-191">You use the `when` clause to test conditions other than equality on a property.</span></span> <span data-ttu-id="fdbb5-192">Cuando termine, tendrá un método bastante similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-192">When you've finished, you'll have a method that looks much like the following:</span></span>

```csharp
vehicle switch
{
    Car { Passengers: 0}        => 2.00m + 0.50m,
    Car { Passengers: 1}        => 2.0m,
    Car { Passengers: 2}        => 2.0m - 0.50m,
    Car c                       => 2.00m - 1.0m,

    Taxi { Fares: 0}  => 3.50m + 1.00m,
    Taxi { Fares: 1 } => 3.50m,
    Taxi { Fares: 2}  => 3.50m - 0.50m,
    Taxi t            => 3.50m - 1.00m,

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

<span data-ttu-id="fdbb5-193">Muchos de estos segmentos modificadores son ejemplos de **patrones recursivos**.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-193">Many of these switch arms are examples of **recursive patterns**.</span></span> <span data-ttu-id="fdbb5-194">Por ejemplo, `Car { Passengers: 1}` muestra un patrón constante dentro de un patrón de propiedad.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-194">For example, `Car { Passengers: 1}` shows a constant pattern inside a property pattern.</span></span>

<span data-ttu-id="fdbb5-195">Puede usar modificadores anidados para que este código sea menos repetitivo.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-195">You can make this code less repetitive by using nested switches.</span></span> <span data-ttu-id="fdbb5-196">Tanto `Car` como `Taxi` tienen cuatro segmentos distintos en los ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-196">The `Car` and `Taxi` both have four different arms in the preceding examples.</span></span> <span data-ttu-id="fdbb5-197">En ambos casos, puede crear un patrón de tipo que se agrega a un patrón de propiedad.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-197">In both cases, you can create a type pattern that feeds into a property pattern.</span></span> <span data-ttu-id="fdbb5-198">Esta técnica se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-198">This technique is shown in the following code:</span></span>

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

<span data-ttu-id="fdbb5-199">En el ejemplo anterior, el uso de una expresión recursiva significa que no repite los segmentos `Car` y `Taxi` que contienen segmentos secundarios que prueban el valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-199">In the preceding sample, using a recursive expression means you don't repeat the `Car` and `Taxi` arms containing child arms that test the property value.</span></span> <span data-ttu-id="fdbb5-200">Esta técnica no se usa para los segmentos `Bus` y `DeliveryTruck`, porque esos segmentos prueban intervalos para la propiedad, no valores discretos.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-200">This technique isn't used for the `Bus` and `DeliveryTruck` arms because those arms are testing ranges for the property, not discrete values.</span></span>

## <a name="add-peak-pricing"></a><span data-ttu-id="fdbb5-201">Incorporación de precio en horas punta</span><span class="sxs-lookup"><span data-stu-id="fdbb5-201">Add peak pricing</span></span>

<span data-ttu-id="fdbb5-202">Para la característica final, la autoridad encargada de los peajes quiere agregar precios en función de las horas punta.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-202">For the final feature, the toll authority wants to add time sensitive peak pricing.</span></span> <span data-ttu-id="fdbb5-203">En las horas de mayor afluencia durante mañana y tarde, el valor de los peajes se dobla.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-203">During the morning and evening rush hours, the tolls are doubled.</span></span> <span data-ttu-id="fdbb5-204">Esa regla solo afecta el tráfico en una dirección: hacia la ciudad en la mañana y desde la ciudad en la tarde.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-204">That rule only affects traffic in one direction: inbound to the city in the morning, and outbound in the evening rush hour.</span></span> <span data-ttu-id="fdbb5-205">En otros momentos durante la jornada laboral, los peajes aumentan en un 50 %.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-205">During other times during the workday, tolls increase by 50%.</span></span> <span data-ttu-id="fdbb5-206">Tarde por la noche y temprano en la mañana, disminuyen en un 25 %.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-206">Late night and early morning, tolls are reduced by 25%.</span></span> <span data-ttu-id="fdbb5-207">Durante el fin de semana, la tarifa es normal independientemente de la hora.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-207">During the weekend, it's the normal rate, regardless of the time.</span></span>

<span data-ttu-id="fdbb5-208">Para esta característica, usará la coincidencia de patrones, pero la integrará con otras técnicas.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-208">You'll use pattern matching for this feature, but you'll integrate it with other techniques.</span></span> <span data-ttu-id="fdbb5-209">Podría crear una expresión de coincidencia de patrones única que consideraría todas las combinaciones de dirección, día de la semana y hora.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-209">You could build a single pattern match expression that would account for all the combinations of direction, day of the week, and time.</span></span> <span data-ttu-id="fdbb5-210">El resultado sería una expresión complicada.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-210">The result would be a complicated expression.</span></span> <span data-ttu-id="fdbb5-211">Podría ser difícil de leer y de comprender.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-211">It would be hard to read and difficult to understand.</span></span> <span data-ttu-id="fdbb5-212">Esto implica que es difícil garantizar su exactitud.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-212">That makes it hard to ensure correctness.</span></span> <span data-ttu-id="fdbb5-213">En su lugar, combine esos método para crear una tupla de valores que describa de manera concisa todos esos estados.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-213">Instead, combine those methods to build a tuple of values that concisely describes all those states.</span></span> <span data-ttu-id="fdbb5-214">Luego, use la coincidencia de patrones para calcular un multiplicador para el peaje.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-214">Then use pattern matching to calculate a multiplier for the toll.</span></span> <span data-ttu-id="fdbb5-215">La tupla contiene tres condiciones discretas:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-215">The tuple contains three discrete conditions:</span></span>

- <span data-ttu-id="fdbb5-216">El día es un día laborable o fin de semana.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-216">The day is either a weekday or a weekend.</span></span>
- <span data-ttu-id="fdbb5-217">La banda de tiempo cuando se cobra el peaje.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-217">The band of time when the toll is collected.</span></span>
- <span data-ttu-id="fdbb5-218">La dirección si va hacia la ciudad o desde la ciudad.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-218">The direction is into the city or out of the city</span></span>

<span data-ttu-id="fdbb5-219">En la tabla siguiente se muestran las combinaciones de valores de entrada y el multiplicador de precio en horas punta:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-219">The following table shows the combinations of input values and the peak pricing multiplier:</span></span>

| <span data-ttu-id="fdbb5-220">Day</span><span class="sxs-lookup"><span data-stu-id="fdbb5-220">Day</span></span>        | <span data-ttu-id="fdbb5-221">Tiempo</span><span class="sxs-lookup"><span data-stu-id="fdbb5-221">Time</span></span>         | <span data-ttu-id="fdbb5-222">Dirección</span><span class="sxs-lookup"><span data-stu-id="fdbb5-222">Direction</span></span> | <span data-ttu-id="fdbb5-223">Recargo</span><span class="sxs-lookup"><span data-stu-id="fdbb5-223">Premium</span></span> |
| ---------- | ------------ | --------- |--------:|
| <span data-ttu-id="fdbb5-224">Día laborable</span><span class="sxs-lookup"><span data-stu-id="fdbb5-224">Weekday</span></span>    | <span data-ttu-id="fdbb5-225">hora punta de la mañana</span><span class="sxs-lookup"><span data-stu-id="fdbb5-225">morning rush</span></span> | <span data-ttu-id="fdbb5-226">hacia la ciudad</span><span class="sxs-lookup"><span data-stu-id="fdbb5-226">inbound</span></span>   | <span data-ttu-id="fdbb5-227">x 2,00</span><span class="sxs-lookup"><span data-stu-id="fdbb5-227">x 2.00</span></span>  |
| <span data-ttu-id="fdbb5-228">Día laborable</span><span class="sxs-lookup"><span data-stu-id="fdbb5-228">Weekday</span></span>    | <span data-ttu-id="fdbb5-229">hora punta de la mañana</span><span class="sxs-lookup"><span data-stu-id="fdbb5-229">morning rush</span></span> | <span data-ttu-id="fdbb5-230">desde la ciudad</span><span class="sxs-lookup"><span data-stu-id="fdbb5-230">outbound</span></span>  | <span data-ttu-id="fdbb5-231">x 1,00</span><span class="sxs-lookup"><span data-stu-id="fdbb5-231">x 1.00</span></span>  |
| <span data-ttu-id="fdbb5-232">Día laborable</span><span class="sxs-lookup"><span data-stu-id="fdbb5-232">Weekday</span></span>    | <span data-ttu-id="fdbb5-233">día</span><span class="sxs-lookup"><span data-stu-id="fdbb5-233">daytime</span></span>      | <span data-ttu-id="fdbb5-234">hacia la ciudad</span><span class="sxs-lookup"><span data-stu-id="fdbb5-234">inbound</span></span>   | <span data-ttu-id="fdbb5-235">x 1,50</span><span class="sxs-lookup"><span data-stu-id="fdbb5-235">x 1.50</span></span>  |
| <span data-ttu-id="fdbb5-236">Día laborable</span><span class="sxs-lookup"><span data-stu-id="fdbb5-236">Weekday</span></span>    | <span data-ttu-id="fdbb5-237">día</span><span class="sxs-lookup"><span data-stu-id="fdbb5-237">daytime</span></span>      | <span data-ttu-id="fdbb5-238">desde la ciudad</span><span class="sxs-lookup"><span data-stu-id="fdbb5-238">outbound</span></span>  | <span data-ttu-id="fdbb5-239">x 1,50</span><span class="sxs-lookup"><span data-stu-id="fdbb5-239">x 1.50</span></span>  |
| <span data-ttu-id="fdbb5-240">Día laborable</span><span class="sxs-lookup"><span data-stu-id="fdbb5-240">Weekday</span></span>    | <span data-ttu-id="fdbb5-241">hora punta de la tarde</span><span class="sxs-lookup"><span data-stu-id="fdbb5-241">evening rush</span></span> | <span data-ttu-id="fdbb5-242">hacia la ciudad</span><span class="sxs-lookup"><span data-stu-id="fdbb5-242">inbound</span></span>   | <span data-ttu-id="fdbb5-243">x 1,00</span><span class="sxs-lookup"><span data-stu-id="fdbb5-243">x 1.00</span></span>  |
| <span data-ttu-id="fdbb5-244">Día laborable</span><span class="sxs-lookup"><span data-stu-id="fdbb5-244">Weekday</span></span>    | <span data-ttu-id="fdbb5-245">hora punta de la tarde</span><span class="sxs-lookup"><span data-stu-id="fdbb5-245">evening rush</span></span> | <span data-ttu-id="fdbb5-246">desde la ciudad</span><span class="sxs-lookup"><span data-stu-id="fdbb5-246">outbound</span></span>  | <span data-ttu-id="fdbb5-247">x 2,00</span><span class="sxs-lookup"><span data-stu-id="fdbb5-247">x 2.00</span></span>  |
| <span data-ttu-id="fdbb5-248">Día laborable</span><span class="sxs-lookup"><span data-stu-id="fdbb5-248">Weekday</span></span>    | <span data-ttu-id="fdbb5-249">noche</span><span class="sxs-lookup"><span data-stu-id="fdbb5-249">overnight</span></span>    | <span data-ttu-id="fdbb5-250">hacia la ciudad</span><span class="sxs-lookup"><span data-stu-id="fdbb5-250">inbound</span></span>   | <span data-ttu-id="fdbb5-251">x 0,75</span><span class="sxs-lookup"><span data-stu-id="fdbb5-251">x 0.75</span></span>  |
| <span data-ttu-id="fdbb5-252">Día laborable</span><span class="sxs-lookup"><span data-stu-id="fdbb5-252">Weekday</span></span>    | <span data-ttu-id="fdbb5-253">noche</span><span class="sxs-lookup"><span data-stu-id="fdbb5-253">overnight</span></span>    | <span data-ttu-id="fdbb5-254">desde la ciudad</span><span class="sxs-lookup"><span data-stu-id="fdbb5-254">outbound</span></span>  | <span data-ttu-id="fdbb5-255">x 0,75</span><span class="sxs-lookup"><span data-stu-id="fdbb5-255">x 0.75</span></span>  |
| <span data-ttu-id="fdbb5-256">Fin de semana</span><span class="sxs-lookup"><span data-stu-id="fdbb5-256">Weekend</span></span>    | <span data-ttu-id="fdbb5-257">hora punta de la mañana</span><span class="sxs-lookup"><span data-stu-id="fdbb5-257">morning rush</span></span> | <span data-ttu-id="fdbb5-258">hacia la ciudad</span><span class="sxs-lookup"><span data-stu-id="fdbb5-258">inbound</span></span>   | <span data-ttu-id="fdbb5-259">x 1,00</span><span class="sxs-lookup"><span data-stu-id="fdbb5-259">x 1.00</span></span>  |
| <span data-ttu-id="fdbb5-260">Fin de semana</span><span class="sxs-lookup"><span data-stu-id="fdbb5-260">Weekend</span></span>    | <span data-ttu-id="fdbb5-261">hora punta de la mañana</span><span class="sxs-lookup"><span data-stu-id="fdbb5-261">morning rush</span></span> | <span data-ttu-id="fdbb5-262">desde la ciudad</span><span class="sxs-lookup"><span data-stu-id="fdbb5-262">outbound</span></span>  | <span data-ttu-id="fdbb5-263">x 1,00</span><span class="sxs-lookup"><span data-stu-id="fdbb5-263">x 1.00</span></span>  |
| <span data-ttu-id="fdbb5-264">Fin de semana</span><span class="sxs-lookup"><span data-stu-id="fdbb5-264">Weekend</span></span>    | <span data-ttu-id="fdbb5-265">día</span><span class="sxs-lookup"><span data-stu-id="fdbb5-265">daytime</span></span>      | <span data-ttu-id="fdbb5-266">hacia la ciudad</span><span class="sxs-lookup"><span data-stu-id="fdbb5-266">inbound</span></span>   | <span data-ttu-id="fdbb5-267">x 1,00</span><span class="sxs-lookup"><span data-stu-id="fdbb5-267">x 1.00</span></span>  |
| <span data-ttu-id="fdbb5-268">Fin de semana</span><span class="sxs-lookup"><span data-stu-id="fdbb5-268">Weekend</span></span>    | <span data-ttu-id="fdbb5-269">día</span><span class="sxs-lookup"><span data-stu-id="fdbb5-269">daytime</span></span>      | <span data-ttu-id="fdbb5-270">desde la ciudad</span><span class="sxs-lookup"><span data-stu-id="fdbb5-270">outbound</span></span>  | <span data-ttu-id="fdbb5-271">x 1,00</span><span class="sxs-lookup"><span data-stu-id="fdbb5-271">x 1.00</span></span>  |
| <span data-ttu-id="fdbb5-272">Fin de semana</span><span class="sxs-lookup"><span data-stu-id="fdbb5-272">Weekend</span></span>    | <span data-ttu-id="fdbb5-273">hora punta de la tarde</span><span class="sxs-lookup"><span data-stu-id="fdbb5-273">evening rush</span></span> | <span data-ttu-id="fdbb5-274">hacia la ciudad</span><span class="sxs-lookup"><span data-stu-id="fdbb5-274">inbound</span></span>   | <span data-ttu-id="fdbb5-275">x 1,00</span><span class="sxs-lookup"><span data-stu-id="fdbb5-275">x 1.00</span></span>  |
| <span data-ttu-id="fdbb5-276">Fin de semana</span><span class="sxs-lookup"><span data-stu-id="fdbb5-276">Weekend</span></span>    | <span data-ttu-id="fdbb5-277">hora punta de la tarde</span><span class="sxs-lookup"><span data-stu-id="fdbb5-277">evening rush</span></span> | <span data-ttu-id="fdbb5-278">desde la ciudad</span><span class="sxs-lookup"><span data-stu-id="fdbb5-278">outbound</span></span>  | <span data-ttu-id="fdbb5-279">x 1,00</span><span class="sxs-lookup"><span data-stu-id="fdbb5-279">x 1.00</span></span>  |
| <span data-ttu-id="fdbb5-280">Fin de semana</span><span class="sxs-lookup"><span data-stu-id="fdbb5-280">Weekend</span></span>    | <span data-ttu-id="fdbb5-281">noche</span><span class="sxs-lookup"><span data-stu-id="fdbb5-281">overnight</span></span>    | <span data-ttu-id="fdbb5-282">hacia la ciudad</span><span class="sxs-lookup"><span data-stu-id="fdbb5-282">inbound</span></span>   | <span data-ttu-id="fdbb5-283">x 1,00</span><span class="sxs-lookup"><span data-stu-id="fdbb5-283">x 1.00</span></span>  |
| <span data-ttu-id="fdbb5-284">Fin de semana</span><span class="sxs-lookup"><span data-stu-id="fdbb5-284">Weekend</span></span>    | <span data-ttu-id="fdbb5-285">noche</span><span class="sxs-lookup"><span data-stu-id="fdbb5-285">overnight</span></span>    | <span data-ttu-id="fdbb5-286">desde la ciudad</span><span class="sxs-lookup"><span data-stu-id="fdbb5-286">outbound</span></span>  | <span data-ttu-id="fdbb5-287">x 1,00</span><span class="sxs-lookup"><span data-stu-id="fdbb5-287">x 1.00</span></span>  |

<span data-ttu-id="fdbb5-288">Hay 16 combinaciones distintas de las tres variables.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-288">There are 16 different combinations of the three variables.</span></span> <span data-ttu-id="fdbb5-289">Mediante la combinación de algunas de las condiciones, simplificará la expresión switch final.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-289">By combining some of the conditions, you'll simplify the final switch expression.</span></span>

<span data-ttu-id="fdbb5-290">El sistema que cobra los peajes usa una estructura <xref:System.DateTime> para la hora en que se cobró el peaje.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-290">The system that collects the tolls uses a <xref:System.DateTime> structure for the time when the toll was collected.</span></span> <span data-ttu-id="fdbb5-291">Genere métodos de miembro que creen las variables a partir de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-291">Build member methods that create the variables from the preceding table.</span></span> <span data-ttu-id="fdbb5-292">La función siguiente usa una expresión switch de coincidencia de patrones para expresar si la estructura <xref:System.DateTime> representa un día laborable o un fin de semana:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-292">The following function uses a pattern matching switch expression to express whether a <xref:System.DateTime> represents a weekend or a weekday:</span></span>

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

<span data-ttu-id="fdbb5-293">Ese método funciona, pero es redundante.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-293">That method works, but it's repetitious.</span></span> <span data-ttu-id="fdbb5-294">Puede simplificarlo tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-294">You can simplify it, as shown in the following code:</span></span>

[!code-csharp[IsWeekDay](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#IsWeekDay)]

<span data-ttu-id="fdbb5-295">A continuación, agregue una función similar para categorizar la hora en los bloques:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-295">Next, add a similar function to categorize the time into the blocks:</span></span>

[!code-csharp[GetTimeBand](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#GetTimeBand)]

<span data-ttu-id="fdbb5-296">El método anterior no usa la coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-296">The previous method doesn't use pattern matching.</span></span> <span data-ttu-id="fdbb5-297">Es más claro usar una cascada familiar de instrucciones `if`.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-297">It's clearer using a familiar cascade of `if` statements.</span></span> <span data-ttu-id="fdbb5-298">Sí agrega una `enum` privada para convertir cada intervalo de tiempo en un valor discreto.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-298">You do add a private `enum` to convert each range of time to a discrete value.</span></span>

<span data-ttu-id="fdbb5-299">Después de usar esos métodos, puede usar otra expresión `switch` con el **patrón de tuplas** para calcular el recargo en los precios.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-299">After you create those methods, you can use another `switch` expression with the **tuple pattern** to calculate the pricing premium.</span></span> <span data-ttu-id="fdbb5-300">Puede crear una expresión `switch` con los 16 segmentos:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-300">You could build a `switch` expression with all 16 arms:</span></span>

[!code-csharp[FullTuplePattern](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#TuplePatternOne)]

<span data-ttu-id="fdbb5-301">El código anterior funciona, pero se puede simplificar.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-301">The above code works, but it can be simplified.</span></span> <span data-ttu-id="fdbb5-302">Las ocho combinaciones para el fin de semana tienen el mismo peaje.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-302">All eight combinations for the weekend have the same toll.</span></span> <span data-ttu-id="fdbb5-303">Puede reemplazar las ocho por la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-303">You can replace all eight with the following line:</span></span>

```csharp
(false, _, _) => 1.0m,
```

<span data-ttu-id="fdbb5-304">Tanto el tráfico hacia la ciudad como el tráfico desde la ciudad tienen el mismo multiplicador durante el día y la noche de los fines de semana.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-304">Both inbound and outbound traffic have the same multiplier during the weekday daytime and overnight hours.</span></span> <span data-ttu-id="fdbb5-305">Esos cuatro segmentos modificadores se pueden reemplazar por las dos líneas siguientes:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-305">Those four switch arms can be replaced with the following two lines:</span></span>

```csharp
(true, TimeBand.Overnight, _) => 0.75m,
(true, TimeBand.Daytime, _)   => 1.5m,
```

<span data-ttu-id="fdbb5-306">El código debe ser similar al código siguiente después de esos dos cambios:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-306">The code should look like the following code after those two changes:</span></span>

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

<span data-ttu-id="fdbb5-307">Por último, puede quitar las dos horas punta en que se paga el precio regular.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-307">Finally, you can remove the two rush hour times that pay the regular price.</span></span> <span data-ttu-id="fdbb5-308">Cuando quite esos segmentos, puede reemplazar `false` por un descarte (`_`) en el segmento modificador final.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-308">Once you remove those arms, you can replace the `false` with a discard (`_`) in the final switch arm.</span></span> <span data-ttu-id="fdbb5-309">Tendrá el siguiente método finalizado:</span><span class="sxs-lookup"><span data-stu-id="fdbb5-309">You'll have the following finished method:</span></span>

[!code-csharp[SimplifiedTuplePattern](../../../samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#FinalTuplePattern)]

<span data-ttu-id="fdbb5-310">En este ejemplo se resalta una de las ventajas de la coincidencia de patrones: las ramas del patrón se evalúan en orden.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-310">This example highlights one of the advantages of pattern matching: the pattern branches are evaluated in order.</span></span> <span data-ttu-id="fdbb5-311">Si vuelve a ordenarlas para que una rama anterior controle uno de los últimos casos, el compilador genera una advertencia sobre el código inaccesible.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-311">If you rearrange them so that an earlier branch handles one of your later cases, the compiler warns you about the unreachable code.</span></span> <span data-ttu-id="fdbb5-312">Esas reglas de lenguaje facilitan la realización de las simplificaciones anteriores con la confianza de que el código no cambió.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-312">Those language rules made it easier to do the preceding simplifications with confidence that the code didn't change.</span></span>

<span data-ttu-id="fdbb5-313">La coincidencia de patrones hace que algunos tipos de código sean más legibles y ofrece una alternativa a las técnicas orientadas a objetos cuando no se puede agregar código a las clases.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-313">Pattern matching makes some types of code more readable and offers an alternative to object-oriented techniques when you can't add code to your classes.</span></span> <span data-ttu-id="fdbb5-314">La nube hace que los datos y la funcionalidad residan por separado.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-314">The cloud is causing data and functionality to live apart.</span></span> <span data-ttu-id="fdbb5-315">La *forma* de los datos y las *operaciones* que se realizan en ellos no necesariamente se describen en conjunto.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-315">The *shape* of the data and the *operations* on it aren't necessarily described together.</span></span> <span data-ttu-id="fdbb5-316">En este tutorial, consumió datos existentes de maneras totalmente distintas de su función original.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-316">In this tutorial, you consumed existing data in entirely different ways from its original function.</span></span> <span data-ttu-id="fdbb5-317">La coincidencia de patrones le ha brindado la capacidad de escribir una funcionalidad que reemplazase a esos tipos, aunque no le permitía extenderlos.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-317">Pattern matching gave you the ability to write functionality that overrode those types, even though you couldn't extend them.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fdbb5-318">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="fdbb5-318">Next steps</span></span>

<span data-ttu-id="fdbb5-319">Puede descargar el código finalizado del repositorio GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished).</span><span class="sxs-lookup"><span data-stu-id="fdbb5-319">You can download the finished code from the [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished) GitHub repository.</span></span> <span data-ttu-id="fdbb5-320">Explore los patrones por su cuenta y agregue esta técnica a sus actividades habituales de codificación.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-320">Explore patterns on your own and add this technique into your regular coding activities.</span></span> <span data-ttu-id="fdbb5-321">Aprender estas técnicas le permite contar con otra forma de enfocar los problemas y crear una funcionalidad nueva.</span><span class="sxs-lookup"><span data-stu-id="fdbb5-321">Learning these techniques gives you another way to approach problems and create new functionality.</span></span>
