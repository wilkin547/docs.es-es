---
title: Eliminación de .NET Core Runtime y el SDK
description: En este artículo se describe cómo determinar las versiones de .NET Core Runtime y el SDK instaladas y, luego, cómo quitarlas en Windows, Mac, and Linux.
ms.date: 12/17/2019
author: billwagner
ms.author: wiwagn
ms.custom: updateeachrelease
ms.openlocfilehash: 71c11825981c6259a779e1ac8f947a41618e922d
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503467"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a>Cómo quitar los componentes .NET Core Runtime y SDK

Con el tiempo, a medida que instale versiones actualizadas del runtime y el SDK de .NET Core, es posible que quiera quitar del equipo versiones obsoletas de .NET Core. Al quitar versiones anteriores de runtime puede cambiar el runtime elegido para ejecutar aplicaciones de marco compartidas, tal como se detalla en el artículo sobre [selección de la versión de .NET Core](selection.md).

## <a name="should-i-remove-a-version"></a>¿Puedo quitar una versión?

Los comportamientos de la [selección de la versión de .NET Core](selection.md) y la compatibilidad de runtime de .NET Core en diferentes actualizaciones permite quitar de forma segura las versiones anteriores. Las actualizaciones de .NET Core Runtime son compatibles con una "banda" de versión principal, como 1.x y 2.x. Además, normalmente las versiones más recientes del SDK de .NET Core mantienen la capacidad de crear aplicaciones destinadas a versiones anteriores del tiempo de ejecución de una forma compatible.

En general, solo se necesita el SDK más reciente y la última versión de revisión de los runtimes necesarios para la aplicación. Los casos en los que se conservan versiones anteriores del SDK o de entorno de ejecución incluyen el mantenimiento de aplicaciones basadas en **project.json**. A menos que la aplicación tenga motivos concretos para utilizar SDK o runtimes anteriores, puede quitar las versiones anteriores.

## <a name="determine-what-is-installed"></a>Determinación de lo instalado

A partir de .NET Core 2.1, la CLI de .NET tiene opciones que puede utilizar para enumerar las versiones del SDK y de runtime que están instaladas en el equipo.  Use [`dotnet --list-sdks`](../tools/dotnet.md#options) para ver la lista de los SDK instalados en el equipo. Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) para ver la lista de los runtimes instalados en el equipo. En el texto siguiente se muestra el resultado típico para Windows, macOS o Linux:

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[Windows](#tab/windows)

Al ejecutar el comando siguiente:

```dotnetcli
dotnet --list-sdks
```

Recibe un resultado similar al siguiente:

```console
2.1.200-preview-007474 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007480 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007509 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007570 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007576 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007587 [C:\Program Files\dotnet\sdk]
2.1.200-preview-007589 [C:\Program Files\dotnet\sdk]
2.1.200 [C:\Program Files\dotnet\sdk]
2.1.201 [C:\Program Files\dotnet\sdk]
2.1.202 [C:\Program Files\dotnet\sdk]
2.1.300-preview2-008533 [C:\Program Files\dotnet\sdk]
2.1.300 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009063 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009088 [C:\Program Files\dotnet\sdk]
2.1.400-preview-009171 [C:\Program Files\dotnet\sdk]
```

Y al ejecutar el comando siguiente:

```dotnetcli
dotnet --list-runtimes
```

Recibe un resultado similar al siguiente:

```console
Microsoft.AspNetCore.All 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.0.6 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.7 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.9 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.2 [C:\Program Files\dotnet\shared\Microsoft.NETCore.App]
```

# <a name="linux"></a>[Linux](#tab/linux)

Al ejecutar el comando siguiente:

```dotnetcli
dotnet --list-sdks
```

Recibe un resultado similar al siguiente:

```console
1.0.1 [/usr/share/dotnet/sdk]
1.0.4 [/usr/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/share/dotnet/sdk]
2.0.0 [/usr/share/dotnet/sdk]
2.1.4 [/usr/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/share/dotnet/sdk]
2.1.300 [/usr/share/dotnet/sdk]
2.1.301 [/usr/share/dotnet/sdk]
```

Y al ejecutar el comando siguiente:

```dotnetcli
dotnet --list-runtimes
```

Recibe un resultado similar al siguiente:

```console
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/share/dotnet/shared/Microsoft.NETCore.App]
```

# <a name="macos"></a>[macOS](#tab/macos)

Al ejecutar el comando siguiente:

```dotnetcli
dotnet --list-sdks
```

Recibe un resultado similar al siguiente:

```console
1.0.1 [/usr/local/share/dotnet/sdk]
1.0.4 [/usr/local/share/dotnet/sdk]
2.0.0-preview1-005977 [/usr/local/share/dotnet/sdk]
2.0.0-preview2-006497 [/usr/local/share/dotnet/sdk]
2.0.0 [/usr/local/share/dotnet/sdk]
2.1.4 [/usr/local/share/dotnet/sdk]
2.1.300-preview2-008530 [/usr/local/share/dotnet/sdk]
2.1.300 [/usr/local/share/dotnet/sdk]
2.1.301 [/usr/local/share/dotnet/sdk]
```

Y al ejecutar el comando siguiente:

```dotnetcli
dotnet --list-runtimes
```

Recibe un resultado similar al siguiente:

```console
Microsoft.AspNetCore.All 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.0-preview2-final [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 1.0.4 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 1.1.2 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview1-002111-00 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0-preview2-25407-01 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.0.5 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0-preview2-26406-04 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.1 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

---

## <a name="uninstall-net-core"></a>Desinstalación de .NET Core

# <a name="windows"></a>[Windows](#tab/windows)

.NET Core usa el cuadro de diálogo **Agregar o quitar programas** de Windows para quitar las versiones del runtime de .NET Core y del SDK. En la siguiente ilustración se muestra el cuadro de diálogo **Agregar o quitar programas** con varias versiones del runtime y SDK de .NET instaladas.

![Agregar o quitar programas para quitar .NET Core](./media/remove-runtime-sdk-versions/programs-and-features.png)

Seleccione las versiones que quiera quitar de su equipo y haga clic en **Desinstalar**.

# <a name="linux"></a>[Linux](#tab/linux)

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

Debe quitar los SDK y runtimes por separado, quitando el directorio que contiene dicha versión. Por ejemplo, para quitar el runtime y el SDK 1.0.1, tendrá que usar los siguientes comandos de bash:

```bash
sudo rm -rf /usr/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/share/dotnet/host/fxr/1.0.1
```

Los directorios primarios para el SDK y runtime se enumeran en el resultado de los comandos `dotnet --list-sdks` y `dotnet --list-runtimes`, como se muestra en la tabla anterior.

# <a name="macos"></a>[macOS](#tab/macos)

En Mac, debe quitar los SDK y runtimes por separado, quitando el directorio que contiene dicha versión. Por ejemplo, para quitar el runtime y el SDK 1.0.1, tendrá que usar los siguientes comandos de bash:

```bash
sudo rm -rf /usr/local/share/dotnet/sdk/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/1.0.1
sudo rm -rf /usr/local/share/dotnet/host/fxr/1.0.1
```

Los directorios primarios para el SDK y runtime se enumeran en el resultado de los comandos `dotnet --list-sdks` y `dotnet --list-runtimes`, como se muestra en la tabla anterior.

---

## <a name="net-core-uninstall-tool"></a>Herramienta de desinstalación de .NET Core

La [herramienta de desinstalación de .NET Core](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) permite quitar los SDK y los entornos de ejecución de .NET Core de un sistema. Hay una colección de opciones disponible para especificar las versiones que se deben desinstalar.

## <a name="visual-studio-dependency-on-net-core-sdk-versions"></a>Dependencia de Visual Studio en versiones de SDK de .NET Core

Antes de la versión 16.3 de Visual Studio 2019, los instaladores de Visual Studio llamaron al instalador de SDK de .NET Core independiente. Como resultado, las versiones del SDK aparecen en el cuadro de diálogo **Agregar o quitar programas** de Windows. La eliminación de los SDK de .NET Core que se instalaron con Visual Studio mediante el instalador independiente podría interrumpir Visual Studio. Si Visual Studio tiene problemas después de desinstalar los SDK, ejecute reparar en esa versión específica de Visual Studio. En la tabla siguiente se muestran algunas de las dependencias de Visual Studio en las versiones de SDK de .NET Core:

| Versión de Visual Studio | Versión del SDK de .NET Core |
| -- | -- |
| Visual Studio 2019, versión 16.2 | SDK de .NET Core 2.2.4xx, 2.1.8xx |
| Visual Studio 2019, versión 16.1 | SDK de .NET Core 2.2.3xx, 2.1.7xx |
| Visual Studio 2019, versión 16.0 | SDK de .NET Core 2.2.2xx, 2.1.6xx |
| Visual Studio 2017, versión 15.9 | SDK de .NET Core 2.2.1xx, 2.1.5xx |
| Visual Studio 2017, versión 15.8 | SDK de .NET Core 2.1.4xx |

A partir de la versión 16.3 de Visual Studio 2019, Visual Studio se encarga de su propia copia de la SDK de .NET Core. Por ese motivo, ya no verá las versiones del SDK en el cuadro de diálogo **Agregar o quitar programas**.

## <a name="remove-the-nuget-fallback-folder"></a>Eliminación de la carpeta de reserva de NuGet

Antes del SDK de .NET Core 3.0, los instaladores de SDK de .NET Core usaban *NuGetFallbackFolder* para almacenar una memoria caché de paquetes NuGet. Esta memoria caché se utilizó durante operaciones como `dotnet restore` o `dotnet build /t:Restore`. `NuGetFallbackFolder` se encuentra en *C:\Archivos de programa\dotnet\sdk* en Windows y en */usr/local/share/dotnet/sdk* en macOS.

Es posible que desee quitar esta carpeta si:

* Solo está desarrollando con el SDK de .NET Core 3.0 o versiones posteriores.
* Está desarrollando con versiones SDK de .NET Core anteriores a la 3.0, pero puede trabajar en línea y las cosas pueden ser más lentas una vez.

Si desea quitar la carpeta de reserva de NuGet, puede eliminarla, pero necesitará privilegios de administrador para hacerlo.

No se recomienda eliminar la carpeta *dotnet*. Si lo hace, se quitarán las herramientas globales que haya instalado previamente. Además, en Windows:

- Interrumpirá Visual Studio 2019 versión 16.3 y versiones posteriores. Puede ejecutar **Reparar** para recuperarlo.
- Si hay SDK de .NET Core entradas en el cuadro de diálogo **Agregar o quitar programas**, se quedarán huérfanas.
