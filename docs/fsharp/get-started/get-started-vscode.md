---
title: Introducción a F# en Visual Studio Code
description: Aprenda a usar F# con Visual Studio Code y el conjunto de complementos de Ionide.
ms.date: 12/23/2018
ms.openlocfilehash: baaa87207122cfe314972aee5dfaf8a41de2c394
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629982"
---
# <a name="get-started-with-f-in-visual-studio-code"></a>Introducción a F# en Visual Studio Code

Puede escribir F# en [Visual Studio Code](https://code.visualstudio.com) con el [complemento Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) para obtener una excelente experiencia de entorno de desarrollo integrado (IDE) multiplataforma y flexible con IntelliSense y refactorizaciones de código básicas. Visite [Ionide.IO](http://ionide.io) para obtener más información sobre el complemento.

Para empezar, asegúrese de que tiene [ F# y el complemento Ionide instalado correctamente](install-fsharp.md#install-f-with-visual-studio-code).

> [!NOTE]
> Ionide generará proyectos F# de .NET Framework, no dotnet Core, que pueden tener problemas de compatibilidad entre plataformas. Si está ejecutando en **Linux** o **OSX**, una forma más sencilla de empezar es usar las [herramientas de línea de comandos](get-started-command-line.md).

## <a name="creating-your-first-project-with-ionide"></a>Crear su primer proyecto con Ionide

Para crear un nuevo F# proyecto, abra Visual Studio Code en una nueva carpeta (puede asignarle el nombre que desee).

A continuación, abra la paleta de comandos (**ver > paleta de comandos**) y escriba lo siguiente:

```
> F# new project
```

Esto está basado en el proyecto de [falsificación](https://github.com/fsharp-editing/Forge).

> [!NOTE]
> Si no ve las opciones de plantilla, intente actualizar las plantillas ejecutando el siguiente comando en la paleta de `>F#: Refresh Project Templates`comandos:.

Seleccione "F#: Nuevo proyecto "presionando **entrar**. Esto le llevará al paso siguiente, que es para seleccionar una plantilla de proyecto.

Seleccione la `classlib` plantilla y presione **entrar**.

A continuación, elija un directorio en el que crear el proyecto. Si lo deja en blanco, se usa el directorio actual.

Por último, asigne un nombre al proyecto en el paso final. F#usa [mayúsculas y minúsculas Pascal](http://c2.com/cgi/wiki?PascalCase) para los nombres de proyecto. En este artículo `ClassLibraryDemo` se usa como nombre. Una vez que haya escrito el nombre que desea para el proyecto, presione **entrar**.

Si siguió el paso anterior, debería obtener el Visual Studio Code área de trabajo en el lado izquierdo para que aparezca con lo siguiente:

1. El F# proyecto en sí, debajo `ClassLibraryDemo` de la carpeta.
2. La estructura de directorios correcta para agregar paquetes [`Paket`](https://fsprojects.github.io/Paket/)a través de.
3. Un script de compilación multiplataforma con [`FAKE`](https://fsharp.github.io/FAKE/).
4. Ejecutable `paket.exe` que puede capturar paquetes y resolver las dependencias automáticamente.
5. Un `.gitignore` archivo si desea agregar este proyecto al control de código fuente basado en Git.

## <a name="writing-some-code"></a>Escribir código

Abra la carpeta *ClassLibraryDemo* .  Debería ver los archivos siguientes:

1. `ClassLibraryDemo.fs`, un F# archivo de implementación con una clase definida.
2. `ClassLibraryDemo.fsproj`, un F# archivo de proyecto que se usa para compilar este proyecto.
3. `Script.fsx`, un F# archivo de script que carga el archivo de código fuente.
4. `paket.references`, un archivo Paket que especifica las dependencias del proyecto.

Abra `Script.fsx`y agregue el código siguiente al final de la misma:

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

Esta función convierte una palabra en una forma de [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin). El siguiente paso es evaluarlo mediante F# Interactive (FSI).

Resalte toda la función (debe tener 11 líneas de longitud). Una vez resaltado, mantenga presionada la tecla **Alt** y presione **entrar**. Observará que aparece una ventana emergente y debería mostrar algo parecido a esto:

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
> Como puede haber observado, las líneas de FSI se terminan con `;;`. Esto se debe a que FSI le permite escribir varias líneas. Al `;;` final permite que FSI sepa cuándo finaliza el código.

## <a name="explaining-the-code"></a>Explicación del código

Si no está seguro de lo que realmente está haciendo el código, aquí se muestra paso a paso.

Como puede ver, `toPigLatin` es una función que toma una palabra como su entrada y la convierte en una representación de Pig-latín de esa palabra. Las reglas para esto son las siguientes:

Si el primer carácter de una palabra comienza con una vocal, agregue "Yay" al final de la palabra. Si no se inicia con una vocal, mueva el primer carácter al final de la palabra y agréguele "Ay".

Es posible que haya observado lo siguiente en FSI:

```fsharp
val toPigLatin : word:string -> string
```

Esto indica que `toPigLatin` es una función que toma `string` como entrada (llamada `word`) y devuelve otra `string`. Esto se conoce como la [firma de tipo de la función](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fundamental F# de la clave para entender F# el código. También observará esto si mantiene el puntero sobre la función en Visual Studio Code.

En el cuerpo de la función, observará dos partes distintas:

1. Función interna, denominada `isVowel`, que determina si un carácter determinado (`c`) es una vocal comprobando si coincide con uno de los patrones proporcionados a través de la coincidencia de [patrones](../language-reference/pattern-matching.md):

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) Expresión que comprueba si el primer carácter es una vocal y crea un valor devuelto fuera de los caracteres de entrada en función de si el primer carácter era una vocal o no:

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

El flujo de `toPigLatin` es así:

Comprueba si el primer carácter de la palabra de entrada es una vocal. Si es así, adjunte "Yay" al final de la palabra. En caso contrario, mueva el primer carácter al final de la palabra y agréguele "Ay".

Hay un aspecto final que se debe tener en cuenta: no hay ninguna instrucción explícita para devolver de la función, a diferencia de muchos otros lenguajes. Esto se debe F# a que se basa en expresiones y la última expresión del cuerpo de una función es el valor devuelto. Dado `if..then..else` que es una expresión, el cuerpo `then` del bloque `else` o el cuerpo del bloque se devolverá en función del valor de entrada.

## <a name="moving-your-script-code-into-the-implementation-file"></a>Mover el código de script al archivo de implementación

En las secciones anteriores de este artículo se ha mostrado un primer paso F# común en la escritura del código: escribir una función inicial y ejecutarla de forma interactiva con FSI. Esto se conoce como desarrollo controlado por REPL, donde [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) representa el bucle de lectura-evaluación-impresión. Es una excelente manera de experimentar con la funcionalidad hasta que tenga algo que funcione.

El siguiente paso del desarrollo controlado por REPL es trasladar el código de trabajo F# a un archivo de implementación. Después, el F# compilador puede compilar en un ensamblado que se pueda ejecutar.

Para empezar, Abra `ClassLibraryDemo.fs`.  Observará que parte del código ya está en él. Continúe y elimine la definición de clase, pero asegúrese de dejar la [`namespace`](../language-reference/namespaces.md) declaración en la parte superior.

A continuación, cree un [`module`](../language-reference/modules.md) nuevo `PigLatin` denominado y copie `toPigLatin` la función en él de la manera siguiente:

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

A continuación, vuelva `Script.fsx` a abrir el archivo y elimine `toPigLatin` toda la función, pero asegúrese de mantener las dos líneas siguientes en el archivo:

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

Seleccione ambas líneas de texto y presione Alt + Entrar para ejecutar estas líneas en FSI. Estos cargarán el contenido de la biblioteca de Pig Latin en el proceso FSI `open` y `ClassLibraryDemo` el espacio de nombres para que tenga acceso a la funcionalidad.

A continuación, en la ventana FSI, llame a la función `PigLatin` con el módulo que definió anteriormente:

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

Correcto Obtiene los mismos resultados que antes, pero ahora se carga desde un F# archivo de implementación. La principal diferencia es que F# los archivos de código fuente se compilan en ensamblados que se pueden ejecutar en cualquier lugar, no solo en FSI.

## <a name="summary"></a>Resumen

En este artículo, ha aprendido lo siguiente:

1. Cómo configurar Visual Studio Code con Ionide.
2. Cómo crear su primer F# proyecto con Ionide.
3. Cómo usar F# scripting para escribir la primera F# función en Ionide y, a continuación, ejecutarla en FSI.
4. Cómo migrar el código de script al F# origen y, después, llamar a ese código desde FSI.

Ahora está preparado para escribir mucho más F# código con Visual Studio Code y Ionide.

## <a name="troubleshooting"></a>solución de problemas

Estas son algunas de las formas en que puede solucionar ciertos problemas que pueden surgir:

1. Para obtener las características de edición de código de Ionide F# , los archivos deben guardarse en el disco y dentro de una carpeta que esté abierta en el área de trabajo Visual Studio Code.
2. Si ha realizado cambios en el sistema o ha instalado los requisitos previos de Ionide con Visual Studio Code abrir, reinicie Visual Studio Code.
3. Compruebe que puede usar el F# compilador F# e interactivo desde la línea de comandos sin una ruta de acceso completa. Puede `fsc` hacerlo escribiendo en una línea de comandos para el `fsi` F# compilador y, o `fsharpi` bien para las F# herramientas visuales en Windows y mono en Mac/Linux, respectivamente.
4. Si tiene caracteres no válidos en los directorios del proyecto, es posible que Ionide no funcione.  Cambie el nombre de los directorios del proyecto si éste es el caso.
5. Si no funciona ninguno de los comandos de Ionide, compruebe los enlaces de la [Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) para ver si se están reemplazando por accidente.
6. Si Ionide se ha interrumpido en el equipo y ninguno de los anteriores ha solucionado el problema, `ionide-fsharp` intente quitar el directorio en la máquina y vuelva a instalar el conjunto de complementos.

Ionide es un proyecto de código abierto creado y mantenido por miembros de F# la comunidad. Informe de los problemas y no dude en contribuir en [el Ionide-VSCode: Repositorio](https://github.com/ionide/ionide-vscode-fsharp)de github de FSharp.

Si tiene un problema para notificar, siga [las instrucciones para obtener los registros que se van a usar al informar de un problema](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).

También puede solicitar más ayuda de la comunidad y F# los desarrolladores de Ionide en el [canal de Gitter de Ionide](https://gitter.im/ionide/ionide-project).

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información F# acerca de y las características del lenguaje, consulte el [paseo F# ](../tour.md)por.
