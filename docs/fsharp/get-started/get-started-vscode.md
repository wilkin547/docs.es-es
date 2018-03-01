---
title: "Introducción a F # en el código de Visual Studio con Ionide"
description: "Obtenga información acerca de cómo usar F # con código de Visual Studio y el conjunto de complemento Ionide."
keywords: "Visual f #, f #, funcional de programación,. NET, Visual Studio Code, vscode, Ionide"
author: cartermp
ms.author: phcart
ms.date: 09/28/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 49775139-082e-442f-b5a2-dd402399b5d2
ms.openlocfilehash: 83099005074ea273eae5319edacd2e2ee0f7145f
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="getting-started-with-f-in-visual-studio-code-with-ionide"></a>Introducción a F # en el código de Visual Studio con Ionide

Puede escribir F # en [código de Visual Studio](https://code.visualstudio.com) con el [Ionide complemento](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp)para obtener una gran experiencia IDE multiplataforma, ligera con IntelliSense y refactorizaciones código básico.  Visite [Ionide.io](https://ionide.io) para obtener más información sobre el conjunto de complementos.

## <a name="prerequisites"></a>Requisitos previos

F # 4.0 o posterior debe instalarse en el equipo para usar Ionide.

También debe tener [git instalado](https://git-scm.com/download) y están disponibles en la ruta de acceso al hacer uso de plantillas de proyecto en Ionide.  Puede comprobar que está instalado correctamente escribiendo `git` en una si presiona prompt.and de comando **ENTRAR**.

### <a name="windows"></a>Windows

Si está en Windows, tiene dos opciones para la instalación de F #.

Si ya ha instalado Visual Studio y no tiene F #, también puede [instalar las herramientas de Visual F #](get-started-visual-studio.md#installing-f).  Este modo se instalará todos los componentes necesarios para escribir, compilar y ejecutar código de F #.

Si prefiere no instalar Visual Studio, utilice las siguientes instrucciones:

1. Instalar [.NET Framework 4.5 o posterior](https://www.microsoft.com/en-US/download/details.aspx?id=30653) si ejecuta Windows 7.  Si usa Windows 8 o posterior, no es necesario hacer esto.

2. Instale el SDK de Windows para el sistema operativo:

    * [Windows 10 SDK](https://dev.windows.com/en-US/downloads/windows-10-sdk)
    * [Windows 8.1 SDK](https://developer.microsoft.com/windows/downloads/sdk-archive)
    * [Windows 8 SDK](https://developer.microsoft.com/windows/downloads/sdk-archive)
    * [Windows 7 SDK](https://www.microsoft.com/download/details.aspx?id=8279)

3. Instalar el [herramientas de generación de Microsoft 2015](https://www.microsoft.com/en-us/download/details.aspx?id=48159).  También puede que deba instalar [2013 de herramientas de compilación de Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=40760).

4. Instalar el [herramientas de Visual F #](https://www.microsoft.com/en-us/download/details.aspx?id=48179).

En Windows de 64 bits, el compilador y las herramientas se encuentran aquí:

```
C:\Program Files (x86)\Microsoft SDKs\F#\4.0\Framework\v4.0\fsc.exe
C:\Program Files (x86)\Microsoft SDKs\F#\4.0\Framework\v4.0\fsi.exe
C:\Program Files (x86)\Microsoft SDKs\F#\4.0\Framework\v4.0\fsiAnyCpu.exe
```

En Windows de 32 bits, las herramientas del compilador se encuentran aquí:

```
C:\Program Files\Microsoft SDKs\F#\4.0\Framework\v4.0\fsc.exe
C:\Program Files\Microsoft SDKs\F#\4.0\Framework\v4.0\fsi.exe
C:\Program Files\Microsoft SDKs\F#\4.0\Framework\v4.0\fsiAnyCpu.exe
```

Ionide detecta automáticamente el compilador y las herramientas, pero si no es así por algún motivo (por ejemplo, las herramientas de Visual F # se instala en un directorio distinto), puede agregar manualmente la carpeta contenedora (`...\Microsoft SDKs\F#\4.0`) a la ruta de acceso.

### <a name="macos"></a>macOS

En Mac OS, usa Ionide [Mono](https://www.mono-project.com).  La manera más fácil de instalar Mono en macOS es a través de Homebrew.  Basta con escribir lo siguiente en su terminal:

```
brew install mono
```

### <a name="linux"></a>Linux

En Linux, también utiliza Ionide [Mono](https://www.mono-project.com).  Si encuentra en Debian o Ubuntu, puede utilizar lo siguiente:

```
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

## <a name="installing-visual-studio-code-and-the-ionide-plugin"></a>Instalar el complemento de Ionide y código de Visual Studio

Puede instalar Visual Studio Code desde el [code.visualstudio.com](https://code.visualstudio.com) sitio Web.  Después de eso, hay dos formas de buscar el complemento Ionide:

1. Usa la paleta de comando (Ctrl + Mayús + P en Windows, ⌘ + MAYÚS + P en macOS, Ctrl + Mayús + P en Linux) y escriba lo siguiente:

    ```
    >ext install Ionide
    ```

2. Haga clic en el icono de extensiones y busque "Ionide":

    ![](media/getting-started-vscode/vscode-ext.png)

El complemento sólo para compatibilidad con F # en Visual Studio Code es [Ionide fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp).  Sin embargo, también puede instalar [Ionide emulación](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) y para obtener [IMITAR](https://fake.build/) admite y [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) para obtener [Paket](https://fsprojects.github.io/Paket/) admite.  FALSIFICAR y Paket son herramientas de la Comunidad de datos adicionales sobre F # para compilar proyectos y administrar dependencias, respectivamente.

## <a name="creating-your-first-project-with-ionide"></a>Crear su primer proyecto con Ionide

Para crear un nuevo proyecto de F #, abra el código de Visual Studio en una nueva carpeta (puede nombre nombre que quiera).

![](media/getting-started-vscode/vscode-open-dir.png)

A continuación, abra la paleta de comando (Ctrl + Mayús + P en Windows, ⌘ + MAYÚS + P en macOS, Ctrl + Mayús + P en Linux) y escriba lo siguiente:

```
>f#: New Project
```

Esto se realiza gracias la [FORGE](https://github.com/fsharp-editing/Forge) proyecto.  Verá algo parecido a esto:

![](media/getting-started-vscode/vscode-new-proj.png)

> [!NOTE]
Si no ve los pasos anteriores, pruebe a actualizar plantillas ejecutando el siguiente comando en la paleta de comando: `>F#: Refresh Project Templates`.

Seleccione ": nuevo proyecto de F #" pulsando **ENTRAR**, que le permitirán a este paso:

![](media/getting-started-vscode/vscode-proj-type.png)

Se seleccionarán una plantilla para un tipo específico de proyecto.  Existen varias opciones en este caso, como un [FsLab](https://fslab.org) plantilla de ciencia de datos o [Suave](https://suave.io) plantilla de programación Web.  Este artículo se utiliza la `classlib` plantilla, por lo que resaltar que y presione **ENTRAR**.  A continuación, se le mostrará el paso siguiente:

![](media/getting-started-vscode/vscode-new-dir.png)

Esto le permite crear el proyecto en un directorio diferente, si lo desea.  Déjelo en blanco por ahora.  Creará el proyecto en el directorio actual.  Una vez que se presiona **ENTRAR**, alcanzará el paso siguiente:

![](media/getting-started-vscode/vscode-proj-name.png)

Esto le permite nombre para el proyecto.  F # utiliza [mayúsculas y minúsculas Pascal](http://c2.com/cgi/wiki?PascalCase) para los nombres de proyecto.  Este artículo usa `ClassLibraryDemo` como el nombre.  Una vez que ha escrito el nombre que desea para el proyecto, presione **ENTRAR**.

Si ha seguido los pasos del paso anterior, debería obtener Visual Studio código de área de trabajo en el lado izquierdo para el siguiente aspecto:

![](media/getting-started-vscode/vscode-new-proj-explorer.png)

Esta plantilla genera algunas cosas que puede encontrar útiles:

1. F # del proyecto, debajo de la directiva la `ClassLibraryDemo` carpeta.
2. La estructura de directorio correcto para agregar paquetes a través de [ `Paket` ](https://fsprojects.github.io/Paket/).
3. Una multiplataforma Generar script con [ `FAKE` ](https://fake.build/).
4. El `paket.exe` archivo ejecutable que puede capturar paquetes y resolver las dependencias para usted.
5. Un `.gitignore` archivo si desea agregar este proyecto al control de origen basado en Git.

## <a name="writing-some-code"></a>Escribir código

Abra la *ClassLibraryDemo* carpeta.  Debería ver los siguientes archivos:

1. `ClassLibraryDemo.fs`, un archivo de implementación de F # con una clase definida.
2. `CassLibraryDemo.fsproj`, un archivo de proyecto de F # utilizado para compilar este proyecto.
3. `Script.fsx`, un archivo script de F # que carga el archivo de origen.
4. `paket.references`, un archivo Paket que especifica las dependencias del proyecto.

Abra `Script.fsx`y agregue el código siguiente al final de la misma:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

Esta función convierte una palabra en un formulario de [Pig latino](https://en.wikipedia.org/wiki/Pig_Latin).  El siguiente paso es evaluar con F # Interactive (FSI).

Resalte toda la función (debe ser 11 líneas de longitud).  Una vez que se resalte, mantenga el **Alt** clave y posicionamiento **ENTRAR**.  Verá una ventana emergente a continuación y debe mostrar algo parecido a esto:

![](media/getting-started-vscode/vscode-fsi.png)

Esto hizo tres cosas:

1. Inició el proceso FSI.
2. El código resaltado que envían a través de los procesos FSI.
3. El proceso FSI evalúa el código enviados a través de.

Porque lo que envía a través no era un [función](../language-reference/functions/index.md), ahora puede llamar a esa función FSI!  En la ventana interactiva, escriba lo siguiente:

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

La función parece funcionar según lo esperado.  Enhorabuena, simplemente se escribió la primera función de F # en el código de Visual Studio y se evalúa con FSI.

>[!NOTE]
Tal y como se observa, las líneas de FSI terminan con `;;`.  Esto es porque FSI le permite escribir varias líneas.  El `;;` al final, FSI podrá saber cuando finalice el código.

## <a name="explaining-the-code"></a>Que explica el código

Si no está seguro de lo que realmente está haciendo el código, este es un paso a paso.

Como puede ver, `toPigLatin` es una función que toma una palabra como entrada y lo convierte en una representación de Pig latino de esa palabra.  Las reglas para esto son los siguientes:

Si el primer carácter de una palabra comienza con una vocal, agregue "yay" al final de la palabra.  Si no se inicia con una vocal, mover ese primer carácter al final de la palabra y "en" Agregar a ella.

Es podrán que haya observado lo siguiente en FSI:

```
val toPigLatin : word:string -> string
```

Esto indica que `toPigLatin` es una función que toma un `string` como entrada (llamado `word`) y devuelve otro `string`.  Esto se conoce como el [signatura de tipo de la función](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fundamental de F #, que es clave para comprender el código de F #.  También podrá observar si mantiene el mouse sobre la función en código de Visual Studio.

En el cuerpo de la función, verá dos partes distintas:

1. Una función interna, denominada `isVowel`, que determina si un carácter determinado (`c`) es una vocal comprobando si coincide con uno de los modelos proporcionados a través de [coincidencia de patrones](../language-reference/pattern-matching.md):

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. Un [ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) que comprueba si el primer carácter es una vocal y construye un valor devuelto de los caracteres de entrada en función de if el primer carácter de expresión era una vocal o no:

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

El flujo de `toPigLatin` es así:

Compruebe si el primer carácter de la palabra de entrada es una vocal.  Si es así, adjuntar "yay" al final de la palabra.  En caso contrario, mueva ese primer carácter al final de la palabra y "en" Agregar a ella.

Hay una última cosa deben tener en cuenta esto: no hay ninguna instrucción explícita para devolver de la función, a diferencia de muchos otros lenguajes por ahí.  Esto es porque F # es basadas en expresiones y la última expresión en el cuerpo de una función es el valor devuelto.  Dado que `if..then..else` es en sí mismo una expresión, el cuerpo de la `then` bloque o en el cuerpo de la `else` bloque se devolverán según el valor de entrada.

## <a name="moving-your-script-code-into-the-implementation-file"></a>Mover el código de script en el archivo de implementación

Las secciones anteriores de este artículo muestran un primer paso comunes para escribir código de F #: escribir una función inicial y se ejecuta de forma interactiva con FSI.  Esto se conoce como el desarrollo basado en la replicación, donde REPL representa "Bucle de impresión evaluar lectura".  Es una excelente manera de experimentar con funcionalidad hasta que haya algo a funcionar.

El siguiente paso en el desarrollo controlado por la replicación es mover el código de trabajo en un archivo de implementación de F #.  A continuación, se pueden compilar por el compilador de F # en un ensamblado que se puede ejecutar.

Para comenzar, abra `ClassLibraryDemo.fs`.  Observará que parte del código está en ella.  Siga adelante y eliminar la definición de clase, pero asegúrese de dejar el [ `namespace` ](../language-reference/namespaces.md) declaración en la parte superior.

A continuación, cree un nuevo [ `module` ](../language-reference/modules.md) llama `PigLatin` y copie la `toPigLatin` función en él como tales:

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

Esta es una de las muchas maneras de que organizar las funciones en código de F # y un enfoque común si también desea llamar al código de C# o proyectos de Visual Basic.

A continuación, abra el `Script.fsx` archivo nuevo y eliminar toda la matriz `toPigLatin` funcionando, pero debe asegurarse de mantener las dos líneas siguientes en el archivo:

```
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

La primera línea es necesario para FSI secuencias de comandos para cargar `ClassLibraryDemo.fs`.  La segunda línea es su comodidad: omitiéndola es opcional, pero debe escribir `open ClassLibraryDemo` en una ventana FSI si desea volver a poner el `ToPigLatin` módulo en el ámbito.

A continuación, en la ventana FSI, llame a la función con el `PigLatin` módulo que definió anteriormente:

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

Correcto  Obtener los mismos resultados que antes, pero ahora se carga desde un archivo de implementación de F #.  La principal diferencia es que los archivos de código fuente de F # se compilan en ensamblados que se pueden ejecutar en cualquier lugar, no solo en FSI.

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
3. Compruebe que puede utilizar el compilador de F # y F # interactive desde la línea de comandos sin una ruta de acceso completa.  Puede hacerlo escribiendo `fsc` en una línea de comandos para el compilador de F #, y `fsi` o `fsharpi` para Visual F # las herramientas de Windows y Mono en Mac o Linux, respectivamente.
4. Si tiene caracteres no válidos en los directorios del proyecto, Ionide podrían no funcionar.  Cambiar el nombre de los directorios del proyecto si éste es el caso.
5. Si ninguno de los comandos Ionide está trabajando, compruebe su [enlaces de teclado de Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) para ver si se está reemplazando por accidente.
6. Si se divide Ionide en su equipo y ninguno de los anteriores solucionó el problema, pruebe a quitar el `ionide-fsharp` directorio en su equipo y vuelva a instalar el conjunto de complementos.

Ionide es un proyecto de código abierto crea y mantiene los miembros de la Comunidad de F #.  Por favor, notificar problemas y no dude en contribuir en el [Ionide VSCode: repositorio de FSharp GitHub](https://github.com/ionide/ionide-vscode-fsharp).

Si tiene un problema al informe, siga [las instrucciones para obtener los registros que se utilizará al informar de un problema](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).

También puede pedir ayuda adicional de los desarrolladores de Ionide y la Comunidad de F # en el [Ionide Gitter canal](https://gitter.im/ionide/ionide-project).

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información sobre F # y las características del lenguaje, visite [paseo de F #](../tour.md).

## <a name="see-also"></a>Vea también

[Paseo por F](../tour.md)

[Referencia del lenguaje F#](../language-reference/index.md)

[Funciones](../language-reference/functions/index.md)

[Módulos](../language-reference/modules.md)

[Espacios de nombres](../language-reference/namespaces.md)

[Tutorial de VSCode Ionide: FSharp](https://github.com/ionide/ionide-vscode-fsharp)
