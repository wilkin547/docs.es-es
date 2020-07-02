---
title: Creación de versiones del entorno de ejecución y el SDK de .NET Core
description: En este artículo se le enseña cómo se crean versiones del entorno de ejecución y el SDK de .NET Core (parecido al control de versiones semántico).
ms.date: 06/24/2020
ms.openlocfilehash: 5e315f49227f3c2ea40652a30fabbf566bdfe495
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619759"
---
# <a name="overview-of-how-net-core-is-versioned"></a>Introducción a la creación de versiones de .NET Core

.NET Core se refiere al runtime y el SDK de .NET Core, que contiene las herramientas que necesita para desarrollar aplicaciones. Los SDK de .NET Core están diseñados para funcionar con cualquier versión anteriores del runtime de .NET Core. En este artículo se explican el runtime y la estrategia de la versión del SDK. En el artículo [.NET Standard](../../standard/net-standard.md#net-implementation-support) se ofrece una explicación de los números de versión de .NET Standard.

El runtime y el SDK de .NET Core agregan características a un ritmo diferente; en general, el SDK de .NET Core incluye herramientas actualizadas antes de que el runtime de .NET Core cambie el runtime que se usa en producción.

## <a name="versioning-details"></a>Detalles de control de versiones

".NET Core 2.1" se refiere al número de versión del runtime de .NET Core. El runtime de .NET Core sigue el esquema de control de versiones "principal/secundaria/revisón", que se basa en el [control de versiones semántico](#semantic-versioning).

El SDK de .NET Core no sigue el esquema de control de versiones semántico. El SDK de .NET Core se publica con mayor rapidez, y sus versiones deben comunicar tanto el runtime alineado como la versión secundaria y las publicaciones de revisiones del propio SDK. Las dos primeras posiciones de la versión del SDK de .NET Core siempre reflejan el runtime de .NET Core con el que se publicó. Cada versión del SDK puede crear aplicaciones tanto para este runtime como para cualquier versión anterior.

La tercera posición del número de versión del SDK comunica tanto la versión secundaria como el número de revisión. La versión secundaria se multiplica por 100. La versión secundaria 1 y la revisión 2 se representan con 102. Los dos dígitos finales representan el número de revisión. Por ejemplo, la versión de .NET Core 2.2 puede crear versiones como en la tabla siguiente:

| Cambio                | Runtime de .NET Core | SDK de .NET Core (\*) |
|-----------------------|-------------------|-------------------|
| Versión inicial       | 2.2.0             | 2.2.100           |
| Revisión del SDK             | 2.2.0             | 2.2.101           |
| Runtime y revisión del SDK | 2.2.1             | 2.2.102           |
| Cambio de características del SDK    | 2.2.1             | 2.2.200           |

(\*) En este gráfico se usa el entorno de ejecución 2.2 de .NET Core como ejemplo, ya que un artefacto histórico indica que el primer SDK de .NET Core 2.1 es el de la versión 2.1.300. Para obtener más información, consulte [.Selección de la versión de .NET Core](selection.md).

NOTAS:

- Si el SDK tiene 10 actualizaciones de características anteriores a la actualización de una de las características del runtime, los números de versión progresarán en la serie de 1000 con números como 2.2.1000, tal como la publicación de características posterior a la versión 2.2.900. No se espera que esta situación llegue a producirse.
- Nunca se publicarán 99 versiones sin publicar ninguna característica. Si una versión se acercase a este número, se forzaría una publicación de características.

Puede ver más detalles en la propuesta inicial, que forma parte del repositorio [dotnet/designs](https://github.com/dotnet/designs/pull/29).

## <a name="semantic-versioning"></a>Control de versiones semántico

En cierto modo, el *runtime* de .NET Core sigue el [Versionamiento Semántico (SemVer)](https://semver.org/), que adopta el uso del esquema de control de versiones `MAJOR.MINOR.PATCH` y emplea las distintas partes del número de versión para describir el grado y el tipo de cambio.

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

Los archivos descargados para .NET Core indican la versión; por ejemplo, `dotnet-sdk-2.1.300-win10-x64.exe`.

### <a name="preview-versions"></a>Versiones preliminares

Las versiones preliminares tienen un elemento `-preview[number]-([build]|"final")` anexado a la versión. Por ejemplo: `2.0.0-preview1-final`.

### <a name="servicing-versions"></a>Versiones de mantenimiento

Cuando se lanza una versión, las ramas de la versión generalmente dejan de producir compilaciones diarias y, en su lugar, empiezan a generar compilaciones de mantenimiento. Las versiones de mantenimiento tienen un elemento `-servicing-[number]` anexado a la versión. Por ejemplo: `2.0.1-servicing-006924`.

## <a name="relationship-to-net-standard-versions"></a>Relación con versiones de .NET Standard

.NET Standard consta de un ensamblado de referencia de .NET. Hay varias implementaciones específicas de cada plataforma. El ensamblado de referencia contiene la definición de las API de .NET que forman parte de una versión concreta de .NET Standard. Cada implementación cumple el contrato de .NET Standard en una plataforma en cuestión. Puede obtener más información sobre .NET Standard en el artículo [.NET Standard](../../standard/net-standard.md) de la guía de .NET.

El ensamblado de referencia de .NET Standard usa el esquema de control de versiones `MAJOR.MINOR`. El nivel `PATCH` no es útil para .NET Standard porque solo expone una especificación de API en lugar de una implementación, de modo que , por definición, cualquier cambio en la API representaría un cambio en el conjunto de características (es decir, una versión de `MINOR` nueva).

Las implementaciones de cada plataforma pueden actualizarse, normalmente como parte de la versión de la plataforma. Por tanto, es posible que no sean evidentes para los programadores que usen .NET Standard en la plataforma en cuestión.

Cada versión de .NET Core implementa una versión de .NET Standard. Implementar una versión de .NET Standard implica la compatibilidad con versiones anteriores de .NET Standard. Versión de .NET standard y .NET Core por separado. Es una coincidencia que .NET Core 2.0 implemente .NET Standard 2.0. .NET Core 2.1 también implementa .NET Standard 2.0. .NET Core será compatible con versiones futuras de .NET Standard en cuanto estén disponibles.

| .NET Core | .NET Standard |
|-----------|---------------|
| 1.0       | hasta la versión 1.6     |
| 2.0       | hasta la versión 2.0     |
| 2.1       | hasta la versión 2.0     |
| 2.2       | hasta la versión 2.0     |
| 3.0       | hasta la versión 2.1     |
| 3.1       | hasta la versión 2.1     |

Para obtener una tabla interactiva de las versiones de .NET Standard y ver cómo se corresponden con las implementaciones de .NET, vea [Versiones de .NET Standard](https://dotnet.microsoft.com/platform/dotnet-standard#versions).

## <a name="see-also"></a>Vea también

- [Marcos de trabajo de destino](../../standard/frameworks.md)
- [Empaquetado de distribución de .NET Core](../distribution-packaging.md)
- [Hoja de información sobre el ciclo de vida de compatibilidad de .NET Core](https://dotnet.microsoft.com/platform/support/policy)
- [.NET Core 2+ Version Binding (Enlace de versión de .NET Core 2+)](https://github.com/dotnet/designs/issues/3)
- [Imágenes de Docker para .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/)
