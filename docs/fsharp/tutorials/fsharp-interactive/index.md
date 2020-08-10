---
title: Referencia de F# Interactive (fsi.exe)
description: Obtenga información sobre cómo se utiliza F# interactivo (fsi.exe) para ejecutar código de F# de manera interactiva en la consola o para ejecutar scripts de F#.
ms.date: 05/16/2016
f1_keywords:
- VS.ToolsOptionsPages.F#_Tools.F#_Interactive
ms.openlocfilehash: 8bb1563ad34e65101fb9f09d6e347278e4b0de78
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87854950"
---
# <a name="interactive-programming-with-f"></a>Programación interactiva con F\#

> [!NOTE]
> En este artículo actualmente solo se describe la experiencia para Windows.

F# Interactive (fsi.exe) se utiliza para ejecutar código de F# de manera interactiva en la consola o para ejecutar scripts de F#. En otras palabras, F# Interactive ejecuta un bucle REPL (del inglés Read, Evaluate, Print Loop - bucle Leer, Evaluar, Imprimir) para el lenguaje F#.

Para usar F# Interactive desde la consola, ejecute fsi.exe. Encontrará fsi.exe en:

```console
C:\Program Files (x86)\Microsoft Visual Studio\2019\<sku>\Common7\IDE\CommonExtensions\Microsoft\FSharp
```

donde `sku` es `Community`, `Professional` o `Enterprise`.

Para obtener más información sobre las opciones de línea de comandos disponibles, vea [Opciones de F# Interactive](../../language-reference/fsharp-interactive-options.md).

Para ejecutar F# Interactive a través de Visual Studio, puede hacer clic en el botón **F# Interactive** de la barra de herramientas o presionar las teclas **Ctrl+Alt+F**. De este modo, se abrirá la ventana interactiva, que es una ventana de herramientas en la que se ejecuta una sesión de F# Interactive. También puede seleccionar el código que quiere ejecutar en la ventana interactiva y presionar la combinación de teclas **Alt+ENTRAR**. F# Interactive se inicia en la ventana de herramientas con la etiqueta **F# Interactive**. Cuando use esta combinación de teclas, asegúrese de que la ventana del editor tiene el foco.

Tanto si usa la consola como si usa Visual Studio, aparece un símbolo del sistema y el intérprete espera una entrada por parte del usuario. Puede escribir código tal y como lo haría en un archivo de código fuente. Para compilar y ejecutar el código, escriba dos signos de punto y coma (**;;**) para finalizar una o varias líneas de entrada.

F# Interactive intenta compilar el código y, si lo logra, lo ejecuta e imprime en pantalla la signatura de los tipos y valores que compiló. Si se producen errores, el intérprete imprime en pantalla los mensajes de error.

El código escrito en una misma sesión tiene acceso a cualquier construcción escrita anteriormente, de modo que es posible crear programas. Un búfer extenso de la ventana de herramientas permite copiar el código en un archivo si es necesario.

Cuando F# Interactive se ejecuta en Visual Studio, lo hace de manera independiente del proyecto, de modo que, por ejemplo, no se pueden usar en F# Interactive las construcciones definidas en el proyecto a menos que se copie el código de dichas funciones en la ventana interactiva.

Si tiene un proyecto abierto que hace referencia a algunas bibliotecas, puede hacer referencia a ellas en F# Interactive a través del **Explorador de soluciones**. Para hacer referencia a una biblioteca en F# Interactive, expanda el nodo **Referencias**, abra el menú contextual de la biblioteca y seleccione **Enviar a F# Interactive**.

Puede controlar los argumentos (opciones) de la línea de comandos de F# Interactive ajustando la configuración. En el menú **Herramientas**, seleccione **Opciones...** y, después, expanda **Herramientas de F#**. Las dos configuraciones que puede cambiar son las opciones de F# Interactive y la opción **F# Interactive de 64 bits**, que solo es relevante si ejecuta F# Interactive en un equipo de 64 bits. Este valor determina si desea ejecutar la versión de 64 bits dedicada de fsi.exe o de fsianycpu.exe, que usa la arquitectura del equipo para determinar si debe ejecutarse como un proceso de 32 o de 64 bits.

## <a name="scripting-with-f"></a>Scripting con F\#

Los scripts usan la extensión de archivo **.fsx** o **.fsscript**. En lugar de compilar el código fuente y después ejecutar el ensamblado compilado, se puede ejecutar simplemente **fsi.exe** y especificar el nombre de archivo del script de código fuente de F#. F# Interactive lee el código y lo ejecuta en tiempo real.

## <a name="differences-between-the-interactive-scripting-and-compiled-environments"></a>Diferencias entre los entornos interactivo, compilado y de scripting

Al compilar código en F# Interactive, tanto si se ejecuta de forma interactiva como si ejecuta un script, se define el símbolo **INTERACTIVE**. Al compilar código en el compilador, se define el símbolo **COMPILED**. Por consiguiente, si el código debe ser diferente en modo interactivo y en modo compilado, se pueden usar las directivas de preprocesador de la compilación condicional para determinar cuál se va a usar.

Cuando se ejecutan scripts en F# Interactive, están disponibles algunas directivas que no están disponibles cuando se ejecuta el compilador. En la siguiente tabla se resumen las directivas que están disponibles cuando se usa F# Interactive.

|Directiva|Descripción|
|---------|-----------|
|**#help**|Muestra información sobre las directivas disponibles.|
|**#I**|Especifica una ruta de búsqueda de ensamblado entre comillas.|
|**#load**|Lee un archivo de código fuente, lo compila y lo ejecuta.|
|**#quit**|Termina una sesión de F# Interactive.|
|**#r**|Hace referencia a un ensamblado.|
|**#time ["on"&#124;"off"]**|Por sí solo, **#time** activa y desactiva la presentación de información sobre el rendimiento. Cuando está habilitado, F# Interactive mide el tiempo real, el tiempo de CPU y la información sobre recolección de elementos no utilizados que se interpreta y ejecuta.|

Al especificar los archivos o rutas de acceso en F# Interactive, se espera un literal de cadena. Por tanto, los archivos y las rutas de acceso deben estar entre comillas y se aplicarán los caracteres de escape habituales. Asimismo, puede usar el carácter @ para hacer que F# Interactive interprete una cadena que contenga una ruta de acceso como una cadena textual. Esto hace que F# Interactive pase por alto cualquier carácter de escape.

Una de las diferencias entre el modo compilado y el modo interactivo es la manera en que se obtiene acceso a los argumentos de la línea de comandos. En modo compilado, use **System.Environment.GetCommandLineArgs**. En los scripts, use **fsi.CommandLineArgs**.

En el código siguiente se muestra cómo crear una función que lea los argumentos de la línea de comandos en un script y cómo hacer referencia a otro ensamblado desde un script. El primer archivo de código, **MyAssembly.fs**, contiene el código del ensamblado al que se hace referencia. Compile este archivo con la línea de comandos: **fsc -a MyAssembly.fs** y, después, ejecute el segundo archivo como un script con la línea de comandos: **fsi --exec file1.fsx** test

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

```fsharp
// file1.fsx
#r "MyAssembly.dll"

printfn "Command line arguments: "

for arg in fsi.CommandLineArgs do
    printfn "%s" arg

printfn "%A" (MyAssembly.myFunction 10 40)
```

La salida es como sigue:

```console
Command line arguments:
file1.fsx
test
90
```

## <a name="related-articles"></a>Artículos relacionados

|Title|Descripción|
|-----|-----------|
|[Opciones de F# Interactive](../../language-reference/fsharp-interactive-options.md)|Describe la sintaxis y las opciones de línea de comandos de F# interactivo, fsi.exe.|
|[Referencia de la biblioteca interactiva de F#](https://msdn.microsoft.com/visualfsharpdocs/conceptual/fsharp-interactive-library-reference)|Describe la funcionalidad de bibliotecas que está disponible cuando se ejecuta código en F# Interactive.|
