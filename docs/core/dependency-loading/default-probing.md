---
title: 'Sondeo predeterminado: .NET Core'
description: Información general de la lógica de sondeo System.Runtime.Loader.AssemblyLoadContext.Default de .NET Core para buscar dependencias.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 500ee6ee863b1f311970a9e718936f57f7d4efd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398008"
---
# <a name="default-probing"></a>Sondeo predeterminado

La instancia de <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> se encarga de buscar las dependencias de un ensamblado. En este artículo se describe la lógica de sondeo de la instancia de <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.

## <a name="host-configured-probing-properties"></a>Propiedades de sondeo configuradas por host

Cuando se inicia el runtime, el host de tiempo de ejecución proporciona un conjunto de propiedades de sondeo con nombre que configuran las rutas de acceso de sondeo de <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>.

Cada propiedad de sondeo es opcional. Si está presente, cada propiedad es un valor de cadena que contiene una lista delimitada de rutas de acceso absolutas. El delimitador es ";" en Windows y ":" en el resto de plataformas.

|Nombre de la propiedad                 |Description  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | Lista de rutas de acceso de archivos de ensamblado de plataforma y aplicación. |
|`PLATFORM_RESOURCE_ROOTS`       | Lista de rutas de acceso de directorio para buscar ensamblados de recursos satélite. |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | Lista de rutas de acceso de directorio para buscar bibliotecas no administradas (nativas).        |
|`APP_PATHS`                     | Lista de rutas de acceso de directorio para buscar bibliotecas administradas. |
|`APP_NI_PATHS`                  | Lista de rutas de acceso de directorio para buscar imágenes nativas de ensamblados administrados. |

### <a name="how-are-the-properties-populated"></a>¿Cómo se rellenan las propiedades?

Existen dos escenarios principales para rellenar las propiedades, en función de si existe el archivo *\<myapp>.deps.json*.

- Cuando el archivo *\*.deps.json* está presente, se analiza para rellenar las propiedades de sondeo.
- Cuando el archivo *\*.deps.json* no está presente, se supone que el directorio de la aplicación contiene todas las dependencias. El contenido del directorio se usa para rellenar las propiedades de sondeo.

Además, los archivos *\*.deps.json* para cualquier marco al que se hace referencia se analizan de forma similar.

Por último, se puede usar la variable de entorno `ADDITIONAL_DEPS` para agregar dependencias adicionales.

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a>Cómo ver las propiedades de sondeo desde un código administrado

Cada propiedad está disponible mediante una llamada a la función <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> con el nombre de la propiedad de la tabla anterior.

### <a name="how-do-i-debug-the-probing-properties-construction"></a>Cómo depurar la construcción de las propiedades de sondeo

El host de tiempo de ejecución de .NET Core generará mensajes de seguimiento útiles cuando se habiliten determinadas variables de entorno:

|Variable de entorno        |Description  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |Habilita el seguimiento.|
|`COREHOST_TRACEFILE=<path>` |Realiza un seguimiento de una ruta de acceso de archivo en lugar del elemento `stderr` predeterminado.|
|`COREHOST_TRACE_VERBOSITY`  |Establece el nivel de detalle de 1 (inferior) a 4 (superior).|

## <a name="managed-assembly-default-probing"></a>Sondeo predeterminado de ensamblado administrado

Al realizar un sondeo para buscar un ensamblado administrado, <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> busca en orden en:

- Archivos que coinciden con <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> en `TRUSTED_PLATFORM_ASSEMBLIES` (después de quitar extensiones de archivo).
- Archivos de ensamblado de imagen nativa en `APP_NI_PATHS` con extensiones de archivo comunes.
- Archivos de ensamblado en `APP_PATHS` con extensiones de archivo comunes.

## <a name="satellite-resource-assembly-probing"></a>Sondeo de ensamblado satélite (recurso)

Con el fin de buscar un ensamblado satélite para una referencia cultural concreta, construya un conjunto de rutas de acceso de archivos.

Para cada ruta de acceso de `PLATFORM_RESOURCE_ROOTS` y, después, `APP_PATHS`, anexe la cadena <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType>, un separador de directorios, la cadena <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> y la extensión ".dll".

Si existe algún archivo coincidente, intente cargarlo y devolverlo.

## <a name="unmanaged-native-library-probing"></a>Sondeo de biblioteca no administrada (nativa)

Al realizar un sondeo para buscar una biblioteca no administrada, `NATIVE_DLL_SEARCH_DIRECTORIES` se busca mediante una búsqueda de una biblioteca coincidente.
