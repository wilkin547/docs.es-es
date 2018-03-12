---
title: "Interpolación de cadenas: C#"
description: "Aprenda cómo funciona la interpolación de cadenas en C# 6."
keywords: .NET, .NET Core, C#, cadena
author: mgroves
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f8806f6b-3ac7-4ee6-9b3e-c524d5301ae9
ms.openlocfilehash: db062ed2f832ae933941da1c49e84303090f4390
ms.sourcegitcommit: 3a96c706e4dbb4667bf3bf37edac9e1666646f93
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2018
---
# <a name="string-interpolation-in-c"></a><span data-ttu-id="86714-104">Interpolación de cadenas en C#</span><span class="sxs-lookup"><span data-stu-id="86714-104">String Interpolation in C#</span></span> #

<span data-ttu-id="86714-105">La interpolación de cadenas es la forma en que los marcadores de posición de una cadena se reemplazan por el valor de una variable de cadena.</span><span class="sxs-lookup"><span data-stu-id="86714-105">String Interpolation is the way that placeholders in a string are replaced by the value of a string variable.</span></span> <span data-ttu-id="86714-106">Antes de C# 6, la manera de hacerlo era con <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="86714-106">Before C# 6, the way to do this is with <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="86714-107">Aunque este sistema funciona bien, como se usan marcadores de posición numerados, puede ser más difícil de leer y más detallado.</span><span class="sxs-lookup"><span data-stu-id="86714-107">This works okay, but since it uses numbered placeholders, it can be harder to read and more verbose.</span></span>

<span data-ttu-id="86714-108">Durante un tiempo, otros lenguajes de programación tuvieron la interpolación de cadenas integrada.</span><span class="sxs-lookup"><span data-stu-id="86714-108">Other programming languages have had string interpolation built into the language for a while.</span></span> <span data-ttu-id="86714-109">Por ejemplo, en PHP:</span><span class="sxs-lookup"><span data-stu-id="86714-109">For instance, in PHP:</span></span>

```php
$name = "Jonas";
echo "My name is $name.";
// This will output "My name is Jonas."
```

<span data-ttu-id="86714-110">En C# 6, tenemos finalmente ese estilo de interpolación de cadenas.</span><span class="sxs-lookup"><span data-stu-id="86714-110">In C# 6, we finally have that style of string interpolation.</span></span> <span data-ttu-id="86714-111">Puede usar `$` delante de una cadena para indicar que se deben sustituir variables y expresiones por sus valores.</span><span class="sxs-lookup"><span data-stu-id="86714-111">You can use a `$` before a string to indicate that it should substitute variables/expressions for their values.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="86714-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="86714-112">Prerequisites</span></span>
<span data-ttu-id="86714-113">Deberá configurar la máquina para ejecutar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="86714-113">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="86714-114">Puede encontrar las instrucciones de instalación en la página de [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="86714-114">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="86714-115">Puede ejecutar esta aplicación en Windows, Ubuntu Linux, macOS o en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="86714-115">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="86714-116">Deberá instalar su editor de código favorito.</span><span class="sxs-lookup"><span data-stu-id="86714-116">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="86714-117">En las siguientes descripciones se usa [Visual Studio Code](https://code.visualstudio.com/), que es un editor multiplataforma de código abierto.</span><span class="sxs-lookup"><span data-stu-id="86714-117">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="86714-118">Sin embargo, puede usar las herramientas que le resulten más cómodas.</span><span class="sxs-lookup"><span data-stu-id="86714-118">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="86714-119">Crear la aplicación</span><span class="sxs-lookup"><span data-stu-id="86714-119">Create the Application</span></span>

<span data-ttu-id="86714-120">Ahora que ha instalado todas las herramientas, cree una nueva aplicación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="86714-120">Now that you've installed all the tools, create a new .NET Core application.</span></span> <span data-ttu-id="86714-121">Para usar el generador de línea de comandos, cree un directorio para el proyecto, como `interpolated`, y ejecute el siguiente comando en su shell favorito:</span><span class="sxs-lookup"><span data-stu-id="86714-121">To use the command line generator, create a directory for your project, such as `interpolated`, and execute the following command in your favorite shell:</span></span>

```
dotnet new console
```

<span data-ttu-id="86714-122">Este comando crea un proyecto de .NET Core esencial con un archivo de proyecto, *interpolated.csproj*, y un archivo de código fuente, *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="86714-122">This command creates a barebones .NET Core project with a project file, *interpolated.csproj*, and a source code file, *Program.cs*.</span></span> <span data-ttu-id="86714-123">Debe ejecutar `dotnet restore` para restaurar las dependencias necesarias para compilar este proyecto.</span><span class="sxs-lookup"><span data-stu-id="86714-123">You will need to execute `dotnet restore` to restore the dependencies needed to compile this project.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="86714-124">Para ejecutar el programa, use `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="86714-124">To execute the program, use `dotnet run`.</span></span> <span data-ttu-id="86714-125">Deberá ver la salida "Hola a todos" a la consola.</span><span class="sxs-lookup"><span data-stu-id="86714-125">You should see "Hello, World" output to the console.</span></span>



## <a name="intro-to-string-interpolation"></a><span data-ttu-id="86714-126">Introducción a la interpolación de cadenas</span><span class="sxs-lookup"><span data-stu-id="86714-126">Intro to String Interpolation</span></span>

<span data-ttu-id="86714-127">Con <xref:System.String.Format%2A?displayProperty=nameWithType>, se especifican "marcadores de posición" en una cadena que se reemplazan por los argumentos que siguen a la cadena.</span><span class="sxs-lookup"><span data-stu-id="86714-127">With <xref:System.String.Format%2A?displayProperty=nameWithType>, you specify "placeholders" in a string that are replaced by the arguments following the string.</span></span> <span data-ttu-id="86714-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="86714-128">For instance:</span></span>

[!code-csharp[String.Format example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]  

<span data-ttu-id="86714-129">El resultado será "My name is Matt Groves".</span><span class="sxs-lookup"><span data-stu-id="86714-129">That will output "My name is Matt Groves".</span></span>

<span data-ttu-id="86714-130">En C# 6, en lugar de usar `String.Format`, se define una cadena interpolada colocando delante el símbolo `$` y luego usando las variables directamente en la cadena.</span><span class="sxs-lookup"><span data-stu-id="86714-130">In C# 6, instead of using `String.Format`, you define an interpolated string by prepending it with the `$` symbol, and then using the variables directly in the string.</span></span> <span data-ttu-id="86714-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="86714-131">For instance:</span></span>

[!code-csharp[Interpolation example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]  

<span data-ttu-id="86714-132">No tiene que usar solo variables.</span><span class="sxs-lookup"><span data-stu-id="86714-132">You don't have to use just variables.</span></span> <span data-ttu-id="86714-133">Puede usar cualquier expresión entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="86714-133">You can use any expression within the brackets.</span></span> <span data-ttu-id="86714-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="86714-134">For instance:</span></span>

[!code-csharp[Interpolation expression example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]  

<span data-ttu-id="86714-135">Cuya salida sería:</span><span class="sxs-lookup"><span data-stu-id="86714-135">Which would output:</span></span>

```
This is line number 1
This is line number 2
This is line number 3
This is line number 4
This is line number 5
```

## <a name="how-string-interpolation-works"></a><span data-ttu-id="86714-136">Cómo funciona la interpolación de cadenas</span><span class="sxs-lookup"><span data-stu-id="86714-136">How string interpolation works</span></span>

<span data-ttu-id="86714-137">En segundo plano, el compilador convierte esta sintaxis de interpolación de cadenas en `String.Format`.</span><span class="sxs-lookup"><span data-stu-id="86714-137">Behind the scenes, this string interpolation syntax is translated into `String.Format` by the compiler.</span></span> <span data-ttu-id="86714-138">Por lo tanto, puede hacer [lo mismo que ha hecho antes con `String.Format`](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="86714-138">So, you can do the [same type of stuff you've done before with `String.Format`](../../standard/base-types/formatting-types.md).</span></span>

<span data-ttu-id="86714-139">Por ejemplo, puede agregar relleno y formato numérico:</span><span class="sxs-lookup"><span data-stu-id="86714-139">For instance, you can add padding and numeric formatting:</span></span>

[!code-csharp[Interpolation formatting example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]  

<span data-ttu-id="86714-140">El comando anterior generaría la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="86714-140">The above would output something like:</span></span>

```
998        5,177.67
999        6,719.30
1000       9,910.61
1001       529.34
1002       1,349.86
1003       2,660.82
1004       6,227.77
```

<span data-ttu-id="86714-141">Si no se encuentra un nombre de variable, se genera un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="86714-141">If a variable name is not found, then a compile-time error is generated.</span></span>

<span data-ttu-id="86714-142">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="86714-142">For instance:</span></span>

```csharp
var animal = "fox";
var localizeMe = $"The {adj} brown {animal} jumped over the lazy {otheranimal}";
var adj = "quick";
Console.WriteLine(localizeMe);
```

<span data-ttu-id="86714-143">Si compila esto, obtiene errores:</span><span class="sxs-lookup"><span data-stu-id="86714-143">If you compile this, you get errors:</span></span>
 
* <span data-ttu-id="86714-144">`Cannot use local variable 'adj' before it is declared`: la variable `adj` no se ha declarado hasta *después* de la cadena interpolada.</span><span class="sxs-lookup"><span data-stu-id="86714-144">`Cannot use local variable 'adj' before it is declared` - the `adj` variable wasn't declared until *after* the interpolated string.</span></span>
* <span data-ttu-id="86714-145">`The name 'otheranimal' does not exist in the current context`: no se ha declarado ninguna variable `otheranimal`.</span><span class="sxs-lookup"><span data-stu-id="86714-145">`The name 'otheranimal' does not exist in the current context` - a variable called `otheranimal` was never even declared</span></span>

## <a name="localization-and-internationalization"></a><span data-ttu-id="86714-146">Internacionalización y localización</span><span class="sxs-lookup"><span data-stu-id="86714-146">Localization and Internationalization</span></span>

<span data-ttu-id="86714-147">Una cadena interpolada admite <xref:System.IFormattable?displayProperty=nameWithType> y <xref:System.FormattableString?displayProperty=nameWithType>, que pueden ser útiles para la internacionalización.</span><span class="sxs-lookup"><span data-stu-id="86714-147">An interpolated string supports <xref:System.IFormattable?displayProperty=nameWithType> and <xref:System.FormattableString?displayProperty=nameWithType>, which can be useful for internationalization.</span></span>

<span data-ttu-id="86714-148">De forma predeterminada, una cadena interpolada usa la referencia cultural actual.</span><span class="sxs-lookup"><span data-stu-id="86714-148">By default, an interpolated string uses the current culture.</span></span> <span data-ttu-id="86714-149">Para usar otra referencia cultural, convierta una cadena interpolada como `IFormattable`.</span><span class="sxs-lookup"><span data-stu-id="86714-149">To use a different culture, cast an interpolated string as `IFormattable`.</span></span> <span data-ttu-id="86714-150">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="86714-150">For instance:</span></span>

[!code-csharp[Interpolation internationalization example](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]  

## <a name="conclusion"></a><span data-ttu-id="86714-151">Conclusión</span><span class="sxs-lookup"><span data-stu-id="86714-151">Conclusion</span></span> 

<span data-ttu-id="86714-152">En este tutorial, aprendió a usar las características de interpolación de cadenas de C# 6.</span><span class="sxs-lookup"><span data-stu-id="86714-152">In this tutorial, you learned how to use string interpolation features of C# 6.</span></span> <span data-ttu-id="86714-153">Básicamente es una manera más concisa de escribir instrucciones `String.Format` simples, con algunas advertencias para usos más avanzados.</span><span class="sxs-lookup"><span data-stu-id="86714-153">It's basically a more concise way of writing simple `String.Format` statements, with some caveats for more advanced uses.</span></span> <span data-ttu-id="86714-154">Para obtener más información, vea el tema [Cadenas interpoladas](../../csharp//language-reference/keywords/interpolated-strings.md).</span><span class="sxs-lookup"><span data-stu-id="86714-154">For more information, see the [Interpolated Strings](../../csharp//language-reference/keywords/interpolated-strings.md) topic.</span></span>
