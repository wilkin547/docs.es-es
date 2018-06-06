---
title: 'Empezar a trabajar con F # en el código de Visual Studio'
description: 'Obtenga información acerca de cómo usar F # con código de Visual Studio y el conjunto de complemento Ionide.'
ms.date: 05/28/2018
ms.openlocfilehash: e56274caf36be231338876ded5a6d7c7968906b0
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728633"
---
# <a name="get-started-with-f-in-visual-studio-code"></a>Empezar a trabajar con F # en el código de Visual Studio

Puede escribir F # en [código de Visual Studio](https://code.visualstudio.com) con el [Ionide complemento](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)para obtener una gran experiencia de entorno de desarrollo integrado (IDE) de multiplataforma, ligera con IntelliSense y el código básico refactorizaciones. Visite [Ionide.io](http://ionide.io) para obtener más información sobre el conjunto de complementos.

## <a name="prerequisites"></a>Requisitos previos

Debe tener [git instalado](https://git-scm.com/download) y están disponibles en la ruta de acceso al hacer uso de plantillas de proyecto en Ionide. Puede comprobar que está instalado correctamente escribiendo `git --version` en un símbolo del sistema y presione **ENTRAR**.

### <a name="macostabmacos"></a>[macOS](#tab/macos)

Usa Ionide [Mono](http://www.mono-project.com). La manera más fácil de instalar Mono en macOS es a través de Homebrew. Basta con escribir lo siguiente en su terminal:

```
brew install mono
```

También debe instalar la [.NET Core SDK](https://www.microsoft.com/net/download).

### <a name="linuxtablinux"></a>[Linux](#tab/linux)

En Linux, también utiliza Ionide [Mono](https://www.mono-project.com). Si encuentra en Debian o Ubuntu, puede utilizar lo siguiente:

```
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

También debe instalar la [.NET Core SDK](https://www.microsoft.com/net/download).

### <a name="windowstabwindows"></a>[Windows](#tab/windows)

Si está en Windows, debe [instalar Visual Studio con compatibilidad con F #](get-started-visual-studio.md#installing-f). Esto instala todos los componentes necesarios para escribir, compilar y ejecutar código de F #.

También debe instalar la [.NET Core SDK](https://www.microsoft.com/net/download/).

---

## <a name="installing-visual-studio-code-and-the-ionide-plugin"></a>Instalar el complemento de Ionide y código de Visual Studio

Puede instalar Visual Studio Code desde el [code.visualstudio.com](https://code.visualstudio.com) sitio Web.

A continuación, haga clic en el icono de extensiones y busque "Ionide":

El complemento sólo para compatibilidad con F # en Visual Studio Code es [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Sin embargo, también puede instalar [Ionide emulación](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) para obtener [IMITAR](https://fsharp.github.io/FAKE/) admite y [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) para obtener [Paket](https://fsprojects.github.io/Paket/) admite. FALSIFICAR y Paket son F # Comunidad herramientas adicionales para compilar proyectos y administrar dependencias, respectivamente.

## <a name="creating-your-first-project-with-ionide"></a>Crear su primer proyecto con Ionide

Para crear un nuevo proyecto de F #, abra el código de Visual Studio en una nueva carpeta (puede nombre nombre que quiera).

A continuación, abrir la paleta de comando (**Vista > comando paleta**) y escriba lo siguiente:

```
> F# new project
```

Esto se realiza gracias la [FORGE](https://github.com/fsharp-editing/Forge) proyecto.

> [!NOTE]
Si no ve ninguna opción de plantilla, pruebe a actualizar plantillas ejecutando el siguiente comando en la paleta de comando: `>F#: Refresh Project Templates`.

Seleccione ": nuevo proyecto de F #" pulsando **ENTRAR**. Esto le llevará al paso siguiente, que es para seleccionar una plantilla de proyecto.

Elegir el `classlib` plantilla del sistema y presione **ENTRAR**.

A continuación, seleccione un directorio para crear el proyecto en. Si se deja en blanco, usa el directorio actual.

Por último, denomine el proyecto en el paso final. F # utiliza [mayúsculas y minúsculas Pascal](http://c2.com/cgi/wiki?PascalCase) para los nombres de proyecto. Este artículo usa `ClassLibraryDemo` como el nombre. Una vez que ha escrito el nombre que desea para el proyecto, presione **ENTRAR**.

Si ha seguido el paso anterior, debe obtener el Visual Studio código de área de trabajo en el lado izquierdo para que aparezca con lo siguiente:

1. F # del proyecto, debajo de la directiva la `ClassLibraryDemo` carpeta.
2. La estructura de directorio correcto para agregar paquetes a través de [ `Paket` ](https://fsprojects.github.io/Paket/).
3. Una multiplataforma Generar script con [ `FAKE` ](https://fsharp.github.io/FAKE/).
4. El `paket.exe` ejecutable que puede capturar paquetes y resolver las dependencias para usted.
5. Un `.gitignore` archivo si desea agregar este proyecto al control de origen basado en Git.

## <a name="writing-some-code"></a>Escribir código

Abra la *ClassLibraryDemo* carpeta.  Debería ver los siguientes archivos:

1. `ClassLibraryDemo.fs`, un archivo de implementación de F # con una clase definida.
2. `ClassLibraryDemo.fsproj`, un archivo de proyecto de F # utilizado para compilar este proyecto.
3. `Script.fsx`, un archivo script de F # que carga el archivo de origen.
4. `paket.references`, un archivo Paket que especifica las dependencias del proyecto.

Abra `Script.fsx`y agregue el código siguiente al final de la misma:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

Esta función convierte una palabra en un formulario de [Pig latino](https://en.wikipedia.org/wiki/Pig_Latin). El siguiente paso es evaluar con F # Interactive (FSI).

Resalte toda la función (debe ser 11 líneas de longitud). Una vez que se resalte, mantenga el **Alt** clave y posicionamiento **ENTRAR**. Verá una ventana emergente a continuación y debe mostrar algo parecido a esto:

![Ejemplo de salida de F # Interactive con Ionide](media/getting-started-vscode/vscode-fsi.png)

Esto hizo tres cosas:

1. Inició el proceso FSI.
2. El código resaltado que envían a través de los procesos FSI.
3. El proceso FSI evalúa el código enviados a través de.

Porque lo que envía a través no era un [función](../language-reference/functions/index.md), ahora puede llamar a esa función FSI! En la ventana interactiva, escriba lo siguiente:

```fsharp
toPigLatin "banana";;
```

Debe ver el siguiente resultado:

```fsharp
val it : string = "ananabay"
```

Ahora, vamos a intentarlo con una vocal como la primera letra. Escriba lo siguiente:

```fsharp
toPigLatin "apple";;
```

Debe ver el siguiente resultado:

```fsharp
val it : string = "appleyay"
```

La función parece funcionar según lo esperado. Enhorabuena, simplemente se escribió la primera función de F # en el código de Visual Studio y se evalúa con FSI.

>[!NOTE]
Tal y como se observa, las líneas de FSI terminan con `;;`. Esto es porque FSI le permite escribir varias líneas. El `;;` al final, FSI podrá saber cuando finalice el código.

## <a name="explaining-the-code"></a>Que explica el código

Si no está seguro de lo que realmente está haciendo el código, este es un paso a paso.

Como puede ver, `toPigLatin` es una función que toma una palabra como entrada y lo convierte en una representación de Pig latino de esa palabra. Las reglas para esto son los siguientes:

Si el primer carácter de una palabra comienza con una vocal, agregue "yay" al final de la palabra. Si no se inicia con una vocal, mover ese primer carácter al final de la palabra y "en" Agregar a ella.

Es podrán que haya observado lo siguiente en FSI:

```fsharp
val toPigLatin : word:string -> string
```

Esto indica que `toPigLatin` es una función que toma un `string` como entrada (llamado `word`) y devuelve otro `string`. Esto se conoce como el [signatura de tipo de la función](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fundamental de F #, que es clave para comprender el código de F #. También podrá observar si mantiene el mouse sobre la función en código de Visual Studio.

En el cuerpo de la función, verá dos partes distintas:

1. Una función interna, denominada `isVowel`, que determina si un carácter determinado (`c`) es una vocal comprobando si coincide con uno de los modelos proporcionados a través de [coincidencia de patrones](../language-reference/pattern-matching.md):

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. Un [ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) expresión que comprueba si el primer carácter es una vocal, y construcciones un retorno de valor fuera de los caracteres de entrada según if el primer carácter era una vocal o no:

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

El flujo de `toPigLatin` es así:

Compruebe si el primer carácter de la palabra de entrada es una vocal. Si es así, adjuntar "yay" al final de la palabra. En caso contrario, mueva ese primer carácter al final de la palabra y "en" Agregar a ella.

Hay una última cosa deben tener en cuenta esto: no hay ninguna instrucción explícita para devolver de la función, a diferencia de muchos otros lenguajes por ahí. Esto es porque F # es basadas en expresiones y la última expresión en el cuerpo de una función es el valor devuelto. Dado que `if..then..else` es en sí mismo una expresión, el cuerpo de la `then` bloque o en el cuerpo de la `else` bloque se devolverán según el valor de entrada.

## <a name="moving-your-script-code-into-the-implementation-file"></a>Mover el código de script en el archivo de implementación

Las secciones anteriores de este artículo muestran un primer paso comunes para escribir código de F #: escribir una función inicial y se ejecuta de forma interactiva con FSI. Esto se conoce como el desarrollo basado en replicación, donde [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) es el acrónimo "Bucle de impresión evaluar lectura". Es una excelente manera de experimentar con funcionalidad hasta que haya algo a funcionar.

El siguiente paso en el desarrollo controlado por la replicación es mover el código de trabajo en un archivo de implementación de F #. A continuación, se pueden compilar por el compilador de F # en un ensamblado que se pueden ejecutar.

Para comenzar, abra `ClassLibraryDemo.fs`.  Observará que parte del código está en ella. Siga adelante y eliminar la definición de clase, pero asegúrese de dejar el [ `namespace` ](../language-reference/namespaces.md) declaración en la parte superior.

A continuación, cree un nuevo [ `module` ](../language-reference/modules.md) llama `PigLatin` y copie la `toPigLatin` función en él como tales:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

A continuación, abra el `Script.fsx` archivo nuevo y eliminar toda la matriz `toPigLatin` funcionando, pero debe asegurarse de mantener las dos líneas siguientes en el archivo:

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

La primera línea es necesario para FSI secuencias de comandos para cargar `ClassLibraryDemo.fs`. La segunda línea es su comodidad: omitiéndola es opcional, pero debe escribir `open ClassLibraryDemo` en una ventana FSI si desea volver a poner el `ToPigLatin` módulo en el ámbito.

A continuación, en la ventana FSI, llame a la función con el `PigLatin` módulo que definió anteriormente:

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

Correcto Obtener los mismos resultados que antes, pero ahora se carga desde un archivo de implementación de F #. La principal diferencia es que los archivos de código fuente de F # se compilan en ensamblados que se pueden ejecutar en cualquier lugar, no solo en FSI.

## <a name="summary"></a>Resumen

En este artículo, ha aprendido:

1. Cómo configurar el código de Visual Studio con Ionide.
2. Cómo crear su primer proyecto de F # con Ionide.
3. Describe cómo usar Scripting F # para escribir su primera función de F # en Ionide y, a continuación, se ejecutan en FSI.
4. Cómo migrar el código de script al código fuente de F # y, a continuación, llame a ese código desde FSI.

Ahora está equipado para escribir mucho más código F # mediante código de Visual Studio y Ionide.

## <a name="troubleshooting"></a>Solución de problemas

Aquí se muestran algunas maneras de que puede solucionar determinados problemas que pueden surgir:

1. Para obtener la características de Ionide de edición de código, los archivos de F # deben guardarse en el disco y dentro de una carpeta que está abierta en el área de trabajo de código de Visual Studio.
2. Si ha realizado cambios en el sistema o instalar requisitos previos de Ionide con código de Visual Studio abierto, reinicie Visual Studio Code.
3. Compruebe que puede utilizar el compilador de F # y F # interactive desde la línea de comandos sin una ruta de acceso completa. Puede hacerlo escribiendo `fsc` en una línea de comandos para el compilador de F #, y `fsi` o `fsharpi` para Visual F # las herramientas de Windows y Mono en Mac o Linux, respectivamente.
4. Si tiene caracteres no válidos en los directorios del proyecto, Ionide podrían no funcionar.  Cambiar el nombre de los directorios del proyecto si éste es el caso.
5. Si ninguno de los comandos Ionide está trabajando, compruebe su [enlaces de teclado de Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) para ver si se está reemplazando por accidente.
6. Si se divide Ionide en su equipo y ninguno de los anteriores solucionó el problema, pruebe a quitar el `ionide-fsharp` directorio en su equipo y vuelva a instalar el conjunto de complementos.

Ionide es un proyecto de código abierto crea y mantiene los miembros de la Comunidad de F #. Por favor, notificar problemas y no dude en contribuir en el [Ionide VSCode: repositorio de FSharp GitHub](https://github.com/ionide/ionide-vscode-fsharp).

Si tiene un problema al informe, siga [las instrucciones para obtener los registros que se utilizará al informar de un problema](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).

También puede pedir ayuda adicional de los desarrolladores de Ionide y la Comunidad de F # en el [Ionide Gitter canal](https://gitter.im/ionide/ionide-project).

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información sobre F # y las características del lenguaje, visite [paseo de F #](../tour.md).
