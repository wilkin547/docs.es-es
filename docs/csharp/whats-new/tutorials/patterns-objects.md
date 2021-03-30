---
title: 'Uso de patrones en objetos: tutorial de C#'
description: En este tutorial se enseñan técnicas para usar la coincidencia de patrones en los miembros de clase a fin de crear mejores modelos para el comportamiento de objetos.
ms.date: 11/05/2020
ms.openlocfilehash: 072f6f57696504c2d691473e3a43c1cda53f227f
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104878975"
---
# <a name="use-pattern-matching-to-build-your-class-behavior-for-better-code"></a>Uso de la coincidencia de patrones para crear el comportamiento de la clase y mejorar el código

Las características de coincidencia de patrones en C# proporcionan la sintaxis para expresar los algoritmos. Puede usar estas técnicas para implementar el comportamiento en las clases. Puede combinar el diseño de clases orientadas a objetos con una implementación orientada a datos para proporcionar un código conciso al modelar objetos del mundo real.

En este tutorial, aprenderá a:

> [!div class="checklist"]
>
> - Expresar las clases orientadas a objetos mediante patrones de datos.
> - Implementar dichos patrones con las características de coincidencia de patrones de C#.
> - Aprovechar los diagnósticos del compilador para validar la implementación.

## <a name="prerequisites"></a>Requisitos previos

Deberá configurar la máquina para ejecutar .NET 5, incluido el compilador de C# 9.0. El compilador de C# 9.0 está disponible a partir de [Visual Studio 2019, versión 16.8 Preview](https://visualstudio.microsoft.com/vs/preview/) o del [SDK de .NET 5.0 Preview](https://dotnet.microsoft.com/download/dotnet/5.0).

## <a name="build-a-simulation-of-a-canal-lock"></a>Compilación de una simulación de una esclusa de canal

En este tutorial, compilará una clase de C# que simula una [esclusa de canal](https://en.wikipedia.org/wiki/Lock_(water_navigation)). En pocas palabras, una esclusa de canal es un dispositivo que permite que los barcos suban y bajen cuando se mueven entre dos cuerpos de agua con distintos niveles. Una esclusa tiene dos compuertas y algún mecanismo que permite cambiar el nivel del agua.

En su funcionamiento habitual, un barco entra por una de las compuertas mientras el nivel del agua en la esclusa se iguala al nivel del agua del lado por donde entra el barco. Una vez en la esclusa, se modifica el nivel del agua para igualarlo al nivel de donde el barco saldrá de la esclusa. Cuando el nivel del agua es igual al de ese lado, se abre la compuerta de la salida. Hay medidas de seguridad que garantizan que un operador no pueda crear una situación de peligro en el canal. El nivel del agua solo se puede modificar cuando ambas compuertas están cerradas. Como mucho, puede haber una compuerta abierta. Para abrir una compuerta, el nivel del agua de la esclusa debe coincidir con el nivel fuera de la compuerta que se está abriendo.

Es posible compilar una clase de C# que modele este comportamiento. Una clase `CanalLock` podría admitir los comandos para abrir o cerrar cualquiera de las compuertas. Tendría otros comandos para aumentar o reducir el nivel del agua. La clase también debería admitir propiedades para leer el estado actual de ambas compuertas y el nivel del agua. Los métodos implementan las medidas de seguridad.

## <a name="define-a-class"></a>Definición de una clase

Compilará una aplicación de consola para probar la clase `CanalLock`. Cree un proyecto de consola nuevo para .NET 5 con Visual Studio o la CLI de .NET. Luego, agregue una clase nueva con el nombre `CanalLock`. Luego, diseñe la API pública, pero deje los métodos sin implementar:

:::code language="csharp" source="snippets/pattern-objects/InterimSteps.cs" ID="APIDesign":::

El código anterior inicializa el objeto de manera que ambas compuertas estén cerradas y el nivel del agua sea bajo. Luego, escriba el código de prueba siguiente en el método `Main` como guía para crear una primera implementación de la clase:

:::code language="csharp" source="snippets/pattern-objects/Program.cs" ID="HappyTests":::

A continuación, agregue una primera implementación de cada método en la clase `CanalLock`. El código siguiente implementa los métodos de la clase sin preocuparse por las reglas de seguridad. Más adelante agregará pruebas de seguridad:

:::code language="csharp" source="snippets/pattern-objects/InterimSteps.cs" ID="FirstImplementation":::

Las pruebas que ha escrito hasta el momento se completan correctamente. Ha implementado los aspectos básicos. Ahora, escriba una prueba para la primera condición de error. Al final de las pruebas anteriores, ambas compuertas están cerradas y el nivel del agua se establece en bajo. Agregue una prueba para intentar abrir la compuerta superior:

:::code language="csharp" source="snippets/pattern-objects/Program.cs" ID="HighGateSafetyTest":::

Esta prueba genera un error porque la compuerta se abre. Como primera implementación, puede corregirlo con este código:

:::code language="csharp" source="snippets/pattern-objects/InterimSteps.cs" ID="SecondImplementation":::

Las pruebas se realizan correctamente. Pero a medida que agrega más pruebas, agregará cada vez más cláusulas `if` y probará distintas propiedades. Pronto, estos métodos resultarán demasiado complicados a medida que agregue más condicionales.

## <a name="implement-the-commands-with-patterns"></a>Implementación de los comandos con patrones

Una mejor manera es usar *patrones* para determinar si el objeto tiene un estado válido para ejecutar un comando. Puede expresar si se permite un comando como una función de tres variables: el estado de la compuerta, el nivel del agua y la nueva configuración:

| Nueva configuración | Estado de la compuerta | Nivel del agua | Resultado             |
| ----------- | ---------- | ----------- | ------------------ |
| Cerrada      | Cerrada     | Alto        | Cerrada             |
| Cerrada      | Cerrada     | Bajo         | Cerrada             |
| Cerrada      | Abrir       | Alto        | Abrir               |
| ~~Closed~~  | ~~Abrir~~   | ~~Baja~~     | ~~Closed~~         |
| Abrir        | Closed     | Alto        | Abrir               |
| Abrir        | Closed     | Bajo         | Cerrada (error)     |
| Abrir        | Abrir       | Alto        | Abrir               |
| ~~Abrir~~    | ~~Abrir~~   | ~~Baja~~     | ~~Cerrada (error)~~ |

La cuarta y la última fila de la tabla tienen tachado el texto porque no son válidas. El código que va a agregar ahora debe garantizar que la compuerta superior no se abrirá nunca si el nivel del agua es bajo.  Esos estados se pueden codificar como una expresión switch única (recuerde que `false` indica "Cerrada"):

:::code language="csharp" source="snippets/pattern-objects/InterimSteps.cs" ID="ThirdImplementation":::

Pruebe esta versión. Las pruebas se realizan correctamente, lo que valida el código. En la tabla completa se muestran las combinaciones posibles de entradas y resultados. Eso significa que tanto usted como otros desarrolladores pueden examinar rápidamente la tabla y ver que se han cubierto todas las entradas posibles. Usar el compilador puede hacerlo más fácil. Después de agregar el código anterior, puede ver que el compilador genera una advertencia: *CS8524* indica que la expresión switch no cubre todas las entradas posibles. El motivo de esta advertencia es que una de las entradas es de tipo `enum`. El compilador interpreta "todas las entradas posibles" como todas las entradas del tipo subyacente, por lo general, un `int`. Esta expresión `switch` solo comprueba los valores declarados en la `enum`. Para quitar la advertencia, puede agregar un patrón de descarte comodín para el último segmento de la expresión. Esta condición genera una excepción porque indica una entrada no válida:

```csharp
_  => throw new InvalidOperationException("Invalid internal state"),
```

El segmento modificador anterior debe ir al final de la expresión `switch` porque coincide con todas las entradas. Experimente poniendo el segmento modificador antes en la expresión. Eso generará un error de compilador *CS8510* para un código inalcanzable en un patrón.  La estructura natural de las expresiones switch permite que el compilador genere errores y advertencias en caso de posibles errores. La "red de seguridad" del compilador facilita la creación de código correcto en menos iteraciones y brinda la libertad de combinar segmentos modificadores con caracteres comodín. El compilador emitirá errores si la combinación da como resultado segmentos inaccesibles no esperados y advertencias si quita un segmento necesario.

El primer cambio consiste en combinar todos los segmentos en los que el comando va a cerrar la compuerta; eso siempre se permite. Agregue el código siguiente como el primer segmento de la expresión switch:

```csharp
(false, _, _) => false,
```

Después de agregar el segmento modificador anterior, recibirá cuatro errores de compilador, uno en cada uno de los segmentos donde el comando es `false`. Estos segmentos ya los cubre el segmento recién agregado. Puede quitar sin problemas esas cuatro líneas. Su intención era que este segmento modificador nuevo reemplazara esas condiciones.

Luego, puede simplificar los cuatro segmentos en los que el comando indica abrir la compuerta. En ambos casos en los que el nivel del agua es alto, se puede abrir la compuerta. (En un caso, ya está abierta). Un caso en el que el nivel del agua es bajo genera una excepción y el otro no debería ocurrir. Debería ser seguro generar la misma excepción si el cierre hidráulico ya tiene un estado no válido. Puede hacer estas simplificaciones para esos segmentos:

```csharp
(true, _, WaterLevel.High) => true,
(true, false, WaterLevel.Low) => throw new InvalidOperationException("Cannot open high gate when the water is low"),
_ => throw new InvalidOperationException("Invalid internal state"),
```

Vuelva a ejecutar las pruebas y las completarán correctamente. Esta es la versión final del método `SetHighGate`:

:::code language="csharp" source="snippets/pattern-objects/CanalLock.cs" ID="FinalImplementaton":::

## <a name="implement-patterns-yourself"></a>Implementación de patrones por su cuenta

Ahora que conoce la técnica, complete usted mismo los métodos `SetLowGate` y `SetWaterLevel`.  Empiece agregando el código siguiente para probar las operaciones no válidas en esos métodos:

:::code language="csharp" source="snippets/pattern-objects/Program.cs" ID="FinalTestCode":::

Vuelva a ejecutar la aplicación. Puede ver que se generan errores en las pruebas nuevas y que la esclusa de canal queda en un estado no válido. Intente implementar usted mismo el resto de los métodos. El método para establecer la compuerta inferior debe ser similar al que se usa para establecer la compuerta superior. El método que cambia el nivel del agua tiene otras comprobaciones, pero debe seguir una estructura similar. Puede que le resulte útil usar el mismo proceso para el método que establece el nivel del agua. Comience con las cuatro entradas: El estado de ambas compuertas, el estado actual del nivel del agua y el nuevo nivel del agua solicitado. La expresión switch debe empezar por:

```csharp
CanalLockWaterLevel = (newLevel, CanalLockWaterLevel, LowWaterGateOpen, HighWaterGateOpen) switch
{
    // elided
};
```

Tendrá que completar un total de 16 segmentos modificadores. Luego, realice la prueba y simplifique.

¿Hizo métodos como este?

:::code language="csharp" source="snippets/pattern-objects/CanalLock.cs" ID="FinalExercise":::

Las pruebas deberían completarse correctamente y la esclusa de canal debería funcionar de manera segura.

## <a name="summary"></a>Resumen

En este tutorial, aprendió a usar la coincidencia de patrones para comprobar el estado interno de un objeto antes de aplicar cualquier cambio en ese estado. Puede comprobar combinaciones de propiedades. Una vez que cree tablas para cualquiera de esas transiciones, probará el código y, luego, lo simplificará para su lectura y mantenimiento. Estas refactorizaciones iniciales pueden sugerir otras refactorizaciones que validen el estado interno o administren otros cambios de la API. En este tutorial se combinan clases y objetos con un enfoque más orientado a datos basado en patrones para implementar esas clases.
