---
title: 'Instalación y administración de plantillas de SDK: .NET Core'
description: Obtenga información sobre cómo instalar plantillas de .NET Core en Windows, Linux y macOS.
author: adegeo
ms.author: adegeo
ms.date: 04/24/2020
zone_pivot_groups: operating-systems-set-one
no-loc:
- dotnet new
- dotnet nuget add source
ms.openlocfilehash: 09acae1409eb0492be10bd3a61b14da5be57c6c7
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324490"
---
# <a name="manage-net-project-and-item-templates"></a>Administración de plantillas de proyectos y elementos de .NET

.NET Core proporciona un sistema de plantillas que permite a los usuarios instalar o desinstalar plantillas de NuGet, un archivo de paquete NuGet o un directorio del sistema de archivos. En este artículo se describe cómo administrar plantillas de .NET Core a través de la CLI del SDK de .NET Core.

Para obtener más información sobre la creación de plantillas, consulte [Tutorial: Creación de plantillas](../tutorials/cli-templates-create-item-template.md).

## <a name="install-template"></a>Instalación de plantillas

Las plantillas se instalan mediante el comando [dotnet new](../tools/dotnet-new.md) del SDK con el parámetro `-i`. Puede proporcionar el identificador de paquete NuGet de una plantilla o una carpeta que contenga los archivos de plantilla.

### <a name="nuget-hosted-package"></a>Paquete hospedado en NuGet

Las plantillas de la CLI de .NET se cargan en [NuGet](https://www.nuget.org/) para una distribución amplia. Las plantillas también se pueden instalar desde una fuente privada. En lugar de cargar una plantilla en una fuente de NuGet, los archivos de plantilla de *nupkg* se pueden distribuir e instalar manualmente, tal como se describe en la sección [Paquete NuGet local](#local-nuget-package).

Para obtener más información sobre cómo configurar las fuentes de NuGet, vea [dotnet nuget add source](../tools/dotnet-nuget-add-source.md).

Para instalar un paquete de plantillas desde la fuente de NuGet predeterminada, use el comando `dotnet new -i {package-id}`:

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates
```

Para instalar un paquete de plantillas desde la fuente de NuGet predeterminada con una versión específica, use el comando `dotnet new -i {package-id}::{version}`:

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.2.6
```

### <a name="local-nuget-package"></a>Paquete NuGet local

Cuando se crea un paquete de plantillas, se genera un archivo *nupkg*. Si tiene un archivo *nupkg* que contiene plantillas, puede instalarlo con el comando `dotnet new -i {path-to-package}`:

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\Some.Templates.1.0.0.nupkg
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/Some.Templates.1.0.0.nupkg
```

::: zone-end

### <a name="folder"></a>Carpeta

Como alternativa a la instalación de una plantilla desde un archivo *nupkg*, también puede instalar plantillas desde una carpeta directamente con el comando `dotnet new -i {folder-path}`. La carpeta especificada se trata como el identificador del paquete de plantillas para cualquier plantilla que se encuentre. Se instalarán todas las plantillas que estén en la jerarquía de la carpeta especificada.

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\some-folder\
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/some-folder/
```

::: zone-end

La ruta `{folder-path}` especificada en el comando se convierte en el identificador del paquete de plantillas para todas las plantillas que se encuentren. Tal como se especifica en la sección [Enumeración de las plantillas](#list-templates), puede obtener una lista de las plantillas instaladas con el comando `dotnet new -u`. En este ejemplo, el identificador del paquete de plantillas se muestra como la carpeta que se ha usado para la instalación:

::: zone pivot="os-windows"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  /home/username/code/templates
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="uninstall-template"></a>Desinstalación de plantillas

Las plantillas se desinstalan mediante el comando [dotnet new](../tools/dotnet-new.md) del SDK con el parámetro `-u`. Puede proporcionar el identificador de paquete NuGet de una plantilla o una carpeta que contenga los archivos de plantilla.

### <a name="nuget-package"></a>Detección de

Una vez instalado el paquete de plantillas de NuGet, ya sea desde una fuente de NuGet o un archivo *nupkg*, puede desinstalarlo mediante una referencia al identificador de paquete NuGet.

Para desinstalar un paquete de plantillas, use el comando `dotnet new -u {package-id}`:

```dotnetcli
dotnet new -u Microsoft.DotNet.Web.Spa.ProjectTemplates
```

### <a name="folder"></a>Carpeta

Cuando las plantillas se instalan a través de una [ruta de acceso de carpeta](#folder), dicha ruta se convierte en el identificador del paquete de plantillas.

Para desinstalar un paquete de plantillas, use el comando `dotnet new -u {package-folder-path}`:

::: zone pivot="os-windows"

```dotnetcli
dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="list-templates"></a>Enumeración de plantillas

Al usar el comando de desinstalación estándar sin un identificador de paquete, puede ver una lista de las plantillas instaladas, junto con el comando que desinstala cada plantilla.

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

## <a name="install-templates-from-other-sdks"></a>Instalación de plantillas desde otros SDK

Si ha instalado cada versión del SDK secuencialmente (por ejemplo, si ha instalado el SDK 2.0, después el SDK 2.1, etc.), tendrá instaladas todas las plantillas del SDK. Pero si comienza con una versión posterior del SDK, como la 3.1, solo se incluyen las plantillas para las [versiones LTS (compatibilidad a largo plazo)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que en el momento de la versión 3.1 del SDK son SDK 2.1 y el SDK 3.1. No se incluyen las plantillas para ninguna otra versión.

Las plantillas de .NET Core están disponibles en NuGet y se pueden instalar como cualquier otra plantilla. Para obtener más información, consulte [Instalación del paquete hospedado en NuGet](#nuget-hosted-package).

| SDK              | Identificador del paquete NuGet                                                                                                      |
|------------------|-------------------------------------------------------------------------------------------------------------------------------|
| .NET Core 2.1    | [`Microsoft.DotNet.Common.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.1) |
| .NET Core 2.2    | [`Microsoft.DotNet.Common.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.2) |
| .NET Core 3.0    | [`Microsoft.DotNet.Common.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.0) |
| .NET Core 3.1    | [`Microsoft.DotNet.Common.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.1) |
| ASP.NET Core 2.1 | [`Microsoft.DotNet.Web.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.1)       |
| ASP.NET Core 2.2 | [`Microsoft.DotNet.Web.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.2)       |
| ASP.NET Core 3.0 | [`Microsoft.DotNet.Web.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.0)       |
| ASP.NET Core 3.1 | [`Microsoft.DotNet.Web.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.1)       |

Por ejemplo, el SDK de .NET Core incluye plantillas para una aplicación de consola que tiene como destino .NET Core 2.1 y .NET Core 3.1. Si quiere que el destino sea .NET Core 3.0, deberá instalar las plantillas de 3.0.

01. Pruebe a crear una aplicación destinada a .NET Core 3.0.

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    Si ve un mensaje de error, debe instalar las plantillas.

    > No se pudo encontrar una plantilla instalada que coincida con la entrada. Buscando en línea una que coincida…

01. Instale las plantillas de proyecto de .NET Core 3.0.

    ```dotnetcli
    dotnet new -i Microsoft.DotNet.Common.ProjectTemplates.3.0
    ```

01. Pruebe a crear la aplicación otra vez.

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    Debería ver un mensaje que indica que se ha creado el proyecto.

    > La plantilla "Console Application" se creó correctamente.
    >
    > Procesando acciones posteriores a la creación… Ejecutando "dotnet restore" en path-to-project-file.csproj… Determinando los proyectos que se van a restaurar… Restauración completada en 1,05 s para path-to-project-file.csproj.
    >
    > Restauración correcta.

## <a name="see-also"></a>Vea también

- [Tutorial: Creación de una plantilla de elemento](../tutorials/cli-templates-create-item-template.md).
- [dotnet new](../tools/dotnet-new.md)
- [dotnet nuget add source](../tools/dotnet-nuget-add-source.md)
