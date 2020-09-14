---
title: Aplicación de archivo único
description: Obtenga información sobre qué es una aplicación de archivo único y por qué debería considerar el uso de este modelo de implementación de aplicaciones.
author: lakshanf
ms.author: lakshanf
ms.date: 08/28/2020
ms.openlocfilehash: 795ea98a9fd9d672b199eb2d9b24151340ef8246
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495758"
---
# <a name="single-file-deployment-and-executable"></a>Implementación de archivo único y ejecutable

La agrupación de todos los archivos dependientes de la aplicación en un único binario proporciona a un desarrollador de aplicaciones la opción atractiva de implementar y distribuir la aplicación como un único archivo. Este modelo de implementación está disponible desde .NET Core 3.0 y se ha mejorado en .NET 5.0. Anteriormente en .NET Core 3.0, cuando un usuario ejecuta la aplicación de archivo único, el host de .NET Core primero extrae todos los archivos en un directorio temporal antes de ejecutar la aplicación. En .NET 5.0 se mejora esta experiencia al ejecutar directamente el código sin necesidad de extraer los archivos de la aplicación.

La implementación de archivo único está disponible para el [modelo de implementación dependiente del marco](index.md#publish-framework-dependent) y [aplicaciones independientes](index.md#publish-self-contained). El tamaño del archivo único de una aplicación independiente será grande, ya que incluirá el runtime y las bibliotecas de .NET Framework. La opción de implementación de archivo único se puede combinar con las opciones de publicación [ReadyToRun](../tools/dotnet-publish.md) y [Trim (una característica experimental de .NET 5.0)](trim-self-contained.md).

Hay algunos inconvenientes que debe tener en cuenta sobre el uso de un archivo único; en primer lugar, se utiliza la información de la ruta de acceso para localizar un archivo en relación con la ubicación de la aplicación. La API <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> devolverá una cadena vacía, que es el comportamiento predeterminado de los ensamblados cargados desde la memoria. El compilador generará una advertencia para esta API durante el tiempo de compilación para avisar al desarrollador del comportamiento concreto. Si se necesita la ruta de acceso al directorio de la aplicación, la API <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> devolverá el directorio donde reside AppHost (el propio paquete de archivo único). Las aplicaciones administradas de C++ no son adecuadas para la implementación de archivo único y se recomienda escribir aplicaciones en C# para que sea compatibles con un archivo único.

De forma predeterminada, las aplicaciones de archivo único no agrupan bibliotecas nativas. En Linux, se realiza el enlace previo del runtime a la agrupación y solo se implementan bibliotecas nativas de la aplicación en el mismo directorio que la aplicación de archivo único. En Windows, solo se realiza el enlace previo del código de hospedaje, y el runtime y las bibliotecas nativas de la aplicación se implementan en el mismo directorio que la aplicación de archivo único. Esto permite garantizar una buena experiencia de depuración, que requiere que los archivos nativos se excluyan del archivo único. Hay una opción para establecer una marca, `IncludeNativeLibrariesForSelfExtract`, a fin de incluir bibliotecas nativas en el paquete de archivo único, pero estos archivos se extraerán en un directorio temporal en el equipo cliente cuando se ejecute la aplicación de archivo único.

## <a name="exclude-files-from-being-embedded"></a>Exclusión de archivos de la inserción

Algunos archivos se pueden excluir de forma explícita de su inserción en el único archivo si se establecen los metadatos siguientes:

```xml
<ExcludeFromSingleFile>true</ExcludeFromSingleFile>
```

Por ejemplo, para colocar algunos archivos en el directorio de publicación pero no empaquetarlos en el archivo único:

```xml
<ItemGroup>
  <Content Update="Plugin.dll">
    <CopyToPublishDirectory>PreserveNewest</CopyToPublishDirectory>
    <ExcludeFromSingleFile>true</ExcludeFromSingleFile>
  </Content>
</ItemGroup>
```

## <a name="publish-a-single-file-app---cli"></a>Publicación de una aplicación de archivo único: CLI

Publique una aplicación de archivo único mediante el comando [dotnet publish](../tools/dotnet-publish.md). Al publicar la aplicación, establezca las propiedades siguientes:

- Publicación para un runtime concreto: `-r win-x64`
- Publicación como archivo único: `-p:PublishSingleFile=true`

En el ejemplo siguiente se publica una aplicación para Windows como aplicación independiente de archivo único.

```dotnetcli
dotnet publish -r win-x64 -p:PublishSingleFile=true --self-contained true
```

En el ejemplo siguiente se publica una aplicación para Linux como una aplicación de archivo único dependiente del marco.

```dotnetcli
dotnet publish -r linux-x64 -p:PublishSingleFile=true --self-contained false
```

Para obtener más información, vea [Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).

## <a name="publish-a-single-file-app---visual-studio"></a>Publicación de una aplicación de archivo único: Visual Studio

Visual Studio crea perfiles de publicación reutilizables que controlan cómo se publica la aplicación.

01. En el panel **Explorador de soluciones**, haga clic con el botón derecho en el proyecto que quiera publicar. Seleccione **Publicar**.

    :::image type="content" source="media/single-file/visual-studio-solution-explorer.png" alt-text="Explorador de soluciones con un menú contextual en el que se resalta la opción Publicar.":::

    Si todavía no tiene un perfil de publicación, siga las instrucciones para crear uno y elija el tipo de destino **Carpeta**.

01. Elija **Editar**.

    :::image type="content" source="media/single-file/visual-studio-publish-edit-settings.png" alt-text="Perfil de publicación de Visual Studio con el botón Editar.":::

01. En el cuadro de diálogo **Configuración de perfil**, establezca las opciones siguientes:

    - Establezca **Modo de implementación** en **Independiente**.
    - Establezca **Tiempo de ejecución de destino** en la plataforma en la que quiera publicar.
    - Seleccione **Producir un único archivo**.

    Elija **Guardar** para guardar la configuración y volver al cuadro de diálogo **Publicar**.

    :::image type="content" source="media/single-file/visual-studio-publish-single-file-properties.png" alt-text="Cuadro de diálogo Configuración de perfil con las opciones Modo de implementación, Tiempo de ejecución de destino y Archivo único resaltadas.":::

01. Elija **Publicar** para publicar la aplicación como un archivo único.

Para obtener más información, vea [Publicación de aplicaciones .NET Core con Visual Studio](deploy-with-vs.md).

## <a name="publish-a-single-file-app---visual-studio-for-mac"></a>Publicación de una aplicación de archivo único: Visual Studio para Mac

Visual Studio para Mac no proporciona opciones para publicar la aplicación como un archivo único. Tendrá que publicar de forma manual mediante las instrucciones de la sección [Publicación de una aplicación de archivo único: CLI](#publish-a-single-file-app---cli). Para obtener más información, vea [Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).

## <a name="see-also"></a>Vea también

- [Implementación de aplicaciones .NET Core](index.md).
- [Publicación de aplicaciones .NET Core con la CLI de .NET Core](deploy-with-cli.md).
- [Publicación de aplicaciones .NET Core con Visual Studio](deploy-with-vs.md).
- [Comando `dotnet publish`](../tools/dotnet-publish.md).
