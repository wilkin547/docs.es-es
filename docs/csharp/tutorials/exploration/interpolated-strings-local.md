---
title: 'Interpolación de cadenas: tutorial de C#'
description: En este tutorial se muestra cómo usar la característica de interpolación de cadenas de C# para incluir resultados de expresión con formato en una cadena mayor.
ms.date: 10/23/2018
ms.openlocfilehash: 593f3a77370da73dfd5f090be98112327b86b1f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75346778"
---
# <a name="use-string-interpolation-to-construct-formatted-strings"></a>Uso de la interpolación de cadenas para construir cadenas con formato

En este tutorial se muestra cómo usar la [interpolación de cadenas](../../language-reference/tokens/interpolated.md) de C# para insertar valores en una cadena de resultado única. Escriba código de C# y vea los resultados de la compilación y la ejecución. Este tutorial contiene una serie de lecciones para mostrarle cómo insertar valores en una cadena y dar formato a estos valores de maneras diferentes.

En este tutorial se supone que cuenta con una máquina que puede usar para el desarrollo. El tutorial de .NET [Hola mundo en 10 minutos](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) cuenta con instrucciones para configurar el entorno de desarrollo local en Windows, Linux o macOS. También puede completar la [versión interactiva](interpolated-strings.yml) de este tutorial en el explorador.

## <a name="create-an-interpolated-string"></a>Crear una cadena interpolada

Cree un directorio denominado *interpolated*. Conviértalo en el directorio actual y ejecute este comando desde una ventana de consola:

```dotnetcli
dotnet new console
```

Este comando crea una nueva aplicación de consola de .NET Core en el directorio actual.

Abra *Program.cs* en su editor favorito y reemplace la línea `Console.WriteLine("Hello World!");` por el código siguiente, teniendo en cuenta que debe reemplazar `<name>` con su nombre:

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```

Pruebe este código escribiendo `dotnet run` en la ventana de la consola. Al ejecutar el programa, se muestra una cadena única que incluye su nombre en el saludo. La cadena que se incluye en la llamada al método <xref:System.Console.WriteLine%2A> es una *expresión de cadena interpolada*. Es un tipo de plantilla que permite construir una sola cadena (denominada *cadena de resultado*) a partir de una cadena que incluye código incrustado. Las cadenas interpoladas son especialmente útiles para insertar valores en una cadena o en cadenas concatenadas (unidas entre sí).

Este sencillo ejemplo contiene los dos elementos que debe tener cada cadena interpolada:

- Un literal de cadena que empieza con el carácter `$` antes del carácter de comillas de apertura. No puede haber ningún espacio entre el símbolo `$` y el carácter de comillas. (Si quiere saber qué pasa si incluye una, inserte un espacio después del carácter `$`, guarde el archivo y vuelva a ejecutar el programa escribiendo `dotnet run` en la ventana de la consola. El compilador de C# muestra un mensaje de error: "error CS1056: carácter no esperado '$'").

- Una o varias *expresiones de interpolación*. Una expresión de interpolación se indica mediante una llave de apertura y de cierre (`{` y `}`). Puede colocar cualquier expresión de C# que devuelva un valor (incluido `null`) dentro de las llaves.

Probemos algunos ejemplos más de interpolación de cadenas con otros tipos de datos.

## <a name="include-different-data-types"></a>Incluir diferentes tipos de datos

En la sección anterior, se ha usado una interpolación de cadena para insertar una cadena dentro de otra, pero el resultado de una expresión de interpolación puede ser cualquier tipo de datos. Vamos a incluir valores de distintos tipos de datos en una cadena interpolada.

En el ejemplo siguiente, primero se define un tipo de datos de [clase](../../programming-guide/classes-and-structs/classes.md)`Vegetable` que tiene una [propiedad ](../../properties.md)`Name` y un [método](../../methods.md)`ToString` que [reemplaza](../../language-reference/keywords/override.md) el comportamiento del método <xref:System.Object.ToString?displayProperty=nameWithType>. El [`public`modificador de acceso](../../language-reference/keywords/public.md) pone ese método a disposición de cualquier código de cliente para obtener la representación de la cadena de una instancia de `Vegetable`. En el ejemplo, el método `Vegetable.ToString` devuelve el valor de la propiedad `Name` que se inicializa en el [constructor](../../programming-guide/classes-and-structs/constructors.md)`Vegetable`:

```csharp
public Vegetable(string name) => Name = name;
```

Luego se crea una instancia de la clase `Vegetable` denominada `item` al usar el [operador `new`](../../language-reference/operators/new-operator.md) y al proporcionar un parámetro de nombre para el constructor `Vegetable`:

```csharp
var item = new Vegetable("eggplant");
```

Por último, se incluye la variable `item` en una cadena interpolada que también contiene un valor <xref:System.DateTime>, un valor <xref:System.Decimal> y un valor de [enumeración](../../language-reference/builtin-types/enum.md)`Unit`. Reemplace todo el código de C# en el editor con el código siguiente y, después, use el comando `dotnet run` para ejecutarlo:

```csharp
using System;

public class Vegetable
{
   public Vegetable(string name) => Name = name;

   public string Name { get; }

   public override string ToString() => Name;
}

public class Program
{
   public enum Unit { item, kilogram, gram, dozen };

   public static void Main()
   {
      var item = new Vegetable("eggplant");
      var date = DateTime.Now;
      var price = 1.99m;
      var unit = Unit.item;
      Console.WriteLine($"On {date}, the price of {item} was {price} per {unit}.");
   }
}
```

Observe que la expresión de interpolación `item` de la cadena interpolada se resuelve en el texto "eggplant" en la cadena de resultado. Esto se debe a que, cuando el tipo del resultado de la expresión no es una cadena, el resultado se resuelve en una cadena de la siguiente manera:

- Si la expresión de interpolación se evalúa en `null`, se usa una cadena vacía ("", o <xref:System.String.Empty?displayProperty=nameWithType>).

- Si la expresión de interpolación no se evalúa en `null`, se suele llamar al método `ToString` del tipo de resultado. Puede probar esto mediante la actualización de la implementación del método `Vegetable.ToString`. Podría incluso no implementar el método `ToString`, puesto que cada tipo de datos tiene alguna implementación de este método. Para probar esto, comente la definición del método `Vegetable.ToString` del ejemplo (para ello, coloque delante un símbolo de comentario `//`). En el resultado, se reemplaza la cadena "eggplant" por el nombre del tipo completo ("Vegetable" en este ejemplo), que es el comportamiento predeterminado del método <xref:System.Object.ToString?displayProperty=nameWithType>. El comportamiento predeterminado del método `ToString` para un valor de enumeración es devolver la representación de cadena del valor.

En el resultado de este ejemplo, la fecha es demasiado precisa (el precio de "eggplant" no varía por segundos) y el valor del precio no indica una unidad de moneda. En la sección siguiente se aprende a corregir esos problemas al controlar el formato de representaciones de cadena de los resultados de la expresión.

## <a name="control-the-formatting-of-interpolation-expressions"></a>Control del formato de las expresiones de interpolación

En la sección anterior, las dos cadenas con formato incorrecto se insertaron en la cadena de resultado. Una era un valor de fecha y hora en la que solo la fecha era apropiada. La segunda era un precio que no indicaba su unidad de moneda. Ambos problemas se podían solucionar fácilmente. La interpolación de cadena permite especificar *cadenas de formato* que controlan el formato de tipos específicos. Modifique la llamada a `Console.WriteLine` del ejemplo anterior para incluir las cadenas de formato para las expresiones de fecha y precio, como se muestra en la siguiente línea:

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```

Especifique una cadena de formato al colocar dos puntos (":") después de la expresión de interpolación y la cadena de formato. "d" es una [cadena de formato de fecha y hora estándar](../../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) que representa el formato de fecha corta. "C2" es una [cadena de formato numérico estándar](../../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) que representa un número como un valor de moneda con dos dígitos después del separador decimal.

Una serie de tipos de las bibliotecas de .NET admiten un conjunto predefinido de cadenas de formato. Esto incluye todos los tipos numéricos y los tipos de fecha y hora. Para obtener una lista completa de los tipos que admiten cadenas de formato, vea [Dar formato a cadenas y tipos de biblioteca de clase .NET](../../../standard/base-types/formatting-types.md#format-strings-and-net-types) en el artículo [Aplicar formato a tipos de .NET](../../../standard/base-types/formatting-types.md).

Pruebe a modificar las cadenas de formato en el editor de texto y, cada vez que realice un cambio, vuelva a ejecutar el programa para ver cómo los cambios afectan al formato de fecha y hora y al valor numérico. Cambie "d" en `{date:d}` a "t" (para mostrar el formato de hora corta), "y" (para mostrar el año y el mes) y "yyyy" (para mostrar el año como un número de cuatro dígitos). Cambie "C2" en `{price:C2}` a "e" (para la notación exponencial) y "F3" (para un valor numérico con tres dígitos después del separador decimal).

Además de controlar el formato, también puede controlar el ancho de campo y la alineación de las cadenas con formato incluidas en la cadena de resultado. En la siguiente sección aprenderá a hacerlo.

## <a name="control-the-field-width-and-alignment-of-interpolation-expressions"></a>Control el ancho de campo y la alineación de expresiones de interpolación

Normalmente, cuando el resultado de una expresión de interpolación tiene formato de cadena, esa cadena se incluye en una cadena de resultado sin espacios iniciales ni finales. Especialmente cuando se trabaja con un conjunto de datos, poder controlar el ancho de un campo y la alineación del texto ayuda a generar una salida más legible. Para ver esto, reemplace todo el código en el editor de texto con el código siguiente, y luego escriba `dotnet run` para ejecutar el programa:

```csharp
using System;
using System.Collections.Generic;

public class Example
{
   public static void Main()
   {
      var titles = new Dictionary<string, string>()
      {
          ["Doyle, Arthur Conan"] = "Hound of the Baskervilles, The",
          ["London, Jack"] = "Call of the Wild, The",
          ["Shakespeare, William"] = "Tempest, The"
      };

      Console.WriteLine("Author and Title List");
      Console.WriteLine();
      Console.WriteLine($"|{"Author",-25}|{"Title",30}|");
      foreach (var title in titles)
         Console.WriteLine($"|{title.Key,-25}|{title.Value,30}|");
   }
}
```

Los nombres de los autores están alineados a la izquierda y los títulos que escribieron están alineados a la derecha. Para especificar la alineación, se agrega una coma (",") después de una expresión de interpolación y se designa el ancho de campo *mínimo*. Si el valor especificado es un número positivo, el campo se alinea a la derecha. Si es un número negativo, el campo se alinea a la izquierda.

Pruebe a quitar el signo negativo del código `{"Author",-25}` y `{title.Key,-25}`, y vuelva a ejecutar el ejemplo, como hace este código:

```csharp
Console.WriteLine($"|{"Author",25}|{"Title",30}|");
foreach (var title in titles)
   Console.WriteLine($"|{title.Key,25}|{title.Value,30}|");
```

Esta vez, la información del autor está alineada a la derecha.

Puede combinar un especificador de alineación y una cadena de formato en una única expresión de interpolación. Para ello, especifique primero la alineación, seguida de dos puntos y la cadena de formato. Reemplace todo el código dentro del método `Main` con el código siguiente, que muestra tres cadenas con formato con los anchos de campo definidos. Después, ejecute el programa escribiendo el comando `dotnet run`.

```csharp
Console.WriteLine($"[{DateTime.Now,-20:d}] Hour [{DateTime.Now,-10:HH}] [{1063.342,15:N2}] feet");
```

El resultado tiene un aspecto similar a este:

```console
[04/14/2018          ] Hour [16        ] [       1,063.34] feet
```

Ha completado el tutorial sobre interpolación de cadenas.

Para más información, vea el tema [Interpolación de cadenas](../../language-reference/tokens/interpolated.md) y el tutorial [Interpolación de cadenas en C#](../../tutorials/string-interpolation.md).
