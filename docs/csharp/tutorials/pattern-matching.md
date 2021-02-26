---
title: 'Tutorial: Algoritmos de compilación con coincidencia de patrones'
description: En este tutorial avanzado se muestra cómo usar técnicas de coincidencia de patrones para crear una funcionalidad con datos y algoritmos creados por separado.
ms.date: 10/06/2020
ms.technology: csharp-whats-new
ms.custom: contperf-fy21q1
ms.openlocfilehash: b0ee4ee905c130876cf201cb3a1a441d54226c52
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "100582788"
---
# <a name="tutorial-use-pattern-matching-to-build-type-driven-and-data-driven-algorithms"></a>Tutorial: Uso de la coincidencia de patrones para compilar algoritmos basados en tipos y basados en datos

C# 7 introdujo las características básicas de coincidencia de patrones. Esas características se han ampliado en C# 8 y C# 9 con nuevas expresiones y patrones. Puede escribir una funcionalidad que se comporta como si se hubiesen ampliado tipos que pueden estar en otras bibliotecas. Los patrones también se usan para crear una funcionalidad que la aplicación requiere y que no es una característica fundamental del tipo que se está ampliando.

En este tutorial, aprenderá a:

> [!div class="checklist"]
>
> - Reconocer situaciones donde se debe usar la coincidencia de patrones.
> - Usar las expresiones de coincidencia de patrones para implementar un comportamiento en función de los tipos y los valores de propiedad.
> - Combinar la coincidencia de patrones con otras técnicas para crear algoritmos completos.

## <a name="prerequisites"></a>Requisitos previos

Tendrá que configurar el equipo para ejecutar .NET 5, que incluye el compilador de C# 9. El compilador de C# 9 está disponible a partir de [Visual Studio 2019, versión 16.9 Preview 1](https://visualstudio.microsoft.com/vs/preview/) o del [SDK de .NET 5.0](https://dot.net/get-dotnet5).

En este tutorial se da por supuesto que está familiarizado con C# y. NET, incluidos Visual Studio o la CLI de .NET Core.

## <a name="scenarios-for-pattern-matching"></a>Escenarios para la coincidencia de patrones

Con frecuencia, el desarrollo moderno incluye integrar datos desde varios orígenes y presentar información y perspectivas a partir de esos datos en una sola aplicación cohesiva. Ni usted ni su equipo tendrán control ni acceso para todos los tipos que representan los datos entrantes.

El diseño clásico orientado a objetos llamaría a la creación de tipos en la aplicación que representen cada tipo de datos de esos orígenes de datos múltiples. Luego, la aplicación podría trabajar con esos tipos nuevos, crear jerarquías de herencia, crear métodos virtuales e implementar abstracciones. Esas técnicas funcionan y son a veces las mejores herramientas. En otras ocasiones, puede escribir menos código. Puede escribir código más claro con técnicas que separan los datos de las operaciones que manipulan esos datos.

En este tutorial, creará y explorará una aplicación que toma datos entrantes de varios orígenes externos para un solo escenario. Verá cómo la **coincidencia de patrones** proporciona una forma eficaz de consumir y procesar esos datos de maneras que no formaban parte del sistema original.

Considere un área metropolitana importante que usa peajes y precios estipulados para las horas de mayor actividad con el fin de administrar el tráfico. Puede escribir una aplicación que calcule los peajes de un vehículo en función de su tipo. Mejoras posteriores incorporan precios basados en la cantidad de ocupantes del vehículo. Otras mejoras agregan precios según la hora y el día de la semana.

Desde esa descripción breve, puede haber esbozado rápidamente una jerarquía de objetos para modelar este sistema. Sin embargo, los datos provienen de varios orígenes, como otros sistemas de administración de registros de vehículos. Estos sistemas ofrecen distintas clases para modelar esos datos y no se tiene un modelo de objetos único que puede usar. En este tutorial, usará estas clases simplificadas para modelar los datos del vehículo desde dichos sistemas externos, tal como se muestra en el código siguiente:

[!code-csharp[ExternalSystems](~/samples/snippets/csharp/tutorials/patterns/start/toll-calculator/ExternalSystems.cs)]

Puede descargar el código de inicio del repositorio [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/start) de GitHub. Puede ver que las clases de vehículo provienen de distintos sistemas y que están en distintos espacios de nombres. No se puede aprovechar ninguna clase base común distinta de `System.Object`.

## <a name="pattern-matching-designs"></a>Diseños de coincidencia de patrones

En el escenario que se usa en este tutorial se resaltan los tipos de problemas en los que resulta adecuado usar la coincidencia de patrones para resolver lo siguiente:

- Los objetos con los que necesita trabajar no están en una jerarquía de objetos que coincida con sus objetivos. Es posible que trabaje con clases que forman parte de sistemas no relacionados.
- La funcionalidad que agrega no forma parte de la abstracción central de estas clases. El peaje que paga un vehículo *cambia* según los distintos tipos de vehículos, pero el peaje no es una función central del vehículo.

Cuando la *forma* de los datos y las *operaciones* que se realizan en esos datos no se describen en conjunto, las características de coincidencia de patrones de C# permiten que sea más fácil trabajar con ellos.

## <a name="implement-the-basic-toll-calculations"></a>Implementación de cálculos de peajes básicos

El cálculo de peaje más básico solo se basa en el tipo de vehículo:

- Un `Car` es USD 2,00.
- Un `Taxi` es USD 3,50.
- Un `Bus` es USD 5,00.
- Un `DeliveryTruck` es USD 10,00

Cree una clase `TollCalculator` nueva e implemente la coincidencia de patrones en el tipo de vehículo para obtener el importe del peaje. En el siguiente código se muestra la implementación inicial de `TollCalculator`.

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

El código anterior usa una **expresión switch** (que no es la misma que en una instrucción [`switch`](../language-reference/keywords/switch.md)) que prueba el **patrón de tipo**. Una **expresión switch** comienza por la variable, `vehicle` en el código anterior, seguida de la palabra clave `switch`. A continuación, todos los **segmentos modificadores** aparecen entre llaves. La expresión `switch` lleva a cabo otras mejoras en la sintaxis que rodea la instrucción `switch`. La palabra clave `case` se omite y el resultado de cada segmento es una expresión. Los dos últimos segmentos muestran una característica de lenguaje nueva. El caso `{ }` coincide con cualquier objeto no nulo que no coincidía con ningún segmento anterior. Este segmento detecta todo tipo incorrecto que se pasa a este método.  El caso `{ }` debe seguir los casos de cada tipo de vehículo. Si se invierte el orden, el caso `{ }` tendrá prioridad. Por último, el patrón `null` detecta si se pasa `null` a este método. El patrón `null` puede ser el último porque los otros patrones de tipos solo coinciden con un objeto no nulo del tipo correcto.

Puede probar este código con el código siguiente en `Program.cs`:

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

Ese código se incluye en el proyecto de inicio, pero se marca como comentario. Quite los comentarios y podrá probar lo que escribió.

Empezará a ver cómo los patrones pueden ayudarlo a crear algoritmos cuando el código y los datos están separados. La expresión `switch` prueba el tipo y genera valores distintos en función de los resultados. Eso es solo el principio.

## <a name="add-occupancy-pricing"></a>Incorporación de precios por ocupación

La autoridad encargada de los peajes quiere incentivar que los vehículos viajen a plena capacidad. Se decidió cobrar más cuando los vehículos circulan con menos pasajeros y se incentiva que los vehículos vayan llenos al ofrecer precios más bajos:

- Los automóviles y taxis sin pasajeros pagan USD 0,50 adicionales.
- Los automóviles y taxis con dos pasajeros tienen un descuento de USD 0,50.
- Los automóviles y taxis con tres o más pasajeros tienen un descuento de USD 1.
- Los buses que viajan con menos del 50 % de su capacidad pagan USD 2 adicionales.
- Los buses que viajan con más del 90 % de su capacidad tienen un descuento de USD 1.

Estas reglas se pueden implementar con el **patrón de propiedad** en la misma expresión switch. Un patrón de propiedades es una cláusula `when` que compara un valor de propiedad con un valor constante. El patrón de propiedad examina las propiedades del objeto una vez que se determina el tipo. El caso único de `Car` se amplía a cuatro casos distintos:

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

Los primeros tres casos prueban el tipo como `Car` y luego comprueban el valor de la propiedad `Passengers`. Si ambos coinciden, esa expresión se evalúa y devuelve.

También podría expandir los casos para los taxis de manera similar:

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

En el ejemplo anterior, la cláusula `when` se omitía en el caso final.

A continuación, implemente las reglas de ocupación mediante la expansión de los casos para los buses, tal como se muestra en el ejemplo siguiente:

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

A la autoridad encargada de los peajes no le preocupa el número de pasajeros en los camiones de reparto. Alternativamente, ajustan el importe del peaje en base a la clase de peso de los camiones, como sigue:

- A los camiones de más de 2268 kilos se les cobran USD 5 adicionales.
- Los camiones livianos, por debajo de los 1360 kilos, tienen un descuento de 2 USD.

Esta regla se implementa con el código siguiente:

```csharp
vehicle switch
{
    // ...

    DeliveryTruck t when (t.GrossWeightClass > 5000) => 10.00m + 5.00m,
    DeliveryTruck t when (t.GrossWeightClass < 3000) => 10.00m - 2.00m,
    DeliveryTruck t => 10.00m,
};
```

En el código anterior se muestra la cláusula `when` de un segmento modificador. Puede usar la cláusula `when` para probar condiciones distintas de la igualdad de una propiedad. Cuando haya terminado, tendrá un método muy similar al código siguiente:

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

Muchos de estos segmentos modificadores son ejemplos de **patrones recursivos**. Por ejemplo, `Car { Passengers: 1}` muestra un patrón constante dentro de un patrón de propiedad.

Puede usar modificadores anidados para que este código sea menos repetitivo. Tanto `Car` como `Taxi` tienen cuatro segmentos distintos en los ejemplos anteriores. En ambos casos, puede crear un patrón de tipo que se agrega a un patrón de propiedad. Esta técnica se muestra en el código siguiente:

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

En el ejemplo anterior, el uso de una expresión recursiva significa que no repite los segmentos `Car` y `Taxi` que contienen segmentos secundarios que prueban el valor de propiedad. Esta técnica no se usa para los segmentos `Bus` y `DeliveryTruck`, porque esos segmentos prueban intervalos para la propiedad, no valores discretos.

## <a name="add-peak-pricing"></a>Incorporación de precio en horas punta

Para la característica final, la autoridad encargada de los peajes quiere agregar precios en función de las horas punta. En las horas de mayor afluencia durante mañana y tarde, el valor de los peajes se dobla. Esa regla solo afecta el tráfico en una dirección: hacia la ciudad en la mañana y desde la ciudad en la tarde. En otros momentos durante la jornada laboral, los peajes aumentan en un 50 %. Tarde por la noche y temprano en la mañana, disminuyen en un 25 %. Durante el fin de semana, la tarifa es normal independientemente de la hora. Puede usar una serie de instrucciones `if` y `else` para expresar esto mediante el código siguiente:

[!code-csharp[FullTuplePattern](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#SnippetPremiumWithoutPattern)]

El código anterior funciona correctamente, pero no es legible. Para que el código tenga sentido, tiene que encadenar todos los casos de entrada y las instrucciones `if` anidadas. En su lugar, usará la coincidencia de patrones para esta característica, pero la integrará con otras técnicas. Podría crear una expresión de coincidencia de patrones única que consideraría todas las combinaciones de dirección, día de la semana y hora. El resultado sería una expresión complicada. Podría ser difícil de leer y de comprender. Esto implica que es difícil garantizar su exactitud. En su lugar, combine esos método para crear una tupla de valores que describa de manera concisa todos esos estados. Luego, use la coincidencia de patrones para calcular un multiplicador para el peaje. La tupla contiene tres condiciones discretas:

- El día es un día laborable o fin de semana.
- La banda de tiempo cuando se cobra el peaje.
- La dirección si va hacia la ciudad o desde la ciudad.

En la tabla siguiente se muestran las combinaciones de valores de entrada y el multiplicador de precio en horas punta:

| Día        | Time         | Dirección | Premium |
| ---------- | ------------ | --------- |--------:|
| Día de la semana    | hora punta de la mañana | hacia la ciudad   | x 2,00  |
| Día de la semana    | hora punta de la mañana | desde la ciudad  | x 1,00  |
| Día de la semana    | día      | hacia la ciudad   | x 1,50  |
| Día de la semana    | día      | desde la ciudad  | x 1,50  |
| Día de la semana    | hora punta de la tarde | hacia la ciudad   | x 1,00  |
| Día de la semana    | hora punta de la tarde | desde la ciudad  | x 2,00  |
| Día de la semana    | noche    | hacia la ciudad   | x 0,75  |
| Día de la semana    | noche    | desde la ciudad  | x 0,75  |
| Fin de semana    | hora punta de la mañana | hacia la ciudad   | x 1,00  |
| Fin de semana    | hora punta de la mañana | desde la ciudad  | x 1,00  |
| Fin de semana    | día      | hacia la ciudad   | x 1,00  |
| Fin de semana    | día      | desde la ciudad  | x 1,00  |
| Fin de semana    | hora punta de la tarde | hacia la ciudad   | x 1,00  |
| Fin de semana    | hora punta de la tarde | desde la ciudad  | x 1,00  |
| Fin de semana    | noche    | hacia la ciudad   | x 1,00  |
| Fin de semana    | noche    | desde la ciudad  | x 1,00  |

Hay 16 combinaciones distintas de las tres variables. Mediante la combinación de algunas de las condiciones, simplificará la expresión switch final.

El sistema que cobra los peajes usa una estructura <xref:System.DateTime> para la hora en que se cobró el peaje. Genere métodos de miembro que creen las variables a partir de la tabla anterior. La función siguiente usa una expresión switch de coincidencia de patrones para expresar si la estructura <xref:System.DateTime> representa un día laborable o un fin de semana:

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

Ese método es correcto, pero es redundante. Puede simplificarlo tal como se muestra en el código siguiente:

[!code-csharp[IsWeekDay](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#IsWeekDay)]

A continuación, agregue una función similar para categorizar la hora en los bloques:

[!code-csharp[GetTimeBand](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#GetTimeBand)]

Agregue un elemento `enum` privado para convertir cada intervalo de tiempo en un valor discreto. Después, el método `GetTimeBand` usa *patrones relacionales* y *patrones OR conjuntivos*, ambos agregados en C# 9.0. El patrón relacional permite probar un valor numérico mediante `<`, `>`, `<=` o `>=`. El patrón `or` comprueba si una expresión coincide con uno o más patrones. También puede usar un patrón `and` para asegurarse de que una expresión coincide con dos patrones distintos, y un patrón `not` para probar que una expresión no coincide con un patrón.

Después de usar esos métodos, puede usar otra expresión `switch` con el **patrón de tuplas** para calcular el recargo en los precios. Puede crear una expresión `switch` con los 16 segmentos:

[!code-csharp[FullTuplePattern](~/samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#TuplePatternOne)]

El código anterior funciona, pero se puede simplificar. Las ocho combinaciones para el fin de semana tienen el mismo peaje. Puede reemplazar las ocho por la siguiente línea:

```csharp
(false, _, _) => 1.0m,
```

Tanto el tráfico hacia la ciudad como el tráfico desde la ciudad tienen el mismo multiplicador durante el día y la noche de los fines de semana. Esos cuatro segmentos modificadores se pueden reemplazar por las dos líneas siguientes:

```csharp
(true, TimeBand.Overnight, _) => 0.75m,
(true, TimeBand.Daytime, _)   => 1.5m,
```

El código debe ser similar al código siguiente después de esos dos cambios:

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

Por último, puede quitar las dos horas punta en que se paga el precio regular. Cuando quite esos segmentos, puede reemplazar `false` por un descarte (`_`) en el segmento modificador final. Tendrá el siguiente método finalizado:

[!code-csharp[SimplifiedTuplePattern](../../../samples/snippets/csharp/tutorials/patterns/finished/toll-calculator/TollCalculator.cs#FinalTuplePattern)]

En este ejemplo se resalta una de las ventajas de la coincidencia de patrones: las ramas del patrón se evalúan en orden. Si vuelve a ordenarlas para que una rama anterior controle uno de los últimos casos, el compilador genera una advertencia sobre el código inaccesible. Esas reglas de lenguaje facilitan la realización de las simplificaciones anteriores con la confianza de que el código no cambió.

La coincidencia de patrones hace que algunos tipos de código sean más legibles y ofrece una alternativa a las técnicas orientadas a objetos cuando no se puede agregar código a las clases. La nube hace que los datos y la funcionalidad residan por separado. La *forma* de los datos y las *operaciones* que se realizan en ellos no necesariamente se describen en conjunto. En este tutorial, consumió datos existentes de maneras totalmente distintas de su función original. La coincidencia de patrones le ha brindado la capacidad de escribir una funcionalidad que reemplazase a esos tipos, aunque no le permitía extenderlos.

## <a name="next-steps"></a>Pasos siguientes

Puede descargar el código finalizado del repositorio GitHub [dotnet/samples](https://github.com/dotnet/samples/tree/master/csharp/tutorials/patterns/finished). Explore los patrones por su cuenta y agregue esta técnica a sus actividades habituales de codificación. Aprender estas técnicas le permite contar con otra forma de enfocar los problemas y crear una funcionalidad nueva.
