---
title: Seleccionar la versión del lenguaje C# - Guía de C#
description: Configurar el compilador para validar la sintaxis con una versión específica del compilador
ms.date: 02/28/2019
ms.openlocfilehash: feb3e51a107f9830071b55c7985f202edc842f4a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770885"
---
# <a name="select-the-c-language-version"></a>Seleccionar la versión del lenguaje C#

El compilador de C# determina una versión de lenguaje predeterminada basada en los marcos o las plataformas de destino del proyecto. Cuando el proyecto tiene como destino un marco en versión preliminar que tenga una versión de lenguaje preliminar correspondiente, la versión de lenguaje que se usa es la que está en versión preliminar. Cuando el proyecto no tiene como destino un marco en versión preliminar, la versión de lenguaje que se usa es la secundaria más reciente.

Por ejemplo, durante el período de versión preliminar de .NET Core 3.0, cualquier proyecto que tenga como destino `netcoreapp3.0` o `netstandard2.1` (en versión preliminar) usará el lenguaje C# 8.0 (también en versión preliminar). Los proyectos que tienen como destino cualquier versión de lanzamiento usarán C# 7.3 (la última versión publicada). Este comportamiento significa que cualquier proyecto que tenga como destino .NET Framework usará la versión más reciente (C# 7.3). 

Esta capacidad hace que la decisión de instalar nuevas versiones del SDK y las herramientas en el entorno de desarrollo no esté vinculada a la decisión de incorporar nuevas características del lenguaje en un proyecto. Puede instalar el SDK y las herramientas más recientes en el equipo de compilación. Cada proyecto se puede configurar para que, durante su compilación, se use una versión de lenguaje específica. El comportamiento predeterminado significa que están habilitadas las características de lenguaje que se basan en nuevos tipos o un nuevo comportamiento de CLR habilitados solo cuando los proyectos tienen como destino esas plataformas de destino.

Puede invalidar el comportamiento predeterminado especificando una versión de lenguaje. Hay varias maneras de establecer la versión de idioma:

- Basarse en una [acción rápida de Visual Studio](#visual-studio-quick-action).
- Establecer la versión del lenguaje en la [interfaz de usuario de Visual Studio](#set-the-language-version-in-visual-studio).
- Editar manualmente el archivo [**.csproj** ](#edit-the-csproj-file).
- Establecer la versión del lenguaje [para varios proyectos en un subdirectorio](#configure-multiple-projects).
- Configurar la opción dl compilador [Reemplace la opción del compilador `-langversion`](#set-the-langversion-compiler-option).

## <a name="visual-studio-quick-action"></a>Acción rápida de Visual Studio

Visual Studio le ayuda a determinar la versión de idioma que necesita. Si usa una característica del lenguaje que no está disponible para la versión configurada actualmente, Visual Studio le propone una solución para actualizar la versión de lenguaje del proyecto.

## <a name="set-the-language-version-in-visual-studio"></a>Establecer la versión de idioma en Visual Studio

Puede establecer la versión de idioma en Visual Studio. En el Explorador de soluciones, haga clic con el botón derecho en el nodo del proyecto y seleccione **Propiedades**. Seleccione la pestaña **Compilar** y, después, el botón **Opciones avanzadas**. En la lista desplegable, seleccione la versión. La siguiente imagen muestra el valor "más reciente":

![Captura de pantalla de la configuración de compilación avanzada en la que se puede especificar la versión del lenguaje](./media/configure-language-version/advanced-build-settings.png)

> [!NOTE]
> Si usa el IDE de Visual Studio para actualizar los archivos csproj, este creará nodos independientes por cada configuración de compilación existente. Normalmente, se establece el mismo valor en todas las configuraciones de compilación, pero deberá establecerse de forma explícita en cada configuración de compilación, o bien seleccionar "All Configurations" (Todas las configuraciones) cuando este valor se modifique. Verá lo siguiente en el archivo csproj:
>
>```xml
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
>  <LangVersion>latest</LangVersion>
></PropertyGroup>
>
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
>  <LangVersion>latest</LangVersion>
> </PropertyGroup>
> ```
>

## <a name="edit-the-csproj-file"></a>Editar el archivo csproj

Puede establecer la versión del lenguaje en el archivo **.csproj**. Agregue un elemento similar al siguiente:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

El valor `latest` usa la versión secundaria más reciente del lenguaje C#. Los valores válidos son:

|Valor|Significado|
|------------|-------------|
|preview|El compilador acepta toda la sintaxis de lenguaje válida de la última versión preliminar.|
|latest|El compilador acepta la sintaxis de la última versión del compilador (incluida las versión secundaria).|
|latestMajor|El compilador acepta la sintaxis de la versión principal más reciente del compilador.|
|8.0|El compilador acepta solo la sintaxis que se incluye en C# 8.0 o versiones anteriores.|
|7.3|El compilador acepta solo la sintaxis que se incluye en C# 7.3 o versiones anteriores.|
|7.2|El compilador acepta solo la sintaxis que se incluye en C# 7.2 o versiones anteriores.|
|7.1|El compilador acepta solo la sintaxis que se incluye en C# 7.1 o versiones anteriores.|
|7|El compilador acepta solo la sintaxis que se incluye en C# 7.0 o versiones anteriores.|
|6|El compilador acepta solo la sintaxis que se incluye en C# 6.0 o versiones anteriores.|
|5|El compilador acepta solo la sintaxis que se incluye en C# 5.0 o versiones anteriores.|
|4|El compilador acepta solo la sintaxis que se incluye en C# 4.0 o versiones anteriores.|
|3|El compilador acepta solo la sintaxis que se incluye en C# 3.0 o versiones anteriores.|
|ISO-2|El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2006 C# (2.0) |
|ISO-1|El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2003 C# (1.0/1.2) |

## <a name="configure-multiple-projects"></a>Configurar varios proyectos

Puede crear un archivo **Directory.Build.props** que contenga el elemento `<LangVersion>` para configurar varios directorios. Por lo general, esto se hace en el directorio de la solución. Agregue lo siguiente a un archivo **Directory.Build.props** en el directorio de la solución:

```xml
<Project>
 <PropertyGroup>
   <LangVersion>7.3</LangVersion>
 </PropertyGroup>
</Project>
```

Ahora, las compilaciones de cada subdirectorio del directorio que contenga ese archivo usarán la sintaxis de la versión 7.3 de C#. Para obtener más información, consulte el artículo [Personalizar una compilación](/visualstudio/msbuild/customize-your-build).

## <a name="set-the-langversion-compiler-option"></a>Establecer la opción del compilador langversion

Puede usar la opción de la línea de comandos `-langversion`. Para obtener más información, consulte el artículo sobre la opción del compilador [-langversion](../language-reference/compiler-options/langversion-compiler-option.md). Para ver una lista de los valores válidos, escriba `csc -langversion:?`.
