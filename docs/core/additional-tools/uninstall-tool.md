---
title: Herramienta de desinstalación
description: Información general de la herramienta de desinstalación de .NET Core, una herramienta guiada que permite limpiar de forma controlada los SDK y los entornos en tiempo de ejecución de .NET Core.
author: sfoslund
ms.date: 05/27/2020
ms.openlocfilehash: ed43b4ec8437ae0ccaf5f1234758dda9f16bd51e
ms.sourcegitcommit: 4f5f1855849cb02c3b610c7006ac21d7429f3348
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "98235357"
---
# <a name="net-core-uninstall-tool"></a>Herramienta de desinstalación de .NET Core

La [herramienta de desinstalación de .NET Core](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) permite quitar los SDK y los entornos en tiempo de ejecución de .NET Core de un sistema. Hay una colección de opciones disponible para especificar las versiones que desea desinstalar.

La herramienta es compatible con Windows y macOS. Linux no se admite actualmente.

En Windows, la herramienta solo puede desinstalar los SDK y entornos en tiempo de ejecución que se instalaron mediante uno de los siguientes instaladores:

- El instalador del SDK y del entorno en tiempo de ejecución de .NET Core.
- El instalador de Visual Studio en versiones anteriores a Visual Studio 2019, versión 16.3.

En macOS, la herramienta solo puede desinstalar los SDK y entornos en tiempo de ejecución ubicados en la carpeta */usr/local/share/dotnet*.

Debido a estas limitaciones, es posible que la herramienta no pueda desinstalar todos los SDK y los entornos en tiempo de ejecución de .NET Core de la máquina. Puede usar el comando `dotnet --info` para buscar todos los SDK y los entornos en tiempo de ejecución de .NET Core instalados, incluidos los entornos en tiempo de ejecución y SDK que esta herramienta no puede quitar. El comando `dotnet-core-uninstall list` muestra qué SDK se pueden desinstalar con la herramienta. La versión 1.2 y posteriores pueden desinstalar SDK y entornos de ejecución con la versión 5.0 o anteriores, mientras que las versiones anteriores de la herramienta pueden desinstalar la versión 3.1 y anteriores.

## <a name="install-the-tool"></a>Instalación de la herramienta

Puede descargar la herramienta de desinstalación de .NET Core desde [la página de versiones de la herramienta](https://aka.ms/dotnet-core-uninstall-tool) y encontrar el código fuente en el repositorio [dotnet/cli-lab](https://github.com/dotnet/cli-lab) de GitHub.

> [!NOTE]
> La herramienta requiere elevación para desinstalar los SDK y los entornos en tiempo de ejecución de .NET Core. Por lo tanto, debe instalarse en un directorio protegido contra escritura, como *C:\Archivos de programa* en Windows o */usr/local/bin* en macOS. Consulte también [Acceso con privilegios elevados para comandos de dotnet](../tools/elevated-access.md). Para obtener más información, vea las [instrucciones de instalación detalladas](https://aka.ms/dotnet-core-uninstall-tool).

## <a name="run-the-tool"></a>Ejecución de la herramienta

En los pasos siguientes se muestra el enfoque recomendado para ejecutar la herramienta de desinstalación:

- [Paso 1: Mostrar los SDK y los entornos en tiempo de ejecución de .NET Core instalados](#step-1---display-installed-net-core-sdks-and-runtimes)
- [Paso 2: Realizar un simulacro](#step-2---do-a-dry-run)
- [Paso 3: Desinstalar los SDK y los entornos en tiempo de ejecución de .NET Core](#step-3---uninstall-net-core-sdks-and-runtimes)
- [Paso 4: Eliminar la carpeta de reserva de NuGet (opcional)](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a>Paso 1: Mostrar los SDK y los entornos en tiempo de ejecución de .NET Core instalados

El comando `dotnet-core-uninstall list` enumera los SDK y los entornos en tiempo de ejecución de .NET Core instalados que se pueden quitar con esta herramienta. Visual Studio puede necesitar algunos SDK y entornos en tiempo de ejecución, que se muestran con una nota de por qué no se recomienda desinstalarlos.

> [!NOTE]
> En la mayoría de los casos, la salida del comando `dotnet-core-uninstall list` no coincidirá con la lista de versiones instaladas en la salida de `dotnet --info`. En concreto, esta herramienta no mostrará las versiones instaladas mediante archivos ZIP ni administradas por Visual Studio (cualquier versión instalada con Visual Studio 2019 16.3 o posterior). Una manera de comprobar si una versión está administrada por Visual Studio es verla en `Add or Remove Programs`, donde las versiones administradas de Visual Studio se marcan como tales en sus nombres para mostrar.

**dotnet-core-uninstall list**

#### <a name="synopsis"></a>Sinopsis

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a>Opciones

## <a name="windows"></a>[Windows](#tab/windows)

* **`--aspnet-runtime`**

  Enumera todos los entornos en tiempo de ejecución de ASP.NET Core que se pueden desinstalar con esta herramienta.

* **`--hosting-bundle`**

  Enumera todos los conjuntos de hospedaje de .NET Core que se pueden desinstalar con esta herramienta.

* **`--runtime`**

  Enumera todos los entornos en tiempo de ejecución de .NET Core que se pueden desinstalar con esta herramienta.

* **`--sdk`**

  Enumera todos los SDK de .NET Core que se pueden desinstalar con esta herramienta.

* **`-v, --verbosity <LEVEL>`**

  Establece el nivel de detalle. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. El valor predeterminado es `normal`.

* **`--x64`**

  Enumera todos los SDK y entornos en tiempo de ejecución de .NET Core x64 que se pueden desinstalar con esta herramienta.

* **`--x86`**

  Enumera todos los SDK y entornos en tiempo de ejecución de .NET Core x86 que se pueden desinstalar con esta herramienta.

## <a name="macos"></a>[macOS](#tab/macos)

* **`--runtime`**

  Enumera todos los entornos en tiempo de ejecución de .NET Core que se pueden desinstalar con esta herramienta.

* **`--sdk`**

  Enumera todos los SDK de .NET Core que se pueden desinstalar con esta herramienta.

* **`-v, --verbosity <LEVEL>`**

  Establece el nivel de detalle. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. El valor predeterminado es `normal`.
  
---

#### <a name="examples"></a>Ejemplos

* Enumerar todos los SDK y entornos en tiempo de ejecución de .NET Core que se pueden quitar con esta herramienta:

  ```console
  dotnet-core-uninstall list
  ```

* Enumerar todos los SDK y entornos en tiempo de ejecución de .NET Core x64:

  ```console
  dotnet-core-uninstall list --x64
  ```

* Enumerar todos los SDK de .NET Core x86:

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a>Paso 2: Realizar un simulacro

Los comandos `dotnet-core-uninstall dry-run` y `dotnet-core-uninstall whatif` muestran los SDK y los entornos en tiempo de ejecución de .NET Core que se quitarán en función de las opciones proporcionadas sin realizar la desinstalación. Estos comandos son sinónimos.

**dotnet-core-uninstall dry-run y dotnet-core-uninstall whatif**

#### <a name="synopsis"></a>Sinopsis

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a>Argumentos

* **`VERSION`**

  La versión especificada que se va a desinstalar. Puede enumerar varias versiones una detrás de la otra, separadas por espacios. También se admiten los archivos de respuesta.

  > [!TIP]
  > Los archivos de respuesta son una alternativa a la colocación de todas las versiones en la línea de comandos.
  > Son archivos de texto, normalmente con una extensión \*.rsp y cada versión aparece en una línea independiente.
  > Para especificar un archivo de respuesta para el argumento `VERSION`, use el carácter \@ seguido inmediatamente del nombre del archivo de respuesta.

#### <a name="options"></a>Opciones

## <a name="windows"></a>[Windows](#tab/windows)

* **`--all`**

  Quita todos los SDK y entornos en tiempo de ejecución de .NET Core.

* **`--all-below <VERSION>[ <VERSION>...]`**

  Quita solo los SDK y los entornos en tiempo de ejecución de .NET Core que tienen una versión menor que la versión especificada. La versión especificada permanece instalada.

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  Quita todos los SDK y entornos en tiempo de ejecución de .NET Core, excepto las versiones especificadas.

* **`--all-but-latest`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto la versión más alta.

* **`--all-lower-patches`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core reemplazados por revisiones superiores. Esta opción protege el archivo global.json.

* **`--all-previews`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares.

* **`--all-previews-but-latest`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares, excepto la versión preliminar más alta.

* **`--aspnet-runtime`**

  Solo quita los entornos en tiempos de ejecución de ASP.NET Core.

* **`--hosting-bundle`**

  Quita el entorno en tiempo de ejecución de .NET Core y los conjuntos de hospedaje.

* **`--major-minor <MAJOR_MINOR>`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core que coinciden con la versión `major.minor` especificada.

* **`--runtime`**

  Solo quita los entornos en tiempo de ejecución de .NET Core.

* **`--sdk`**

  Solo quita los SDK de .NET Core.

* **`-v, --verbosity <LEVEL>`**

  Establece el nivel de detalle. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. El valor predeterminado es `normal`.

* **`--x64`**

  Se debe usar con `--sdk`, `--runtime` y `--aspnet-runtime` para quitar los SDK o los entornos en tiempo de ejecución x64.

* **`--x86`**

  Se debe usar con `--sdk`, `--runtime` y `--aspnet-runtime` para quitar los SDK o los entornos en tiempo de ejecución x86.

* **`--force`** Fuerza la eliminación de las versiones que Visual Studio puede usar.

Notas:

1. Se requiere exactamente uno de los valores `--sdk`, `--runtime`, `--aspnet-runtime` y `--hosting-bundle`.
2. `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` y `[<VERSION>...]` son valores exclusivos.
3. Si no se especifica `--x64` o `--x86`, se quitarán tanto x64 como x86.

## <a name="macos"></a>[macOS](#tab/macos)

* **`--all`**

  Quita todos los SDK y entornos en tiempo de ejecución de .NET Core.

* **`--all-below <VERSION>[ <VERSION>...]`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core inferiores a la versión especificada. La versión especificada se conservará.

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto las versiones especificadas.

* **`--all-but-latest`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto la versión más alta.

* **`--all-lower-patches`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core reemplazados por revisiones superiores. Esta opción protege el archivo global.json.

* **`--all-previews`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares.

* **`--all-previews-but-latest`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares, excepto la versión preliminar más alta.

* **`--major-minor <MAJOR_MINOR>`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core que coinciden con la versión `major.minor` especificada.

* **`--runtime`**

  Solo quita los entornos en tiempo de ejecución de .NET Core.

* **`--sdk`**

  Solo quita los SDK de .NET Core.

* **`-v, --verbosity <LEVEL>`**

  Establece el nivel de detalle. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. El valor predeterminado es `normal`.
  
* **`--force`** Fuerza la eliminación de las versiones que Visual Studio o los SDK puedes usar.

Notas:

1. Se requiere uno de los valores `--sdk` y `--runtime`.
2. `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` y `[<VERSION>...]` son valores exclusivos.

---

#### <a name="examples"></a>Ejemplos

> [!NOTE]
> De forma predeterminada, los SDK y los entornos en tiempo de ejecución de .NET Core que puede necesitar Visual Studio u otros SDK no se incluyen en la salida de `dotnet-core-uninstall dry-run`. En los siguientes ejemplos, es posible que algunos de los SDK y entornos en tiempo de ejecución especificados no se incluyan en la salida, según el estado de la máquina. Para incluir todos los SDK y entornos en tiempo de ejecución, agréguelos explícitamente como argumentos o use la opción `--force`.

* Realizar un simulacro de la eliminación de todos entornos en tiempo de ejecución de .NET Core que se han reemplazado por revisiones superiores:

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* Realizar un simulacro de la eliminación de todos los SDK de .NET Core inferiores a la versión `2.2.301`:

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a>Paso 3: Desinstalar los SDK y los entornos en tiempo de ejecución de .NET Core

`dotnet-core-uninstall remove` desinstala los SDK y los entornos en tiempo de ejecución de .NET Core especificados por una colección de opciones. La versión 1.2 y posteriores pueden desinstalar SDK y entornos de ejecución con la versión 5.0 o anteriores, mientras que las versiones anteriores de la herramienta pueden desinstalar la versión 3.1 y anteriores.

Dado que esta herramienta tiene un comportamiento destructivo, es **altamente** recomendable que realice un simulacro antes de ejecutar el comando remove. El simulacro le mostrará qué SDK y entornos en tiempo de ejecución de .NET Core se quitarán cuando use el comando `remove`. Consulte [¿Puedo quitar una versión?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version) para saber qué SDK y entornos en tiempo de ejecución se pueden quitar de forma segura.

> [!CAUTION]
> Tenga en cuenta las siguientes advertencias:
>
>- Esta herramienta puede desinstalar las versiones del SDK de .NET Core que necesitan los archivos `global.json` de la máquina. Puede volver a instalar los SDK de .NET Core desde la página [Descarga de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).
>- Esta herramienta puede desinstalar las versiones del entorno en tiempo de ejecución de .NET Core que necesitan las aplicaciones que dependen del marco de trabajo de la máquina. Puede volver a instalar los entornos en tiempo de ejecución de .NET Core desde la página [Descarga de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).
>- Esta herramienta puede desinstalar las versiones del SDK y del entorno en tiempo de ejecución de .NET Core en las que se basa Visual Studio. Si interrumpe la instalación de Visual Studio, ejecute "Reparar" en el instalador de Visual Studio para volver a un estado de funcionamiento.

De forma predeterminada, todos los comandos mantienen los SDK y los entornos en tiempo de ejecución de .NET Core que puede necesitar Visual Studio u otros SDK. Estos SDK y entornos en tiempos de ejecución se pueden desinstalar si se enumeran explícitamente como argumentos o mediante la opción `--force`.

La herramienta requiere elevación para desinstalar los SDK y los entornos en tiempo de ejecución de .NET Core. Ejecute la herramienta en un símbolo del sistema de administrador en Windows y con `sudo` en macOS. Los comandos `dry-run` y `whatif` no requieren elevación.

**dotnet-core-uninstall remove**

#### <a name="synopsis"></a>Sinopsis

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a>Argumentos

* **`VERSION`**

  La versión especificada que se va a desinstalar. Puede enumerar varias versiones una detrás de la otra, separadas por espacios. También se admiten los archivos de respuesta.

  > [!TIP]
  > Los archivos de respuesta son una alternativa a la colocación de todas las versiones en la línea de comandos.
  > Son archivos de texto, normalmente con una extensión \*.rsp y cada versión aparece en una línea independiente.
  > Para especificar un archivo de respuesta para el argumento `VERSION`, use el carácter \@ seguido inmediatamente del nombre del archivo de respuesta.

#### <a name="options"></a>Opciones

## <a name="windows"></a>[Windows](#tab/windows)

* **`--all`**

  Quita todos los SDK y entornos en tiempo de ejecución de .NET Core.

* **`--all-below <VERSION>[ <VERSION>...]`**

  Quita solo los SDK y los entornos en tiempo de ejecución de .NET Core que tienen una versión menor que la versión especificada. La versión especificada permanece instalada.

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  Quita todos los SDK y entornos en tiempo de ejecución de .NET Core, excepto las versiones especificadas.

* **`--all-but-latest`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto la versión más alta.

* **`--all-lower-patches`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core reemplazados por revisiones superiores. Esta opción protege el archivo global.json.

* **`--all-previews`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares.

* **`--all-previews-but-latest`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares, excepto la versión preliminar más alta.

* **`--aspnet-runtime`**

  Solo quita los entornos en tiempos de ejecución de ASP.NET Core.

* **`--hosting-bundle`**

  Solo quita conjuntos de hospedaje de .NET Core.

* **`--major-minor <MAJOR_MINOR>`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core que coinciden con la versión `major.minor` especificada.

* **`--runtime`**

  Solo quita los entornos en tiempo de ejecución de .NET Core.

* **`--sdk`**

  Solo quita los SDK de .NET Core.

* **`-v, --verbosity <LEVEL>`**

  Establece el nivel de detalle. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. El valor predeterminado es `normal`.

* **`--x64`**

  Se debe usar con `--sdk`, `--runtime` y `--aspnet-runtime` para quitar los SDK o los entornos en tiempo de ejecución x64.

* **`--x86`**

  Se debe usar con `--sdk`, `--runtime` y `--aspnet-runtime` para quitar los SDK o los entornos en tiempo de ejecución x86.

* **`-y, --yes`** Ejecuta el comando sin requerir una confirmación sí o no.

* **`--force`** Fuerza la eliminación de las versiones que Visual Studio puede usar.

Notas:

1. Se requiere exactamente uno de los valores `--sdk`, `--runtime`, `--aspnet-runtime` y `--hosting-bundle`.
2. `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` y `[<VERSION>...]` son valores exclusivos.
3. Si no se especifica `--x64` o `--x86`, se quitarán tanto x64 como x86.

## <a name="macos"></a>[macOS](#tab/macos)

* **`--all`**

  Quita todos los SDK y entornos en tiempo de ejecución de .NET Core.

* **`--all-below <VERSION>[ <VERSION>...]`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core inferiores a la versión especificada. La versión especificada se conservará.

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto las versiones especificadas.

* **`--all-but-latest`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core, excepto la versión más alta.

* **`--all-lower-patches`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core reemplazados por revisiones superiores. Esta opción protege el archivo global.json.

* **`--all-previews`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares.

* **`--all-previews-but-latest`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core marcados como versiones preliminares, excepto la versión preliminar más alta.

* **`--major-minor <MAJOR_MINOR>`**

  Quita los SDK y los entornos en tiempo de ejecución de .NET Core que coinciden con la versión `major.minor` especificada.

* **`--runtime`**

  Solo quita los entornos en tiempo de ejecución de .NET Core.

* **`--sdk`**

  Solo quita los SDK de .NET Core.

* **`-v, --verbosity <LEVEL>`**

  Establece el nivel de detalle. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. El valor predeterminado es `normal`.

* **`-y, --yes`** Ejecuta el comando sin requerir una confirmación S/N.
  
* **`--force`** Fuerza la eliminación de las versiones que Visual Studio o los SDK puedes usar.

Notas:

1. Se requiere uno de los valores `--sdk` y `--runtime`.
2. `--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` y `[<VERSION>...]` son valores exclusivos.

---

#### <a name="examples"></a>Ejemplos

> [!NOTE]
> De forma predeterminada, los SDK y los entornos en tiempo de ejecución de .NET Core que puede necesitar Visual Studio u otros SDK se mantienen. En los siguientes ejemplos, es posible que algunos de los SDK y entornos en tiempo de ejecución especificados se mantengan, según el estado de la máquina. Para quitar todos los SDK y entornos en tiempo de ejecución, agréguelos explícitamente como argumentos o use la opción `--force`.

* Quitar todos los entornos en tiempo de ejecución de .NET Core excepto la versión `3.0.0-preview6-27804-01` sin necesidad de la confirmación S/N:

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* Quitar todos los SDK de .NET Core 1.1 sin necesidad de la confirmación de S/N:

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* Quitar el SDK de .NET Core 1.1.11 sin salida de consola:

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* Quitar todos los SDK de .NET Core que se puedan quitar con seguridad con esta herramienta:

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* Quitar todos los SDK de .NET Core que puede quitar esta herramienta, incluidos los SDK que puede necesitar Visual Studio (no recomendado):

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* Quitar todos los SDK de .NET Core que se especifican en el archivo de respuesta `versions.rsp`

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  El contenido de *versions.rsp* es el siguiente:
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a>Paso 4: Eliminar la carpeta de reserva de NuGet (opcional)

En algunos casos, ya no necesita `NuGetFallbackFolder` y puede que desee eliminarlo. Para más información sobre cómo eliminar esta carpeta, consulte [Quitar NuGetFallbackFolder](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).

## <a name="uninstall-the-tool"></a>Desinstalación de la herramienta.

## <a name="windows"></a>[Windows](#tab/windows)

1. Abra **Agregar o quitar programas**.
2. Busque `Microsoft .NET Core SDK Uninstall Tool`.
3. Seleccione **Desinstalar**.

## <a name="macos"></a>[macOS](#tab/macos)

Elimine el archivo *dotnet-Core-Uninstall.tar.gz* descargado del directorio donde se instaló. Si descomprimió el contenido de este archivo en otro directorio, asegúrese de eliminar también dicho contenido.

---
