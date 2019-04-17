---
title: Introducción a F# en Visual Studio Code
description: Aprenda a usar F# con Visual Studio Code y Ionide complemento suite.
ms.date: 12/23/2018
ms.openlocfilehash: 7c2ecab14b3351d441249e7fc7cb3188a4ee7eba
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612893"
---
# <a name="get-started-with-f-in-visual-studio-code"></a>Introducción a F# en Visual Studio Code

Puede escribir F# en [Visual Studio Code](https://code.visualstudio.com) con el [Ionide complemento](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) para obtener una gran experiencia de entorno de desarrollo integrado (IDE) ligero en varias plataformas, con IntelliSense y el código básico refactorizaciones. Visite [Ionide.io](http://ionide.io) para obtener más información sobre el complemento.

Para empezar, asegúrese de que tiene [ F# y ha instalado correctamente el complemento de Ionide](install-fsharp.md#install-f-with-visual-studio-code).

> [!NOTE]
> Ionide generará .NET Framework F# proyectos, no de dotnet core, lo que puede tener problemas de compatibilidad multiplataforma. Si está ejecutando en **Linux** o **OSX**, una forma más sencilla de empezar a trabajar es usar el [herramientas de línea de comandos](https://docs.microsoft.com/en-us/dotnet/fsharp/get-started/get-started-command-line).

## <a name="creating-your-first-project-with-ionide"></a>Crear su primer proyecto con Ionide

Para crear un nuevo F# del proyecto, abra Visual Studio Code en una nueva carpeta (puede denominarlo que prefiera).

A continuación, abra la paleta de comandos (**Vista > Paleta de comandos**) y escriba lo siguiente:

```
> F# new project
```

Esto funciona con el [FALSIFICAR](https://github.com/fsharp-editing/Forge) proyecto.

> [!NOTE]
> Si no ve las opciones de plantilla, pruebe a actualizar las plantillas ejecutando el siguiente comando en la paleta de comandos: `>F#: Refresh Project Templates`.

Seleccione "F#: Nuevo proyecto"pulsando **ENTRAR**. Esto le lleva al paso siguiente, que es para seleccionar una plantilla de proyecto.

Elegir el `classlib` plantilla del sistema y presione **ENTRAR**.

A continuación, seleccione un directorio para crear el proyecto en. Si se deja en blanco, usa el directorio actual.

Por último, nombre del proyecto en el paso final. F#usa [mayúsculas y minúsculas Pascal](http://c2.com/cgi/wiki?PascalCase) los nombres de proyecto. Este artículo se usa `ClassLibraryDemo` como el nombre. Una vez que haya escrito el nombre que desee para el proyecto, presione **ENTRAR**.

Si ha seguido el paso anterior, debería obtener Visual Studio código de área de trabajo en el lado izquierdo que aparezca con el siguiente:

1. El F# propio proyecto, debajo de la directiva el `ClassLibraryDemo` carpeta.
2. Para agregar paquetes a través de la estructura de directorio correcto [ `Paket` ](https://fsprojects.github.io/Paket/).
3. Una multiplataforma crear secuencia de comandos con [ `FAKE` ](https://fsharp.github.io/FAKE/).
4. El `paket.exe` ejecutable que puede capturar paquetes y resolver las dependencias para usted.
5. Un `.gitignore` archivo si desea agregar este proyecto al control de código fuente basados en Git.

## <a name="writing-some-code"></a>Escribir código

Abra el *ClassLibraryDemo* carpeta.  Debería ver los archivos siguientes:

1. `ClassLibraryDemo.fs`, un F# archivo de implementación con una clase definida.
2. `ClassLibraryDemo.fsproj`, un F# archivo de proyecto utilizado para compilar el proyecto.
3. `Script.fsx`, un F# archivo de script que se carga el archivo de origen.
4. `paket.references`, un archivo Paket que especifica las dependencias del proyecto.

Abra `Script.fsx`y agregue el código siguiente al final de la misma:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

Esta función convierte una palabra en un formulario de [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin). El siguiente paso es evaluar mediante F# interactivo (FSI).

Resaltar toda la función (debe ser 11 líneas de largo). Una vez que se resalta, mantenga el **Alt** clave y posicionamiento **ENTRAR**. Verá una ventana emergente a continuación, y debe aparecer algo parecido a esto:

![Ejemplo de F# interactivo de salida con Ionide](media/getting-started-vscode/vscode-fsi.png)

Esto hizo tres cosas:

1. Inició el proceso FSI.
2. El código resaltado que envíe a través del proceso FSI.
3. El proceso FSI evalúa el código que envían a través.

Debido a que era lo que se envía a través de un [función](../language-reference/functions/index.md), ahora puede llamar a esa función con FSI! En la ventana interactiva, escriba lo siguiente:

```fsharp
toPigLatin "banana";;
```

Debería ver el resultado siguiente:

```fsharp
val it : string = "ananabay"
```

Ahora, vamos a probar con una vocal como la primera letra. Escriba lo siguiente:

```fsharp
toPigLatin "apple";;
```

Debería ver el resultado siguiente:

```fsharp
val it : string = "appleyay"
```

La función parece que funciona según lo previsto. Enhorabuena, acaba de escribir su primer F# funcionan en Visual Studio Code y se evalúa con FSI!

> [!NOTE]
> Como habrá advertido, las líneas en FSI terminan con `;;`. Esto es porque FSI le permite escribir varias líneas. El `;;` al final sabrá FSI cuando finalice el código.

## <a name="explaining-the-code"></a>Que explica el código

Si no está seguro acerca de lo que realmente está haciendo el código, este es un paso a paso.

Como puede ver, `toPigLatin` es una función que toma una palabra como entrada y lo convierte en una representación de Pig Latin de esa palabra. Las reglas para esto son los siguientes:

Si el primer carácter de una palabra comienza con una vocal, agregue "¡viva" al final de la palabra. Si no se inicia con una vocal, mover ese primer carácter al final de la palabra y "ay" Agregar a ella.

Es podrán que haya observado lo siguiente en FSI:

```fsharp
val toPigLatin : word:string -> string
```

Esto indica que `toPigLatin` es una función que toma un `string` como entrada (denominado `word`) y devuelve otra `string`. Esto se conoce como el [signatura de tipo de la función](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fundamental de F# que es clave para comprender F# código. También podrá observar si mantiene el mouse sobre la función en Visual Studio Code.

En el cuerpo de la función, verá dos partes distintas:

1. Una función interna, llamada `isVowel`, que determina si un carácter determinado (`c`) es una vocal comprobando si coincide con uno de los patrones proporcionados a través de [coincidencia de patrones](../language-reference/pattern-matching.md):

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. Un [ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) expresión que comprueba si el primer carácter sea una vocal y construcciones un retorno de valor fuera de los caracteres de entrada en función de si el primer carácter o no era una vocal:

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

El flujo de `toPigLatin` por tanto, es:

Compruebe si el primer carácter de la palabra de entrada sea una vocal. Si es así, adjuntar "¡viva" al final de la palabra. En caso contrario, mueva ese primer carácter al final de la palabra y "ay" Agregar a ella.

Hay una última cosa a tener en cuenta sobre esto: no hay ninguna instrucción explícita para devolver de la función, a diferencia de muchos otros lenguajes ahí. Esto es porque F# está basado en la expresión, y la última expresión en el cuerpo de una función es el valor devuelto. Dado que `if..then..else` es en sí mismo una expresión, el cuerpo de la `then` bloque o en el cuerpo de la `else` bloque se devolverán según el valor de entrada.

## <a name="moving-your-script-code-into-the-implementation-file"></a>Migración de código de script en el archivo de implementación

Las secciones anteriores de este artículo muestran un primer paso común escrito F# código: escribir una función inicial y se ejecuta interactivamente con FSI. Esto se conoce como el desarrollo controlado por REPL, donde [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) es el acrónimo "Read-Evaluate-Print Loop". Es una excelente manera de experimentar con la funcionalidad hasta que haya algo funcione.

El siguiente paso en el desarrollo controlado por REPL es mover el código de trabajo en un F# archivo de implementación. A continuación, se puede compilar si la F# compilador en un ensamblado que se puede ejecutar.

Para comenzar, abra `ClassLibraryDemo.fs`.  Observará que algún código ya está en no existe. Siga adelante y eliminar la definición de clase, pero asegúrese de dejar el [ `namespace` ](../language-reference/namespaces.md) declaración en la parte superior.

A continuación, cree un nuevo [ `module` ](../language-reference/modules.md) llamado `PigLatin` y copie el `toPigLatin` función como tal en él:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

A continuación, abra el `Script.fsx` archivo nuevo y eliminar toda la `toPigLatin` funcionando, pero asegúrese de mantener las dos líneas siguientes en el archivo:

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

Seleccione ambas líneas de texto y presione Alt + Intro para ejecutar estas líneas en FSI. Estos cargará el contenido de la biblioteca de Pig Latin en el proceso FSI y `open` el `ClassLibraryDemo` espacio de nombres para que tengan acceso a la funcionalidad.

A continuación, en la ventana FSI, llame a la función con el `PigLatin` módulo que definió anteriormente:

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

Correcto Obtener los mismos resultados como antes, pero ahora se cargan desde un F# archivo de implementación. La principal diferencia es que F# archivos de código fuente se compilan en ensamblados que se pueden ejecutar en cualquier lugar, no solo en FSI.

## <a name="summary"></a>Resumen

En este artículo, ha aprendido:

1. Cómo configurar Visual Studio Code con Ionide.
2. Cómo crear su primer F# proyecto con Ionide.
3. Cómo usar F# secuencias de comandos para escribir su primer F# funcionar en Ionide y, a continuación, ejecútelo de FSI.
4. Cómo migrar el código de script a F# de origen y, a continuación, invocar dicho código desde FSI.

Ahora está equipado para escribir mucho más F# del código mediante Visual Studio Code y Ionide.

## <a name="troubleshooting"></a>Solución de problemas

Estas son algunas maneras de que solucionar ciertos problemas que pueden surgir:

1. Para obtener el código en la edición de las características de Ionide, su F# los archivos deben guardarse en el disco y dentro de una carpeta que está abierta en el área de trabajo de Visual Studio Code.
2. Si ha realizado cambios en el sistema o instalar requisitos previos de Ionide con código de Visual Studio abierta, reinicie Visual Studio Code.
3. Compruebe que puede usar el F# compilador y F# interactivo desde la línea de comandos sin una ruta de acceso completa. Puede hacerlo escribiendo `fsc` en una línea de comandos para el F# compilador, y `fsi` o `fsharpi` para el objeto Visual F# herramientas en Windows y Mono en Mac/Linux, respectivamente.
4. Si tiene caracteres no válidos en los directorios del proyecto, Ionide podría no funcionar.  Cambiar el nombre de los directorios de proyecto si este es el caso.
5. Si ninguno de los comandos Ionide está trabajando, compruebe su [enlaces de teclado de Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) para ver si se está reemplazando por accidente.
6. Si Ionide se divide en el equipo y ninguno de los anteriores ha se ha corregido el problema, pruebe a quitar el `ionide-fsharp` directorio en el equipo y vuelva a instalar el conjunto de complemento.

Ionide es un proyecto de código abierto creado y mantenido por los miembros de la F# Comunidad. Por favor, notificar problemas y no dude en contribuir en el [Ionide VSCode: Repositorio de FSharp GitHub](https://github.com/ionide/ionide-vscode-fsharp).

Si tiene un problema al informe, siga [las instrucciones para obtener los registros que se usará al informar de un problema](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).

También puede pedir ayuda adicional de los desarrolladores Ionide y F# Comunidad en el [Ionide Gitter canal](https://gitter.im/ionide/ionide-project).

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información sobre F# y las características del lenguaje, eche un vistazo [paseo F# ](../tour.md).
