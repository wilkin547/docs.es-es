---
title: Actualización de aplicaciones de Windows Forms a .NET 5
description: Use el Asistente para actualización de .NET para actualizar una aplicación .NET Framework de Windows Forms existente a .NET 5. El Asistente para actualización de .NET es una herramienta de la CLI que ayuda a migrar una aplicación .NET Framework a .NET 5.
author: ardalis
ms.date: 02/25/2021
ms.openlocfilehash: 376b74ae52b12056e7799278933eda0f39781f78
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102108315"
---
# <a name="upgrade-a-windows-forms-app-to-net-5-with-the-net-upgrade-assistant"></a>Actualización de una aplicación de Windows Forms a .NET 5 con el Asistente para actualización de .NET

El [Asistente para actualización de .NET](upgrade-assistant-overview.md) es una herramienta de la línea de comandos que puede ayudar en la actualización de aplicaciones .NET Framework de Windows Forms (WinForms) a .NET 5. En este artículo se proporciona:

* Demostración de cómo se ejecuta la herramienta en una aplicación .NET Framework de Windows Forms
* Sugerencias de solución de problemas

## <a name="upgrade-net-framework-windows-forms-apps"></a>Actualización de aplicaciones .NET Framework de Windows Forms

En esta sección se muestra cómo ejecutar el Asistente para actualización de .NET en una aplicación de Windows Forms recién creada para .NET Framework 4.6.1. Para obtener más información sobre cómo instalar la herramienta, consulte [Información general del Asistente para actualización de .NET](upgrade-assistant-overview.md).

### <a name="initial-demo-setup"></a>Configuración inicial de demo

Si está ejecutando el Asistente para actualización de .NET en su propia aplicación .NET Framework, puede omitir este paso. Si solo desea probarlo para ver cómo funciona, este paso le muestra cómo configurar un proyecto .NET de Windows Forms de ejemplo para usarlo.

Con Visual Studio, cree un nuevo proyecto de Windows Forms con .NET Framework.

:::image type="content" source="media/upgrade-assistant-winforms-framework/vs-new-project-winforms.png" alt-text="Nuevo proyecto de Windows Forms en Visual Studio":::

Asigne el nombre **WinformsTest** al proyecto. Configure el proyecto para usar **.NET Framework 4.6.1**.

:::image type="content" source="media/upgrade-assistant-winforms-framework/vs-configure-project-winforms.png" alt-text="Configuración del proyecto de Windows Forms en Visual Studio":::

Revise el proyecto creado y sus archivos, especialmente los archivos de proyecto.

### <a name="run-upgrade-assistant"></a>Ejecución del asistente para actualización

Abra un terminal y desplácese hasta la carpeta en la que se encuentra el proyecto o la solución de destino. Ejecute el comando `upgrade-assistant`, pasando el nombre del proyecto de destino (puede ejecutar el comando desde cualquier lugar, siempre que la ruta de acceso al archivo de proyecto sea válida).

```console
upgrade-assistant .\WinformsTest.csproj
```

La herramienta se ejecuta y muestra una lista de los pasos que realizará.

:::image type="content" source="media/upgrade-assistant-winforms-framework/step1.png" alt-text="Pantalla inicial del Asistente para actualización de .NET":::

A medida que se completa cada paso, la herramienta proporciona un conjunto de comandos que permiten al usuario aplicar u omitir el paso siguiente, consultar más detalles, configurar el registro o salir del proceso. Si la herramienta detecta que un paso no realizará ninguna acción, omitirá automáticamente ese paso y continuará al paso siguiente hasta que llegue a uno que tenga acciones por realizar. Al presionar Entrar, se realizará el siguiente paso si no se realiza ninguna otra selección.

En este ejemplo, cada vez se elige el paso Aplicar. El primer paso es realizar una copia de seguridad del proyecto.

:::image type="content" source="media/upgrade-assistant-winforms-framework/backup-project.png" alt-text="Copia de seguridad del proyecto en el Asistente para actualización de .NET":::

La herramienta solicita una ruta de acceso personalizada para la copia de seguridad o bien usar el valor predeterminado, que colocará la copia de seguridad del proyecto en la misma carpeta con una extensión `.backup`. El siguiente paso que realiza la herramienta es convertir el archivo de proyecto al estilo SDK.

:::image type="content" source="media/upgrade-assistant-winforms-framework/convert-project.png" alt-text="Conversión del proyecto al estilo SDK en el Asistente para actualización de .NET":::

Una vez actualizado el formato del proyecto, el paso siguiente es actualizar el TFM del proyecto.

:::image type="content" source="media/upgrade-assistant-winforms-framework/update-tfm.png" alt-text="Conversión del proyecto al estilo SDK en el Asistente para actualización de .NET":::

A continuación, la herramienta actualiza los paquetes NuGet del proyecto.

:::image type="content" source="media/upgrade-assistant-winforms-framework/update-nuget-packages.png" alt-text="Actualización de los paquetes NuGet en el Asistente para actualización de .NET":::

Una vez actualizados los paquetes, el paso siguiente consiste en agregar archivos de plantilla, si los hay. En este caso, no hay ningún archivo de plantilla que deba agregarse. Este paso continúa y migra los archivos de configuración de la aplicación y actualiza el origen de C# para aplicar correcciones, como se muestra a continuación. Este proyecto no necesitaba ningún archivo de configuración ni cambios de código fuente, por lo que estos pasos se realizaron automáticamente.

:::image type="content" source="media/upgrade-assistant-winforms-framework/add-template-files.png" alt-text="Adición de archivos de plantilla y migración de la configuración en el Asistente para actualización de .NET":::

Como este es el último proyecto, el paso siguiente, "Pasar al siguiente proyecto", le pide que complete el proceso de migración de toda la solución.

:::image type="content" source="media/upgrade-assistant-winforms-framework/complete-solution.png" alt-text="Compleción de la solución en el Asistente para actualización de .NET":::

Una vez completado este proceso, el proyecto de Windows Forms migrado tendrá un aspecto similar al siguiente:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>net5.0-windows</TargetFramework>
    <OutputType>WinExe</OutputType>
    <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
    <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Microsoft.CSharp" Version="4.7.0" />
    <PackageReference Include="Microsoft.DotNet.UpgradeAssistant.Extensions.Default.Analyzers" Version="0.2.211730">
      <PrivateAssets>all</PrivateAssets>
    </PackageReference>
    <PackageReference Include="Microsoft.Windows.Compatibility" Version="5.0.2" />
  </ItemGroup>
</Project>
```

Tenga en cuenta que el Asistente para actualización de .NET también agrega analizadores al proyecto que ayudan a continuar el proceso de actualización.

## <a name="troubleshooting-tips"></a>Sugerencias de solución de problemas

Hay varios problemas conocidos que pueden producirse al usar el Asistente para actualización de .NET. En algunos casos, se trata de problemas con la [herramienta try-convert](https://github.com/dotnet/try-convert) que el Asistente para actualización de .NET usa internamente. Esta herramienta se actualiza con frecuencia para abordar más escenarios, por lo que debe asegurarse de que está usando una versión reciente.

- La herramienta **try-convert** debe instalarse y actualizarse al menos a la versión _0.7.212201_.
- Las versiones anteriores de la herramienta **try-convert** no admitían archivos de destino o de propiedades personalizados. Si no puede actualizar a la versión más reciente, es posible que tenga que resolver manualmente estos problemas. Si el archivo de proyecto de destino incluye referencias a destinos o archivos de propiedades personalizados, puede que sea necesario eliminar manualmente estas referencias del archivo antes de ejecutar el Asistente para actualización de .NET en él.

[El repositorio de GitHub de la herramienta](https://github.com/dotnet/upgrade-assistant#troubleshooting-common-issues) contiene más sugerencias para la solución de problemas y problemas conocidos.

## <a name="see-also"></a>Vea también

- [Actualización de una aplicación de WPF a .NET 5 con el Asistente para actualización de .NET](upgrade-assistant-wpf-framework.md)
- [Actualización de una aplicación ASP.NET de MVC a .NET 5 con el Asistente para actualización de .NET](upgrade-assistant-aspnetmvc.md)
- [Información general sobre el Asistente para actualización de .NET](upgrade-assistant-overview.md)
- [Repositorio de GitHub del Asistente para actualización de .NET](https://github.com/dotnet/upgrade-assistant)
