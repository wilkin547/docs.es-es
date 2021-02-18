---
title: Propiedades de MSBuild para Microsoft.NET.Sdk.Desktop
description: Referencia de las propiedades y los elementos de MSBuild admitidos por el SDK de Escritorio de .NET, que incluye WPF y WinForms.
ms.date: 02/04/2021
ms.topic: reference
author: adegeo
ms.author: adegeo
ms.custom: updateeachrelease
no-loc:
- App.xaml
- Application.xaml
- ApplicationDefinition
- Page
- EmbeddedResource
- Compile
- None
ms.openlocfilehash: 6d1903558dd03776a72eb6ee56ddae09fb66615b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100488270"
---
# <a name="msbuild-reference-for-net-desktop-sdk-projects"></a>Referencia de MSBuild para proyectos del SDK de Escritorio de .NET

Esta página es una referencia sobre las propiedades y los elementos de MSBuild que se usan para configurar proyectos de Windows Forms (WinForms) y Windows Presentation Foundation (WPF) con el SDK de Escritorio de .NET.

> [!NOTE]
> En este artículo se documenta un subconjunto de las propiedades de MSBuild para el SDK de .NET en lo que se refiere a las aplicaciones de escritorio. Para obtener una lista de propiedades de MSBuild específicas del SDK de .NET, vea [Referencia de MSBuild para proyectos de SDK de .NET](msbuild-props.md). Para obtener una lista de las propiedades comunes de MSBuild, vea [Propiedades comunes de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).

## <a name="enable-net-desktop-sdk"></a>Habilitación del SDK de Escritorio de .NET

Para usar WinForms o WPF, configure el archivo del proyecto.

### <a name="net-50"></a>.NET 5.0

Especifique los valores de configuración siguientes en el archivo del proyecto de WinForms o WPF:

- Seleccione como destino el SDK `Microsoft.NET.Sdk` de .NET. Para obtener más información, vea [Archivos del proyecto](overview.md#project-files).
- Establezca [`TargetFramework`](msbuild-props.md#targetframework) en `net5.0-windows`.
- Agregue una propiedad de marco de interfaz de usuario (o ambas, si es necesario):
  - Establezca [`UseWPF`](#usewpf) en `true` para importar y usar WPF.
  - Establezca [`UseWindowsForms`](#usewindowsforms) en `true` para importar y usar WinForms.
- (Opcional) Establezca `OutputType` en `WinExe`. Esto genera una aplicación en lugar de una biblioteca. Para generar una biblioteca, omita esta propiedad.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>

    <UseWPF>true</UseWPF>
    <!-- and/or -->
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

### <a name="net-core-31"></a>.NET Core 3.1

Especifique los valores de configuración siguientes en el archivo del proyecto de WinForms o WPF:

- Seleccione como destino el SDK `Microsoft.NET.Sdk.WindowsDesktop` de .NET. Para obtener más información, vea [Archivos del proyecto](overview.md#project-files).
- Establezca [`TargetFramework`](msbuild-props.md#targetframework) en `netcoreapp3.1`.
- Agregue una propiedad de marco de interfaz de usuario (o ambas, si es necesario):
  - Establezca [`UseWPF`](#usewpf) en `true` para importar y usar WPF.
  - Establezca [`UseWindowsForms`](#usewindowsforms) en `true` para importar y usar WinForms.
- (Opcional) Establezca `OutputType` en `WinExe`. Esto genera una aplicación en lugar de una biblioteca. Para generar una biblioteca, omita esta propiedad.

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>

    <UseWPF>true</UseWPF>
    <!-- and/or -->
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>

</Project>
```

## <a name="wpf-default-includes-and-excludes"></a>Inclusiones y exclusiones predeterminadas de WPF

Los proyectos de SDK definen un conjunto de reglas para incluir o excluir archivos del proyecto de forma implícita. Estas reglas también establecen automáticamente la acción de compilación del archivo. Esto es diferente a los proyectos de .NET Framework anteriores que no son de SDK, que no tienen reglas predeterminadas de inclusión o exclusión. En los proyectos de .NET Framework es necesario declarar de forma explícita los archivos que se van a incluir en el proyecto.

Los archivos del proyecto de .NET incluyen un [conjunto estándar de reglas](overview.md#default-includes-and-excludes) para el procesamiento automático de los archivos. Los proyectos de WPF agregan reglas adicionales.

En la tabla siguiente se muestra qué elementos y qué [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) se incluyen y excluyen en el SDK de Escritorio de .NET cuando la propiedad del proyecto [`UseWPF`](#usewpf) se establece en `true`:

| Elemento               | Glob para incluir                 | Glob para excluir                                                                                           | Glob para quitar  |
|-----------------------|------------------------------|--------------------------------------------------------------------|--------------|
| ApplicationDefinition | App.xaml o Application.xaml | N/D                                                                | N/D          |
| Page                  | \*\*/\*.xaml                 | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc<br>Cualquier XAML definido por *ApplicationDefinition* | N/D          |
| None                  | N/D                          | N/D                                                                | \*\*/\*.xaml |

Estos son los valores de configuración de las inclusiones y exclusiones predeterminadas para todos los tipos de proyecto. Para obtener más información, consulte [Inclusiones y exclusiones predeterminadas](overview.md#default-includes-and-excludes).

| Elemento           | Glob para incluir                              | Glob para excluir                                                  | Glob para quitar              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| Compile           | \*\*/\*.cs; \*\*/\*.vb (o extensiones de otros lenguajes) | \*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc  | N/D          |
| EmbeddedResource  | \*\*/\*.resx                              | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | N/D                      |
| None              | \*\*/\*                                   | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | \*\*/\*.cs; \*\*/\*.resx |

### <a name="errors-related-to-duplicate-items"></a>Errores relacionados con elementos "duplicados"

Si ha agregado archivos de forma explícita al proyecto, o bien si tiene patrones globales de XAML para incluir archivos automáticamente en el proyecto, es posible que se produzca uno de los errores siguientes:

* Se han incluido elementos "ApplicationDefinition" duplicados.
* Se han incluido elementos "Page" duplicados.

Estos errores son el resultado de patrones globales *Include* implícitos en conflicto con la configuración. Para solucionar temporalmente este problema, establezca [`EnableDefaultApplicationDefinition`](#enabledefaultapplicationdefinition) o [`EnableDefaultPageItems`](#enabledefaultpageitems) en `false`. Al establecer estos valores en `false`, se revierte el comportamiento de los SDK anteriores en los que tenía que definir explícitamente los patrones globales predeterminados en el proyecto, o bien definir de forma explícita los archivos que se iban a incluir en el proyecto.

Puede deshabilitar completamente todas las inclusiones implícitas si establece la [propiedad `EnableDefaultItems`](msbuild-props.md#enabledefaultitems) en `false`.

## <a name="wpf-settings"></a>Configuración de WPF

- [UseWPF](#usewpf)
- [EnableDefaultApplicationDefinition](#enabledefaultapplicationdefinition)
- [EnableDefaultPageItems](#enabledefaultpageitems)

Para obtener información sobre la configuración de proyectos no específicos de WPF, vea [Referencia de MSBuild para los proyectos del SDK de .NET](msbuild-props.md).

### <a name="usewpf"></a>UseWPF

La propiedad `UseWPF` controla si se deben incluir o no referencias a las bibliotecas de WPF. Esto también altera la canalización de MSBuild para procesar correctamente un proyecto de WPF y los archivos relacionados. El valor predeterminado es `false`. Establezca la propiedad `UseWPF` en `true` para habilitar la compatibilidad con WPF. Cuando esta propiedad está habilitada, solo puede seleccionar como destino la plataforma Windows.

```xml
<PropertyGroup>
  <UseWPF>true</UseWPF>
</PropertyGroup>
```

Cuando esta propiedad se establece en `true`, los proyectos de .NET 5.0 y versiones posteriores importarán de forma automática el [SDK de Escritorio de .NET](#enable-net-desktop-sdk).

Los proyectos de .NET Core 3.1 deben tener como destino explícitamente el [SDK de Escritorio de .NET](#enable-net-desktop-sdk) para usar esta propiedad.

### <a name="enabledefaultapplicationdefinition"></a>EnableDefaultApplicationDefinition

La propiedad `EnableDefaultApplicationDefinition` controla si los elementos `ApplicationDefinition` se incluyen en el proyecto de forma implícita. El valor predeterminado es `true`. Establezca la propiedad `EnableDefaultApplicationDefinition` en `false` para deshabilitar la inclusión de archivos implícita.

```xml
<PropertyGroup>
  <EnableDefaultApplicationDefinition>false</EnableDefaultApplicationDefinition>
</PropertyGroup>
```

Esta propiedad necesita que la [propiedad `EnableDefaultItems`](msbuild-props.md#enabledefaultitems) esté establecida en `true`, que es el valor de configuración predeterminado.

### <a name="enabledefaultpageitems"></a>EnableDefaultPageItems

La propiedad `EnableDefaultPageItems` controla si los elementos `Page`, que son archivos _.xaml_, se incluyen en el proyecto de forma implícita. El valor predeterminado es `true`. Establezca la propiedad `EnableDefaultPageItems` en `false` para deshabilitar la inclusión de archivos implícita.

```xml
<PropertyGroup>
  <EnableDefaultPageItems>false</EnableDefaultPageItems>
</PropertyGroup>
```

Esta propiedad necesita que la [propiedad `EnableDefaultItems`](msbuild-props.md#enabledefaultitems) esté establecida en `true`, que es el valor de configuración predeterminado.

## <a name="windows-forms-settings"></a>Configuración de Windows Forms

- [UseWindowsForms](#usewindowsforms)

Para obtener información sobre las propiedades de proyecto que no son específicas de WinForms, vea [Referencia de MSBuild para los proyectos del SDK de .NET](msbuild-props.md).

### <a name="usewindowsforms"></a>UseWindowsForms

La propiedad `UseWindowsForms` controla si la aplicación se compila o no para destinarla a Windows Forms. Esta propiedad también altera la canalización de MSBuild para procesar correctamente un proyecto de Windows Forms y los archivos relacionados. El valor predeterminado es `false`. Establezca la propiedad `UseWindowsForms` en `true` para habilitar la compatibilidad con Windows Forms. Cuando este valor de configuración está habilitado, solo puede seleccionar como destino la plataforma Windows.

```xml
<PropertyGroup>
  <UseWindowsForms>true</UseWindowsForms>
</PropertyGroup>
```

Cuando esta propiedad se establece en `true`, los proyectos de .NET 5.0 y versiones posteriores importarán de forma automática el [SDK de Escritorio de .NET](#enable-net-desktop-sdk).

Los proyectos de .NET Core 3.1 deben tener como destino explícitamente el [SDK de Escritorio de .NET](#enable-net-desktop-sdk) para usar esta propiedad.

## <a name="shared-settings"></a>Configuración compartida

- [DisableWinExeOutputInference](#disablewinexeoutputinference)

### <a name="disablewinexeoutputinference"></a>DisableWinExeOutputInference

Se aplica al SDK de .NET 5.0 y versiones posteriores.

Cuando una aplicación tiene el valor `Exe` establecido para la propiedad `OutputType`, se crea una ventana de consola si la aplicación no se ejecuta desde una consola. Normalmente este no es el comportamiento deseado de una aplicación de escritorio de Windows. Con el valor `WinExe`, no se crea una ventana de consola. A partir del SDK de .NET 5.0, el valor `Exe` se transforma automáticamente en `WinExe`.

La propiedad `DisableWinExeOutputInference` revierte el comportamiento de tratar `Exe` como `WinExe`. Establezca este valor en `true` para restaurar el comportamiento del valor de la propiedad `OutputType` de `Exe`. El valor predeterminado es `false`.

```xml
<PropertyGroup>
  <DisableWinExeOutputInference>true</DisableWinExeOutputInference>
</PropertyGroup>
```

## <a name="see-also"></a>Vea también

- [SDK de proyectos de .NET](overview.md)
- [Referencia de MSBuild para proyectos del SDK de .NET](msbuild-props.md)
- [Referencia del esquema de MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [Propiedades comunes de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties)
- [Personalización de una compilación](/visualstudio/msbuild/customize-your-build)
