---
title: 'Tutorial sobre cadenas interpoladas: guías de inicio rápido para entornos locales de C#'
description: En esta guía de inicio rápido sobre cadenas interpoladas, escribiremos código de C# para incluir el resultado de una expresión en una cadena mayor.
author: rpetrusha
ms.author: ronpet
ms.date: 01/11/2018
ms.topic: get-started-article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 1edd2b9f59d1933547c4152343f226a86ad90216
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="interpolated-strings"></a>Cadenas interpoladas

En esta guía de inicio rápido se muestra cómo usar cadenas interpoladas en C# para insertar valores en una cadena de salida única. Escriba código de C# y vea los resultados de la compilación y la ejecución. Esta guía de inicio rápido contiene una serie de lecciones para insertar valores en cadenas y dar formato a estos valores de maneras diferentes.

En esta guía de inicio rápido se supone que cuenta con una máquina que puede usar para el desarrollo. El tema de .NET [Iniciar en 10 minutos](https://www.microsoft.com/net/core) cuenta con instrucciones para configurar el entorno de desarrollo local en Mac, PC o Linux. En las [guías de inicio rápido de introducción al entorno local](local-environment.md) puede obtener información general sobre los comandos que usará con vínculos que amplían la información. 

## <a name="create-an-interpolated-string"></a>Crear una cadena interpolada

Cree un directorio denominado **interpolated-quickstart**. Conviértalo en el directorio actual y ejecute este comando desde una ventana de consola:

```console
dotnet new console -n interpolated -o .
```

Este comando crea una nueva aplicación de consola de .NET Core en el directorio actual.

Abra **Program.cs** en su editor favorito y reemplace la línea `Console.WriteLine("Hello World!");` por el código siguiente, teniendo en cuenta que debe reemplazar `<name>` con su nombre:

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```
Pruebe este código escribiendo `dotnet run` en la ventana de la consola. Al ejecutar el programa, se muestra una cadena única que incluye su nombre en el saludo. La cadena que se incluye en la llamada al método <xref:System.Console.WriteLine%2A> es una *cadena interpolada*. Es un tipo de plantilla que permite construir una sola cadena (denominada *cadena de resultado*) a partir de una cadena que incluye código incrustado. Las cadenas interpoladas son especialmente útiles para insertar valores en una cadena o en cadenas concatenadas (unidas entre sí). 
    
Este sencillo ejemplo contiene los dos elementos que debe tener cada cadena interpolada: 

- Un literal de cadena que empieza con el carácter `$` antes del carácter de comillas de apertura. No puede haber ningún espacio entre el símbolo `$` y el carácter de comillas. (Si quiere saber qué pasa si incluye una, inserte un espacio después del carácter `$`, guarde el archivo y vuelva a ejecutar el programa escribiendo `dotnet run` en la ventana de la consola. El compilador de C# muestra un mensaje de error: "error CS1056: carácter no esperado '$'"). 

- Una o varias *expresiones interpoladas*. Una expresión interpolada se indica mediante una llave de apertura y de cierre (`{` y `}`). Puede colocar cualquier expresión de C# que devuelva un valor (incluido `null`) dentro de las llaves. 

Probemos algunos ejemplos más de cadenas interpoladas con otros tipos de datos.
    
## <a name="include-different-data-types"></a>Incluir diferentes tipos de datos

En la sección anterior, se usó una cadena interpolada para insertar una cadena dentro de otra. Una expresión de cadena interpolada puede ser cualquier tipo de datos. Probemos una cadena interpolada que tiene valores de varios tipos de datos. 
    
En este ejemplo se incluyen expresiones interpoladas con un objeto `Vegetable`, un miembro de la enumeración `Unit`, un valor <xref:System.DateTime> y un valor <xref:System.Decimal>. Reemplace todo el código de C# en el editor con el código siguiente y, después, use el comando `console run` para ejecutarlo:

```csharp
using System;

public class Vegetable
{
   public Vegetable(string name) => Name = name;
   
   public string Name { get; }
   
   public override string ToString() => Name;
}

public class Example
{
   public enum Unit { item, pound, ounce, dozen };
   
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
    
Tenga en cuenta que la segunda expresión interpolada incluye el objeto `item` en la cadena de resultado que se muestra en la consola y, en este caso, la cadena "eggplant" se inserta en la cadena de resultado. La razón es que, cuando el tipo de una expresión interpolada no es una cadena, el compilador de C# hace lo siguiente:

- Si la expresión interpolada es `null`, la expresión interpolada devuelve una cadena vacía ("" o <xref:System.String.Empty?displayProperty=nameWithType>).

- Si la expresión interpolada no es `null`, se llama al método `ToString` del tipo de la expresión interpolada. Para probar esto, inserte un comentario en la definición del método `Vegetable.ToString` colocando delante de él un símbolo de comentario (`//`). En el resultado, se reemplaza la cadena "eggplant" por el tipo de nombre, "Vegetable", que es el comportamiento predeterminado del método <xref:System.Object.ToString?displayProperty=nameWithType>.   

En el resultado de este ejemplo, la fecha es demasiado precisa (el precio de "eggplant" no varía por segundos) y el valor del precio no indica una unidad de moneda. En la siguiente sección, aprenderá cómo corregir esos problemas controlando el formato de las cadenas devueltas por expresiones interpoladas.

## <a name="control-the-formatting-of-interpolated-expressions"></a>Controlar el formato de expresiones interpoladas

En la sección anterior, las dos cadenas con formato incorrecto se insertaron en la cadena de resultado. Una era un valor de fecha y hora en la que solo la fecha era apropiada. La segunda era un precio que no indicaba su unidad de moneda. Ambos problemas se podían solucionar fácilmente. Las expresiones interpoladas pueden incluir *cadenas de formato* que controlan el formato de tipos específicos. Modifique la llamada a `Console.WriteLine` desde el ejemplo anterior para incluir el especificador de formato para los campos de fecha y precio, tal y como se muestra en esta línea:

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```
    
Especifique una cadena de formato siguiendo la expresión interpolada con dos puntos y la cadena de formato. "d" es una [cadena de formato de fecha y hora estándar](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) que representa el formato de fecha corta. "C2" es una [cadena de formato numérico estándar](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) que representa un número como un valor de moneda con dos dígitos después del separador decimal.

Un determinado número de tipos en las bibliotecas de .NET Standard admite un conjunto predefinido de cadenas de formato. Esto incluye todos los tipos numéricos y los tipos de fecha y hora. Para obtener una lista completa de los tipos que admiten cadenas de formato, vea [Dar formato a cadenas y tipos de biblioteca de clase .NET](../../standard/base-types/formatting-types.md#stringRef) en el artículo [Aplicar formato a tipos de .NET](../../standard/base-types/formatting-types.md). Cualquier tipo puede admitir un conjunto de cadenas de formato y también puede desarrollar extensiones de formato personalizadas que proporcionan el formato personalizado para los tipos existentes. Para más información sobre el formato personalizado mediante una implementación de <xref:System.ICustomFormatter>, vea [Formato personalizado con ICustomFormatter](../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter) en el artículo [Aplicar formato a tipos de .NET](../../standard/base-types/formatting-types.md).

Pruebe a modificar las cadenas de formato en el editor de texto y, cada vez que realice un cambio, vuelva a ejecutar el programa para ver cómo los cambios afectan al formato de fecha y hora y al valor numérico. Cambie "d" en `{date:d}` a "t" (para mostrar el formato de hora corta), "y" (para mostrar el año y el mes) y "yyyy" (para mostrar el año como un número de cuatro dígitos). Cambie "C2" en `{price:C2}` a "e" (para la notación exponencial) y "F3" (para un valor numérico con tres dígitos después del separador decimal).

Además de controlar el formato, también puede controlar el ancho de campo y la alineación de las cadenas devueltas por una expresión interpolada. En la siguiente sección aprenderá a hacerlo.

## <a name="control-the-field-width-and-alignment-of-interpolated-expressions"></a>Controlar el ancho de campo y la alineación de expresiones interpoladas

Normalmente, cuando la cadena devuelta por una expresión interpolada se incluye en una cadena de resultado, no tiene espacios iniciales ni finales. Especialmente para instancias en las que se trabaja con un conjunto de datos, las expresiones interpoladas permiten especificar un ancho de campo y su alineación. Para ver esto, reemplace todo el código en el editor de texto con el código siguiente, y luego escriba `console run` para ejecutar el programa:
    
```csharp
using System;
using System.Collections.Generic;

public class Example
{
   public static void Main()
   {
      var titles = new Dictionary<string, string>();
      titles.Add("Doyle, Arthur Conan", "Hound of the Baskervilles, The");
      titles.Add("London, Jack", "Call of the Wild, The");
      titles.Add("Shakespeare, William", "Tempest, The");

      Console.WriteLine("Author and Title List");
      Console.WriteLine($"\n{"Author",-25}    {"Title",30}\n");
      foreach (var title in titles)
         Console.WriteLine($"{title.Key,-25}     {title.Value,30}");
   }
}
```
    
Los nombres de los autores están alineados a la izquierda y los títulos que escribieron están alineados a la derecha. Para especificar la alineación, se agrega una coma (",") después de la expresión y se designa el ancho de campo. Si el ancho de campo es un número positivo, el campo está alineado a la derecha:

```text
{expression, width}
```

Si el ancho de campo es un número negativo, el campo está alineado a la izquierda:

```text
{expression, -width}
```

Pruebe a quitar el signo negativo de las expresiones interpoladas `{"Author",-25}` y `{title.Key,-25}`, y vuelva a ejecutar el ejemplo, como hace este código:

```csharp
Console.WriteLine($"\n{"Author",25}    {"Title",30}\n");
foreach (var title in titles)
   Console.WriteLine($"{title.Key,25}     {title.Value,30}");
```

Esta vez, la información del autor está alineada a la derecha.

Puede combinar un ancho de campo y una cadena de formato en una única expresión interpolada. El ancho de campo se muestra primero, seguido de dos puntos y la cadena de formato. Reemplace todo el código dentro del método `Main` con el código siguiente, que muestra tres cadenas con formato con los anchos de campo definidos. Después, ejecute el programa escribiendo el comando `dotnet run`.

```csharp
Console.WriteLine($"{DateTime.Now,-20:d} Hour {DateTime.Now,-10:HH} {1063.342,15:N2} feet");
```
El resultado tiene un aspecto similar a este:

```console
1/11/2018            Hour 09                1,063.34 feet
```

Ha completado el inicio rápido sobre cadenas interpoladas. 
    
Puede continuar con la guía de inicio rápido [Matrices y colecciones](arrays-and-collections.md) en su propio entorno de desarrollo.

Para aprender más sobre cadenas interpoladas, eche un vistazo al tema [Interpolación de cadenas](../language-reference/tokens/interpolated.md) en la referencia de C#.
