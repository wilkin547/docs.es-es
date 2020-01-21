---
title: Novedades de .NET Core 3.1
description: Conozca las nuevas características que se encuentran en .NET Core 3.1.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.openlocfilehash: eba3d21cfc787c5d388de31f988b835522118151
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936924"
---
# <a name="whats-new-in-net-core-31"></a>Novedades de .NET Core 3.1

En este artículo se describen las novedades de .NET Core 3.1. Esta versión contiene ligeras mejoras de .NET Core 3.0, y se centra en pequeñas correcciones, pero importantes. La característica más importante sobre .NET Core 3.1 es que es una versión de [soporte técnico a largo plazo (LTS)](#long-term-support).

Si usa Visual Studio 2019, debe actualizar a [Visual Studio 2019, versión 16.4](https://visualstudio.microsoft.com/downloads/) para trabajar con proyectos de .NET Core 3.1. Para más información sobre las novedades de Visual Studio, consulte el [blog de Visual Studio](https://devblogs.microsoft.com/visualstudio/tis-the-season-visual-studio-2019/).

Visual Studio para Mac también admite e incluye .NET Core 3.1 en el canal de la versión preliminar de Visual Studio para Mac 8.4. Deberá participar en el canal de versión preliminar para usar .NET Core 3.1.

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

Para agregar compatibilidad con C++/CLI en Visual Studio 2019 16.4, instale la [carga de trabajo Desarrollo para el escritorio con C++](https://docs.microsoft.com/cpp/build/vscpp-step-0-installation?view=vs-2019#step-4---choose-workloads). Esta carga de trabajo agrega dos plantillas a Visual Studio:

- Biblioteca de clases de CLR (.NET Core)
- Proyecto vacío de CLR (.NET Core)

## <a name="next-steps"></a>Pasos siguientes

- [Revise los cambios importantes entre .NET Core 3.0 y 3.1.](../compatibility/3.0-3.1.md)
- [Revise los cambios importantes en .NET Core 3.1 para aplicaciones de Windows Forms.](../compatibility/winforms.md#net-core-31)
