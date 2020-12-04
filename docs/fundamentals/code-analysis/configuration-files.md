---
title: Archivos de configuración para las reglas de análisis de código
description: Obtenga información sobre los distintos archivos de configuración para configurar reglas de análisis de código.
ms.date: 09/24/2020
ms.topic: conceptual
no-loc:
- EditorConfig
ms.openlocfilehash: cf9b8f4033e6774684b2b7e3b788ef3c157d95df
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96594727"
---
# <a name="configuration-files-for-code-analysis-rules"></a>Archivos de configuración para las reglas de análisis de código

Las reglas de análisis de código tienen varias [Opciones de configuración](configuration-options.md). Estas opciones se especifican como pares clave-valor en uno de los siguientes archivos de configuración del analizador:

- [EditorConfig](#editorconfig) archivo: opciones de configuración basadas en archivos o carpetas.
- Archivo [AnalyzerConfig global](#global-analyzerconfig) : opciones de configuración de nivel de proyecto.

## EditorConfig

[EditorConfig](/visualstudio/ide/create-portable-custom-editor-options) los archivos se usan para proporcionar **opciones que se aplican a archivos o carpetas de origen específicos**. Las opciones se colocan en encabezados de sección para identificar los archivos y carpetas aplicables. Agregue una entrada para cada regla que desee configurar y colóquela en la sección de la extensión de archivo correspondiente, por ejemplo, `[*.cs]` .

```ini
[*.cs]
<option_name> = <option_value>
```

En el ejemplo anterior, `[*.cs]` es un encabezado de sección editorconfig para seleccionar todos los archivos de C# con `.cs` extensión de archivo dentro de la carpeta actual, incluidas las subcarpetas. La entrada siguiente, `<option_name> = <option_value>` , es una opción del analizador que se aplicará a todos los archivos de C#.

Puede aplicar EditorConfig las convenciones de archivo a una carpeta, un proyecto o un repositorio completo colocando el archivo en el directorio correspondiente. Estas opciones se aplican al ejecutar el análisis en tiempo de compilación y mientras edita código en Visual Studio.

Si tiene un archivo *. editorconfig* existente para la configuración del editor, como el tamaño de sangría o si desea recortar el espacio en blanco final, puede colocar las opciones de configuración de análisis de código en el mismo archivo.

> [!TIP]
> Visual Studio proporciona una plantilla de elemento *. editorconfig* que facilita la tarea de agregar uno de estos archivos al proyecto. Para obtener más información, vea [Agregar un EditorConfig archivo a un proyecto](/visualstudio/ide/create-portable-custom-editor-options#add-an-editorconfig-file-to-a-project).

### <a name="example"></a>Ejemplo

A continuación se encuentra un EditorConfig archivo de ejemplo para configurar las opciones y la gravedad de la regla:

```ini
# Remove the line below if you want to inherit .editorconfig settings from higher directories
root = true

# C# files
[*.cs]

#### Core EditorConfig Options ####

# Indentation and spacing
indent_size = 4
indent_style = space
tab_width = 4

#### .NET Coding Conventions ####

# this. and Me. preferences
dotnet_style_qualification_for_method = true:warning

#### Diagnostic configuration ####

# CA1000: Do not declare static members on generic types
dotnet_diagnostic.CA1000.severity = warning
```

## <a name="global-analyzerconfig"></a>AnalyzerConfig global

A partir del SDK de .NET 5,0 (que es compatible con la versión 16,8 de Visual Studio 2019 y versiones posteriores), también puede configurar las opciones del analizador con archivos _AnalyzerConfig_ globales. Estos archivos se usan para proporcionar **las opciones que se aplican a todos los archivos de origen de un proyecto**, independientemente de sus nombres de archivo o rutas de acceso de archivo.

A diferencia [EditorConfig](#editorconfig) de los archivos, los archivos de configuración global no se pueden usar para configurar los valores de estilo de editor para IDE, como el tamaño de sangría o si se debe recortar el espacio en blanco final. En su lugar, están diseñados exclusivamente para especificar las opciones de configuración del analizador de nivel de proyecto.

### <a name="format"></a>Formato

A diferencia EditorConfig de los archivos, que deben tener encabezados de sección, como `[*.cs]` , para identificar los archivos y carpetas aplicables, los archivos AnalyzerConfig globales no tienen encabezados de sección. En su lugar, requieren una entrada de nivel superior del formulario `is_global = true` para diferenciarlos de EditorConfig los archivos normales. Esto indica que todas las opciones del archivo se aplican a todo el proyecto. Por ejemplo:

```ini
is_global = true
<option_name> = <option_value>
```

### <a name="naming"></a>Nomenclatura

A diferencia de EditorConfig los archivos, que se deben denominar `.editorconfig` , los archivos de configuración global no necesitan tener un nombre o una extensión específicos. Sin embargo, si asigna un nombre a estos archivos como `.globalconfig` , se aplicarán implícitamente a todos los proyectos de C# y Visual Basic dentro de la carpeta actual, incluidas las subcarpetas. De lo contrario, debe agregar explícitamente el `GlobalAnalyzerConfigFiles` elemento al archivo de proyecto de MSBuild:

```xml
<ItemGroup>
  <GlobalAnalyzerConfigFiles Include="<path_to_global_analyzer_config>" />
</ItemGroup>
```

> [!NOTE]
> La entrada de nivel superior `is_global = true` es necesaria incluso cuando el archivo se denomina `.globalconfig` .

### <a name="example"></a>Ejemplo

A continuación se encuentra un archivo AnalyzerConfig global de ejemplo para configurar las opciones y la gravedad de la regla en el nivel de proyecto:

```ini
# Top level entry required to mark this as a global AnalyzerConfig file
is_global = true

# NOTE: No section headers for configuration entries

#### .NET Coding Conventions ####

# this. and Me. preferences
dotnet_style_qualification_for_method = true:warning

#### Diagnostic configuration ####

# CA1000: Do not declare static members on generic types
dotnet_diagnostic.CA1000.severity = warning
```

## <a name="precedence"></a>Prioridad

Tanto archivos EditorConfig como archivos AnalyzerConfig globales especifican un par clave-valor para cada opción. Se producen conflictos cuando hay varias entradas con la misma clave pero con distintos valores.

### <a name="general-options"></a>Opciones generales

Cuando surgen conflictos entre las opciones, se usan las siguientes reglas de prioridad para resolver los conflictos:

- Entradas en conflicto en el mismo archivo de configuración: la entrada que aparece más adelante en el archivo gana. Esto se aplica a las entradas conflictivas dentro de un único EditorConfig archivo y también dentro de un único archivo AnalyzerConfig global.

- Entradas en conflicto en dos EditorConfig archivos: la entrada en el EditorConfig archivo que es más profunda en el sistema de archivos y, por tanto, tiene una ruta de acceso de archivo más larga, gana.

- Entradas en conflicto en dos archivos AnalyzerConfig globales: se indica una advertencia del compilador y se omiten ambas entradas.

- Entradas en conflicto en un EditorConfig archivo y un archivo AnalyzerConfig global: la entrada en el EditorConfig archivo gana.

### <a name="severity-options"></a>Opciones de gravedad

Las [reglas de prioridad general](#general-options) anteriores se aplican a todas las opciones especificadas en los archivos de configuración. En el caso de las opciones de [configuración de gravedad](configuration-options.md#severity-level) , se aplican las siguientes reglas de prioridad adicionales:

- Las opciones de gravedad especificadas en la línea de comandos como opciones del compilador ( `/nowarn` o `/warnaserror` ) siempre invalidan las opciones de [configuración de gravedad](configuration-options.md#severity-level) especificadas en EditorConfig y archivos AnalyzerConfig globales.

- Las opciones de gravedad también se pueden especificar con un archivo [ruleset](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) . Sin embargo, los archivos de conjuntos de archivos están en desuso en favor de EditorConfig los archivos AnalyzerConfig globales. Se recomienda [convertir los archivos ruleset en un EditorConfig archivo equivalente](/visualstudio/code-quality/use-roslyn-analyzers#convert-an-existing-ruleset-file-to-editorconfig-file). Prioridad de las entradas de gravedad conflictivas de un archivo ruleset y de que EditorConfig los archivos AnalyzerConfig globales no estén _definidos_.

- Para obtener información sobre las reglas de prioridad de las opciones de gravedad relacionadas con claves diferentes, por ejemplo, cuando se especifican diferentes gravedades para una sola regla y para la categoría en la que esta regla se encuentra bajo, vea [Opciones de configuración para el análisis de código](configuration-options.md#precedence).

## <a name="see-also"></a>Vea también

- [EditorConfig problema de diseño de AnalyzerConfig global de vs](https://github.com/dotnet/roslyn/issues/47707)
