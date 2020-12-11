---
title: Creación de versiones del entorno de ejecución y el SDK de .NET
description: En este artículo se explica cómo crear versiones del entorno de ejecución y el SDK de .NET (parecido al control de versiones semántico).
ms.date: 12/07/2020
ms.openlocfilehash: 2fe0b162b52f1e4500ec87f7d5d92054cd569552
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009311"
---
# <a name="overview-of-how-net-is-versioned"></a>Información general sobre la creación de versiones de .NET

El [entorno de ejecución y el SDK de .NET](../introduction.md#sdk-and-runtimes) agregan nuevas características con distintas frecuencias. En general, el SDK se actualiza con más frecuencia que el entorno de ejecución. En este artículo se detallan los números de versión del SDK y el entorno de ejecución.

## <a name="versioning-details"></a>Detalles de control de versiones

El entorno de ejecución de .NET sigue el esquema de control de versiones "principal/secundaria/revisión", que se basa en el [control de versiones semántico](#semantic-versioning).

El SDK de .NET no sigue el esquema de control de versiones semántico. El SDK de .NET se publica con mayor rapidez, y sus números de versión deben indicar tanto el entorno de ejecución alineado como la versión secundaria y las publicaciones de revisiones del SDK.

Las dos primeras posiciones del número de versión del SDK de .NET siempre reflejan el entorno de ejecución de .NET con el que se publicó. Cada versión del SDK puede crear aplicaciones tanto para este runtime como para cualquier versión anterior.

La tercera posición del número de versión del SDK comunica tanto la versión secundaria como el número de revisión. La versión secundaria se multiplica por 100. La versión secundaria 1 y la revisión 2 se representan con 102. Los dos dígitos finales representan el número de revisión. Por ejemplo, esta es una secuencia posible de los números de versión del SDK y el entorno de ejecución:

| Change                | Runtime de .NET      | SDK de .NET (\*)     |
|-----------------------|-------------------|-------------------|
| Versión inicial       | 2.2.0             | 2.2.100           |
| Revisión del SDK             | 2.2.0             | 2.2.101           |
| Runtime y revisión del SDK | 2.2.1             | 2.2.102           |
| Cambio de características del SDK    | 2.2.1             | 2.2.200           |

NOTAS:

- Si el SDK tiene 10 actualizaciones de características anteriores a la actualización de una de las características del runtime, los números de versión progresarán en la serie de 1000 con números como 2.2.1000, tal como la publicación de características posterior a la versión 2.2.900. No se espera que esta situación llegue a producirse.
- Nunca se publicarán 99 versiones sin publicar ninguna característica. Si una versión se acercase a este número, se forzaría una publicación de características.

Puede ver más detalles en la propuesta inicial, que forma parte del repositorio [dotnet/designs](https://github.com/dotnet/designs/pull/29).

## <a name="semantic-versioning"></a>Control de versiones semántico

En cierto modo, el *entorno de ejecución* de .NET Core el [Versionamiento Semántico (SemVer)](https://semver.org/), que adopta el uso del esquema de control de versiones `MAJOR.MINOR.PATCH` y emplea las distintas partes del número de versión para describir el grado y el tipo de cambio.

```
MAJOR.MINOR.PATCH[-PRERELEASE-BUILDNUMBER]
```

Los elementos opcionales `PRERELEASE` y `BUILDNUMBER` nunca forman parte de las versiones compatibles y solo están presentes en las compilaciones nocturnas, en las compilaciones locales a partir de destinos de origen y en las versiones preliminares no compatibles.

### <a name="understand-runtime-version-number-changes"></a>Comprender los cambios en el número de versión del runtime

`MAJOR` se incrementa cuando:

- Se producen cambios importantes en el producto, o bien este toma una nueva dirección.
- Se han realizado cambios importantes. Hay un nivel de aceptación de cambios importantes elevado.
- Ya no se admite una versión antigua.
- Se adopta una versión `MAJOR` más reciente de una dependencia existente.

`MINOR` se incrementa cuando:

- Se agrega un área expuesta de API pública.
- Se agrega un nuevo comportamiento.
- Se adopta una versión `MINOR` más reciente de una dependencia existente.
- Se presenta una nueva dependencia.

`PATCH` se incrementa cuando:

- Se realizan correcciones de errores.
- Se agrega compatibilidad con una plataforma más reciente.
- Se adopta una versión `PATCH` más reciente de una dependencia existente.
- Cualquier otro cambio no se ajusta a uno de los casos anteriores.

Cuando hay varios cambios, se incrementa el elemento superior afectado por cambios individuales, mientras que los siguientes se restablecen a cero. Por ejemplo, cuando se incrementa `MAJOR`, `MINOR` y `PATCH` se restablecen a cero. Cuando se incrementa `MINOR`, `PATCH` se restablece a cero mientras que `MAJOR` no se modifica.

## <a name="version-numbers-in-file-names"></a>Números de versión en los nombres de archivo

Los archivos descargados para .NET indican la versión; por ejemplo, `dotnet-sdk-2.1.300-win10-x64.exe`.

### <a name="preview-versions"></a>Versiones preliminares

Las versiones preliminares tienen un elemento `-preview[number]-([build]|"final")` anexado al número de versión. Por ejemplo: `2.0.0-preview1-final`.

### <a name="servicing-versions"></a>Versiones de mantenimiento

Cuando se lanza una versión, las ramas de la versión generalmente dejan de producir compilaciones diarias y, en su lugar, empiezan a generar compilaciones de mantenimiento. Las versiones de mantenimiento tienen un elemento `-servicing-[number]` anexado a la versión. Por ejemplo: `2.0.1-servicing-006924`.

## <a name="relationship-to-net-standard-versions"></a>Relación con versiones de .NET Standard

.NET Standard consta de un ensamblado de referencia de .NET. Hay varias implementaciones específicas de cada plataforma. El ensamblado de referencia contiene la definición de las API de .NET que forman parte de una versión concreta de .NET Standard. Cada implementación cumple el contrato de .NET Standard en una plataforma en cuestión.

El ensamblado de referencia de .NET Standard usa el esquema de control de versiones `MAJOR.MINOR`. El nivel `PATCH` no es útil para .NET Standard porque solo expone una especificación de API en lugar de una implementación, de modo que , por definición, cualquier cambio en la API representaría un cambio en el conjunto de características (es decir, una versión de `MINOR` nueva).

Las implementaciones de cada plataforma pueden actualizarse, normalmente como parte de la versión de la plataforma. Por tanto, es posible que no sean evidentes para los programadores que usen .NET Standard en la plataforma en cuestión.

Para más información, consulte [.NET Standard](../../standard/net-standard.md).

## <a name="see-also"></a>Vea también

- [Marcos de trabajo de destino](../../standard/frameworks.md)
- [Empaquetado de distribución de .NET](../distribution-packaging.md)
- [Hoja de información sobre el ciclo de vida de compatibilidad de .NET](https://dotnet.microsoft.com/platform/support/policy)
- [Imágenes de Docker para .NET](https://hub.docker.com/_/microsoft-dotnet/)
