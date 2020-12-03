---
title: Eliminación del entorno de ejecución y el SDK de .NET
description: En este artículo se describe cómo determinar las versiones del entorno de ejecución y el SDK de .NET instaladas y, luego, cómo quitarlas en Windows, Mac, and Linux.
author: adegeo
ms.author: adegeo
ms.date: 11/20/2020
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: f07a9acdc5be310d38da18602dde2ebf678e9a1b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031727"
---
# <a name="how-to-remove-the-net-runtime-and-sdk"></a>Procedimiento para quitar el entorno de ejecución y el SDK de .NET

Con el tiempo, a medida que instale versiones actualizadas del entorno de ejecución y el SDK de .NET, es posible que quiera quitar del equipo las versiones obsoletas de .NET. Al quitar versiones anteriores del entorno de ejecución es posible que se cambie el elegido para ejecutar aplicaciones de marco compartido, como se detalla en el artículo sobre [selección de la versión de .NET](../versions/selection.md).

## <a name="should-i-remove-a-version"></a>¿Puedo quitar una versión?

Los comportamientos de la [selección de la versión de .NET](../versions/selection.md) y la compatibilidad del entorno de ejecución de .NET entre actualizaciones permite quitar de forma segura las versiones anteriores. Las actualizaciones del entorno de ejecución de .NET son compatibles con una **banda** de versión principal, como 1.x y 2.x. Además, normalmente las versiones más recientes del SDK de .NET mantienen la capacidad de crear aplicaciones destinadas a versiones anteriores del entorno de ejecución de una forma compatible.

En general, solo se necesita el SDK más reciente y la última versión de revisión de los runtimes necesarios para la aplicación. Los casos en los que interesa conservar versiones anteriores del SDK o del runtime incluyen el mantenimiento de aplicaciones basadas en *project.json*. A menos que la aplicación tenga motivos concretos para utilizar SDK o runtimes anteriores, puede quitar las versiones anteriores.

## <a name="determine-what-is-installed"></a>Determinación de lo instalado

La CLI de .NET tiene opciones que puede usar para enumerar las versiones del SDK y del entorno de ejecución instaladas en el equipo.  Use [`dotnet --list-sdks`](../tools/dotnet.md#options) para ver la lista de los SDK instalados en el equipo. Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) para ver la lista de los runtimes instalados en el equipo. Para obtener más información, vea [Cómo comprobar que .NET Core ya está instalado](how-to-detect-installed-versions.md).

## <a name="uninstall-net"></a>Desinstalación de .NET

::: zone pivot="os-windows"

.NET usa el cuadro de diálogo **Aplicaciones y características** de Windows para quitar las versiones del entorno de ejecución y del SDK de .NET. En la siguiente ilustración se muestra el cuadro de diálogo **Aplicaciones y características**. Puede buscar **core sdk** o **.net sdk** para filtrar y mostrar las versiones instaladas de .NET.

![Agregar o quitar programas para quitar .NET](./media/remove-runtime-sdk-versions/programs-and-features.png)

Seleccione las versiones que quiera quitar de su equipo y haga clic en **Desinstalar**.

::: zone-end

::: zone pivot="os-linux"

Para desinstalar .NET (el SDK o el entorno de ejecución) en Linux tiene más opciones. La mejor forma de desinstalar .NET es repetir la misma acción que se ha usado para instalarlo. Los detalles específicos dependerán de la distribución que elija y del método de instalación.

> [!IMPORTANT]
> Para las instalaciones de Red Hat, consulte la [documentación del producto Red Hat para .NET](https://access.redhat.com/documentation/en-us/net/5.0/).

No es necesario desinstalar el SDK de .NET al actualizarlo mediante un administrador de paquetes, a menos que se actualice desde una versión preliminar. Los comandos `update` o `refresh` del administrador de paquetes quitarán automáticamente la versión anterior tras la instalación correcta de una versión más reciente. Si tiene instalada una versión preliminar, desinstálela.

Si ha instalado .NET con un administrador de paquetes, use ese mismo administrador de paquetes para desinstalar el SDK o el entorno de ejecución de .NET. Las instalaciones de .NET admiten los administradores de paquetes más conocidos. Consulte la documentación del administrador de paquetes de su distribución para conocer la sintaxis exacta en su entorno:

- [apt-get(8)](https://linux.die.net/man/8/apt-get) se utiliza en sistemas basados en Debian, incluido Ubuntu.
- [yum(8)](https://linux.die.net/man/8/yum) se utiliza en Fedora, CentOS y Oracle Linux.
- [zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) se utiliza en openSUSE y SUSE Linux Enterprise Server (SLES).
- [DNF(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) se utiliza en Fedora.

En casi todos los casos, el comando para quitar un paquete es `remove`.

El nombre del paquete para la instalación del SDK de .NET en la mayoría de administradores de paquetes es `dotnet-sdk`, seguido por el número de versión. A partir de la versión 2.1.300 del SDK de .NET y de la versión `2.1` del entorno de ejecución, solo se necesitan el primer y el segundo número de versión: por ejemplo, puede hacer referencia a la versión 2.1.300 del SDK de .NET como el paquete `dotnet-sdk-2.1`. Para las versiones anteriores se necesita la cadena de versión completa: por ejemplo, se necesitaría `dotnet-sdk-2.1.200` para la versión 2.1.200 del SDK de .NET.

En los equipos en los que solo se ha instalado el entorno de ejecución, y no el SDK, el nombre del paquete es `dotnet-runtime-<version>` para el entorno de ejecución de .NET y `aspnetcore-runtime-<version>` para la pila de entorno de ejecución entera.

> [!TIP]
> Al instalar las versiones de .NET Core anteriores a 2.0 no se desinstaló la aplicación host al desinstalar el SDK mediante el administrador de paquetes. Al usar `apt-get`, el comando es:
>
> ```bash
> apt-get remove dotnet-host
> ```
>
> No hay ninguna versión conectada a `dotnet-host`.

Si ha realizado la instalación mediante un archivo tarball, debe quitar .NET mediante el método manual.

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

## <a name="net-uninstall-tool"></a>Herramienta de desinstalación de .NET

La [herramienta de desinstalación de .NET](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) permite quitar los SDK y los entornos de ejecución de .NET de un sistema. Hay una colección de opciones disponible para especificar las versiones que se deben desinstalar.

## <a name="visual-studio-dependency-on-net-core-sdk-versions"></a>Dependencia de Visual Studio en versiones de SDK de .NET Core

Antes de la versión 16.3 de Visual Studio 2019, los instaladores de Visual Studio llamaron al instalador de SDK de .NET Core independiente. Como resultado, las versiones del SDK aparecen en el cuadro de diálogo **Aplicaciones y características** de Windows. La eliminación de los SDK de .NET Core que se instalaron con Visual Studio mediante el instalador independiente podría interrumpir Visual Studio. Si Visual Studio tiene problemas después de desinstalar los SDK, ejecute reparar en esa versión específica de Visual Studio. En la tabla siguiente se muestran algunas de las dependencias de Visual Studio en las versiones de SDK de .NET Core:

| Versión de Visual Studio           | Versión del SDK de .NET Core          |
|---------------------------------|--------------------------------|
| Visual Studio 2019, versión 16.2 | SDK de .NET Core 2.2.4xx, 2.1.8xx |
| Visual Studio 2019, versión 16.1 | SDK de .NET Core 2.2.3xx, 2.1.7xx |
| Visual Studio 2019, versión 16.0 | SDK de .NET Core 2.2.2xx, 2.1.6xx |
| Visual Studio 2017, versión 15.9 | SDK de .NET Core 2.2.1xx, 2.1.5xx |
| Visual Studio 2017, versión 15.8 | SDK de .NET Core 2.1.4xx          |

A partir de la versión 16.3 de Visual Studio 2019, Visual Studio se encarga de su propia copia del SDK de .NET. Por ese motivo, ya no verá las versiones del SDK en el cuadro de diálogo **Aplicaciones y características**.

## <a name="remove-the-nuget-fallback-folder"></a>Eliminación de la carpeta de reserva de NuGet

Antes del SDK de .NET Core 3.0, los instaladores del SDK de .NET Core usaban una carpeta denominada *NuGetFallbackFolder* para almacenar una memoria caché de paquetes NuGet. Esta memoria caché se utilizó durante operaciones como `dotnet restore` o `dotnet build /t:Restore`. La carpeta *NuGetFallbackFolder* se encuentra en *C:\Archivos de programa\dotnet\sdk* en Windows y en */usr/local/share/dotnet/sdk* en macOS.

Es posible que desee quitar esta carpeta si:

- Solo desarrolla con el SDK de .NET Core 3.0, .NET 5.0 o versiones posteriores.
- Está desarrollando con versiones del SDK de .NET Core anteriores a la 3.0, pero puede trabajar en línea.

Si desea quitar la carpeta de reserva de NuGet, puede eliminarla, pero necesitará privilegios de administrador para hacerlo.

No se recomienda eliminar la carpeta *dotnet*. Si lo hace, se quitarán las herramientas globales que haya instalado previamente. Además, en Windows:

- Interrumpirá Visual Studio 2019 versión 16.3 y versiones posteriores. Puede ejecutar **Reparar** para recuperarlo.
- Si hay entradas del SDK de .NET Core en el cuadro de diálogo **Aplicaciones y características**, se quedarán huérfanas.
