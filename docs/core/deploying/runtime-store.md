---
title: Almacenamiento de paquetes en tiempo de ejecución
description: Aprenda a usar el almacenamiento de paquetes en tiempo de ejecución para destinar manifiestos que usa .NET Core.
ms.date: 08/12/2017
ms.openlocfilehash: 7a833ed95147608c6fb403f8f0dec179d2a73833
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448963"
---
# <a name="runtime-package-store"></a>Almacenamiento de paquetes en tiempo de ejecución

A partir de .NET Core 2.0, es posible empaquetar e implementar aplicaciones en un conjunto conocido de paquetes que existen en el entorno de destino. Las ventajas son implementaciones más rápidas, menor uso de espacio en disco y un rendimiento de inicio mejorado en algunos casos.

Esta característica se implementa como un *almacenamiento de paquetes en tiempo de ejecución*, que es un directorio en disco donde se almacenan los paquetes (normalmente en */usr/local/share/dotnet/store* en macOS/Linux y *C:/Program Files/dotnet/store* en Windows). En este directorio, existen subdirectorios para las arquitecturas y las [plataformas de destino](../../standard/frameworks.md). El diseño del archivo es similar a la manera en que los [activos de NuGet se colocan en el disco](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):

```
\dotnet
    \store
        \x64
            \netcoreapp2.0
                \microsoft.applicationinsights
                \microsoft.aspnetcore
                ...
        \x86
            \netcoreapp2.0
                \microsoft.applicationinsights
                \microsoft.aspnetcore
                ...
```

Un archivo de *manifiesto de destino* muestra los paquetes en el almacenamiento de paquetes en tiempo de ejecución. Los desarrolladores pueden dirigirse a este manifiesto cuando publican su aplicación. Normalmente, el propietario del entorno de producción de destino proporciona el manifiesto de destino.

## <a name="preparing-a-runtime-environment"></a>Preparación de un entorno en tiempo de ejecución

El administrador de un entorno en tiempo de ejecución puede optimizar aplicaciones para obtener implementaciones más rápidas y un menor uso de espacio en disco creando un almacenamiento de paquetes en tiempo de ejecución y el manifiesto de destino correspondiente.

El primer paso consiste en crear un *manifiesto de almacenamiento de paquetes* que muestra los paquetes que forman el almacenamiento de paquetes en tiempo de ejecución. El formato de archivo es compatible con el formato de archivo del proyecto (*csproj*).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="<NUGET_PACKAGE>" Version="<VERSION>" />
    <!-- Include additional packages here -->
  </ItemGroup>
</Project>
```

**Ejemplo**

El siguiente manifiesto de almacenamiento de paquetes de ejemplo (*packages.csproj*) se usa para agregar [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) y [`Moq`](https://www.nuget.org/packages/moq/) a un almacenamiento de paquetes en tiempo de ejecución:

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.3" />
    <PackageReference Include="Moq" Version="4.7.63" />
  </ItemGroup>
</Project>
```

Aprovisione el almacenamiento de paquetes en tiempo de ejecución ejecutando `dotnet store` con el manifiesto de almacenamiento de paquetes, el runtime y el marco:

```dotnetcli
dotnet store --manifest <PATH_TO_MANIFEST_FILE> --runtime <RUNTIME_IDENTIFIER> --framework <FRAMEWORK>
```

**Ejemplo**

```dotnetcli
dotnet store --manifest packages.csproj --runtime win10-x64 --framework netcoreapp2.0 --framework-version 2.0.0
```

Puede pasar varias rutas de manifiesto de almacenamiento de paquetes de destino a un único comando [`dotnet store`](../tools/dotnet-store.md) repitiendo la opción y la ruta en el comando.

De manera predeterminada, el resultado del comando es un almacenamiento de paquetes en el subdirectorio *.dotnet/store* del perfil de usuario. Puede especificar una ubicación diferente con la opción `--output <OUTPUT_DIRECTORY>`. El directorio raíz del almacenamiento contiene un archivo *artifact.xml* de manifiesto de destino. Este archivo puede estar disponible para su descarga y usarse por los autores de aplicaciones que quieran dirigirse a este almacenamiento al realizar la publicación.

**Ejemplo**

El siguiente archivo *artifact.xml* se genera después de ejecutar el ejemplo anterior. Tenga en cuenta que [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) es una dependencia de `Moq`, de manera que se incluye automáticamente y aparece en el archivo de manifiesto *artifacts.xml*.

```xml
<StoreArtifacts>
  <Package Id="Newtonsoft.Json" Version="10.0.3" />
  <Package Id="Castle.Core" Version="4.1.0" />
  <Package Id="Moq" Version="4.7.63" />
</StoreArtifacts>
```

## <a name="publishing-an-app-against-a-target-manifest"></a>Publicación de una aplicación en un manifiesto de destino

Si tiene un archivo de manifiesto de destino en disco, especifique la ruta al archivo al publicar su aplicación con el comando [`dotnet publish`](../tools/dotnet-publish.md):

```dotnetcli
dotnet publish --manifest <PATH_TO_MANIFEST_FILE>
```

**Ejemplo**

```dotnetcli
dotnet publish --manifest manifest.xml
```

Implemente la aplicación publicada resultante en un entorno que tenga los paquetes descritos en el manifiesto de destino. Realizar esto incorrectamente produce errores en el inicio de la aplicación.

Especifique varios manifiestos de destino al publicar una aplicación repitiendo la opción y la ruta (por ejemplo, `--manifest manifest1.xml --manifest manifest2.xml`). Cuando realice esto, la aplicación se reduce para la unión de los paquetes especificados en los archivos de manifiesto de destino que se proporcionan para el comando.

## <a name="specifying-target-manifests-in-the-project-file"></a>Especificar los manifiestos de destino en el archivo del proyecto

Una alternativa de especificar manifiestos de destino con el comando [`dotnet publish`](../tools/dotnet-publish.md) es especificarlos en el archivo de proyecto como una lista de rutas separadas por punto y coma en una etiqueta **\<TargetManifestFiles>** .

```xml
<PropertyGroup>
  <TargetManifestFiles>manifest1.xml;manifest2.xml</TargetManifestFiles>
</PropertyGroup>
```

Especifique los manifiestos de destino en el archivo de proyecto solo cuando el entorno de destino de la aplicación sea muy conocido, como para los proyectos de .NET Core. Este no es el caso de los proyectos de código abierto. Los usuarios de un proyecto de código abierto normalmente lo implementan en diferentes entornos de producción. Estos entornos de producción generalmente tienen diferentes conjuntos de paquetes preinstalados. No puede realizar presuposiciones sobre el manifiesto de destino en dichos entornos, por lo que debe usar la opción `--manifest` de [`dotnet publish`](../tools/dotnet-publish.md).

## <a name="aspnet-core-implicit-store"></a>Almacenamiento implícito de ASP.NET Core

El almacenamiento implícito de ASP.NET Core solo se aplica a ASP.NET Core 2.0. Se recomienda encarecidamente que las aplicaciones usen ASP.NET Core 2.1 y versiones posteriores, que **no** usan almacenamiento implícito. ASP.NET Core 2.1 y versiones posteriores usan el marco de trabajo compartido.

La característica de almacenamiento de paquetes en tiempo de ejecución se usa implícitamente por una aplicación de ASP.NET Core cuando la aplicación se implementa como una aplicación de [implementación dependiente del marco (FDD)](index.md#publish-runtime-dependent). Los destinos en [`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) incluyen manifiestos que hacen referencia al almacenamiento de paquetes implícito en el sistema de destino. Además, cualquier aplicación de FDD que depende del paquete `Microsoft.AspNetCore.All` tiene como resultado una aplicación publicada que contiene solo la aplicación y sus activos y no los paquetes que se muestran en el metapaquete `Microsoft.AspNetCore.All`. Se presupone que esos paquetes están presentes en el sistema de destino.

El almacenamiento de paquetes en tiempo de ejecución está instalado en el host cuando el SDK de .NET Core está instalado. Otros instaladores pueden proporcionar el almacenamiento de paquetes en tiempo de ejecución, incluidas las instalaciones Zip/tarball del SDK de .NET Core, `apt-get`, Red Hat Yum, la agrupación de hospedaje de Windows Server para .NET Core y las instalaciones manuales de almacenamiento de paquetes en tiempo de ejecución.

Al implementar una aplicación de [implementación dependiente del marco (FDD)](index.md#publish-runtime-dependent), asegúrese de que el entorno de destino tiene el SDK de .NET Core instalado. Si la aplicación se implementa en un entorno que no incluye ASP.NET Core, puede rechazar el almacenamiento implícito especificando **\<PublishWithAspNetCoreTargetManifest>** en `false` en el archivo de proyecto como se muestra en el ejemplo siguiente:

```xml
<PropertyGroup>
  <PublishWithAspNetCoreTargetManifest>false</PublishWithAspNetCoreTargetManifest>
</PropertyGroup>
```

> [!NOTE]
> Para las aplicaciones de [implementación independiente (SCD)](index.md#publish-self-contained), se presupone que el sistema de destino no contiene necesariamente los paquetes de manifiesto necesarios. Por lo tanto, **\<PublishWithAspNetCoreTargetManifest>** no puede establecerse en `true` para una aplicación de SCD.

Si implementa una aplicación con una dependencia de manifiesto que está presente en la implementación (el ensamblado está presente en la carpeta *bin*), el almacenamiento de paquetes en tiempo de ejecución *no se usa* en el host de ese ensamblado. El ensamblado de la carpeta *bin* se usa independientemente de su presencia en el almacenamiento de paquetes en tiempo de ejecución en el host.

La versión de la dependencia indicada en el manifiesto debe coincidir con la versión de la dependencia en el almacenamiento de paquetes en tiempo de ejecución. Si no coinciden las versiones entre la dependencia del manifiesto de destino y la versión que existe en el almacenamiento de paquetes en tiempo de ejecución, y la aplicación no incluye la versión necesaria del paquete en su implementación, se produce un error en el inicio de la aplicación. La excepción incluye el nombre del manifiesto de destino que se ha llamado para el ensamblado del almacenamiento de paquetes en tiempo de ejecución, que le ayuda a solucionar los errores de coincidencia.

Cuando la implementación se *reduce* en su publicación, solo las versiones específicas de los paquetes de manifiesto que indique se retienen del resultado publicado. Los paquetes de las versiones indicadas deben estar presentes en el host para que se inicie la aplicación.

## <a name="see-also"></a>Vea también

- [dotnet-publish](../tools/dotnet-publish.md)
- [dotnet-store](../tools/dotnet-store.md)
