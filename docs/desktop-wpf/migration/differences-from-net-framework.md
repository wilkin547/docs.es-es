---
title: Diferencias entre .NET Framework y .NET Core
description: Describe las diferencias entre la implementación de .NET Framework de Windows Presentation Foundation (WPF) y .NET Core WPF. Al migrar la aplicación, debe tener en cuenta estas incompatibilidades.
author: thraka
ms.date: 09/21/2019
ms.author: adegeo
ms.openlocfilehash: 4386654aad205e3c9f2cbd986d7b812e261e737f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "81433137"
---
# <a name="differences-in-wpf"></a>Diferencias en WPF

En este artículo se describen las diferencias entre Windows Presentation Foundation (WPF) en .NET Core y .NET Framework. WPF para .NET Core es un marco de [código abierto](https://github.com/dotnet/wpf) bifurcado desde el código fuente original de WPF para .NET Framework.

Hay algunas características de .NET Framework que .NET Core no admite. Para obtener más información sobre tecnologías no admitidas, vea Tecnologías de [.NET Framework no disponibles en .NET Core](../../core/porting/net-framework-tech-unavailable.md).

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a>Proyectos al estilo SDK

.NET Core usa archivos de proyecto de estilo SDK. Estos archivos de proyecto son diferentes de los archivos de proyecto tradicionales de .NET Framework administrados por Visual Studio. Para migrar las aplicaciones WPF de .NET Framework a .NET Core, debe convertir los proyectos. Para obtener más información, vea [Migrar aplicaciones WPF a .NET Core 3.0](convert-project-from-net-framework.md).

## <a name="nuget-package-references"></a>Referencias de paquetes de NuGet

Si la aplicación .NET Framework enumera sus dependencias NuGet en [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) un archivo *packages.config,* migre al formato:

1. En Visual Studio, abra el **panel Explorador de soluciones.**
1. En el proyecto WPF, haga clic con el botón secundario en **packages.config** > **Migrate packages.config a PackageReference**.

![Actualización a PackageReference](media/differences-from-net-framework/package-reference-migration.png)

Aparecerá un cuadro de diálogo que muestra las dependencias NuGet calculadas de nivel superior y que pregunta qué otros paquetes NuGet se deben promocionar al nivel superior. Seleccione **Aceptar** y el archivo *packages.config* se `<PackageReference>` quitará del proyecto y los elementos se agregarán al archivo de proyecto.

Cuando el `<PackageReference>`proyecto usa , los paquetes no se almacenan localmente en una carpeta *Packages,* se almacenan globalmente. Abra el archivo de `<Analyzer>` proyecto y quite los elementos que hace referencia a la carpeta *Paquetes.* Estos analizadores se incluyen automáticamente con las referencias de paquete NuGet.

## <a name="code-access-security"></a>Seguridad de acceso del código

.NET Core o WPF para .NET Core no admiten la seguridad de acceso de código (CAS). Todas las funciones relacionadas con CAS se tratan bajo la suposición de plena confianza. WPF para .NET Core quita el código relacionado con CAS. La superficie de API pública de estos tipos todavía existe para garantizar que las llamadas a estos tipos se realicen correctamente.

Los tipos relacionados con CAS definidos públicamente se movieron fuera de los ensamblados WPFWPF y en los ensamblados CoreFX. Los ensamblados de WPFWPF tienen el acceso a tipos establecido en la nueva ubicación de los tipos movidos.

| Ensamblaje de origen | Ensamblaje de destino | Tipo                |
| --------------- | --------------- | ------------------- |
| *WindowsBase.dll* | *System.Security.Permissions.dll* | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| *System.Xaml.dll* | *System.Security.Permissions.dll* | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| *System.Xaml.dll* | *System.Windows.Extension.dll*    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> Para minimizar la fricción de portabilidad, se retuvo la funcionalidad para almacenar `XamlAccessLevel` y recuperar información relacionada con las siguientes propiedades en el tipo.
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a>Pasos siguientes

- [Aprenda a migrar una aplicación WPF de .NET Framework a .NET Core.](convert-project-from-net-framework.md)
