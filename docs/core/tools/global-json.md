---
title: Información general de global.json
description: Obtenga información sobre cómo usar el archivo global.json para establecer la versión del SDK de .NET Core al ejecutar comandos de la CLI de .NET Core.
ms.date: 12/03/2018
ms.custom: updateeachrelease
ms.openlocfilehash: 4da703266e98b209cdd031f4ea856b4d7c83930c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714168"
---
# <a name="globaljson-overview"></a>Información general de global.json

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

El archivo *global.json* permite definir qué versión del SDK de .NET Core se usa al ejecutar comandos de la CLI de .NET Core. La selección del SDK de .NET Core es independiente de especificar el runtime al que está destinado el proyecto. La versión del SDK de .NET Core indica qué versiones de las herramientas de la CLI de .NET Core se usan. En general, le interesa usar la versión más reciente de las herramientas, por lo que no es necesario ningún archivo *global.json*.

Para obtener más información sobre cómo especificar el runtime en su lugar, vea [Plataformas de destino](../../standard/frameworks.md).

El SDK de .NET Core busca un archivo *global.json* en el directorio de trabajo actual (que no es necesariamente el mismo que el directorio del proyecto) o en uno de sus directorios principales.

## <a name="globaljson-schema"></a>Esquema de global.JSON

### <a name="sdk"></a>sdk

Tipo: Object

Especifica información sobre el SDK de .NET Core que se va a seleccionar.

#### <a name="version"></a>version

Tipo: String

La versión del SDK de .NET Core que se va a usar.

Tenga en cuenta que este campo:

- No admite comodines, es decir, se debe especificar el número de versión completo.
- No admite intervalos de versiones.

En el ejemplo siguiente se muestra el contenido de un archivo *global.json*:

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a>global.json y la CLI de .NET Core

Resulta útil saber qué versiones están disponibles con el fin de establecer una en el archivo *global.json*. Puede encontrar la lista completa de los SDK disponibles admitidos en la página de [descargas de .NET Core](https://dotnet.microsoft.com/download/dotnet-core). A partir del SDK de .NET Core SDK 2.1, puede ejecutar el comando siguiente para comprobar qué versiones del SDK ya están instaladas en el equipo:

```dotnetcli
dotnet --list-sdks
```

Para instalar otras versiones del SDK de .NET Core en el equipo, visite la página de [descargas de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).

Puede crear un archivo *global.json* en el directorio actual mediante la ejecución del comando [dotnet new](dotnet-new.md), similar al ejemplo siguiente:

```dotnetcli
dotnet new globaljson --sdk-version 2.2.100
```

## <a name="matching-rules"></a>Reglas de coincidencia

> [!NOTE]
> Las reglas de coincidencia se rigen por el host de aplicaciones, que forma parte del runtime de .NET Core.
> Cuando hay varios runtimes instalados en paralelo, se usa la versión más reciente del host.

A partir de .NET Core 2.0, se aplican las reglas siguientes al determinar qué versión del SDK se va a usar:

- Si no se encuentra ningún archivo *global.json* o en *global.json* no se especifica una versión del SDK, se usa la versión instalada del SDK más reciente. La versión del SDK más reciente puede ser la versión o la versión preliminar: prevalece el número de versión más alto.
- Si *global.json* especifica una versión del SDK:
  - Si la versión del SDK especificada se encuentra en el equipo, se usa esa versión exacta.
  - Si la versión del SDK especificada no se encuentra en el equipo, se usa la **versión de revisión** del SDK instalada más reciente de esa versión. La **versión de revisión** del SDK instalada más reciente puede ser la versión o la versión preliminar: prevalece el número de versión más alto. En .NET Core 2.1 y versiones posteriores, las **versiones de revisión** inferiores a la **versión de revisión** especificada se omiten en la selección del SDK.
  - Si no se encuentra la versión del SDK especificada y una **versión de revisión** adecuada del SDK, se produce un error.

Actualmente, la versión del SDK se compone de los elementos siguientes:

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

La **versión de características** del SDK de .NET Core se representa por medio del primer dígito (`x`) de la última parte del número (`xyz`) para las versiones 2.1.100 del SDK y posteriores. En general, el SDK de .NET Core tiene un ciclo de versiones más rápido que .NET Core.

La **versión de revisión** se define mediante los dos últimos dígitos (`yz`) de la última parte del número (`xyz`) para las versiones 2.1.100 del SDK y posteriores. Por ejemplo, si especifica `2.1.300` como la versión del SDK, la selección del SDK busca hasta `2.1.399` pero `2.1.400` no se considera una versión de revisión para `2.1.300`.

Las versiones del SDK de .NET Core de `2.1.100` a `2.1.201` se publicaron durante la transición entre las combinaciones de número de versión y no procesan correctamente la notación `xyz`. Si estas versiones se especifican en el archivo *global.json*, se recomienda encarecidamente asegurarse de que las versiones especificadas están en los equipos de destino.

Con el SDK 1.x de .NET Core, si se especificaba una versión y no se encontraba ninguna coincidencia exacta, se usaba la versión del SDK instalada más reciente. La versión del SDK más reciente puede ser la versión o la versión preliminar: prevalece el número de versión más alto.

## <a name="troubleshooting-build-warnings"></a>Solución de problemas de advertencias de compilación

> [!WARNING]
> Trabaja con una versión preliminar del SDK de .NET Core. Puede definir la versión del SDK a través de un archivo global.json en el proyecto actual. Más información en <https://go.microsoft.com/fwlink/?linkid=869452>.

Esta advertencia indica que el proyecto se está compilando con una versión preliminar del SDK de .NET Core, como se explica en la sección [Reglas de coincidencia](#matching-rules). Las versiones del SDK de .NET Core tienen un historial y el compromiso de ser de alta calidad. Pero si no quiere usar una versión preliminar, agregue un archivo *global.json* a la estructura de jerarquía del proyecto para especificar qué versión del SDK se va a utilizar, y use `dotnet --list-sdks` para confirmar que la versión está instalada en el equipo. Cuando se publica una versión nueva, para usarla, quite el archivo *global.json* o actualícelo para usar la versión más reciente.

> [!WARNING]
> El proyecto de inicio "{proyectoDeInicio}" está destinado a la versión "{versiónPlataformaDeDestino}" de ".NETCoreApp". Esta versión de las herramientas de línea de comandos de Entity Framework Core .NET solo admite la versión 2.0 o superior. Para obtener información sobre el uso de las versiones anteriores de las herramientas, vea <https://go.microsoft.com/fwlink/?linkid=871254>

A partir del SDK de .NET Core 2.1 (versión 2.1.300), el comando `dotnet ef` se incluye en el SDK. Esta advertencia indica que el proyecto tiene como destino EF Core 1.0 ó 1.1, que no es compatible con el SDK de .NET Core 2.1 y versiones posteriores. Para compilar el proyecto, instale el SDK de .NET Core 2.0 (versión 2.1.201) y versiones anteriores en el equipo y defina la versión del SDK deseada mediante el archivo *global.json*. Para obtener más información sobre el comando `dotnet ef`, vea [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet) (Herramientas de línea de comandos de EF Core .NET).

## <a name="see-also"></a>Vea también

- [Resolución de los SDK de proyecto](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
