---
description: Otras opciones del compilador de C#. Estas opciones proporcionan opciones generales para el compilador.
title: Opciones del compilador de C# que no encajan en otras categorías
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- ResponseFiles compiler option [C#]
- NoLogo compiler option [C#]
- NoConfig compiler option [C#]
ms.openlocfilehash: ec7d9c3685c9acb5ca3cda28aca55abb26b836cf
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482477"
---
# <a name="miscellaneous-c-compiler-options"></a>Otras opciones del compilador de C#

Las opciones siguientes controlan distintos comportamientos del compilador. La nueva sintaxis de MSBuild se muestra en **negrita**. La sintaxis de *csc.exe* anterior se muestra en `code style`.

- **ResponseFiles** / `-@`: se lee el archivo de respuesta para ver más opciones.
- **NoLogo** / `-nologo`: se suprime el mensaje de copyright del compilador.
- **NoConfig** / `-noconfig`: no se incluye el archivo *CSC.RSP* de forma automática.

## <a name="responsefiles"></a>ResponseFiles

La opción **ResponseFiles** le permite especificar un archivo que contiene opciones del compilador y archivos de código fuente para compilar.

```xml
<ResponseFiles>response_file</ResponseFiles>
```

`response_file` especifica el archivo en el que se enumeran las opciones del compilador o los archivos de código fuente que se van a compilar. El compilador procesará las opciones del compilador y los archivos de código fuente como si se hubieran especificado en la línea de comandos. Para especificar más de un archivo de respuesta en una compilación, especifique varias opciones de archivo de respuesta. En un archivo de respuesta, puede haber varias opciones del compilador y archivos de código fuente en una sola línea. Una sola especificación de opción del compilador debe aparecer en una línea (no puede abarcar varias). Los archivos de respuesta pueden tener comentarios que comiencen con el símbolo #. Especificar opciones del compilador desde un archivo de respuesta es igual que enviar esos comandos en la línea de comandos. El compilador procesa las opciones de comando a medida que se leen. Los argumentos de línea de comandos pueden reemplazar las opciones enumeradas anteriormente en archivos de respuesta. Por el contrario, las opciones en un archivo de respuesta reemplazarán las opciones enumeradas anteriormente en la línea de comandos o en otros archivos de respuesta. C# proporciona el archivo csc.rsp, que se encuentra en el mismo directorio que el archivo csc.exe. Para obtener más información sobre el formato de archivo de respuesta, vea [**NoConfig**](#noconfig). No se puede establecer esta opción del compilador en el entorno de desarrollo de Visual Studio, ni se puede cambiar mediante programación. Estas son algunas líneas de un archivo de respuesta de ejemplo:

```console
# build the first output file
-target:exe -out:MyExe.exe source1.cs source2.cs
```

## <a name="nologo"></a>NoLogo

La opción **NoLogo** suprime la presentación del banner de inicio de sesión cuando se inicia el compilador y muestra mensajes informativos durante la compilación.

```xml
<NoLogo>true</NoLogo>
```

## <a name="noconfig"></a>NoConfig

La opción **NoConfig** indica al compilador que no realice la compilación con el archivo *csc.rsp*.

```xml
<NoConfig>true</NoConfig>
```

El archivo *csc.rsp* hace referencia a todos los ensamblados incluidos en .NET Framework. Las referencias reales que incluye el entorno de desarrollo Visual Studio de .NET dependen del tipo de proyecto. Es posible modificar el archivo *csc.rsp* y especificar opciones del compilador adicionales que se deban incluir en todas las compilaciones. Si no quiere que el compilador busque y use la configuración del archivo *csc.rsp*, especifique **NoConfig**. Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.
