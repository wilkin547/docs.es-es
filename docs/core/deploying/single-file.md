---
title: Aplicación de archivo único
description: Obtenga información sobre qué es una aplicación de archivo único y por qué debería considerar el uso de este modelo de implementación de aplicaciones.
author: lakshanf
ms.author: lakshanf
ms.date: 12/17/2020
ms.openlocfilehash: 10ffc947f6a3adcf2889a03edd2616007ce236f3
ms.sourcegitcommit: 3a8f1979a98c6c19217a1930e0af5908988eb8ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "98536143"
---
# <a name="single-file-deployment-and-executable"></a>Implementación de archivo único y ejecutable

La agrupación de todos los archivos dependientes de la aplicación en un único binario proporciona a un desarrollador de aplicaciones la opción atractiva de implementar y distribuir la aplicación como un único archivo. Este modelo de implementación está disponible desde .NET Core 3.0 y se ha mejorado en .NET 5.0. Anteriormente en .NET Core 3.0, cuando un usuario ejecuta la aplicación de archivo único, el host de .NET Core primero extrae todos los archivos en un directorio temporal antes de ejecutar la aplicación. En .NET 5.0 se mejora esta experiencia al ejecutar directamente el código sin necesidad de extraer los archivos de la aplicación.

La implementación de archivo único está disponible para el [modelo de implementación dependiente del marco](index.md#publish-framework-dependent) y [aplicaciones independientes](index.md#publish-self-contained). El tamaño del archivo único de una aplicación independiente será grande, ya que incluirá el runtime y las bibliotecas de .NET Framework. La opción de implementación de archivo único se puede combinar con las opciones de publicación [ReadyToRun](ready-to-run.md) y [Trim (una característica experimental de .NET 5.0)](trim-self-contained.md).

## <a name="api-incompatibility"></a>Incompatibilidad de API

Algunas API no son compatibles con la implementación de un solo archivo y las aplicaciones pueden requerir modificaciones si usan estas API. Si usa un paquete o un marco de terceros, es posible que también pueda usar una de estas API y necesite modificarla. La causa más común de los problemas es la dependencia de las rutas de acceso de archivo de los archivos o DLL que se incluyen con la aplicación.

En la tabla siguiente se incluyen los detalles pertinentes de la API de la biblioteca del entorno de ejecución para el uso de un solo archivo.

| API                            | Nota:                                                                   |
|--------------------------------|------------------------------------------------------------------------|
| `Assembly.Location`            | Devuelve una cadena vacía.                                               |
| `Module.FullyQualifiedName`    | Devuelve una cadena con el valor de `<Unknown>` o produce una excepción. |
| `Module.Name`                  | Devuelve una cadena con el valor de `<Unknown>`.                        |
| `Assembly.GetFile`             | Produce <xref:System.IO.IOException>.                                   |
| `Assembly.GetFiles`            | Produce <xref:System.IO.IOException>.                                   |
| `Assembly.CodeBase`            | Produce <xref:System.PlatformNotSupportedException>.                    |
| `Assembly.EscapedCodeBase`     | Produce <xref:System.PlatformNotSupportedException>.                    |
| `AssemblyName.CodeBase`        | Devuelve `null`.                                                        |
| `AssemblyName.EscapedCodeBase` | Devuelve `null`.                                                        |

Tenemos algunas recomendaciones para solucionar escenarios comunes:

* Para obtener acceso a los archivos que se encuentran junto al archivo ejecutable, use <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>.

* Para buscar el nombre del archivo ejecutable, use el primer elemento de <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>.

* Para evitar el envío completo de archivos sueltos, considere la posibilidad de usar [recursos incrustados](../../framework/resources/creating-resource-files-for-desktop-apps.md).

## <a name="attaching-a-debugger"></a>Asociación de un depurador

En Linux, el único depurador que puede asociarse a los procesos de un solo archivo independientes o depurar los volcados de memoria es [SOS con LLDB](../diagnostics/dotnet-sos.md).

En Windows y Mac, Visual Studio y VS Code se pueden usar para depurar volcados de memoria. La asociación a un archivo ejecutable de un solo archivo independiente en ejecución requiere un archivo adicional: _mscordbi.{dll,so}_ .

Sin este archivo, Visual Studio puede producir el error "No se puede asociar al proceso. No se ha instalado un componente de depuración" y VS Code puede generar el error "No se pudo asociar al proceso: Error desconocido: 0x80131c3c".

Para corregir estos errores, _mscordbi_ debe copiarse junto al archivo ejecutable. A _mscordbi_ se le aplica `publish` de forma predeterminada en el subdirectorio con el identificador del entorno de ejecución de la aplicación. Por lo tanto, por ejemplo, si se publica un archivo ejecutable de un solo archivo independiente mediante la CLI de `dotnet` para Windows que usa los parámetros `-r win-x64`, el ejecutable se colocará en _bin/Debug/net5.0/win-x64/publish_. En _bin/Debug/net5.0/win-x64_ hay una copia de _mscordbi.dll_.

## <a name="other-considerations"></a>Otras consideraciones

De forma predeterminada, las aplicaciones de archivo único no agrupan bibliotecas nativas. En Linux, se realiza el enlace previo del runtime a la agrupación y solo se implementan bibliotecas nativas de la aplicación en el mismo directorio que la aplicación de archivo único. En Windows, solo se realiza el enlace previo del código de hospedaje, y el runtime y las bibliotecas nativas de la aplicación se implementan en el mismo directorio que la aplicación de archivo único. Esto permite garantizar una buena experiencia de depuración, que requiere que los archivos nativos se excluyan del archivo único. Hay una opción para establecer una marca, `IncludeNativeLibrariesForSelfExtract`, a fin de incluir bibliotecas nativas en el paquete de archivo único, pero estos archivos se extraerán en un directorio temporal en el equipo cliente cuando se ejecute la aplicación de archivo único.

Si se especifica `IncludeAllContentForSelfExtract`, se extraerán todos los archivos antes de ejecutar el archivo ejecutable. Esto permite conservar el comportamiento original de implementación de un solo archivo de .NET Core.

La aplicación de un solo archivo tendrá todos los archivos PDB relacionados junto con él y no se agrupará de forma predeterminada. Si desea incluir PDB dentro del ensamblado para los proyectos que se compilan, establezca `DebugType` en `embedded` tal y como se describe [a continuación](#include-pdb-files-inside-the-bundle) en detalle.

Los componentes administrados de C++ no son adecuados para la implementación de archivo único y se recomienda escribir aplicaciones en C# u otro lenguaje de C++ no administrado para que sean compatibles con un archivo único.

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

## <a name="include-pdb-files-inside-the-bundle"></a>Inclusión de archivos PDB dentro de la agrupación

El archivo PDB de un ensamblado se puede insertar en el propio ensamblado (`.dll`) mediante la configuración siguiente. Puesto que los símbolos forman parte del ensamblado, también formarán parte de la aplicación de un solo archivo:

```xml
<DebugType>embedded</DebugType>
```

Por ejemplo, agregue la siguiente propiedad al archivo de proyecto de un ensamblado para insertar el archivo PDB en ese ensamblado:

```xml
<PropertyGroup>
  <DebugType>embedded</DebugType>
</PropertyGroup>
```

## <a name="publish-a-single-file-app---sample-project-file"></a>Publicación de una aplicación de archivo único: archivo de proyecto de ejemplo

Este es un archivo de proyecto de ejemplo que especifica la publicación de un archivo único:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <PublishSingleFile>true</PublishSingleFile>
    <SelfContained>true</SelfContained>
    <RuntimeIdentifier>win-x64</RuntimeIdentifier>
    <PublishTrimmed>true</PublishTrimmed>
    <PublishReadyToRun>true</PublishReadyToRun>
  </PropertyGroup>

</Project>
```

Estas propiedades tienen las siguientes funciones:

* `PublishSingleFile`: habilita la publicación de un solo archivo.
* `SelfContained`: determina si la aplicación será independiente o dependiente de la plataforma.
* `RuntimeIdentifier`: especifica el [sistema operativo y el tipo de CPU](../rid-catalog.md) que tiene como destino.
* `PublishTrimmed`: habilita el uso del [recorte de ensamblados](trim-self-contained.md), que solo se admite para aplicaciones independientes.
* `PublishReadyToRun`: habilita la [compilación Ahead Of Time (AOT)](ready-to-run.md).

**Notas:**

* Las aplicaciones son específicas del sistema operativo y de la arquitectura. Debe publicar para cada configuración, como Linux x64, Linux ARM64, Windows x64, etc.
* Los archivos de configuración, como *\*.runtimeconfig.json*, se incluyen en el archivo único. Si se necesita un archivo de configuración adicional, puede colocarlo junto al archivo único.

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
