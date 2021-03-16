---
title: Actualización de aplicaciones de MVC de ASP.NET a .NET 5
description: Use el Asistente para actualización de .NET para actualizar una aplicación .NET Framework de MVC de ASP.NET existente a .NET 5. El Asistente para actualización de .NET es una herramienta de la CLI que ayuda a migrar una aplicación de .NET Framework a .NET 5.
author: ardalis
ms.date: 02/25/2021
ms.openlocfilehash: 0c9af9e12b78df7c4a2aaed18155f7ee9f02870d
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102108362"
---
# <a name="upgrade-an-aspnet-mvc-app-to-net-5-with-the-net-upgrade-assistant"></a>Actualización de una aplicación ASP.NET de MVC a .NET 5 con el Asistente para actualización de .NET

El [Asistente para actualización de .NET](upgrade-assistant-overview.md) es una herramienta de la línea de comandos que puede ayudar en la actualización de aplicaciones .NET Framework de MVC de ASP.NET a .NET 5. En este artículo se proporciona:

* Demostración de cómo se ejecuta la herramienta en una aplicación .NET Framework de MVC de ASP.NET
* Sugerencias de solución de problemas

## <a name="upgrade-net-framework-aspnet-mvc-apps"></a>Actualización de aplicaciones .NET Framework de ASP.NET de MVC

En esta sección se muestra cómo ejecutar el Asistente para actualización de .NET en una aplicación de MVC de ASP.NET recién creada para .NET Framework 4.6.1. Para obtener más información sobre cómo instalar la herramienta, consulte [Información general del Asistente para actualización de .NET](upgrade-assistant-overview.md).

### <a name="initial-demo-setup"></a>Configuración inicial de demo

Si está ejecutando el Asistente para actualización de .NET en su propia aplicación .NET Framework, puede omitir este paso. Si solo desea probarlo para ver cómo funciona, este paso le muestra cómo configurar un proyecto de ejemplo de MVC de ASP.NET y API web (.NET Framework) para usarlo.

Con Visual Studio, cree un nuevo proyecto de aplicación web de ASP.NET con .NET Framework.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/new-project.png" alt-text="Nuevo proyecto de aplicación web de ASP.NET en Visual Studio":::

Asigne el nombre **AspNetMvcTest** al proyecto. Configure el proyecto para usar **.NET Framework 4.6.1**.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/configure-project.png" alt-text="Configuración del proyecto de ASP.NET en Visual Studio":::

En el siguiente cuadro de diálogo, elija la aplicación **MVC** y, a continuación, seleccione **Crear**.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/create-mvc-webapi.png" alt-text="Creación de un proyecto de MVC de ASP.NET en Visual Studio":::

Revise el proyecto creado y sus archivos, especialmente los archivos de proyecto.

### <a name="run-upgrade-assistant"></a>Ejecución del asistente para actualización

Abra un terminal y desplácese hasta la carpeta en la que se encuentra el proyecto o la solución de destino. Ejecute el comando `upgrade-assistant`, pasando el nombre del proyecto de destino (puede ejecutar el comando desde cualquier lugar, siempre que la ruta de acceso al archivo de proyecto sea válida).

```console
upgrade-assistant .\AspNetMvcTest.csproj
```

La herramienta se ejecuta y muestra una lista de los pasos que realizará.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/initial-run.png" alt-text="Pantalla inicial del Asistente para actualización de .NET":::

A medida que se completa cada paso, la herramienta proporciona un conjunto de comandos que permiten al usuario aplicar u omitir el paso siguiente, consultar más detalles, configurar el registro o salir del proceso. Si la herramienta detecta que un paso no realizará ninguna acción, omite automáticamente ese paso y continua al paso siguiente hasta que llega a uno que tiene acciones por realizar. Al presionar <kbd>Entrar</kbd>, se realizará el siguiente paso si no se realiza ninguna otra selección.

En este ejemplo, cada vez se elige el paso Aplicar. El primer paso es realizar una copia de seguridad del proyecto.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/backup-project.png" alt-text="Copia de seguridad del proyecto en el Asistente para actualización de .NET":::

La herramienta solicita una ruta de acceso personalizada para la copia de seguridad o bien usar el valor predeterminado, que colocará la copia de seguridad del proyecto en la misma carpeta con una extensión `.backup`. El siguiente paso que realiza la herramienta es convertir el archivo de proyecto al estilo SDK.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/convert-project.png" alt-text="Conversión del proyecto al estilo SDK en el Asistente para actualización de .NET":::

Una vez actualizado el formato del proyecto, el paso siguiente es actualizar el TFM del proyecto.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/update-tfm.png" alt-text="Conversión del proyecto al estilo SDK en el Asistente para actualización de .NET":::

A continuación, la herramienta actualiza los paquetes NuGet del proyecto. Varios paquetes necesitan actualizaciones y se agrega un nuevo paquete de analizador.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/update-nuget-packages.png" alt-text="Actualización de los paquetes NuGet en el Asistente para actualización de .NET":::

Una vez actualizados los paquetes, el paso siguiente consiste en agregar archivos de plantilla, si los hay. La herramienta observa que hay cuatro elementos de plantilla esperados que se deben agregar y, a continuación, los agrega. Entre ellos, se incluyen los siguientes archivos:

- `Program.cs`
- `Startup.cs`
- `appsettings.json`
- `appsettings.Development.json`

Estos archivos se usan en ASP.NET Core para el [inicio](/aspnet/core/fundamentals/startup) y la [configuración de la aplicación](/aspnet/core/fundamentals/configuration).

:::image type="content" source="media/upgrade-assistant-aspnetmvc/add-template-files.png" alt-text="Adición de archivos de plantilla en el Asistente para actualización de .NET":::

A continuación, la herramienta migra los archivos de configuración. La herramienta identifica la configuración de la aplicación, deshabilita las secciones de configuración no admitidas y, a continuación, migra los valores de configuración de `appSettings`.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/migrate-config.png" alt-text="Migración de la configuración en el Asistente para actualización de .NET":::

La herramienta completa la migración de los archivos de configuración con la migración de `system.web.webPages.razor/pages/namespaces`.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/migrate-config2.png" alt-text="Migración de la configuración en el Asistente para actualización de .NET":::

La herramienta aplica correcciones conocidas para migrar las referencias de C# a sus nuevos homólogos.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/update-csharp.png" alt-text="Actualización del origen de C# en el Asistente para actualización de .NET":::

Como este es el último proyecto, el paso siguiente, "Pasar al siguiente proyecto", le pide que complete el proceso de migración de toda la solución.

:::image type="content" source="media/upgrade-assistant-aspnetmvc/complete-solution.png" alt-text="Compleción de la solución en el Asistente para actualización de .NET":::

Una vez completado este proceso, abra el archivo del proyecto y revíselo. Busque archivos estáticos como los siguientes:

```xml
  <ItemGroup>
    <Content Include="fonts\glyphicons-halflings-regular.woff2" />
    <Content Include="fonts\glyphicons-halflings-regular.woff" />
    <Content Include="fonts\glyphicons-halflings-regular.ttf" />
    <Content Include="fonts\glyphicons-halflings-regular.eot" />
    <Content Include="Content\bootstrap.min.css.map" />
    <Content Include="Content\bootstrap.css.map" />
    <Content Include="Content\bootstrap-theme.min.css.map" />
    <Content Include="Content\bootstrap-theme.css.map" />
    <Content Include="Scripts\jquery-3.4.1.slim.min.map" />
    <Content Include="Scripts\jquery-3.4.1.min.map" />
  </ItemGroup>
```

Los archivos estáticos que debe proporcionar el servidor web deben trasladarse a una carpeta adecuada dentro de una carpeta de nivel raíz denominada `wwwroot`. Consulte [Archivos estáticos en ASP.NET Core](/aspnet/core/fundamentals/static-files?view=aspnetcore-5.0) para obtener más información. Una vez que se han trasladado los archivos, se pueden eliminar los elementos `<Content>` del archivo del proyecto correspondientes a estos archivos. De hecho, se pueden quitar todos los elementos `<Content>` y sus grupos contenedores. Además, debe quitarse cualquier `<PackageReference>` en una biblioteca del lado del cliente como `bootstrap` o `jQuery`.

De forma predeterminada, el proyecto se convertirá como una biblioteca de clases. Cambie el atributo `Sdk` de la primera línea a `Microsoft.NET.Sdk.Web` y establezca `<TargetFramework>` en `net5.0`. Compile el proyecto. En este momento, el número de errores debería ser bastante pequeño. Al portar un nuevo proyecto de MVC de ASP.NET 4.6.1, los errores restantes hacen referencia a archivos de la carpeta `App_Start`:

- BundleConfig.cs
- FilterConfig.cs
- RouteConfig.cs

Estos archivos (y toda la carpeta `App_Start`) se pueden eliminar. Del mismo modo, los archivos `Global.asax` y `Global.asax.cs` se pueden quitar.

En este momento, los únicos errores que quedan están relacionados con la unión. Hay [varias maneras de configurar la unión y la minificación en ASP.NET Core](/aspnet/core/migration/mvc?view=aspnetcore-5.0#configure-bundling-and-minification). Elija la que sea más conveniente para el proyecto.

## <a name="troubleshooting-tips"></a>Sugerencias de solución de problemas

Hay varios problemas conocidos que pueden producirse al usar el Asistente para actualización de .NET. En algunos casos, se trata de problemas con la [herramienta try-convert](https://github.com/dotnet/try-convert) que el Asistente para actualización de .NET usa internamente. Esta herramienta se actualiza con frecuencia para abordar más escenarios, por lo que debe asegurarse de que está usando una versión reciente.

- La herramienta **try-convert** debe instalarse y actualizarse al menos a la versión _0.7.212201_.
- Las versiones anteriores de la herramienta **try-convert** no admitían archivos de destino o de propiedades personalizados. Si no puede actualizar a la versión más reciente, es posible que tenga que resolver manualmente estos problemas. Si el archivo de proyecto de destino incluye referencias a destinos o archivos de propiedades personalizados, puede que sea necesario eliminar manualmente estas referencias del archivo antes de ejecutar el Asistente para actualización de .NET en él.

```xml
<Import Project="packages\Microsoft.CodeDom.Providers.DotNetCompilerPlatform.2.0.1\build\net46\Microsoft.CodeDom.Providers.DotNetCompilerPlatform.props" Condition="Exists('packages\Microsoft.CodeDom.Providers.DotNetCompilerPlatform.2.0.1\build\net46\Microsoft.CodeDom.Providers.DotNetCompilerPlatform.props')" />
```

[El repositorio de GitHub de la herramienta](https://github.com/dotnet/upgrade-assistant#troubleshooting-common-issues) contiene más sugerencias para la solución de problemas y problemas conocidos.

## <a name="see-also"></a>Vea también

- [Actualización de una aplicación de WPF a .NET 5 con el Asistente para actualización de .NET](upgrade-assistant-wpf-framework.md)
- [Actualización de una aplicación de Windows Forms a .NET 5 con el Asistente para actualización de .NET](upgrade-assistant-winforms-framework.md)
- [Información general sobre el Asistente para actualización de .NET](upgrade-assistant-overview.md)
- [Repositorio de GitHub del Asistente para actualización de .NET](https://github.com/dotnet/upgrade-assistant)
