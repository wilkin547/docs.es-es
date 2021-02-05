---
title: Seleccione la versión del lenguaje Visual Basic
description: Configure el compilador para realizar la validación de la sintaxis mediante una versión específica del compilador.
ms.date: 05/24/2018
ms.openlocfilehash: 09503db726f9d993bc986860c57aa98652b696d1
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585460"
---
# <a name="select-the-visual-basic-language-version"></a>Seleccione la versión del lenguaje Visual Basic

El compilador de Visual Basic tiene como valor predeterminado la versión principal más reciente del idioma que se ha publicado. Puede elegir compilar cualquier proyecto con una versión nueva del lenguaje. Elegir la versión más reciente del lenguaje permite que el proyecto use las últimas características de ese lenguaje. En otros escenarios, puede ser necesario validar que un proyecto se compile correctamente cuando se usa una versión anterior del lenguaje.

Esta capacidad hace que la decisión de instalar nuevas versiones del SDK y las herramientas en el entorno de desarrollo no esté vinculada a la decisión de incorporar nuevas características del lenguaje en un proyecto. Puede instalar el SDK y las herramientas más recientes en el equipo de compilación. Cada proyecto se puede configurar para que, durante su compilación, se use una versión de lenguaje específica.

Hay tres formas de establecer la versión de idioma:

- Editar manualmente el [archivo **. vbproj**](#edit-the-vbproj-file)
- Establecer la versión [de idioma de varios proyectos en un subdirectorio](#configure-multiple-projects)
- Configurar la [ `-langversion` opción del compilador](#set-the-langversion-compiler-option)

## <a name="edit-the-vbproj-file"></a>Edición del archivo vbproj

Puede establecer la versión de idioma en el archivo **. vbproj** . Agregue el siguiente elemento:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

El valor `latest` usa la versión secundaria más reciente del lenguaje Visual Basic. Los valores válidos son:

|Value|Significado|
|------------|-------------|
|default|El compilador acepta toda la sintaxis de lenguaje válida de la última versión principal que puede admitir.|
|9|El compilador acepta solo la sintaxis que se incluye en Visual Basic 9,0 o inferior.|
|10|El compilador acepta solo la sintaxis que se incluye en Visual Basic 10,0 o inferior.|
|11|El compilador acepta solo la sintaxis que se incluye en Visual Basic 11,0 o inferior.|
|12|El compilador acepta solo la sintaxis que se incluye en Visual Basic 12,0 o inferior.|
|14|El compilador acepta solo la sintaxis que se incluye en Visual Basic 14,0 o inferior.|
|15|El compilador acepta solo la sintaxis que se incluye en Visual Basic 15,0 o inferior.|
|15,3|El compilador acepta solo la sintaxis que se incluye en Visual Basic 15,3 o inferior.|
|15,5|El compilador acepta solo la sintaxis que se incluye en Visual Basic 15,5 o inferior.|
|16|El compilador acepta solo la sintaxis que se incluye en Visual Basic 16 o inferior.|
|16,9|El compilador acepta solo la sintaxis que se incluye en Visual Basic 16,9 o inferior.|
|latest|El compilador acepta toda la sintaxis de lenguaje válida que puede admitir.|

Las cadenas especiales `default` y `latest` se resuelven en las versiones de lenguaje principal y secundaria respectivamente más recientes que haya instaladas en el equipo de compilación.

## <a name="configure-multiple-projects"></a>Configurar varios proyectos

Puede crear un archivo **Directory.build.props** que contenga el elemento `<LangVersion>` para configurar varios directorios. Por lo general, esto se hace en el directorio de la solución. Agregue lo siguiente a un archivo **Directory. Build. props** en el directorio de la solución:

```xml
<Project>
 <PropertyGroup>
   <LangVersion>15.5</LangVersion>
 </PropertyGroup>
</Project>
```

Ahora, las compilaciones en cada subdirectorio del directorio que contiene ese archivo usarán Visual Basic sintaxis de la versión 15,5. Para obtener más información, consulte el artículo [Personalizar una compilación](/visualstudio/msbuild/customize-your-build).

## <a name="set-the-langversion-compiler-option"></a>Establecer la opción del compilador langversion

Puede usar la opción de la línea de comandos `-langversion`. Para obtener más información, consulte el artículo sobre la opción del compilador [-langversion](../reference/command-line-compiler/langversion.md). Puede ver una lista de los valores válidos escribiendo  `vbc -langversion:?` .
