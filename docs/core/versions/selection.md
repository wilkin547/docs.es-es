---
title: Selección de la versión de .NET Core que se va a usar
description: Obtenga información sobre cómo .NET Core busca y elige las versiones de runtime para el programa. Además, este artículo le enseña cómo forzar una versión específica.
author: thraka
ms.author: adegeo
ms.date: 03/24/2020
ms.openlocfilehash: 26aecdf2bf3ebd033e80eec26159eb9fa3cd54dd
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345156"
---
# <a name="select-the-net-core-version-to-use"></a>Selección de la versión de .NET Core que se va a usar

En este artículo se explican las directivas que usan las herramientas de .NET Core, el SDK y el runtime para la selección de versiones. Estas directivas proporcionan un equilibrio entre la ejecución de aplicaciones con las versiones especificadas y facilitan la actualización de los equipos del desarrollador y el usuario final. Estas directivas realizan las siguientes acciones:

- La implementación sencilla y eficaz de .NET Core, incluidas las actualizaciones de seguridad y confiabilidad.
- Usar las herramientas y los comandos más recientes independientemente del runtime de destino.

La selección de versiones se produce:

- Al ejecutar un comando del SDK, [el SDK usa la versión instalada más reciente](#the-sdk-uses-the-latest-installed-version).
- Al compilar un ensamblado, [los monikers de la plataforma de destino definen las API de tiempo de compilación](#target-framework-monikers-define-build-time-apis).
- Al ejecutar una aplicación .NET Core, [las aplicaciones dependientes de la plataforma de destino se ponen al día](#framework-dependent-apps-roll-forward).
- Al publicar una aplicación autocontenida, [las implementaciones autocontenidas incluyen el runtime seleccionado](#self-contained-deployments-include-the-selected-runtime).

En el resto de este documento se examinan los cuatro escenarios.

## <a name="the-sdk-uses-the-latest-installed-version"></a>El SDK usa la versión instalada más reciente

Los comandos de SDK incluyen `dotnet new` y `dotnet run`. La CLI de .NET Core debe elegir una versión del SDK para cada comando `dotnet`. Usa el SDK más reciente instalado en el equipo de forma predeterminada, aunque:

- El proyecto tenga como destino una versión anterior del entorno de ejecución de .NET Core.
- La versión mas reciente del SDK de .NET Core sea una versión preliminar.

Puede beneficiarse de las características y mejoras del SDK más reciente mientras selecciona como destino versiones anteriores del runtime de .NET Core. Puede tener como destino varias versiones del runtime de .NET Core en otros proyectos, con las mismas herramientas del SDK para todos los proyectos.

En raras ocasiones, es posible que tenga que usar una versión anterior del SDK. Esa versión se especifica en un [archivo *global.json*](../tools/global-json.md). La directiva "usar la versión más reciente" significa que solo se usa *global.json* para especificar una versión del SDK de .NET Core anterior a la versión instalada más reciente.

*global.json* se puede colocar en cualquier lugar de la jerarquía de archivos. La CLI busca el primer archivo *global.json* hacia arriba desde el directorio del proyecto. Puede controlar a qué proyectos se aplica un archivo *global.json* determinado mediante su lugar en el sistema de archivos. La CLI de .NET busca un archivo *global.json* de forma iterativa desplazándose hacia arriba en la ruta de acceso desde el directorio de trabajo actual. El primer archivo *global.json* que se encuentra especifica la versión que se usa. Si esa versión del SDK está instalada, es la que se usa. Si no se encuentra el SDK especificado en *global.json*, la CLI de .NET usa [reglas de coincidencia](../tools/global-json.md#matching-rules) para seleccionar un SDK compatible, o bien se produce un error si no se encuentra ninguno.

En el ejemplo siguiente se muestra la sintaxis de *global.json*:

``` json
{
  "sdk": {
    "version": "3.0.0"
  }
}
```

El proceso de selección de una versión del SDK es la siguiente:

1. `dotnet` busca un archivo *global.json* de forma iterativa desplazándose hacia arriba de forma inversa en la ruta de acceso desde el directorio de trabajo actual.
1. `dotnet` usa el SDK especificado en el primer archivo *global.json* que encuentra.
1. `dotnet` usa el SDK instalado más reciente si no se encuentra ningún archivo *global.json*.

Puede obtener más información sobre cómo seleccionar una versión del SDK en la sección [Reglas de coincidencia](../tools/global-json.md#matching-rules) del artículo sobre *global.json*.

## <a name="target-framework-monikers-define-build-time-apis"></a>Los monikers de la plataforma de destino definen las API de tiempo de compilación

El proyecto se compila con las API definidas en un **moniker de la plataforma de destino** (TFM). La [plataforma de destino](../../standard/frameworks.md) se especifica en el archivo del proyecto. Establezca el elemento `TargetFramework` del archivo del proyecto como se muestra en el ejemplo siguiente:

``` xml
<TargetFramework>netcoreapp3.0</TargetFramework>
```

Puede compilar el proyecto con varios TFM. Configurar varias plataformas de destino es más común para las bibliotecas, pero también se puede hacer con las aplicaciones. Especifique una propiedad `TargetFrameworks` (el plural de `TargetFramework`). Las plataformas de destino se delimitan por punto y coma, como se muestra en el ejemplo siguiente:

``` xml
<TargetFrameworks>netcoreapp3.0;net47</TargetFrameworks>
```

Un SDK determinado admite un conjunto fijo de plataformas, limitado a la plataforma de destino del runtime con el que se suministra. Por ejemplo, el SDK de .NET Core 3.0 incluye el runtime .NET Core 3.0, que es una implementación de la plataforma de destino `netcoreapp3.0`. El SDK de .NET Core 3.0 admite `netcoreapp2.1`, `netcoreapp2.2` y `netcoreapp3.0`, pero no `netcoreapp3.1` (o una versión posterior). El SDK de .NET Core 3.1 se instala para compilar para `netcoreapp3.1`.

Las plataformas de destino de .NET Standard también se limitan a la plataforma de destino del runtime con el que se incluye el SDK. El SDK de .NET Core 3.1 está limitado a `netstandard2.1`. Para más información, consulte [.NET Standard](../../standard/net-standard.md).

## <a name="framework-dependent-apps-roll-forward"></a>Puesta al día de las aplicaciones dependientes de la plataforma

Cuando una aplicación se ejecuta desde el origen con [`dotnet run`](../tools/dotnet-run.md), desde una [**implementación dependiente del marco**](../deploying/index.md#publish-runtime-dependent) con [`dotnet myapp.dll`](../tools/dotnet.md#description) o desde un [**ejecutable dependiente del marco**](../deploying/index.md#publish-runtime-dependent) con `myapp.exe`, el ejecutable `dotnet` es el **host** de la aplicación.

El host elige la versión de revisión más reciente instalada en el equipo. Por ejemplo, si se especifica `netcoreapp3.0` en el archivo de proyecto, y `3.0.4` es el runtime de .NET instalado más reciente, se usa el runtime `3.0.4`.

Si no se encuentra ninguna versión de `3.0.*` aceptable, se usa una versión de `3.*` nueva. Por ejemplo, si se especificó `netcoreapp3.0` y solo está instalado `3.1.0`, la aplicación se ejecuta con el runtime `3.1.0`. Este comportamiento se conoce como "puesta al día de versión secundaria". Las versiones inferiores no se considerarán. Cuando no hay ningún runtime aceptable instalado, la aplicación no se ejecutará.

Algunos ejemplos de uso muestran el comportamiento; si indica como destino la versión 3.0:

- ✔️ Se especifica la versión 3.0. 3.0.5 es la versión de revisión instalada más reciente. Se usa la versión 3.0.5.
- ❌ Se especifica la versión 3.0. No hay ninguna versión 3.0.* instalada. 2.1.1 es la versión del runtime instalada más alta. Se muestra un mensaje de error.
- ✔️ Se especifica la versión 3.0. No hay ninguna versión 3.0.* instalada. 3.1.0 es la versión del runtime instalada más alta. Se usa la versión 3.1.0.
- ❌ Se especifica la versión 2.0. No hay ninguna versión 2.x instalada. 3.0.0 es la versión del runtime instalada más reciente. Se muestra un mensaje de error.

La puesta al día de versión secundaria tiene un efecto secundario que puede afectar a los usuarios finales. Considere el caso siguiente:

1. La aplicación especifica que se requiere la versión 3.0.
2. Cuando se ejecuta, la versión 3.0.* no está instalada, pero sí que lo está la 3.1.0. Se usará la versión 3.1.0.
3. Más adelante, el usuario instala la versión 3.0.5 y ejecuta de nuevo la aplicación. Ahora se usará la versión 3.0.5.

Es posible que las versiones 3.0.5 y 3.1.0 se comporten de forma diferente, especialmente en escenarios como la serialización de datos binarios.

## <a name="self-contained-deployments-include-the-selected-runtime"></a>Las implementaciones autocontenidas incluyen el runtime seleccionado.

Puede publicar una aplicación como una [**distribución autocontenida**](../deploying/index.md#publish-self-contained). Este enfoque empaqueta el runtime y las bibliotecas de .NET Core con la aplicación. Las implementaciones autocontenidas no tienen una dependencia de los entornos de runtime. La selección de la versión del runtime se produce en el momento de la publicación, no en el tiempo de ejecución.

El proceso de publicación selecciona la versión de revisión más reciente de la familia de runtime indicada. Por ejemplo, `dotnet publish` seleccionará .NET Core 3.0.4 si es la versión de revisión más reciente de la familia de runtime de .NET Core 3.0. La plataforma de destino (incluidas las revisiones de seguridad instaladas más recientes) se empaqueta con la aplicación.

Es un error que no se cumpla la versión mínima especificada para una aplicación. `dotnet publish` se enlaza a la versión de revisión de runtime más reciente (dentro de una familia de versión principal.secundaria determinada). `dotnet publish` no es compatible con la semántica de puesta al día de `dotnet run`. Para obtener más información sobre las revisiones y las implementaciones autocontenidas, vea el artículo sobre [selección de revisión de runtime](../deploying/runtime-patch-selection.md) en la implementación de aplicaciones .NET Core.

Las implementaciones autocontenidas pueden requerir una versión de revisión específica. Puede invalidar la versión de revisión de runtime mínima (para versiones superiores o inferiores) en el archivo del proyecto, como se muestra en el ejemplo siguiente:

``` xml
<RuntimeFrameworkVersion>3.0.4</RuntimeFrameworkVersion>
```

El elemento `RuntimeFrameworkVersion` invalida la directiva de versión predeterminada. Para las implementaciones autocontenidas, `RuntimeFrameworkVersion` especifica la versión de la plataforma de runtime *exacta*. Para las aplicaciones dependientes de la plataforma, `RuntimeFrameworkVersion` especifica la versión de la plataforma de runtime *mínima* que se requiere.

## <a name="see-also"></a>Vea también

- [Descarga e instalación de .NET Core](../install/index.md)
- [Eliminación de los componentes .NET Core Runtime y SDK](remove-runtime-sdk-versions.md)
