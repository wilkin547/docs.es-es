---
title: Eliminación de .NET Core Runtime y el SDK
description: En este artículo se describe cómo determinar las versiones de .NET Core Runtime y el SDK instaladas y, luego, cómo quitarlas en Windows, Mac, and Linux.
author: adegeo
ms.author: adegeo
ms.date: 04/28/2020
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 1e4a846cf5e3d0209f5ade873520ef64abc12e7c
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324644"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a>Cómo quitar los componentes .NET Core Runtime y SDK

Con el tiempo, a medida que instale versiones actualizadas del runtime y el SDK de .NET Core, es posible que quiera quitar del equipo versiones obsoletas de .NET Core. Al quitar versiones anteriores de runtime puede cambiar el runtime elegido para ejecutar aplicaciones de marco compartidas, tal como se detalla en el artículo sobre [selección de la versión de .NET Core](../versions/selection.md).

## <a name="should-i-remove-a-version"></a>¿Puedo quitar una versión?

Los comportamientos de la [selección de la versión de .NET Core](../versions/selection.md) y la compatibilidad de runtime de .NET Core en diferentes actualizaciones permite quitar de forma segura las versiones anteriores. Las actualizaciones de .NET Core Runtime son compatibles con una "banda" de versión principal, como 1.x y 2.x. Además, normalmente las versiones más recientes del SDK de .NET Core mantienen la capacidad de crear aplicaciones destinadas a versiones anteriores del tiempo de ejecución de una forma compatible.

En general, solo se necesita el SDK más reciente y la última versión de revisión de los runtimes necesarios para la aplicación. Los casos en los que interesa conservar versiones anteriores del SDK o del runtime incluyen el mantenimiento de aplicaciones basadas en *project.json*. A menos que la aplicación tenga motivos concretos para utilizar SDK o runtimes anteriores, puede quitar las versiones anteriores.

## <a name="determine-what-is-installed"></a>Determinación de lo instalado

A partir de .NET Core 2.1, la CLI de .NET tiene opciones que puede utilizar para enumerar las versiones del SDK y de runtime que están instaladas en el equipo.  Use [`dotnet --list-sdks`](../tools/dotnet.md#options) para ver la lista de los SDK instalados en el equipo. Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) para ver la lista de los runtimes instalados en el equipo. Para más información, consulte [Cómo comprobar que .NET Core ya está instalado](how-to-detect-installed-versions.md).

## <a name="uninstall-net-core"></a>Desinstalación de .NET Core

::: zone pivot="os-windows"

.NET Core usa el cuadro de diálogo **Aplicaciones y características** de Windows para quitar las versiones del runtime de .NET Core y del SDK. En la siguiente ilustración se muestra el cuadro de diálogo **Aplicaciones y características**. Puede buscar **core sdk** para filtrar y mostrar las versiones instaladas de .NET Core.

![Agregar o quitar programas para quitar .NET Core](./media/remove-runtime-sdk-versions/programs-and-features.png)

Seleccione las versiones que quiera quitar de su equipo y haga clic en **Desinstalar**.

::: zone-end

::: zone pivot="os-linux"

Para desinstalar .NET Core (SDK o runtime) en Linux tiene más opciones. La mejor forma de desinstalar .NET Core es repetir la misma acción que se usó para instalarlo. Los detalles específicos dependerán de la distribución que elija y del método de instalación.

> [!IMPORTANT]
> Para obtener información sobre las instalaciones y desinstalaciones de .NET Core en Red Hat, consulte la [Guía de introducción a Red Hat](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel).

A partir de .NET Core 2.1, no hace falta desinstalar el SDK de .NET Core al actualizarlo mediante un administrador de paquetes. Los comandos `update` o `refresh` del administrador de paquetes quitarán automáticamente la versión anterior tras la instalación correcta de una versión más reciente.

Si ha instalado .NET Core con un administrador de paquetes, use ese mismo administrador de paquetes para desinstalar el SDK o el runtime de .NET. Las instalaciones de .NET Core admiten los administradores de paquetes más populares. Consulte la documentación del administrador de paquetes de su distribución para conocer la sintaxis exacta en su entorno:

- [apt-get(8)](https://linux.die.net/man/8/apt-get) se utiliza en sistemas basados en Debian, incluido Ubuntu.
- [yum(8)](https://linux.die.net/man/8/yum) se utiliza en Fedora, CentOS y Oracle Linux.
- [zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) se utiliza en openSUSE y SUSE Linux Enterprise Server (SLES).
- [DNF(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) se utiliza en Fedora.

En casi todos los casos, el comando para quitar un paquete es `remove`.

El nombre del paquete para la instalación del SDK de .NET Core para la mayoría de administradores de paquetes es `dotnet-sdk`, seguido por el número de versión. A partir de la versión 2.1.300 del SDK de .NET Core y de la versión `2.1` del runtime, solo se requieren el primer y el segundo número de versión: por ejemplo, puede hacer referencia a la versión 2.1.300 del SDK de .NET Core como el paquete `dotnet-sdk-2.1`. Para las versiones anteriores se requiere la cadena de versión completa: por ejemplo, se requeriría `dotnet-sdk-2.1.200` para la versión 2.1.200 del SDK de .NET Core.

En los equipos en los que solo se ha instalado el runtime, y no el SDK, el nombre del paquete es `dotnet-runtime-<version>` para .NET Core Runtime y `aspnetcore-runtime-<version>` para la pila de runtime entera.

Al instalar las versiones de .NET Core anteriores a 2.0 no se desinstaló la aplicación host al desinstalar el SDK mediante el administrador de paquetes. Al usar `apt-get`, el comando es:

```bash
apt-get remove dotnet-host
```

Tenga en cuenta que no hay ninguna versión conectada a `dotnet-host`.

Si ha realizado la instalación mediante un paquete tarball, debe quitar .NET Core mediante el método manual.

En Linux, debe quitar los SDK y runtimes por separado, quitando los directorios con versiones. De esta manera, se elimina el SDK y el runtime del disco. Por ejemplo, para quitar el runtime y el SDK 1.0.1, tendrá que usar los siguientes comandos de bash:

```bash
version="1.0.1"
sudo rm -rf /usr/local/share/dotnet/sdk/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.All/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/$version
sudo rm -rf /usr/local/share/dotnet/host/fxr/$version
```

Los directorios primarios para el SDK y runtime se enumeran en el resultado de los comandos `dotnet --list-sdks` y `dotnet --list-runtimes`, como se muestra en la tabla anterior.

::: zone-end

::: zone pivot="os-macos"

En Mac, debe quitar los SDK y runtimes por separado, quitando los directorios con versiones. De esta manera, se elimina el SDK y el runtime del disco. Por ejemplo, para quitar el runtime y el SDK 1.0.1, tendrá que usar los siguientes comandos de bash:

```bash
version="1.0.1"
sudo rm -rf /usr/local/share/dotnet/sdk/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.All/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/$version
sudo rm -rf /usr/local/share/dotnet/host/fxr/$version
```

Los directorios primarios para el SDK y runtime se enumeran en el resultado de los comandos `dotnet --list-sdks` y `dotnet --list-runtimes`, como se muestra en la tabla anterior.

::: zone-end

## <a name="net-core-uninstall-tool"></a>Herramienta de desinstalación de .NET Core

La [herramienta de desinstalación de .NET Core](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) permite quitar los SDK y los entornos de ejecución de .NET Core de un sistema. Hay una colección de opciones disponible para especificar las versiones que se deben desinstalar.

## <a name="visual-studio-dependency-on-net-core-sdk-versions"></a>Dependencia de Visual Studio en versiones de SDK de .NET Core

Antes de la versión 16.3 de Visual Studio 2019, los instaladores de Visual Studio llamaron al instalador de SDK de .NET Core independiente. Como resultado, las versiones del SDK aparecen en el cuadro de diálogo **Aplicaciones y características** de Windows. La eliminación de los SDK de .NET Core que se instalaron con Visual Studio mediante el instalador independiente podría interrumpir Visual Studio. Si Visual Studio tiene problemas después de desinstalar los SDK, ejecute reparar en esa versión específica de Visual Studio. En la tabla siguiente se muestran algunas de las dependencias de Visual Studio en las versiones de SDK de .NET Core:

| Versión de Visual Studio           | Versión del SDK de .NET Core          |
|---------------------------------|--------------------------------|
| Visual Studio 2019, versión 16.2 | SDK de .NET Core 2.2.4xx, 2.1.8xx |
| Visual Studio 2019, versión 16.1 | SDK de .NET Core 2.2.3xx, 2.1.7xx |
| Visual Studio 2019, versión 16.0 | SDK de .NET Core 2.2.2xx, 2.1.6xx |
| Visual Studio 2017, versión 15.9 | SDK de .NET Core 2.2.1xx, 2.1.5xx |
| Visual Studio 2017, versión 15.8 | SDK de .NET Core 2.1.4xx          |

A partir de la versión 16.3 de Visual Studio 2019, Visual Studio se encarga de su propia copia de la SDK de .NET Core. Por ese motivo, ya no verá las versiones del SDK en el cuadro de diálogo **Aplicaciones y características**.

## <a name="remove-the-nuget-fallback-folder"></a>Eliminación de la carpeta de reserva de NuGet

Antes del SDK de .NET Core 3.0, los instaladores del SDK de .NET Core usaban una carpeta denominada *NuGetFallbackFolder* para almacenar una memoria caché de paquetes NuGet. Esta memoria caché se utilizó durante operaciones como `dotnet restore` o `dotnet build /t:Restore`. La carpeta *NuGetFallbackFolder* se encuentra en *C:\Archivos de programa\dotnet\sdk* en Windows y en */usr/local/share/dotnet/sdk* en macOS.

Es posible que desee quitar esta carpeta si:

- Solo está desarrollando con el SDK de .NET Core 3.0 o versiones posteriores.
- Está desarrollando con versiones del SDK de .NET Core anteriores a la 3.0, pero puede trabajar en línea.

Si desea quitar la carpeta de reserva de NuGet, puede eliminarla, pero necesitará privilegios de administrador para hacerlo.

No se recomienda eliminar la carpeta *dotnet*. Si lo hace, se quitarán las herramientas globales que haya instalado previamente. Además, en Windows:

- Interrumpirá Visual Studio 2019 versión 16.3 y versiones posteriores. Puede ejecutar **Reparar** para recuperarlo.
- Si hay entradas del SDK de .NET Core en el cuadro de diálogo **Aplicaciones y características**, se quedarán huérfanas.
