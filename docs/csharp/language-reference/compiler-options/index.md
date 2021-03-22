---
description: Opciones del compilador de C# Obtenga más información sobre las opciones que controlan el comportamiento del compilador de C#.
title: Opciones del compilador de C#
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
ms.openlocfilehash: cbe4db51652e8bfd00c555b6ddd230e124a08360
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103478469"
---
# <a name="c-compiler-options"></a>Opciones del compilador de C#

En esta sección se describen las opciones que interpreta el compilador de C#. Hay dos formas de establecer las opciones del compilador en los proyectos de .NET:

- ***Especificar la opción en el \*archivo .csproj***: puede agregar elementos XML para cualquier opción del compilador en el archivo *\*.csproj*. El nombre del elemento es el mismo que el de la opción del compilador. El valor del elemento XML establece el valor de la opción del compilador. Para obtener más información sobre el procedimiento para establecer las opciones en los archivos de proyecto, consulte el artículo [Referencia de MSBuild para proyectos del SDK de .NET](../../../core/project-sdk/msbuild-props.md).
- ***Usar las páginas Propiedad de Visual Studio***: Visual Studio cuenta con páginas de propiedades para editar las propiedades de compilación. Para obtener más información al respecto, consulte [Administrar propiedades de soluciones y proyectos (Windows)](/visualstudio/ide/managing-project-and-solution-properties#c-visual-basic-and-f-projects) y [Administrar propiedades de soluciones y proyectos (Mac)](/visualstudio/mac/managing-solutions-and-project-properties).

## <a name="net-framework-projects"></a>Proyectos de .NET Framework

> [!IMPORTANT]
> Esta sección solo se aplica a los proyectos de .NET Framework.

Además de los mecanismos descritos anteriormente, puede establecer las opciones del compilador por medio de dos métodos más para los proyectos de .NET Framework:

- **Argumentos de la línea de comandos para proyectos de .NET Framework**: los proyectos de .NET Framework usan *csc.exe* en lugar de `dotnet build` para compilar los proyectos. En el caso de los proyectos de .NET Framework, puede especificar argumentos de la línea de comandos a *csc.exe*.
- **Páginas de ASP.NET compiladas**: los proyectos de .NET Framework usan una sección del archivo *web.config* para compilar páginas. Para el nuevo sistema de compilación, así como los proyectos de ASP.NET Core, las opciones se toman del archivo del proyecto.

En el caso de algunas opciones del compilador, la palabra ha cambiado de *csc.exe* al nuevo sistema de MSBuild, y también para los proyectos de .NET Framework. En esta sección se emplea la nueva sintaxis. Ambas versiones figuran al principio de cada página. Para *csc.exe*, los argumentos figuran seguidos de la opción y dos puntos. Por ejemplo, la opción `-doc` sería:

```console
-doc:DocFile.xml
```

Puede invocar el compilador de C# escribiendo el nombre de su archivo ejecutable (*csc.exe*) en un símbolo del sistema.

En el caso de los proyectos de .NET Framework, también puede ejecutar *csc.exe* mediante la línea de comandos. Cada opción del compilador está disponible en dos formatos: **-option** y **/option**. En los proyectos web de .NET Framework, debe especificar las opciones para compilar el código subyacente en el archivo *web.config*. Para obtener más información, consulte [Elemento \<compiler>](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).

Si usa la ventana **Símbolo del sistema para desarrolladores de Visual Studio**, todas las variables de entorno necesarias se establecen automáticamente. Para obtener información sobre cómo acceder a esta herramienta, vea [Símbolo del sistema para desarrolladores de Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).

El archivo ejecutable *csc.exe* normalmente se encuentra en la carpeta Microsoft.NET\Framework\\ *\<Version>* , en el directorio *Windows*. Su ubicación puede variar, según la configuración exacta de un equipo concreto. Si se instala más de una versión de .NET Framework en el equipo, encontrará varias versiones de este archivo. Para obtener más información sobre estas instalaciones, vea [Cómo: Determinar qué versiones de .NET Framework están instaladas](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md).
