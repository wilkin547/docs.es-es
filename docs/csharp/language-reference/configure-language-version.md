---
title: 'Control de versiones del lenguaje C#: Guía de C#'
description: Obtenga información sobre cómo la versión del lenguaje C# se determina en función del proyecto y los distintos valores a los que puede ajustarlo manualmente.
ms.date: 07/10/2019
ms.openlocfilehash: 3c1035d983660ea0a945e4d4b7b72c69736c90cb
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980137"
---
# <a name="c-language-versioning"></a>Control de versiones del lenguaje C#

El compilador de C# más actualizado determina una versión de lenguaje predeterminada basada en los marcos o las plataformas de destino del proyecto. Esto se debe a que el lenguaje C# puede tener características que se basan en tipos o componentes en tiempo de ejecución que no están disponibles en cada implementación de. NET. Esto también garantiza que, para cualquier destino para el cual se compiló el proyecto, obtendrá la última versión de lenguaje compatible de forma predeterminada.

Las reglas de este artículo se aplican al compilador ofrecido con Visual Studio 2019 o al SDK de .NET Core 3.0. Los compiladores de C# que forman parte de la instalación de Visual Studio 2017 o versiones anteriores del SDK de .NET Core tienen como destino C# 7.0 de forma predeterminada. 

## <a name="defaults"></a>Valores predeterminados

El compilador determina un valor predeterminado según estas reglas:

|Marco de destino|version|Versión predeterminada del lenguaje C#|
|----------------|-------|---------------------------|
|.NET Core|3.x|C# 8.0|
|.NET Core|2.x|C# 7.3|
|.NET Standard|2.1|C# 8.0|
|.NET Standard|2.0|C# 7.3|
|.NET Standard|1.x|C# 7.3|
|.NET Framework|todo|C# 7.3|

## <a name="default-for-previews"></a>Valor predeterminado para las versiones preliminares

Cuando el proyecto tiene como destino un marco en versión preliminar que tenga una versión de lenguaje preliminar correspondiente, la versión de lenguaje que se usa es la que está en versión preliminar. Esto asegura que puede usar las características más recientes que se garantiza que funcionen con esa versión preliminar en cualquier entorno sin que afecte a los proyectos que tienen como destino una versión de .NET Core.

## <a name="override-a-default"></a>Invalidación de un valor predeterminado

Si debe especificar su versión de C# explícitamente, puede hacerlo de varias maneras:

- Editar manualmente el [archivo del proyecto](#edit-the-project-file).
- Establecer la versión del lenguaje [para varios proyectos en un subdirectorio](#configure-multiple-projects).
- Configurar la opción dl compilador [Reemplace la opción del compilador `-langversion`](compiler-options/langversion-compiler-option.md).

### <a name="edit-the-project-file"></a>Edición del archivo del proyecto

Puede establecer la versión del lenguaje en el archivo del proyecto. Por ejemplo, si quiere acceder explícitamente a las características en versión preliminar, agregue un elemento similar al siguiente:

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

El valor `preview` usa la versión preliminar más reciente disponible del lenguaje C# que admite el compilador.

### <a name="configure-multiple-projects"></a>Configurar varios proyectos

Para configurar varios proyectos, se puede crear un archivo **Directory.Build.props** que contenga el elemento `<LangVersion>`. Por lo general, esto se hace en el directorio de la solución. Agregue lo siguiente a un archivo **Directory.Build.props** en el directorio de la solución:

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

Ahora, las compilaciones de cada subdirectorio del directorio que contenga ese archivo usarán la sintaxis de la versión preliminar de C#. Para obtener más información, consulte el artículo [Personalizar una compilación](/visualstudio/msbuild/customize-your-build).

## <a name="c-language-version-reference"></a>Referencia de la versión del lenguaje C#

En la siguiente tabla se muestran las versiones actuales del lenguaje C#. El compilador no entenderá necesariamente todos los valores si es más antiguo. Si instala .NET Core 3.0, tendrá acceso a todo lo que aparece.

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
|ISO-2|El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2006 C# (2.0). |
|ISO-1|El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2003 C# (1.0/1.2). |
