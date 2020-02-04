---
title: Introducción a F# en Visual Studio Code
description: Aprenda a usar F# con Visual Studio Code y el conjunto de complementos de Ionide.
ms.date: 12/23/2018
ms.openlocfilehash: 2aa62bb1afc220348f884865e55c4d7de4359b7f
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980358"
---
# <a name="get-started-with-f-in-visual-studio-code"></a>Introducción a F# en Visual Studio Code

Puede escribir F# en [Visual Studio Code](https://code.visualstudio.com) con el [complemento Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) para obtener una excelente experiencia de entorno de desarrollo integrado (IDE) multiplataforma y flexible con IntelliSense y refactorizaciones de código. Visite [Ionide.IO](http://ionide.io) para obtener más información sobre el complemento.

Para empezar, asegúrese de que tiene [ F# y el complemento Ionide instalado correctamente](install-fsharp.md#install-f-with-visual-studio-code).

## <a name="create-your-first-project-with-ionide"></a>Cree su primer proyecto con Ionide

Para crear un nuevo F# proyecto, abra una línea de comandos y cree un nuevo proyecto con el CLI de .net Core:

```dotnetcli
dotnet new console -lang "F#" -o FirstIonideProject
```

Una vez finalizado, cambie el directorio al proyecto y abra Visual Studio Code:

```console
cd FirstIonideProject
code .
```

Después de que el proyecto se cargue en Visual Studio Code, debería F# ver el panel de explorador de soluciones en el lado izquierdo de la ventana abierta. Esto significa que Ionide ha cargado correctamente el proyecto que acaba de crear. Puede escribir código en el editor antes de este momento, pero cuando esto suceda, todo ha terminado de cargarse.

## <a name="configure-f-interactive"></a>Configuración F# de Interactive

En primer lugar, asegúrese de que el scripting de .NET Core es el entorno de scripting predeterminado:

1. Abra la configuración de Visual Studio Code (**código** > **preferencias** > **configuración**).
1. Busque el término  **F# script**.
1. Haga clic en la casilla que indica **FSharp: usar scripts de SDK**.

Esto es necesario actualmente debido a algunos comportamientos heredados en scripting basado en .NET Framework que no funcionan con el scripting de .NET Core y Ionide está intentando actualmente la compatibilidad con versiones anteriores. En el futuro, el scripting de .NET Core se convertirá en el valor predeterminado.

### <a name="write-your-first-script"></a>Escribir el primer script

Una vez que haya configurado Visual Studio Code para usar el scripting de .NET Core, vaya a la vista del explorador en Visual Studio Code y cree un archivo nuevo. Asígnele el nombre *MyFirstScript. FSX*.

Ahora, agregue el siguiente código:

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

Esta función convierte una palabra en una forma de [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin). El siguiente paso es evaluarlo mediante F# Interactive (FSI).

Resalte toda la función (debe tener 11 líneas de longitud). Una vez resaltado, mantenga presionada la tecla **Alt** y presione **entrar**. Observará que aparece una ventana de terminal en la parte inferior de la pantalla y debería tener un aspecto similar al siguiente:

![Ejemplo de F# salida interactiva con Ionide](./media/getting-started-vscode/vscode-fsi.png)

Esto hizo tres cosas:

1. Se inició el proceso FSI.
2. Envió el código que resaltó en el proceso FSI.
3. El proceso FSI evaluó el código que ha enviado.

Dado que lo que envió es una [función](../language-reference/functions/index.md), ahora puede llamar a esa función con FSI. En la ventana interactiva, escriba lo siguiente:

```fsharp
toPigLatin "banana";;
```

Debería ver el siguiente resultado:

```fsharp
val it : string = "ananabay"
```

Ahora, vamos a probar una vocal como la primera letra. Escriba lo siguiente:

```fsharp
toPigLatin "apple";;
```

Debería ver el siguiente resultado:

```fsharp
val it : string = "appleyay"
```

Parece que la función funciona según lo esperado. Enhorabuena, acaba de escribir su primera F# función en Visual Studio Code y la evaluó con FSI.

> [!NOTE]
> Como puede haber observado, las líneas de FSI finalizan con `;;`. Esto se debe a que FSI le permite escribir varias líneas. El `;;` al final permite que FSI sepa cuándo finaliza el código.

## <a name="explaining-the-code"></a>Explicación del código

Si no está seguro de lo que realmente está haciendo el código, aquí se muestra paso a paso.

Como puede ver, `toPigLatin` es una función que toma una palabra como su entrada y la convierte en una representación de un Pig de esa palabra. Las reglas para esto son las siguientes:

Si el primer carácter de una palabra comienza con una vocal, agregue "Yay" al final de la palabra. Si no se inicia con una vocal, mueva el primer carácter al final de la palabra y agréguele "Ay".

Es posible que haya observado lo siguiente en FSI:

```fsharp
val toPigLatin : word:string -> string
```

Esto indica que `toPigLatin` es una función que toma un `string` como entrada (denominada `word`) y devuelve otro `string`. Esto se conoce como la [firma de tipo de la función](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fundamental F# de la clave para entender F# el código. También observará esto si mantiene el puntero sobre la función en Visual Studio Code.

En el cuerpo de la función, observará dos partes distintas:

1. Función interna, denominada `isVowel`, que determina si un carácter determinado (`c`) es una vocal comprobando si coincide con uno de los patrones proporcionados a través de la [coincidencia de patrones](../language-reference/pattern-matching.md):

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expresión que comprueba si el primer carácter es una vocal y construye un valor devuelto fuera de los caracteres de entrada en función de si el primer carácter era una vocal o no:

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

El flujo de `toPigLatin` es así:

Comprueba si el primer carácter de la palabra de entrada es una vocal. Si es así, adjunte "Yay" al final de la palabra. En caso contrario, mueva el primer carácter al final de la palabra y agréguele "Ay".

Hay un aspecto final que se debe tener en cuenta: F#en, no hay ninguna instrucción explícita que devolver desde la función. Esto se debe F# a que se basa en expresiones y la última expresión evaluada en el cuerpo de una función determina el valor devuelto de esa función. Dado que `if..then..else` es en sí misma una expresión, la evaluación del cuerpo del bloque de `then` o el cuerpo del bloque de `else` determina el valor devuelto por la función de `toPigLatin`.

## <a name="turn-the-console-app-into-a-pig-latin-generator"></a>Convertir la aplicación de consola en un generador de Pig Latin

En las secciones anteriores de este artículo se ha mostrado un primer paso F# común en la escritura del código: escribir una función inicial y ejecutarla de forma interactiva con FSI. Esto se conoce como desarrollo controlado por REPL, donde [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) representa el bucle de lectura-evaluación-impresión. Es una excelente manera de experimentar con la funcionalidad hasta que tenga algo que funcione.

El siguiente paso del desarrollo controlado por REPL es trasladar el código de trabajo F# a un archivo de implementación. Después, el F# compilador puede compilar en un ensamblado que se pueda ejecutar.

Para empezar, abra el archivo *Program. FS* que creó anteriormente con el CLI de .net Core. Observará que parte del código ya está en él.

A continuación, cree una nueva [`module`](../language-reference/modules.md) denominada `PigLatin` y copie en ella la función de `toPigLatin` que creó anteriormente:

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L3-L14)]

Este módulo debe estar por encima de la `main` función y debajo de la declaración de `open System`. El orden de las declaraciones es F#importante en, por lo que deberá definir la función antes de llamarla en un archivo.

Ahora, en la función `main`, llame a la función de generador de Pig Latin en los argumentos:

```fsharp
[<EntryPoint>]
let main argv =
    for name in argv do
        let newName = PigLatin.toPigLatin name
        printfn "%s in Pig Latin is: %s" name newName

    0
```

Ahora puede ejecutar la aplicación de consola desde la línea de comandos:

```dotnetcli
dotnet run apple banana
```

Y verá que genera el mismo resultado que el archivo de script, pero esta vez como un programa en ejecución.

## <a name="troubleshooting-ionide"></a>Solución de problemas de Ionide

Estas son algunas de las formas en que puede solucionar ciertos problemas que pueden surgir:

1. Para obtener las características de edición de código de Ionide F# , los archivos deben guardarse en el disco y dentro de una carpeta que esté abierta en el área de trabajo Visual Studio Code.
1. Si ha realizado cambios en el sistema o ha instalado los requisitos previos de Ionide con Visual Studio Code abrir, reinicie Visual Studio Code.
1. Si tiene caracteres no válidos en los directorios del proyecto, es posible que Ionide no funcione.  Cambie el nombre de los directorios del proyecto si éste es el caso.
1. Si no funciona ninguno de los comandos de Ionide, compruebe los [enlaces de teclado de Visual Studio Code](https://code.visualstudio.com/docs/getstarted/keybindings#_advanced-customization) para ver si se están reemplazando por accidente.
1. Si Ionide se ha interrumpido en el equipo y ninguno de los anteriores ha solucionado el problema, intente quitar el directorio de `ionide-fsharp` de la máquina y vuelva a instalar el conjunto de complementos.
1. Si un proyecto no se cargó (el F# explorador de soluciones lo mostrará), haga clic con el botón derecho en el proyecto y haga clic en **Ver detalles** para obtener más información de diagnóstico.

Ionide es un proyecto de código abierto creado y mantenido por miembros de F# la comunidad. Informe de los problemas y no dude en contribuir en el [repositorio de github ionide-vscode-FSharp](https://github.com/ionide/ionide-vscode-fsharp).

También puede solicitar más ayuda de la comunidad y F# los desarrolladores de Ionide en el [canal de Gitter de Ionide](https://gitter.im/ionide/ionide-project).

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información F# acerca de y las características del lenguaje, consulte el [paseo F# ](../tour.md)por.
