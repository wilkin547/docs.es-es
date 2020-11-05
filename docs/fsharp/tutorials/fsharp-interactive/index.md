---
title: Referencia sobre F# interactivo (dotnet)
description: Obtenga información sobre cómo se utiliza F# interactivo (dotnet fsi) para ejecutar código de F# de manera interactiva en la consola o para ejecutar scripts de F#.
ms.date: 10/31/2020
f1_keywords:
- VS.ToolsOptionsPages.F#_Tools.F#_Interactive
ms.openlocfilehash: 770ac24feababcfc840ae26196ba8b6180d378a0
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282016"
---
# <a name="interactive-programming-with-f"></a>Programación interactiva con F\#

F# interactivo (dotnet fsi) se utiliza para ejecutar código de F# de manera interactiva en la consola o para ejecutar scripts de F#. En otras palabras, F# Interactive ejecuta un bucle REPL (del inglés Read, Evaluate, Print Loop - bucle Leer, Evaluar, Imprimir) para el lenguaje F#.

Para ejecutar F# interactivo desde la consola, ejecute `dotnet fsi`. Encontrará `dotnet fsi` en cualquier SDK de .NET.

Para obtener más información sobre las opciones de línea de comandos disponibles, vea [Opciones de F# Interactive](../../language-reference/fsharp-interactive-options.md).

## <a name="executing-code-directly-in-f-interactive"></a>Ejecución del código directamente en F# interactivo

Dado que F# interactivo es un REPL (read–eval–print loop), puede ejecutar el código en él de forma interactiva. Este es un ejemplo de una sesión interactiva después de ejecutar `dotnet fsi` desde la línea de comandos:

```console
Microsoft (R) F# Interactive version 11.0.0.0 for F# 5.0
Copyright (c) Microsoft Corporation. All Rights Reserved.

For help type #help;;

> let square x = x *  x;;
val square : x:int -> int

> square 12;;
val it : int = 144

> printfn "Hello, FSI!"
- ;;
Hello, FSI!
val it : unit = ()
```

Observará dos cuestiones principales:

1. Todo el código debe terminar con un punto y coma doble (`;;`) para que se evalúe.
2. El código se evalúa y se almacena en un valor `it`. Puede hacer referencia a `it` de forma interactiva.

F# interactivo también admite la entrada de varias líneas. Solo tiene que terminar el envío con un punto y coma doble (`;;`). Observe el siguiente fragmento de código que se ha pegado en F# interactivo para su evaluación:

```console
> let getOddSquares xs =
-     xs
-     |> List.filter (fun x -> x % 2 <> 0)
-     |> List.map (fun x -> x * x)
-
- printfn "%A" (getOddSquares [1..10]);;
[1; 9; 25; 49; 81]
val getOddSquares : xs:int list -> int list
val it : unit = ()

>
```

Se conserva el formato del código, y la entrada termina con un punto y coma doble (`;;`). F# interactivo evaluó el código e imprimió los resultados.

## <a name="scripting-with-f"></a>Scripting con F\#

La evaluación del código de forma interactiva en F# interactivo puede ser una magnífica herramienta de aprendizaje, pero se dará cuenta rápidamente de que no es tan productivo como escribir código en un editor normal. Para admitir la edición normal de código, puede escribir scripts de F#.

Los scripts usan la extensión de archivo **.fsx**. En lugar de compilar el código fuente y después ejecutar el ensamblado compilado, se puede ejecutar simplemente **dotnet fsi** y especificar el nombre de archivo del script de código fuente de F#. F# interactivo lee el código y lo ejecuta en tiempo real. Por ejemplo, vamos a analizar el siguiente script llamado `Script.fsx`:

```fsharp
let getOddSquares xs =
    xs
    |> List.filter (fun x -> x % 2 <> 0)
    |> List.map (fun x -> x * x)

getOddSquares [1..10]
```

Cuando este archivo se crea en el equipo, puede ejecutarlo con `dotnet fsi` y ver la salida directamente en la ventana de terminal:

```console
dotnet fsi Script.fsx
[1; 9; 25; 49; 81]
```

El scripting de F# es compatible de forma nativa con [Visual Studio](../../get-started/get-started-visual-studio.md), [Visual Studio Code](../../get-started/get-started-vscode.md) y [Visual Studio para Mac](../../get-started/get-started-visual-studio-for-mac.md).

## <a name="referencing-packages-in-f-interactive"></a>Referencia a paquetes en F# interactivo

> [!NOTE] La administración de paquetes es una característica de F# 5 que está disponible actualmente con el último SDK de .NET 5.

F# interactivo permite hacer referencia a paquetes de NuGet con la sintaxis `#r "nuget:"` y una versión opcional:

```fsharp
#r "nuget: Newtonsoft.Json"
open Newtonsoft.Json

let data = {| Name = "Don Syme"; Occupation = "F# Creator" |}
JsonConvert.SerializeObject(data)
```

Si no se especifica ninguna versión, se usa el paquete más alto disponible que no se encuentra en versión preliminar. Para hacer referencia a una versión concreta, introduzca la versión con una coma. Esto puede ser útil cuando se hace referencia a una versión preliminar de un paquete. Por ejemplo, considere este script mediante una versión preliminar de [DiffSharp](https://diffsharp.github.io/):

```fsharp
#r "nuget: DiffSharp-lite,1.0.0-preview-328097867"
open DiffSharp

// A 1D tensor
let t1 = dsharp.tensor [ 0.0 .. 0.2 .. 1.0 ]

// A 2x2 tensor
let t2 = dsharp.tensor [ [ 0; 1 ]; [ 2; 2 ] ]

// Define a scalar-to-scalar function
let f (x: Tensor) = sin (sqrt x)

printfn "%A" (f (dsharp.tensor 1.2))
```

Puede especificar tantas referencias de paquete como desee en un script.

## <a name="referencing-assemblies-on-disk-with-f-interactive"></a>Referencias a ensamblados en el disco con F# interactivo

Como alternativa, si tiene un ensamblado en el disco y desea hacer referencia a él en un script, puede usar la sintaxis `#r` para especificar un ensamblado. Considere el siguiente código en un proyecto compilado en `MyAssembly.dll`:

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

Una vez compilado, puede hacer referencia a él en un archivo denominado `Script.fsx` similar al siguiente:

```fsharp
#r "path/to/MyAssembly.dll"

printfn "%A" (MyAssembly.myFunction 10 40)
```

La salida es como sigue:

```console
dotnet fsi Script.fsx
90
```

Puede especificar tantas referencias de ensamblado como desee en un script.

## <a name="loading-other-scripts"></a>Carga de otros scripts

Al crear scripts, a menudo puede ser útil usar diferentes scripts para distintas tareas. En ocasiones, es posible que desee volver a usar el código del script en otro. En lugar de copiar y pegar su contenido en el archivo, puede cargarlo y evaluarlo con `#load`.

Observe la sintaxis `Script1.fsx` siguiente:

```fsharp
let square x = x * x
```

Y también el uso del archivo `Script2.fsx`:

```fsharp
#load "Script1.fsx"
open Script1

printfn "%d" (square 12)
```

Tenga en cuenta que la declaración `open Script1` es obligatoria. Esto se debe a que las construcciones de un script de F# se compilan en un módulo de nivel superior cuyo nombre coincide con el del archivo de script en el que está incluido.

Puede evaluar `Script2.fsx` de una forma similar a la siguiente:

```console
dotnet fsi Script2.fsx
144
```

Puede especificar tantas directivas `#load` como desee en un script.

## <a name="using-the-fsi-object-in-f-code"></a>Uso del objeto `fsi` en el código de F#

Los scripts de F# tienen acceso a un objeto `fsi` personalizado que representa la sesión de F# interactivo. Permite personalizar aspectos como el formato de la salida. También define la forma de acceder a los argumentos de la línea de comandos.

En el ejemplo siguiente se muestra cómo usar argumentos de la línea de comandos y la forma de acceder a ellos:

```fsharp
let args = fsi.CommandLineArgs

for arg in args do
    printfn "%s" arg
```

Cuando se evalúa, imprime todos los argumentos. El primer argumento siempre es el nombre del script que se evalúa:

```dotnet
dotnet fsi Script1.fsx hello world from fsi
Script1.fsx
hello
world
from
fsi
```

Tenga en cuenta que también puede utilizar `System.Environment.GetCommandLineArgs()` para acceder a los mismos argumentos.

## <a name="f-interactive-directive-reference"></a>Referencia a directivas de F# interactivo

Las directivas `#r` y `#load` abordadas anteriormente solo están disponibles en F# interactivo. Hay varias directivas que solo están disponibles en F# interactivo:

|Directiva|Descripción|
|---------|-----------|
|`#r "nuget:..."`|Hace referencia a un paquete de NuGet|
|`#r "assembly-name.dll"`|Hace referencia a un ensamblado del disco|
|`#load "file-name.fsx"`|Lee un archivo de código fuente, lo compila y lo ejecuta.|
|`#help`|Muestra información sobre las directivas disponibles.|
|`#I`|Especifica una ruta de búsqueda de ensamblado entre comillas.|
|`#quit`|Termina una sesión de F# Interactive.|
|`#time "on"` o `#time "off"`|Por sí solo, `#time` activa y desactiva la presentación de información sobre el rendimiento. Si el valor es `"on"`, F# interactivo mide el tiempo real, el tiempo de CPU y la información sobre recolección de elementos no utilizados que se interpreta y ejecuta.|

Al especificar los archivos o rutas de acceso en F# Interactive, se espera un literal de cadena. Por tanto, los archivos y las rutas de acceso deben estar entre comillas y se aplicarán los caracteres de escape habituales. Puede usar el carácter `@` para conseguir que F# interactivo interprete una cadena que contenga una ruta de acceso como una cadena textual. Esto hace que F# Interactive pase por alto cualquier carácter de escape.

## <a name="interactive-and-compiled-preprocessor-directives"></a>Directivas de preprocesador compiladas e interactivas

Al compilar código en F# interactivo, tanto si se ejecuta de forma interactiva como si ejecuta un script, se define el símbolo **INTERACTIVE**. Al compilar código en el compilador, se define el símbolo **COMPILED**. Por consiguiente, si el código debe ser diferente en modo interactivo y en modo compilado, se pueden usar estas directivas de preprocesador de la compilación condicional para determinar cuál se va a usar. Por ejemplo:

```fsharp
#if INTERACTIVE
// Some code that executes only in FSI
// ...
#endif
```

## <a name="using-f-interactive-in-visual-studio"></a>Uso de F# interactivo en Visual Studio

Para ejecutar F# Interactive a través de Visual Studio, puede hacer clic en el botón **F# Interactive** de la barra de herramientas o presionar las teclas **Ctrl+Alt+F**. De este modo, se abrirá la ventana interactiva, que es una ventana de herramientas en la que se ejecuta una sesión de F# Interactive. También puede seleccionar el código que quiere ejecutar en la ventana interactiva y presionar la combinación de teclas **Alt+ENTRAR**. F# Interactive se inicia en la ventana de herramientas con la etiqueta **F# Interactive**. Cuando use esta combinación de teclas, asegúrese de que la ventana del editor tiene el foco.

Tanto si usa la consola como si usa Visual Studio, aparece un símbolo del sistema y el intérprete espera una entrada por parte del usuario. Puede escribir código tal y como lo haría en un archivo de código fuente. Para compilar y ejecutar el código, escriba dos signos de punto y coma ( **;;** ) para finalizar una o varias líneas de entrada.

F# Interactive intenta compilar el código y, si lo logra, lo ejecuta e imprime en pantalla la signatura de los tipos y valores que compiló. Si se producen errores, el intérprete imprime en pantalla los mensajes de error.

El código escrito en una misma sesión tiene acceso a cualquier construcción escrita anteriormente, de modo que es posible crear programas. Un búfer extenso de la ventana de herramientas permite copiar el código en un archivo si es necesario.

Cuando F# Interactive se ejecuta en Visual Studio, lo hace de manera independiente del proyecto, de modo que, por ejemplo, no se pueden usar en F# Interactive las construcciones definidas en el proyecto a menos que se copie el código de dichas funciones en la ventana interactiva.

Puede controlar los argumentos (opciones) de la línea de comandos de F# Interactive ajustando la configuración. En el menú **Herramientas** , seleccione **Opciones...** y, después, expanda **Herramientas de F#**. Las dos configuraciones que puede cambiar son las opciones de F# Interactive y la opción **F# Interactive de 64 bits** , que solo es relevante si ejecuta F# Interactive en un equipo de 64 bits. Este valor determina si desea ejecutar la versión de 64 bits dedicada de **fsi.exe** o **fsianycpu.exe** , que usa la arquitectura del equipo para determinar si debe ejecutarse como un proceso de 32 o 64 bits.

## <a name="related-articles"></a>Artículos relacionados

|Title|Descripción|
|-----|-----------|
|[Opciones de F# Interactive](../../language-reference/fsharp-interactive-options.md)|Describe la sintaxis y las opciones de línea de comandos de F# interactivo, fsi.exe.|
