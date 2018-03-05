---
title: "Tutorial sobre cadenas interpoladas: guías de inicio rápido para entornos locales de C#"
description: "En esta guía de inicio rápido sobre cadenas interpoladas, escribiremos código de C# para incluir el resultado de una expresión en una cadena mayor."
author: rpetrusha
ms.author: ronpet
ms.date: 01/11/2018
ms.topic: get-started-article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: b6089b69eb350fce29f86f19f5abeb44acb4b6b4
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2018
---
# <a name="interpolated-strings"></a><span data-ttu-id="1b235-103">Cadenas interpoladas</span><span class="sxs-lookup"><span data-stu-id="1b235-103">Interpolated strings</span></span>

<span data-ttu-id="1b235-104">En esta guía de inicio rápido se muestra cómo usar cadenas interpoladas en C# para insertar valores en una cadena de salida única.</span><span class="sxs-lookup"><span data-stu-id="1b235-104">This quickstart teaches you how to use interpolated strings in C# to insert values into a single ouput string.</span></span> <span data-ttu-id="1b235-105">Escriba código de C# y vea los resultados de la compilación y la ejecución.</span><span class="sxs-lookup"><span data-stu-id="1b235-105">You write C# code and see the results of compiling and running it.</span></span> <span data-ttu-id="1b235-106">Esta guía de inicio rápido contiene una serie de lecciones para insertar valores en cadenas y dar formato a estos valores de maneras diferentes.</span><span class="sxs-lookup"><span data-stu-id="1b235-106">The quickstart contains a series of lessons that insert values into strings, and format those values in different ways.</span></span>

<span data-ttu-id="1b235-107">En esta guía de inicio rápido se supone que cuenta con una máquina que puede usar para el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="1b235-107">This quickstart expects that you have a machine you can use for development.</span></span> <span data-ttu-id="1b235-108">El tema de .NET [Iniciar en 10 minutos](https://www.microsoft.com/net/core) cuenta con instrucciones para configurar el entorno de desarrollo local en Mac, PC o Linux.</span><span class="sxs-lookup"><span data-stu-id="1b235-108">The .NET topic [Get Started in 10 minutes](https://www.microsoft.com/net/core) has instructions for setting up your local development environment on Mac, PC or Linux.</span></span> <span data-ttu-id="1b235-109">En las [guías de inicio rápido de introducción al entorno local](local-environment.md) puede obtener información general sobre los comandos que usará con vínculos que amplían la información.</span><span class="sxs-lookup"><span data-stu-id="1b235-109">A quick overview of the commands you'll use is in the [introduction to the local quickstarts](local-environment.md) with links to more details.</span></span> 

## <a name="create-an-interpolated-string"></a><span data-ttu-id="1b235-110">Crear una cadena interpolada</span><span class="sxs-lookup"><span data-stu-id="1b235-110">Create an interpolated string</span></span>

<span data-ttu-id="1b235-111">Cree un directorio denominado **interpolated-quickstart**.</span><span class="sxs-lookup"><span data-stu-id="1b235-111">Create a directory named **interpolated-quickstart**.</span></span> <span data-ttu-id="1b235-112">Conviértalo en el directorio actual y ejecute este comando desde una ventana de consola:</span><span class="sxs-lookup"><span data-stu-id="1b235-112">Make it the current directory and run the following command from a console window:</span></span>

```console
dotnet new console -n interpolated -o .
```

<span data-ttu-id="1b235-113">Este comando crea una nueva aplicación de consola de .NET Core en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="1b235-113">This command creates a new .NET Core console application in the current directory.</span></span>

<span data-ttu-id="1b235-114">Abra **Program.cs** en su editor favorito y reemplace la línea `Console.WriteLine("Hello World!");` por el código siguiente, teniendo en cuenta que debe reemplazar `<name>` con su nombre:</span><span class="sxs-lookup"><span data-stu-id="1b235-114">Open **Program.cs** in your favorite editor, and replace the line `Console.WriteLine("Hello World!");` with the following code, where you replace `<name>` with your name:</span></span>

```csharp
var name = "<name>";
Console.WriteLine($"Hello, {name}. It's a pleasure to meet you!");
```
<span data-ttu-id="1b235-115">Pruebe este código escribiendo `dotnet run` en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="1b235-115">Try this code by typing `dotnet run` in your console window.</span></span> <span data-ttu-id="1b235-116">Al ejecutar el programa, se muestra una cadena única que incluye su nombre en el saludo.</span><span class="sxs-lookup"><span data-stu-id="1b235-116">When you run the program, it displays a single string that includes your name in the greeting.</span></span> <span data-ttu-id="1b235-117">La cadena que se incluye en la llamada al método <xref:System.Console.WriteLine%2A> es una *cadena interpolada*.</span><span class="sxs-lookup"><span data-stu-id="1b235-117">The string included in the <xref:System.Console.WriteLine%2A> method call is an *interpolated string*.</span></span> <span data-ttu-id="1b235-118">Es un tipo de plantilla que permite construir una sola cadena (denominada *cadena de resultado*) a partir de una cadena que incluye código incrustado.</span><span class="sxs-lookup"><span data-stu-id="1b235-118">It's a kind of template that lets you construct a single string (called the *result string*) from a string that includes embedded code.</span></span> <span data-ttu-id="1b235-119">Las cadenas interpoladas son especialmente útiles para insertar valores en una cadena o en cadenas concatenadas (unidas entre sí).</span><span class="sxs-lookup"><span data-stu-id="1b235-119">Interpolated strings are particularly useful for inserting values into a string or concatenating (joining together) strings.</span></span> 
    
<span data-ttu-id="1b235-120">Este sencillo ejemplo contiene los dos elementos que debe tener cada cadena interpolada:</span><span class="sxs-lookup"><span data-stu-id="1b235-120">This simple example contains the two elements that every interpolated string must have:</span></span> 

- <span data-ttu-id="1b235-121">Un literal de cadena que empieza con el carácter `$` antes del carácter de comillas de apertura.</span><span class="sxs-lookup"><span data-stu-id="1b235-121">A string literal that begins with the `$` character before its opening quotation mark character.</span></span> <span data-ttu-id="1b235-122">No puede haber ningún espacio entre el símbolo `$` y el carácter de comillas.</span><span class="sxs-lookup"><span data-stu-id="1b235-122">There can't be any spaces between the `$` symbol and the quotation mark character.</span></span> <span data-ttu-id="1b235-123">(Si quiere saber qué pasa si incluye una, inserte un espacio después del carácter `$`, guarde el archivo y vuelva a ejecutar el programa escribiendo `dotnet run` en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="1b235-123">(If you'd like to see what happens if you include one, insert a space after the `$` character, save the file, and run the program again by typing `dotnet run` in the console window.</span></span> <span data-ttu-id="1b235-124">El compilador de C# muestra un mensaje de error: "error CS1056: carácter no esperado '$'").</span><span class="sxs-lookup"><span data-stu-id="1b235-124">The C# compiler displays an error message, "error CS1056: Unexpected character '$'".)</span></span> 

- <span data-ttu-id="1b235-125">Una o varias *expresiones interpoladas*.</span><span class="sxs-lookup"><span data-stu-id="1b235-125">One or more *interpolated expressions*.</span></span> <span data-ttu-id="1b235-126">Una expresión interpolada se indica mediante una llave de apertura y de cierre (`{` y `}`).</span><span class="sxs-lookup"><span data-stu-id="1b235-126">An interpolated expression is indicated by an opening and closing brace (`{` and `}`).</span></span> <span data-ttu-id="1b235-127">Puede colocar cualquier expresión de C# que devuelva un valor (incluido `null`) dentro de las llaves.</span><span class="sxs-lookup"><span data-stu-id="1b235-127">You can put any C# expression that returns a value (including `null`) inside the braces.</span></span> 

<span data-ttu-id="1b235-128">Probemos algunos ejemplos más de cadenas interpoladas con otros tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="1b235-128">Let's try a few more interpolated string examples with some other data types.</span></span>
    
## <a name="include-different-data-types"></a><span data-ttu-id="1b235-129">Incluir diferentes tipos de datos</span><span class="sxs-lookup"><span data-stu-id="1b235-129">Include different data types</span></span>

<span data-ttu-id="1b235-130">En la sección anterior, se usó una cadena interpolada para insertar una cadena dentro de otra.</span><span class="sxs-lookup"><span data-stu-id="1b235-130">In the previous section, you used an interpolated string to insert one string inside of another.</span></span> <span data-ttu-id="1b235-131">Una expresión de cadena interpolada puede ser cualquier tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="1b235-131">An interpolated string expression can be any data type, though.</span></span> <span data-ttu-id="1b235-132">Probemos una cadena interpolada que tiene valores de varios tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="1b235-132">Let's try an interpolated string that has values of multiple data types.</span></span> 
    
<span data-ttu-id="1b235-133">En este ejemplo se incluyen expresiones interpoladas con un objeto `Vegetable`, un miembro de la enumeración `Unit`, un valor <xref:System.DateTime> y un valor <xref:System.Decimal>.</span><span class="sxs-lookup"><span data-stu-id="1b235-133">The following example includes interpolated expressions with a `Vegetable` object, a member of the `Unit` enumeration, a <xref:System.DateTime> value, and a <xref:System.Decimal> value.</span></span> <span data-ttu-id="1b235-134">Reemplace todo el código de C# en el editor con el código siguiente y, después, use el comando `console run` para ejecutarlo:</span><span class="sxs-lookup"><span data-stu-id="1b235-134">Replace all of the C# code in your editor with the following code, and then use the `console run` command to run it:</span></span>

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
    
<span data-ttu-id="1b235-135">Tenga en cuenta que la segunda expresión interpolada incluye el objeto `item` en la cadena de resultado que se muestra en la consola y, en este caso, la cadena "eggplant" se inserta en la cadena de resultado.</span><span class="sxs-lookup"><span data-stu-id="1b235-135">Note that the second interpolated expression includes the `item` object in the result string that's displayed to the console, and in this case the string "eggplant" is inserted into the result string.</span></span> <span data-ttu-id="1b235-136">La razón es que, cuando el tipo de una expresión interpolada no es una cadena, el compilador de C# hace lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1b235-136">That's because, when the type of an interpolated expression is not a string, the C# compiler does the following:</span></span>

- <span data-ttu-id="1b235-137">Si la expresión interpolada es `null`, la expresión interpolada devuelve una cadena vacía ("" o <xref:System.String.Empty?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="1b235-137">If the interpolated expression is `null`, the interpolated expression returns an empty string ("", or <xref:System.String.Empty?displayProperty=nameWithType>).</span></span>

- <span data-ttu-id="1b235-138">Si la expresión interpolada no es `null`, se llama al método `ToString` del tipo de la expresión interpolada.</span><span class="sxs-lookup"><span data-stu-id="1b235-138">If the interpolated expression is not `null`, the `ToString` method of the type of the interpolated expression is called.</span></span> <span data-ttu-id="1b235-139">Para probar esto, inserte un comentario en la definición del método `Vegetable.ToString` colocando delante de él un símbolo de comentario (`//`).</span><span class="sxs-lookup"><span data-stu-id="1b235-139">You can test this by commenting out the definition of the `Vegetable.ToString` method in the example by putting a comment symbol (`//`) in front of it.</span></span> <span data-ttu-id="1b235-140">En el resultado, se reemplaza la cadena "eggplant" por el tipo de nombre, "Vegetable", que es el comportamiento predeterminado del método <xref:System.Object.ToString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1b235-140">In the output, the string "eggplant" is replaced by the type name, "Vegetable", which is the default behavior of the <xref:System.Object.ToString?displayProperty=nameWithType> method.</span></span>   

<span data-ttu-id="1b235-141">En el resultado de este ejemplo, la fecha es demasiado precisa (el precio de "eggplant" no varía por segundos) y el valor del precio no indica una unidad de moneda.</span><span class="sxs-lookup"><span data-stu-id="1b235-141">In the output from this example, the date is too precise (the price of eggplant does not vary by the second), and the price value doesn't indicate a unit of currency.</span></span> <span data-ttu-id="1b235-142">En la siguiente sección, aprenderá cómo corregir esos problemas controlando el formato de las cadenas devueltas por expresiones interpoladas.</span><span class="sxs-lookup"><span data-stu-id="1b235-142">In the next section, you'll learn how to fix those issues by controlling the format of strings returned by interpolated expressions.</span></span>

## <a name="control-the-formatting-of-interpolated-expressions"></a><span data-ttu-id="1b235-143">Controlar el formato de expresiones interpoladas</span><span class="sxs-lookup"><span data-stu-id="1b235-143">Control the formatting of interpolated expressions</span></span>

<span data-ttu-id="1b235-144">En la sección anterior, las dos cadenas con formato incorrecto se insertaron en la cadena de resultado.</span><span class="sxs-lookup"><span data-stu-id="1b235-144">In the previous section, two poorly formatted strings were inserted into the result string.</span></span> <span data-ttu-id="1b235-145">Una era un valor de fecha y hora en la que solo la fecha era apropiada.</span><span class="sxs-lookup"><span data-stu-id="1b235-145">One was a date and time value for which only the date was appropriate.</span></span> <span data-ttu-id="1b235-146">La segunda era un precio que no indicaba su unidad de moneda.</span><span class="sxs-lookup"><span data-stu-id="1b235-146">The second was a price that did not indicate its unit of currency.</span></span> <span data-ttu-id="1b235-147">Ambos problemas se podían solucionar fácilmente.</span><span class="sxs-lookup"><span data-stu-id="1b235-147">Both issues are easy to address.</span></span> <span data-ttu-id="1b235-148">Las expresiones interpoladas pueden incluir *cadenas de formato* que controlan el formato de tipos específicos.</span><span class="sxs-lookup"><span data-stu-id="1b235-148">Interpolated expressions can include *format strings* that control the formatting of particular types.</span></span> <span data-ttu-id="1b235-149">Modifique la llamada a `Console.WriteLine` desde el ejemplo anterior para incluir el especificador de formato para los campos de fecha y precio, tal y como se muestra en esta línea:</span><span class="sxs-lookup"><span data-stu-id="1b235-149">Modify the call to `Console.WriteLine` from the previous example to include the format specifier for the date and price fields as shown in the following line:</span></span>

```csharp
Console.WriteLine($"On {date:d}, the price of {item} was {price:C2} per {unit}.");
```
    
<span data-ttu-id="1b235-150">Especifique una cadena de formato siguiendo la expresión interpolada con dos puntos y la cadena de formato.</span><span class="sxs-lookup"><span data-stu-id="1b235-150">You specify a format string by following the interpolated expression with a colon and the format string.</span></span> <span data-ttu-id="1b235-151">"d" es una [cadena de formato de fecha y hora estándar](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) que representa el formato de fecha corta.</span><span class="sxs-lookup"><span data-stu-id="1b235-151">"d" is a [standard date and time format string](../../standard/base-types/standard-date-and-time-format-strings.md#the-short-date-d-format-specifier) that represents the short date format.</span></span> <span data-ttu-id="1b235-152">"C2" es una [cadena de formato numérico estándar](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) que representa un número como un valor de moneda con dos dígitos después del separador decimal.</span><span class="sxs-lookup"><span data-stu-id="1b235-152">"C2" is a  [standard numeric format string](../../standard/base-types/standard-numeric-format-strings.md#the-currency-c-format-specifier) that represents a number as a currency value with two digits after the decimal point.</span></span>

<span data-ttu-id="1b235-153">Un determinado número de tipos en las bibliotecas de .NET Standard admite un conjunto predefinido de cadenas de formato.</span><span class="sxs-lookup"><span data-stu-id="1b235-153">A number of types in the .NET Standard libraries support a predefined set of format strings.</span></span> <span data-ttu-id="1b235-154">Esto incluye todos los tipos numéricos y los tipos de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="1b235-154">These include all the numeric types and the date and time types.</span></span> <span data-ttu-id="1b235-155">Para obtener una lista completa de los tipos que admiten cadenas de formato, vea [Dar formato a cadenas y tipos de biblioteca de clase .NET](../../standard/base-types/formatting-types.md#stringRef) en el artículo [Aplicar formato a tipos de .NET](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="1b235-155">For a complete list of types that support format strings, see [Format Strings and .NET Class Library Types](../../standard/base-types/formatting-types.md#stringRef) in the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) article.</span></span> <span data-ttu-id="1b235-156">Cualquier tipo puede admitir un conjunto de cadenas de formato y también puede desarrollar extensiones de formato personalizadas que proporcionan el formato personalizado para los tipos existentes.</span><span class="sxs-lookup"><span data-stu-id="1b235-156">Any type can support a set of format strings, and you can also develop custom formatting extensions that provide custom formatting for existing types.</span></span> <span data-ttu-id="1b235-157">Para más información sobre el formato personalizado mediante una implementación de <xref:System.ICustomFormatter>, vea [Formato personalizado con ICustomFormatter](../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter) en el artículo [Aplicar formato a tipos de .NET](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="1b235-157">For information on custom formatting by providing an <xref:System.ICustomFormatter> implementation, see [Custom Formatting with ICustomFormatter](../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter) in the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) article.</span></span>

<span data-ttu-id="1b235-158">Pruebe a modificar las cadenas de formato en el editor de texto y, cada vez que realice un cambio, vuelva a ejecutar el programa para ver cómo los cambios afectan al formato de fecha y hora y al valor numérico.</span><span class="sxs-lookup"><span data-stu-id="1b235-158">Try modifying the format strings in your text editor and, each time you make a change, rerun the program to see how the changes affect the formatting of the date and time and the numeric value.</span></span> <span data-ttu-id="1b235-159">Cambie "d" en `{date:d}` a "t" (para mostrar el formato de hora corta), "y" (para mostrar el año y el mes) y "yyyy" (para mostrar el año como un número de cuatro dígitos).</span><span class="sxs-lookup"><span data-stu-id="1b235-159">Change the "d" in `{date:d}` to "t" (to display the short time format), "y" (to display the year and month), and "yyyy" (to display the year as a four-digit number).</span></span> <span data-ttu-id="1b235-160">Cambie "C2" en `{price:C2}` a "e" (para la notación exponencial) y "F3" (para un valor numérico con tres dígitos después del separador decimal).</span><span class="sxs-lookup"><span data-stu-id="1b235-160">Change the "C2" in `{price:C2}` to "e" (for exponential notation) and "F3" (for a numeric value with three digits after the decimal point).</span></span>

<span data-ttu-id="1b235-161">Además de controlar el formato, también puede controlar el ancho de campo y la alineación de las cadenas devueltas por una expresión interpolada.</span><span class="sxs-lookup"><span data-stu-id="1b235-161">In addition to controlling formatting, you can also control the field width and alignment of the strings returned by an interpolated expression.</span></span> <span data-ttu-id="1b235-162">En la siguiente sección aprenderá a hacerlo.</span><span class="sxs-lookup"><span data-stu-id="1b235-162">In the next section, you'll learn how to do this.</span></span>

## <a name="control-the-field-width-and-alignment-of-interpolated-expressions"></a><span data-ttu-id="1b235-163">Controlar el ancho de campo y la alineación de expresiones interpoladas</span><span class="sxs-lookup"><span data-stu-id="1b235-163">Control the field width and alignment of interpolated expressions</span></span>

<span data-ttu-id="1b235-164">Normalmente, cuando la cadena devuelta por una expresión interpolada se incluye en una cadena de resultado, no tiene espacios iniciales ni finales.</span><span class="sxs-lookup"><span data-stu-id="1b235-164">Ordinarily, when the string returned by an interpolated expression is included in a result string, it has no leading or trailing spaces.</span></span> <span data-ttu-id="1b235-165">Especialmente para instancias en las que se trabaja con un conjunto de datos, las expresiones interpoladas permiten especificar un ancho de campo y su alineación.</span><span class="sxs-lookup"><span data-stu-id="1b235-165">Particularly for instances in which you are working with a set of data, interpolated expressions let you specify a field width and its alignment.</span></span> <span data-ttu-id="1b235-166">Para ver esto, reemplace todo el código en el editor de texto con el código siguiente, y luego escriba `console run` para ejecutar el programa:</span><span class="sxs-lookup"><span data-stu-id="1b235-166">To see this, replace all the code in your text editor with the following code, then type `console run` to execute the program:</span></span>
    
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
    
<span data-ttu-id="1b235-167">Los nombres de los autores están alineados a la izquierda y los títulos que escribieron están alineados a la derecha.</span><span class="sxs-lookup"><span data-stu-id="1b235-167">The names of authors are left-aligned, and the titles they wrote are right-aligned.</span></span> <span data-ttu-id="1b235-168">Para especificar la alineación, se agrega una coma (",") después de la expresión y se designa el ancho de campo.</span><span class="sxs-lookup"><span data-stu-id="1b235-168">You specify the alignment by adding a comma (",") after the expression and designating the field width.</span></span> <span data-ttu-id="1b235-169">Si el ancho de campo es un número positivo, el campo está alineado a la derecha:</span><span class="sxs-lookup"><span data-stu-id="1b235-169">If the field width is a positive number, the field is right-aligned:</span></span>

```text
{expression, width}
```

<span data-ttu-id="1b235-170">Si el ancho de campo es un número negativo, el campo está alineado a la izquierda:</span><span class="sxs-lookup"><span data-stu-id="1b235-170">If the field width is a negative number, the field is left-aligned:</span></span>

```text
{expression, -width}
```

<span data-ttu-id="1b235-171">Pruebe a quitar el signo negativo de las expresiones interpoladas `{"Author",-25}` y `{title.Key,-25}`, y vuelva a ejecutar el ejemplo, como hace este código:</span><span class="sxs-lookup"><span data-stu-id="1b235-171">Try removing the negative signs from the `{"Author",-25}` and `{title.Key,-25}` interpolated expressions and run the example again, as the following code does:</span></span>

```csharp
Console.WriteLine($"\n{"Author",25}    {"Title",30}\n");
foreach (var title in titles)
   Console.WriteLine($"{title.Key,25}     {title.Value,30}");
```

<span data-ttu-id="1b235-172">Esta vez, la información del autor está alineada a la derecha.</span><span class="sxs-lookup"><span data-stu-id="1b235-172">This time, the author information is right-aligned.</span></span>

<span data-ttu-id="1b235-173">Puede combinar un ancho de campo y una cadena de formato en una única expresión interpolada.</span><span class="sxs-lookup"><span data-stu-id="1b235-173">You can combine a field width and a format string in a single interpolated expression.</span></span> <span data-ttu-id="1b235-174">El ancho de campo se muestra primero, seguido de dos puntos y la cadena de formato.</span><span class="sxs-lookup"><span data-stu-id="1b235-174">The field width comes first, followed by a colon and the format string.</span></span> <span data-ttu-id="1b235-175">Reemplace todo el código dentro del método `Main` con el código siguiente, que muestra tres cadenas con formato con los anchos de campo definidos.</span><span class="sxs-lookup"><span data-stu-id="1b235-175">Replace all of the code inside the `Main` method with the following code, which displays three formatted strings with defined field widths.</span></span> <span data-ttu-id="1b235-176">Después, ejecute el programa escribiendo el comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="1b235-176">Then run the program by entering the `dotnet run` command.</span></span>

```csharp
Console.WriteLine($"{DateTime.Now,-20:d} Hour {DateTime.Now,-10:HH} {1063.342,15:N2} feet");
```
<span data-ttu-id="1b235-177">El resultado tiene un aspecto similar a este:</span><span class="sxs-lookup"><span data-stu-id="1b235-177">The output looks something like the following:</span></span>

```console
1/11/2018            Hour 09                1,063.34 feet
```

<span data-ttu-id="1b235-178">Ha completado el inicio rápido sobre cadenas interpoladas.</span><span class="sxs-lookup"><span data-stu-id="1b235-178">You've completed the interpolated strings quickstart.</span></span> 
    
<span data-ttu-id="1b235-179">Puede continuar con la guía de inicio rápido [Matrices y colecciones](arrays-and-collections.md) en su propio entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="1b235-179">You can continue with the [Arrays and collections](arrays-and-collections.md) quickstart in your own development environment.</span></span>

<span data-ttu-id="1b235-180">Para aprender más sobre cómo trabajar con cadenas interpoladas, eche un vistazo al tema [Cadenas interpoladas](../language-reference/keywords/interpolated-strings.md) en la referencia de C#.</span><span class="sxs-lookup"><span data-stu-id="1b235-180">You can learn more about working with interpolated strings in the [Interpolated Strings](../language-reference/keywords/interpolated-strings.md) topic in the C# Reference.</span></span>

