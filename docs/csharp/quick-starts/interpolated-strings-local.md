---
title: 'Tutorial sobre interpolación de cadenas: guías de inicio rápido para entornos locales de C#'
description: En esta guía de inicio rápido se muestra cómo usar la característica de interpolación de cadenas de C# para incluir resultados de expresión con formato en una cadena mayor.
author: rpetrusha
ms.author: ronpet
ms.date: 04/14/2018
ms.custom: mvc
ms.openlocfilehash: da111790ebbc299df16297650347045b9395a90f
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2018
ms.locfileid: "46580699"
---
# <a name="string-interpolation"></a><span data-ttu-id="05a15-103">Interpolación de cadenas</span><span class="sxs-lookup"><span data-stu-id="05a15-103">String interpolation</span></span>

<span data-ttu-id="05a15-104">En esta guía de inicio rápido se muestra cómo usar la [interpolación de cadenas](../language-reference/tokens/interpolated.md) de C# para insertar valores en una cadena de resultado única.</span><span class="sxs-lookup"><span data-stu-id="05a15-104">This quickstart teaches you how to use C# [string interpolation](../language-reference/tokens/interpolated.md) to insert values into a single result string.</span></span> <span data-ttu-id="05a15-105">Escriba código de C# y vea los resultados de la compilación y la ejecución.</span><span class="sxs-lookup"><span data-stu-id="05a15-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="05a15-106">Esta guía de inicio rápido contiene una serie de lecciones para mostrarle cómo insertar valores en una cadena y dar formato a estos valores de maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="05a15-106">The quickstart contains a series of lessons that show you how to insert values into a string and format those values in different ways.</span></span>

<span data-ttu-id="05a15-107">En esta guía de inicio rápido se supone que cuenta con una máquina que puede usar para el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="05a15-107">This quickstart expects that you have a machine you can use for development.</span></span> <span data-ttu-id="05a15-108">El tema de .NET [Iniciar en 10 minutos](https://www.microsoft.com/net/core) cuenta con instrucciones para configurar el entorno de desarrollo local en Mac, PC o Linux.</span><span class="sxs-lookup"><span data-stu-id="05a15-108">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="05a15-109">En las [guías de inicio rápido de introducción al entorno local](local-environment.md) puede obtener información general sobre los comandos que usará con vínculos que amplían la información.</span><span class="sxs-lookup"><span data-stu-id="05a15-109">A quick overview of the commands you'll use is in the [introduction to the local quickstarts](local-environment.md) with links to more details.</span></span> <span data-ttu-id="05a15-110">También puede completar la [versión interactiva](interpolated-strings.yml) de esta guía de inicio rápido en el explorador.</span><span class="sxs-lookup"><span data-stu-id="05a15-110">You also can complete the [interactive version](interpolated-strings.yml) of this quickstart in your browser.</span></span>

## <a name="create-an-interpolated-string"></a><span data-ttu-id="05a15-111">Crear una cadena interpolada</span><span class="sxs-lookup"><span data-stu-id="05a15-111">Create an interpolated string</span></span>

<span data-ttu-id="05a15-112">Cree un directorio denominado **interpolated**.</span><span class="sxs-lookup"><span data-stu-id="05a15-112">Create a directory named **interpolated**.</span></span> <span data-ttu-id="05a15-113">Conviértalo en el directorio actual y ejecute este comando desde una ventana de consola:</span><span class="sxs-lookup"><span data-stu-id="05a15-113">Make it the current directory and run the following command from a console window:</span></span>

```console
dotnet new console
```

<span data-ttu-id="05a15-114">Este comando crea una nueva aplicación de consola de .NET Core en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="05a15-114">This command creates a new .NET Core console application in the current directory.</span></span>

<span data-ttu-id="05a15-115">Abra **Program.cs** en su editor favorito y reemplace la línea `Console.WriteLine("Hello World!");` por el código siguiente, teniendo en cuenta que debe reemplazar `<name>` con su nombre:</span><span class="sxs-lookup"><span data-stu-id="05a15-115">Open **Program.cs** in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code, where you replace `<name>` with your name:</span></span>

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```

<span data-ttu-id="05a15-116">Pruebe este código escribiendo `dotnet run` en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="05a15-116">Try this code by typing `dotnet run` in your console window.</span></span> <span data-ttu-id="05a15-117">Al ejecutar el programa, se muestra una cadena única que incluye su nombre en el saludo.</span><span class="sxs-lookup"><span data-stu-id="05a15-117">When you run the program, it displays a single string that includes your name in the greeting.</span></span> <span data-ttu-id="05a15-118">La cadena que se incluye en la llamada al método <xref:System.Console.WriteLine%2A> es una *cadena interpolada*.</span><span class="sxs-lookup"><span data-stu-id="05a15-118">The string included in the <xref:System.Console.WriteLine%2A> method call is an *interpolated string*.</span></span> <span data-ttu-id="05a15-119">Es un tipo de plantilla que permite construir una sola cadena (denominada *cadena de resultado*) a partir de una cadena que incluye código incrustado.</span><span class="sxs-lookup"><span data-stu-id="05a15-119">It's a kind of template that lets you construct a single string (called the *result string*) from a string that includes embedded code.</span></span> <span data-ttu-id="05a15-120">Las cadenas interpoladas son especialmente útiles para insertar valores en una cadena o en cadenas concatenadas (unidas entre sí).</span><span class="sxs-lookup"><span data-stu-id="05a15-120">Interpolated strings are particularly useful for inserting values into a string or concatenating (joining together) strings.</span></span>

<span data-ttu-id="05a15-121">Este sencillo ejemplo contiene los dos elementos que debe tener cada cadena interpolada:</span><span class="sxs-lookup"><span data-stu-id="05a15-121">This simple example contains the two elements that every interpolated string must have:</span></span>

- <span data-ttu-id="05a15-122">Un literal de cadena que empieza con el carácter `$` antes del carácter de comillas de apertura.</span><span class="sxs-lookup"><span data-stu-id="05a15-122">A string literal that begins with the `$` character before its opening quotation mark character.</span></span> <span data-ttu-id="05a15-123">No puede haber ningún espacio entre el símbolo `$` y el carácter de comillas.</span><span class="sxs-lookup"><span data-stu-id="05a15-123">There can't be any spaces between the `$` symbol and the quotation mark character.</span></span> <span data-ttu-id="05a15-124">(Si quiere saber qué pasa si incluye una, inserte un espacio después del carácter `$`, guarde el archivo y vuelva a ejecutar el programa escribiendo `dotnet run` en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="05a15-124">(If you'd like to see what happens if you include one, insert a space after the `$` character, save the file, and run the program again by typing `dotnet run` in the console window.</span></span> <span data-ttu-id="05a15-125">El compilador de C# muestra un mensaje de error: "error CS1056: carácter no esperado '$'").</span><span class="sxs-lookup"><span data-stu-id="05a15-125">The C# compiler displays an error message, "error CS1056: Unexpected character '$'".)</span></span>

- <span data-ttu-id="05a15-126">Una o varias *expresiones interpoladas*.</span><span class="sxs-lookup"><span data-stu-id="05a15-126">One or more *interpolated expressions*.</span></span> <span data-ttu-id="05a15-127">Una expresión interpolada se indica mediante una llave de apertura y de cierre (`{` y `}`).</span><span class="sxs-lookup"><span data-stu-id="05a15-127">An interpolated expression is indicated by an opening and closing brace (`{` and `}`).</span></span> <span data-ttu-id="05a15-128">Puede colocar cualquier expresión de C# que devuelva un valor (incluido `null`) dentro de las llaves.</span><span class="sxs-lookup"><span data-stu-id="05a15-128">You can put any C# expression that returns a value (including `null`) inside the braces.</span></span>

<span data-ttu-id="05a15-129">Probemos algunos ejemplos más de interpolación de cadenas con otros tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="05a15-129">Let's try a few more string interpolation examples with some other data types.</span></span>

## <a name="include-different-data-types"></a><span data-ttu-id="05a15-130">Incluir diferentes tipos de datos</span><span class="sxs-lookup"><span data-stu-id="05a15-130">Include different data types</span></span>

<span data-ttu-id="05a15-131">En la sección anterior, se ha usado una interpolación de cadena para insertar una cadena dentro de otra,</span><span class="sxs-lookup"><span data-stu-id="05a15-131">In the previous section, you used string interpolation to insert one string inside of another.</span></span> <span data-ttu-id="05a15-132">pero el resultado de una expresión interpolada puede ser cualquier tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="05a15-132">The result of an interpolated expression can be of any data type, though.</span></span> <span data-ttu-id="05a15-133">Vamos a incluir valores de distintos tipos de datos en una cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="05a15-133">Let's include values of various data types in an interpolated string.</span></span>

<span data-ttu-id="05a15-134">En el ejemplo siguiente, en primer lugar se define un tipo de datos de [clase](../programming-guide/classes-and-structs/classes.md) `Vegetable` que tiene la [propiedad ](../properties.md) `Name` y el [método](../methods.md) `ToString` que [reemplaza](../language-reference/keywords/override.md) el comportamiento del método <xref:System.Object.ToString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="05a15-134">In the following example, first, we define a [class](../programming-guide/classes-and-structs/classes.md) data type `Vegetable` that has the `Name` [property](../properties.md) and the `ToString` [method](../methods.md), which [overrides](../language-reference/keywords/override.md) the behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="05a15-135">El [`public`modificador de acceso](../language-reference/keywords/public.md) pone ese método a disposición de cualquier código de cliente para obtener la representación de la cadena de una instancia de `Vegetable`.</span><span class="sxs-lookup"><span data-stu-id="05a15-135">The [`public` access modifier](../language-reference/keywords/public.md) makes that method available to any client code to get the string representation of a `Vegetable` instance.</span></span> <span data-ttu-id="05a15-136">En el ejemplo, el método `Vegetable.ToString` devuelve el valor de la propiedad `Name` que se inicializa en el [constructor](../programming-guide/classes-and-structs/constructors.md) `Vegetable`:</span><span class="sxs-lookup"><span data-stu-id="05a15-136">In the example the `Vegetable.ToString` method returns the value of the `Name` property that is initialized at the `Vegetable` [constructor](../programming-guide/classes-and-structs/constructors.md):</span></span>

```csharp
public Vegetable(string name) => Name = name;
```

<span data-ttu-id="05a15-137">Luego se crea una instancia de la clase `Vegetable` al usar la [`new`palabra clave](../language-reference/keywords/new-operator.md) y al proporcionar un parámetro de nombre para el constructor `Vegetable`:</span><span class="sxs-lookup"><span data-stu-id="05a15-137">Then we create an instance of the `Vegetable` class by using [`new` keyword](../language-reference/keywords/new-operator.md) and providing a name parameter for the constructor `Vegetable`:</span></span>

```csharp
var item = new Vegetable("eggplant");
```

<span data-ttu-id="05a15-138">Por último, se incluye la variable `item` en una cadena interpolada que también contiene un valor <xref:System.DateTime>, un valor <xref:System.Decimal> y un valor de [enumeración](../programming-guide/enumeration-types.md) `Unit`.</span><span class="sxs-lookup"><span data-stu-id="05a15-138">Finally, we include the `item` variable into an interpolated string that also contains a <xref:System.DateTime> value, a <xref:System.Decimal> value, and a `Unit` [enumeration](../programming-guide/enumeration-types.md) value.</span></span> <span data-ttu-id="05a15-139">Reemplace todo el código de C# en el editor con el código siguiente y, después, use el comando `dotnet run` para ejecutarlo:</span><span class="sxs-lookup"><span data-stu-id="05a15-139">Replace all of the C# code in your editor with the following code, and then use the `dotnet run` command to run it:</span></span>

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

<span data-ttu-id="05a15-140">Observe que la expresión interpolada `item` de la cadena interpolada se resuelve en el texto "eggplant" en la cadena de resultado.</span><span class="sxs-lookup"><span data-stu-id="05a15-140">Note that the interpolated expression `item` in the interpolated string resolves to the text "eggplant" in the result string.</span></span> <span data-ttu-id="05a15-141">Esto se debe a que, cuando el tipo del resultado de la expresión no es una cadena, el resultado se resuelve en una cadena de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="05a15-141">That's because, when the type of the expression result is not a string, the result is resolved to a string in the following way:</span></span>

- <span data-ttu-id="05a15-142">Si la expresión interpolada se evalúa en `null`, se usa una cadena vacía ("", o <xref:System.String.Empty?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="05a15-142">If the interpolated expression evaluates to `null`, an empty string ("", or <xref:System.String.Empty?displayProperty=nameWithType>) is used.</span></span>

- <span data-ttu-id="05a15-143">Si la expresión interpolada no se evalúa en `null`, se suele llamar al método `ToString` del tipo de resultado.</span><span class="sxs-lookup"><span data-stu-id="05a15-143">If the interpolated expression doesn't evaluate to `null`, typically the `ToString` method of the result type is called.</span></span> <span data-ttu-id="05a15-144">Puede probar esto mediante la actualización de la implementación del método `Vegetable.ToString`.</span><span class="sxs-lookup"><span data-stu-id="05a15-144">You can test this by updating the implementation of the `Vegetable.ToString` method.</span></span> <span data-ttu-id="05a15-145">Podría incluso no implementar el método `ToString`, puesto que cada tipo de datos tiene alguna implementación de este método.</span><span class="sxs-lookup"><span data-stu-id="05a15-145">You might not even need to implement the `ToString` method since every type has some implementation of this method.</span></span> <span data-ttu-id="05a15-146">Para probar esto, comente la definición del método `Vegetable.ToString` del ejemplo (para ello, coloque delante un símbolo de comentario `//`).</span><span class="sxs-lookup"><span data-stu-id="05a15-146">To test this, comment out the definition of the `Vegetable.ToString` method in the example (to do that, put a comment symbol, `//`, in front of it).</span></span> <span data-ttu-id="05a15-147">En el resultado, se reemplaza la cadena "eggplant" por el nombre del tipo completo ("Vegetable" en este ejemplo), que es el comportamiento predeterminado del método <xref:System.Object.ToString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="05a15-147">In the output, the string "eggplant" is replaced by the fully qualified type name ("Vegetable" in this example), which is the default behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="05a15-148">El comportamiento predeterminado del método `ToString` para un valor de enumeración es devolver la representación de cadena del valor.</span><span class="sxs-lookup"><span data-stu-id="05a15-148">The default behavior of the `ToString` method for an enumeration value is to return the string representation of the value.</span></span>

<span data-ttu-id="05a15-149">En el resultado de este ejemplo, la fecha es demasiado precisa (el precio de "eggplant" no varía por segundos) y el valor del precio no indica una unidad de moneda.</span><span class="sxs-lookup"><span data-stu-id="05a15-149">In the output from this example, the date is too precise (the price of eggplant doesn't change every second), and the price value doesn't indicate a unit of currency.</span></span> <span data-ttu-id="05a15-150">En la sección siguiente se aprende a corregir esos problemas al controlar el formato de representaciones de cadena de los resultados de la expresión.</span><span class="sxs-lookup"><span data-stu-id="05a15-150">In the next section, you'll learn how to fix those issues by controlling the format of string representations of the expression results.</span></span>

## <a name="control-the-formatting-of-interpolated-expressions"></a><span data-ttu-id="05a15-151">Controlar el formato de expresiones interpoladas</span><span class="sxs-lookup"><span data-stu-id="05a15-151">Control the formatting of interpolated expressions</span></span>

<span data-ttu-id="05a15-152">En la sección anterior, las dos cadenas con formato incorrecto se insertaron en la cadena de resultado.</span><span class="sxs-lookup"><span data-stu-id="05a15-152">In the previous section, two poorly formatted strings were inserted into the result string.</span></span> <span data-ttu-id="05a15-153">Una era un valor de fecha y hora en la que solo la fecha era apropiada.</span><span class="sxs-lookup"><span data-stu-id="05a15-153">One was a date and time value for which only the date was appropriate.</span></span> <span data-ttu-id="05a15-154">La segunda era un precio que no indicaba su unidad de moneda.</span><span class="sxs-lookup"><span data-stu-id="05a15-154">The second was a price that didn't indicate its unit of currency.</span></span> <span data-ttu-id="05a15-155">Ambos problemas se podían solucionar fácilmente.</span><span class="sxs-lookup"><span data-stu-id="05a15-155">Both issues are easy to address.</span></span> <span data-ttu-id="05a15-156">La interpolación de cadena permite especificar *cadenas de formato* que controlan el formato de tipos específicos.</span><span class="sxs-lookup"><span data-stu-id="05a15-156">String interpolation lets you specify *format strings* that control the formatting of particular types.</span></span> <span data-ttu-id="05a15-157">Modifique la llamada a `Console.WriteLine` del ejemplo anterior para incluir las cadenas de formato para las expresiones de fecha y precio, como se muestra en la siguiente línea:</span><span class="sxs-lookup"><span data-stu-id="05a15-157">Modify the call to `Console.WriteLine` from the previous example to include the format strings for the date and price expressions as shown in the following line:</span></span>

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```

<span data-ttu-id="05a15-158">Especifique una cadena de formato al colocar después de la expresión interpolada dos puntos (":") y la cadena de formato.</span><span class="sxs-lookup"><span data-stu-id="05a15-158">You specify a format string by following the interpolated expression with a colon (":") and the format string.</span></span> <span data-ttu-id="05a15-159">"d" es una [cadena de formato de fecha y hora estándar](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) que representa el formato de fecha corta.</span><span class="sxs-lookup"><span data-stu-id="05a15-159">"d" is a [standard date and time format string](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) that represents the short date format.</span></span> <span data-ttu-id="05a15-160">"C2" es una [cadena de formato numérico estándar](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) que representa un número como un valor de moneda con dos dígitos después del separador decimal.</span><span class="sxs-lookup"><span data-stu-id="05a15-160">"C2" is a  [standard numeric format string](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) that represents a number as a currency value with two digits after the decimal point.</span></span>

<span data-ttu-id="05a15-161">Una serie de tipos de las bibliotecas de .NET admiten un conjunto predefinido de cadenas de formato.</span><span class="sxs-lookup"><span data-stu-id="05a15-161">A number of types in the .NET libraries support a predefined set of format strings.</span></span> <span data-ttu-id="05a15-162">Esto incluye todos los tipos numéricos y los tipos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="05a15-162">These include all the numeric types and the date and time types.</span></span> <span data-ttu-id="05a15-163">Para obtener una lista completa de los tipos que admiten cadenas de formato, vea [Dar formato a cadenas y tipos de biblioteca de clase .NET](../../standard/base-types/formatting-types.md#stringRef) en el artículo [Aplicar formato a tipos de .NET](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="05a15-163">For a complete list of types that support format strings, see [Format Strings and .NET Class Library Types](../../standard/base-types/formatting-types.md#stringRef) in the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) article.</span></span>

<span data-ttu-id="05a15-164">Pruebe a modificar las cadenas de formato en el editor de texto y, cada vez que realice un cambio, vuelva a ejecutar el programa para ver cómo los cambios afectan al formato de fecha y hora y al valor numérico.</span><span class="sxs-lookup"><span data-stu-id="05a15-164">Try modifying the format strings in your text editor and, each time you make a change, rerun the program to see how the changes affect the formatting of the date and time and the numeric value.</span></span> <span data-ttu-id="05a15-165">Cambie "d" en `{date:d}` a "t" (para mostrar el formato de hora corta), "y" (para mostrar el año y el mes) y "yyyy" (para mostrar el año como un número de cuatro dígitos).</span><span class="sxs-lookup"><span data-stu-id="05a15-165">Change the "d" in `{date:d}` to "t" (to display the short time format), "y" (to display the year and month), and "yyyy" (to display the year as a four-digit number).</span></span> <span data-ttu-id="05a15-166">Cambie "C2" en `{price:C2}` a "e" (para la notación exponencial) y "F3" (para un valor numérico con tres dígitos después del separador decimal).</span><span class="sxs-lookup"><span data-stu-id="05a15-166">Change the "C2" in `{price:C2}` to "e" (for exponential notation) and "F3" (for a numeric value with three digits after the decimal point).</span></span>

<span data-ttu-id="05a15-167">Además de controlar el formato, también puede controlar el ancho de campo y la alineación de las cadenas con formato incluidas en la cadena de resultado.</span><span class="sxs-lookup"><span data-stu-id="05a15-167">In addition to controlling formatting, you can also control the field width and alignment of the formatted strings that are included in the result string.</span></span> <span data-ttu-id="05a15-168">En la siguiente sección aprenderá a hacerlo.</span><span class="sxs-lookup"><span data-stu-id="05a15-168">In the next section, you'll learn how to do this.</span></span>

## <a name="control-the-field-width-and-alignment-of-interpolated-expressions"></a><span data-ttu-id="05a15-169">Controlar el ancho de campo y la alineación de expresiones interpoladas</span><span class="sxs-lookup"><span data-stu-id="05a15-169">Control the field width and alignment of interpolated expressions</span></span>

<span data-ttu-id="05a15-170">Normalmente, cuando el resultado de una expresión interpolada tiene formato de cadena, esa cadena se incluye en una cadena de resultado sin espacios iniciales ni finales.</span><span class="sxs-lookup"><span data-stu-id="05a15-170">Ordinarily, when the result of an interpolated expression is formatted to string, that string is included in a result string without leading or trailing spaces.</span></span> <span data-ttu-id="05a15-171">Especialmente cuando se trabaja con un conjunto de datos, poder controlar el ancho de un campo y la alineación del texto ayuda a generar una salida más legible.</span><span class="sxs-lookup"><span data-stu-id="05a15-171">Particularly when you work with a set of data, being able to control a field width and text alignment helps to produce a more readable output.</span></span> <span data-ttu-id="05a15-172">Para ver esto, reemplace todo el código en el editor de texto con el código siguiente, y luego escriba `dotnet run` para ejecutar el programa:</span><span class="sxs-lookup"><span data-stu-id="05a15-172">To see this, replace all the code in your text editor with the following code, then type `dotnet run` to execute the program:</span></span>

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

<span data-ttu-id="05a15-173">Los nombres de los autores están alineados a la izquierda y los títulos que escribieron están alineados a la derecha.</span><span class="sxs-lookup"><span data-stu-id="05a15-173">The names of authors are left-aligned, and the titles they wrote are right-aligned.</span></span> <span data-ttu-id="05a15-174">Para especificar la alineación, se agrega una coma (",") después de una expresión interpolada y se designa el ancho de campo *mínimo*.</span><span class="sxs-lookup"><span data-stu-id="05a15-174">You specify the alignment by adding a comma (",") after an interpolated expression and designating the *minimum* field width.</span></span> <span data-ttu-id="05a15-175">Si el valor especificado es un número positivo, el campo se alinea a la derecha.</span><span class="sxs-lookup"><span data-stu-id="05a15-175">If the specified value is a positive number, the field is right-aligned.</span></span> <span data-ttu-id="05a15-176">Si es un número negativo, el campo se alinea a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="05a15-176">If it is a negative number, the field is left-aligned.</span></span>

<span data-ttu-id="05a15-177">Pruebe a quitar el signo negativo del código `{"Author",-25}` y `{title.Key,-25}`, y vuelva a ejecutar el ejemplo, como hace este código:</span><span class="sxs-lookup"><span data-stu-id="05a15-177">Try removing the negative signs from the `{"Author",-25}` and `{title.Key,-25}` code and run the example again, as the following code does:</span></span>

```csharp
Console.WriteLine($"|{"Author",25}|{"Title",30}|");
foreach (var title in titles)
   Console.WriteLine($"|{title.Key,25}|{title.Value,30}|");
```

<span data-ttu-id="05a15-178">Esta vez, la información del autor está alineada a la derecha.</span><span class="sxs-lookup"><span data-stu-id="05a15-178">This time, the author information is right-aligned.</span></span>

<span data-ttu-id="05a15-179">Puede combinar un especificador de alineación y una cadena de formato en una única expresión interpolada.</span><span class="sxs-lookup"><span data-stu-id="05a15-179">You can combine an alignment specifier and a format string for a single interpolated expression.</span></span> <span data-ttu-id="05a15-180">Para ello, especifique primero la alineación, seguida de dos puntos y la cadena de formato.</span><span class="sxs-lookup"><span data-stu-id="05a15-180">To do that, specify the alignment first, followed by a colon and the format string.</span></span> <span data-ttu-id="05a15-181">Reemplace todo el código dentro del método `Main` con el código siguiente, que muestra tres cadenas con formato con los anchos de campo definidos.</span><span class="sxs-lookup"><span data-stu-id="05a15-181">Replace all of the code inside the `Main` method with the following code, which displays three formatted strings with defined field widths.</span></span> <span data-ttu-id="05a15-182">Después, ejecute el programa escribiendo el comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="05a15-182">Then run the program by entering the `dotnet run` command.</span></span>

```csharp
Console.WriteLine($"[{DateTime.Now,-20:d}] Hour [{DateTime.Now,-10:HH}] [{1063.342,15:N2}] feet");
```

<span data-ttu-id="05a15-183">El resultado tiene un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="05a15-183">The output looks something like the following:</span></span>

```console
[04/14/2018          ] Hour [16        ] [       1,063.34] feet
```

<span data-ttu-id="05a15-184">Ha completado la guía de inicio rápido sobre interpolación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="05a15-184">You've completed the string interpolation quickstart.</span></span>

<span data-ttu-id="05a15-185">Puede continuar con la guía de inicio rápido [Colección de listas](arrays-and-collections.md) en su propio entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="05a15-185">You can continue with the [List collection](arrays-and-collections.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="05a15-186">Para más información, vea el tema [Interpolación de cadenas](../language-reference/tokens/interpolated.md) y el tutorial [Interpolación de cadenas en C#](../tutorials/string-interpolation.md).</span><span class="sxs-lookup"><span data-stu-id="05a15-186">For more information, see the [String interpolation](../language-reference/tokens/interpolated.md) topic and the [String interpolation in C#](../tutorials/string-interpolation.md) tutorial.</span></span>
