---
title: Novedades de .NET Core 3.1
description: Conozca las nuevas características que se encuentran en .NET Core 3.1.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: 323a2390f079c17b81db01e4e3787916251943bf
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156561"
---
# <a name="whats-new-in-net-core-31"></a>Novedades de .NET Core 3.1

En este artículo se describen las novedades de .NET Core 3.1. Esta versión contiene ligeras mejoras de .NET Core 3.0, y se centra en pequeñas correcciones, pero importantes. La característica más importante sobre .NET Core 3.1 es que es una versión de [soporte técnico a largo plazo (LTS)](#long-term-support).

Si usa Visual Studio 2019, debe actualizar a [Visual Studio 2019, versión 16.4](https://visualstudio.microsoft.com/downloads/) para trabajar con proyectos de .NET Core 3.1. Para obtener más información sobre las novedades de Visual Studio, vea [Novedades de Visual Studio 2019 versión 16.4](/visualstudio/releases/2019/release-notes#whats-new-in-visual-studio-2019-version-164).

Visual Studio para Mac también admite e incluye .NET Core 3.1 en Visual Studio para Mac 8.4.

Para más información sobre la versión, consulte el [anuncio de .NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).

- [Descargue .NET Core 3.1 y empiece a trabajar](https://dotnet.microsoft.com/download/dotnet-core/3.1) en Windows, macOS o Linux.

## <a name="long-term-support"></a>Compatibilidad a largo plazo

.NET Core 3.1 es una versión LTS con soporte técnico de Microsoft durante los próximos tres años. Se recomienda encarecidamente mover las aplicaciones a .NET Core 3.1. El ciclo de vida actual de otras versiones principales es el siguiente:

| Release | Nota |
| ------- | ---- |
| .NET Core 3.0 | Fin del ciclo de vida el 3 de marzo de 2020.     |
| .NET Core 2.2 | Fin del ciclo de vida el 23 de diciembre de 2019. |
| .NET Core 2.1 | Fin del ciclo de vida el 21 de agosto de 2021.    |

Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

## <a name="macos-apphost-and-notarization"></a>appHost y certificación de macOS

*Solo para macOS*

A partir del SDK de .NET Core 3.1 para macOS, la configuración de appHost está deshabilitada de forma predeterminada. Para obtener más información, vea [Certificación de macOS Catalina y el impacto en las descargas y proyectos de .NET Core](../install/macos-notarization-issues.md).

Cuando la configuración de appHost está habilitada, .NET Core genera un ejecutable Mach-O nativo al compilar o publicar. La aplicación se ejecuta en el contexto de appHost cuando se ejecuta desde el código fuente con el comando `dotnet run` o mediante el inicio directo del ejecutable Mach-O.

Sin appHost, la única manera en que un usuario puede iniciar una aplicación [dependiente del entorno de ejecución](../deploying/index.md#publish-runtime-dependent) es con el comando `dotnet <filename.dll>`. Siempre se crea un instancia de appHost al publicar la aplicación de manera [independiente](../deploying/index.md#publish-self-contained).

Puede configurar appHost en el nivel de proyecto, o bien cambiar la instancia de appHost de un comando `dotnet` específico con el parámetro `-p:UseAppHost`:

- Archivo del proyecto

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- Parámetro de línea de comandos

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

Para obtener más información sobre la configuración de `UseAppHost`, vea [Propiedades de MSBuild para Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).

## <a name="windows-forms"></a>Windows Forms

*Solo Windows*

> [!WARNING]
> Hay cambios importantes en Windows Forms.

Se incluyeron controles heredados en Windows Forms que llevan un tiempo sin estar disponibles en el cuadro de herramientas del diseñador de Visual Studio. Estos controles se volvieron a reemplazar por otros nuevos en .NET Framework 2.0 y se han quitado del SDK de escritorio para .NET Core 3.1.

| Control eliminado | Reemplazo recomendado | API asociadas eliminadas |
| --------------- | ----------------------- | ----------------------- |
| DataGrid        | <xref:System.Windows.Forms.DataGridView>      | DataGridCell<br/>DataGridRow<br/>DataGridTableCollection<br/>DataGridColumnCollection<br/>DataGridTableStyle<br/>DataGridColumnStyle<br/>DataGridLineStyle<br/>DataGridParentRowsLabel<br/>DataGridParentRowsLabelStyle<br/>DataGridBoolColumn<br/>DataGridTextBox<br/>GridColumnStylesCollection<br/>GridTableStylesCollection<br/>HitTestType |
| ToolBar         | <xref:System.Windows.Forms.ToolStrip>         | ToolBarAppearance |
| ToolBarButton   | <xref:System.Windows.Forms.ToolStripButton>   | ToolBarButtonClickEventArgs<br/>ToolBarButtonClickEventHandler<br/>ToolBarButtonStyle<br/>ToolBarTextAlign |
| ContextMenu     | <xref:System.Windows.Forms.ContextMenuStrip>  |  |
| :::no-loc text="Menu"::: | <xref:System.Windows.Forms.ToolStripDropDown><br/><xref:System.Windows.Forms.ToolStripDropDownMenu> | MenuItemCollection |
| MainMenu        | <xref:System.Windows.Forms.MenuStrip>         |  |
| MenuItem        | <xref:System.Windows.Forms.ToolStripMenuItem> |  |

Se recomienda actualizar las aplicaciones a .NET Core 3.1 y pasar a los controles de reemplazo. Reemplazar los controles es un proceso sencillo; se trata básicamente de "buscar y reemplazar" el tipo.

## <a name="ccli"></a>C++/CLI

*Solo Windows*

Se ha agregado compatibilidad con la creación de proyectos de C++/CLI (lo que también se conoce como "C++ administrado"). Los archivos binarios generados a partir de estos proyectos son compatibles con .NET Core 3.0 y versiones posteriores.

Para agregar compatibilidad con C++/CLI a Visual Studio 2019 versión 16.4, instale la [carga de trabajo Desarrollo para el escritorio con C++](/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads). Esta carga de trabajo agrega dos plantillas a Visual Studio:

- Biblioteca de clases de CLR (.NET Core)
- Proyecto vacío de CLR (.NET Core)

## <a name="next-steps"></a>Pasos siguientes

- [Revise los cambios importantes entre .NET Core 3.0 y 3.1.](../compatibility/3.0-3.1.md)
- [Revise los cambios importantes de .NET Core 3.1 para aplicaciones de Windows Forms](../compatibility/winforms.md#net-core-31).
