---
title: "Interpolación de cadenas: C# | Microsoft Docs"
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 4437ce5d344cf06d30e31911def6287999fc6ffc
ms.openlocfilehash: 8396be84d229563973011470d0333af017302dc9
ms.contentlocale: es-es
ms.lasthandoff: 06/12/2017

---

<a id="string-interpolation-in-c" class="xliff"></a>

# Interpolación de cadenas en C# #

La interpolación de cadenas es la forma en que los marcadores de posición de una cadena se reemplazan por el valor de una variable de cadena. Antes de C# 6, la manera de hacerlo era con `System.String.Format`. Aunque este sistema funciona bien, como se usan marcadores de posición numerados, puede ser más difícil de leer y más detallado.

Durante un tiempo, otros lenguajes de programación tuvieron la interpolación de cadenas integrada. Por ejemplo, en PHP:

```php
$name = "Jonas";
echo "My name is $name.";
// This will output "My name is Jonas."
```

En C# 6, tenemos finalmente ese estilo de interpolación de cadenas. Puede usar `$` delante de una cadena para indicar que se deben sustituir variables y expresiones por sus valores.

<a id="prerequisites" class="xliff"></a>

## Requisitos previos
Deberá configurar la máquina para ejecutar .NET Core. Puede encontrar las instrucciones de instalación en la página de [.NET Core](https://www.microsoft.com/net/core).
Puede ejecutar esta aplicación en Windows, Ubuntu Linux, macOS o en un contenedor de Docker. Deberá instalar su editor de código favorito. En las siguientes descripciones se usa [Visual Studio Code](https://code.visualstudio.com/), que es un editor multiplataforma de código abierto. Sin embargo, puede usar las herramientas que le resulten más cómodas.

<a id="create-the-application" class="xliff"></a>

## Crear la aplicación

Ahora que ha instalado todas las herramientas, cree una nueva aplicación de .NET Core. Para usar el generador de línea de comandos, cree un directorio para el proyecto, como `interpolated`, y ejecute el siguiente comando en su shell favorito:

```
dotnet new console
```

Este comando creará un proyecto de .NET Core esencial con un archivo de proyecto, *interpolated.csproj*, y un archivo de código fuente, *Program.cs*. Debe ejecutar `dotnet restore` para restaurar las dependencias necesarias para compilar este proyecto.

Para ejecutar el programa, use `dotnet run`. Deberá ver la salida "Hola a todos" a la consola.

<a id="intro-to-string-interpolation" class="xliff"></a>

## Introducción a la interpolación de cadenas

Con `System.String.Format`, se especifican "marcadores de posición" en una cadena que se reemplazan por los parámetros que siguen a la cadena. Por ejemplo:

[!code-csharp[Ejemplo de String.Format](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#StringFormatExample)]  

El resultado será "My name is Matt Groves".

En C# 6, en lugar de usar `String.Format`, se define una cadena interpolada colocando delante el símbolo `$` y luego usando las variables directamente en la cadena. Por ejemplo:

[!code-csharp[Ejemplo de interpolación](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExample)]  

No tiene que usar solo variables. Puede usar cualquier expresión entre corchetes. Por ejemplo:

[!code-csharp[Ejemplo de expresiones de interpolación](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationExpressionExample)]  

Cuya salida sería:

```
This is line number 1
This is line number 2
This is line number 3
This is line number 4
This is line number 5
```

<a id="how-string-interpolation-works" class="xliff"></a>

## Cómo funciona la interpolación de cadenas

En segundo plano, el compilador convierte esta sintaxis de interpolación de cadenas en String.Format. Por lo tanto, puede hacer [lo mismo que ha hecho antes con String.Format](https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx).

Por ejemplo, puede agregar relleno y formato numérico:

[!code-csharp[Ejemplo de formato de interpolación](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationFormattingExample)]  

El comando anterior generaría la siguiente salida:

```
998        5,177.67
999        6,719.30
1000       9,910.61
1001       529.34
1002       1,349.86
1003       2,660.82
1004       6,227.77
```

Si no se encuentra un nombre de variable, se generará un error en tiempo de compilación.

Por ejemplo:

```csharp
var animal = "fox";
var localizeMe = $"The {adj} brown {animal} jumped over the lazy {otheranimal}";
var adj = "quick";
Console.WriteLine(localizeMe);
```

Si compila esto, obtendrá errores:
 
* `Cannot use local variable 'adj' before it is declared` - the `adj` variable wasn't declared until *after* the interpolated string.
* `The name 'otheranimal' does not exist in the current context` - a variable called `otheranimal` was never even declared

<a id="localization-and-internationalization" class="xliff"></a>

## Internacionalización y localización

Una cadena interpolada admite `IFormattable` y `FormattableString`, que pueden ser útiles para la internacionalización.

De forma predeterminada, una cadena interpolada usa la referencia cultural actual. Para usar una referencia cultural diferente, puede convertirla a `IFormattable`.

Por ejemplo:

[!code-csharp[Ejemplo de internacionalización de interpolación](../../../samples/snippets/csharp/new-in-6/string-interpolation.cs#InterpolationInternationalizationExample)]  

<a id="conclusion" class="xliff"></a>

## Conclusión 

En este tutorial, aprendió a usar las características de interpolación de cadenas de C# 6. Básicamente es una manera más concisa de escribir instrucciones simples `String.Format`, con algunas advertencias para usos más avanzados de ellas.

