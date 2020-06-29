---
title: Diferencias entre .NET Framework y .NET Core
description: Se describen las diferencias entre la implementación de .NET Framework de Windows Presentation Foundation (WPF) y WPF de .NET Core. Al migrar la aplicación, se deben tener en cuenta estas incompatibilidades.
author: adegeo
ms.date: 09/21/2019
ms.author: adegeo
ms.openlocfilehash: 3bedc30046c36d4c5430feedf5854276ebaef8aa
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325686"
---
# <a name="differences-in-wpf"></a>Diferencias en WPF

En este artículo se describen las diferencias entre Windows Presentation Foundation (WPF) en .NET Core y .NET Framework. WPF para .NET Core es un [marco de código abierto](https://github.com/dotnet/wpf) que surge del código fuente de WPF para .NET Framework original.

Hay algunas características de .NET Framework que .NET Core no admite. Para más información sobre las tecnologías no admitidas, vea [Tecnologías de .NET Framework no disponibles en .NET Core](../../core/porting/net-framework-tech-unavailable.md).

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a>Proyectos de estilo SDK

.NET Core usa archivos de proyecto de estilo SDK. Estos archivos de proyecto son diferentes de los archivos de proyecto de .NET Framework tradicionales administrados por Visual Studio. Para migrar las aplicaciones de WPF de .NET Framework a .NET Core, debe convertir los proyectos. Para más información, vea [Migración de aplicaciones de WPF a .NET Core 3.0](convert-project-from-net-framework.md).

## <a name="nuget-package-references"></a>Referencias de paquetes de NuGet

Si la aplicación de .NET Framework refleja sus dependencias de NuGet en un archivo *packages.config*, migre al formato [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files):

1. En Visual Studio, abra el panel del **Explorador de soluciones**.
1. En el proyecto de WPF, haga clic con el botón derecho en **packages.config** > **Migrar packages.config a PackageReference**.

![Actualización a PackageReference](media/differences-from-net-framework/package-reference-migration.png)

Se abrirá un cuadro de diálogo en el que se muestran las dependencias de NuGet de nivel superior calculadas y en el que se pregunta por otros paquetes NuGet que se deban promover al nivel superior. Seleccione **Aceptar**; el archivo *packages.config* se quitará del proyecto y se agregarán elementos `<PackageReference>` al archivo de proyecto.

Cuando el proyecto usa `<PackageReference>`, los paquetes no se almacenan localmente en una carpeta *Packages*, sino que se almacenan de forma global. Abra el archivo de proyecto y quite los elementos `<Analyzer>` que se remitan a la carpeta *Packages*. Estos analizadores se incluyen automáticamente con las referencias del paquete NuGet.

## <a name="code-access-security"></a>Seguridad de acceso del código

Ni .NET Core ni WPF para .NET Core admiten la seguridad de acceso del código (CAS). Toda la funcionalidad relativa a CAS se tratará como si fuera de plena confianza. WPF para .NET Core quita el código relativo a CAS. La superficie de API pública de estos tipos seguirá existiendo para garantizar que las llamadas a estos tipos se efectúan correctamente.

Los tipos de CAS definidos públicamente se han extraído de los ensamblados de WPF y se han incluido en los ensamblados principales de la biblioteca de .NET. Los ensamblados de WPF tienen el reenvío de tipos establecido en la nueva ubicación de los tipos desplazados.

| Ensamblado de origen | Ensamblado de destino | Tipo                |
| --------------- | --------------- | ------------------- |
| *WindowsBase.dll* | *System.Security.Permissions.dll* | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| *System.Xaml.dll* | *System.Security.Permissions.dll* | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| *System.Xaml.dll* | *System.Windows.Extension.dll*    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> A fin de minimizar posibles complicaciones durante el cambio, en el tipo `XamlAccessLevel` se ha conservado la funcionalidad para almacenar y recuperar información relativa a las siguientes propiedades.
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a>Pasos siguientes

- [Más información sobre cómo portar una aplicación de WPF de .NET Framework a .NET Core](convert-project-from-net-framework.md)
