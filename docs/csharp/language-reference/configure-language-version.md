---
title: Seleccionar la versión del lenguaje C# - Guía de C#
description: Configurar el compilador para validar la sintaxis con una versión específica del compilador
ms.date: 05/24/2018
ms.openlocfilehash: 9b91e62168ced0f373e1a55def8b279dc64833d8
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208091"
---
# <a name="select-the-c-language-version"></a>Seleccionar la versión del lenguaje C#

El compilador de C# tiene como valor predeterminado la última versión principal del lenguaje que se haya publicado. Puede elegir compilar cualquier proyecto con una versión nueva del lenguaje. Elegir la versión más reciente del lenguaje permite que el proyecto use las últimas características de ese lenguaje. En otros escenarios, puede ser necesario validar que un proyecto se compile correctamente cuando se usa una versión anterior del lenguaje.

Esta capacidad hace que la decisión de instalar nuevas versiones del SDK y las herramientas en el entorno de desarrollo no esté vinculada a la decisión de incorporar nuevas características del lenguaje en un proyecto. Puede instalar el SDK y las herramientas más recientes en el equipo de compilación. Cada proyecto se puede configurar para que, durante su compilación, se use una versión de lenguaje específica.

Hay varias maneras de establecer la versión de idioma:

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
|default|El compilador acepta toda la sintaxis de lenguaje válida de la última versión principal que puede admitir.|
|ISO-1|El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2003 C# (1.0/1.2) |
|ISO-2|El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2006 C# (2.0) |
|3|El compilador acepta solo la sintaxis que se incluye en C# 3.0 o versiones anteriores.|
|4|El compilador acepta solo la sintaxis que se incluye en C# 4.0 o versiones anteriores.|
|5|El compilador acepta solo la sintaxis que se incluye en C# 5.0 o versiones anteriores.|
|6|El compilador acepta solo la sintaxis que se incluye en C# 6.0 o versiones anteriores.|
|7|El compilador acepta solo la sintaxis que se incluye en C# 7.0 o versiones anteriores.|
|7.1|El compilador acepta solo la sintaxis que se incluye en C# 7.1 o versiones anteriores.|
|7.2|El compilador acepta solo la sintaxis que se incluye en C# 7.2 o versiones anteriores.|
|7.3|El compilador acepta solo la sintaxis que se incluye en C# 7.3 o versiones anteriores.|
|latest|El compilador acepta toda la sintaxis de lenguaje válida que puede admitir.|

Las cadenas especiales `default` y `latest` se resuelven en las versiones de lenguaje principal (C# 7.0) y secundaria (C# 7.3) respectivamente más recientes que haya instaladas en el equipo de compilación.

## <a name="configure-multiple-projects"></a>Configurar varios proyectos

Puede crear un archivo **Directory.build.props** que contenga el elemento `<LangVersion>` para configurar varios directorios. Por lo general, esto se hace en el directorio de la solución. Agregue lo siguiente a un archivo **Directory.build.props** en el directorio de la solución:

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
