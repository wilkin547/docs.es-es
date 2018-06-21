---
title: Control de versiones de .NET Core
description: Comprenda cómo funciona el control de versiones de .NET Core.
author: bleroy
ms.author: mairaw
ms.date: 02/13/2018
ms.openlocfilehash: 33c545fdea254133fe6e65f4d6dd725f5184faec
ms.sourcegitcommit: 640cee8fc5d256cdd80e5b80240469feac10499e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2018
ms.locfileid: "36298245"
---
# <a name="net-core-versioning"></a>Control de versiones de .NET Core

.NET Core se compone de [paquetes NuGet](../packages.md), herramientas y marcos de trabajo distribuidos como una unidad. Las versiones de cada uno de estos niveles de plataforma se pueden controlar por separado, lo que proporciona más agilidad. Aunque hay bastante flexibilidad en el control de versiones en ese aspecto, también existe el deseo de controlar las versiones de la plataforma como una unidad para que el producto sea más fácil de comprender.

En este artículo se pretende aclarar cómo funciona el control de versiones del SDK y el entorno de ejecución de .NET Core.

En .NET Core hay una gran cantidad de elementos móviles cuyas versiones se controlan por separado. Sin embargo, a partir de .NET Core 2.0 hay un número de versión de nivel superior fácil de comprender que todo el mundo entiende como *la* versión de ".NET Core" como un todo. En el resto de este documento se profundiza en los detalles del control de versiones de todos esos elementos. Estos detalles pueden ser importantes cuando se es administrador de paquetes, por ejemplo.

> [!IMPORTANT]
> Los detalles del control de versiones que se explican en este tema no se aplican a la versión actual del SDK de .NET Core ni del entorno de ejecución.
> El esquema de la versión cambia en futuras versiones. Puede ver la propuesta actual en el repositorio [dotnet/diseños](https://github.com/dotnet/designs/pull/29).

## <a name="versioning-details"></a>Detalles de control de versiones

Con .NET Core 2.0, las descargas muestran un número de versión único en su nombre de archivo. Se han unificado los siguientes números de versión:

* Marco de trabajo compartido y entorno de ejecución asociado.
* SDK de .NET Core y CLI asociados a .NET Core.
* Metapaquete `Microsoft.NETCore.App`.

El empleo de un número de versión único permite que los usuarios sepan más fácilmente qué versión del SDK deben instalar en sus equipos de desarrollo y cuál debe ser la versión correspondiente del marco de trabajo compartido cuando llegue la hora de aprovisionar un entorno de producción. Al descargar un SDK o entorno de ejecución, el número de versión que vea va a ser el mismo.

### <a name="installers"></a>Instaladores

Con .NET Core 2.0, las descargas de las [compilaciones diarias](https://github.com/dotnet/core-setup#daily-builds) y las [versiones](https://www.microsoft.com/net/download/core) se ajustan a un nuevo esquema de nomenclatura más fácil de entender.
La interfaz de usuario del instalador de esas descargas también se modificó para presentar claramente los nombres y las versiones de los componentes que se van a instalar. En concreto, los títulos ahora muestran el mismo número de versión que se encuentra en el nombre de archivo de la descarga.

#### <a name="file-name-format"></a>Formato de nombre de archivo

`[product]-[component]-[major].[minor].[patch]-[previewN]-[optional build #]-[rid].[file ext]`

Estos son algunos ejemplos de este formato:

```
dotnet-runtime-2.0.4-osx.10.12-x64.pkg            # Mac runtime installer
dotnet-sdk-2.0.4-win-x64.exe                      # Windows SDK installer
dotnet-sdk-2.0.4-linux-x64.tar.gz                 # Linux binary archive

#Ubuntu file set needed for the SDK
dotnet-host-2.0.4-ubuntu.16.04-x64.deb            # Host / muxer and host policy
dotnet-runtime-2.0.4-ubuntu.16.04-x64.deb         # runtime
dotnet-sdk-2.0.4-ubuntu.16.04-x64.deb             # SDK tools
```

El formato se puede leer y muestra claramente lo que se está descargando, de qué versión se trata y dónde se puede usar. El nombre del paquete del entorno de ejecución incluye `runtime`, y el SDK, `SDK`.

#### <a name="ui-string-format"></a>Formato de cadena de interfaz de usuario

Todas las descripciones del sitio web y las cadenas de la interfaz de usuario de los instaladores son coherentes, precisas y simples. En la tabla siguiente se proporcionan algunos ejemplos:

| Installer | Título de ventana                          | Otro contenido del instalador | Elemento que se instala                               |
| :--       | :--                                   | :--                        | :--                                             |
| SDK       | Instalador del SDK de .NET Core 2.0 (x64)     | SDK de .NET Core 2.0.4        | Herramientas de .NET Core 2.0.4 + Runtime de .NET Core 2.0.4 |
| Tiempo de ejecución   | Instalador del entorno de ejecución de .NET Core 2.0 (x64) | Entorno de ejecución de .NET Core 2.0.4    | Entorno de ejecución de .NET Core 2.0.4                         |

Las versiones preliminares varían muy ligeramente:

| Installer | Título de ventana                                    | Otro contenido del instalador        | Elemento que se instala                                                   |
| :--       | :--                                             | :--                               | :--                                                                 |
| SDK       | Instalador del SDK de .NET Core 2.0 Preview 1 (x64)     | SDK de .NET Core 2.0.0 Preview 1     | Herramientas de .NET Core 2.0.0 Preview 1 y entorno de ejecución de .NET Core 2.0.0 Preview 1 |
| Tiempo de ejecución   | Instalador del entorno de ejecución de .NET Core 2.0 Preview 1 (x64) | Entorno de ejecución de .NET Core 2.0.0 Preview 1 | Entorno de ejecución de .NET Core 2.0.0 Preview 1                                   |

Puede ocurrir que una versión del SDK contenga más de una versión del entorno de ejecución. En este caso, la experiencia de usuario del instalador es similar a la siguiente (solo se muestra la versión del SDK; las versiones instaladas del entorno de ejecución se muestran en una página de resumen al final del proceso de instalación en Windows y Mac):

| Installer | Título de ventana                      | Otro contenido del instalador                                   | Elemento que se instala                                                         |
| :--       | :--                               | :--                                                          | :--                                                                       |
| SDK       | Instalador del SDK de .NET Core 2.1 (x64) | SDK de .NET Core 2.1.1 <br> Entorno de ejecución de .NET Core 2.1.1 <br> Entorno de ejecución de .NET Core 2.0.6 | Herramientas de .NET Core 2.1.1, entorno de ejecución de .NET Core 2.1.1 y entorno de ejecución de .NET Core 2.0.6 |

También es posible que haya que actualizar las herramientas de .NET Core sin realizar cambios en el entorno de ejecución. En ese caso, se incrementa la versión del SDK (por ejemplo, a 2.1.2) y, luego, el entorno de ejecución la alcanza la siguiente vez que se distribuye (por ejemplo, el entorno de ejecución y el SDK se distribuyen como 2.1.3 la siguiente vez).

### <a name="package-managers"></a>Administradores de paquetes

Hay otras entidades aparte de Microsoft que pueden distribuir .NET Core. En concreto, los propietarios de distribuciones y los mantenedores de paquetes de Linux pueden agregar paquetes de .NET Core a sus administradores de paquetes. Para obtener recomendaciones sobre cómo nombrar y controlar las versiones de dichos paquetes, vea [.NET Core distribution packaging (Empaquetado de distribución de .NET Core)](../build/distribution-packaging.md).

#### <a name="minimum-package-set"></a>Conjunto de paquetes mínimo

* `dotnet-runtime-[major].[minor]`: entorno de ejecución con la versión especificada (solo la última versión de revisión para una combinación determinada principal+secundaria debe estar disponible en el administrador de paquetes). Las nuevas versiones de revisión actualizan el paquete, pero las nuevas versiones secundarias o principales son paquetes independientes.

  **Dependencias**: `dotnet-host`

* `dotnet-sdk`: el último SDK. `update` pone al día las versiones de revisión, las versiones principales y las secundarias.

  **Dependencias**: el último `dotnet-sdk-[major].[minor]`.

* `dotnet-sdk-[major].[minor]`: el SDK con la versión especificada. La versión especificada es la versión incluida más alta de los marcos compartidos incluidos, para que los usuarios puedan relacionar con facilidad un SDK con un marco compartido. Las nuevas versiones de revisión actualizan el paquete, pero las nuevas versiones secundarias o principales son paquetes independientes.

  **Dependencias**: `dotnet-host`, una o varias instancias de `dotnet-runtime-[major].[minor]` (una de ellas es usada por el propio código del SDK; las demás están disponibles para que los usuarios realicen tareas de compilación y ejecución).

* `dotnet-host`: el último host.

##### <a name="preview-versions"></a>Versiones preliminares

Los mantenedores de paquetes pueden decidir incluir versiones preliminares del entorno de ejecución y del SDK. No incluya dichas versiones preliminares en el paquete `dotnet-sdk` sin versión; puede publicarlas como paquetes con versión con un marcador de versión preliminar adicional anexado a las secciones de versión principal y secundaria del nombre. Por ejemplo, puede haber un paquete `dotnet-sdk-2.0-preview1-final`.

### <a name="docker"></a>Docker

Una convención de nomenclatura de etiquetas Docker general es colocar el número de versión antes del nombre de componente. Se puede seguir usando esta convención. Las etiquetas actuales solo incluyen la versión del entorno de ejecución del modo siguiente.

* 1.0.8-runtime
* 1.0.8-sdk
* 2.0.4-runtime
* 2.0.4-sdk
* 2.1.1-runtime
* 2.1.1-sdk

Las etiquetas del SDK deben actualizarse para representar la versión del SDK en lugar de la del entorno de ejecución.

También es posible que las herramientas de la CLI de .NET Core (incluidas en el SDK) se corrijan pero se vuelvan a enviar con un entorno de ejecución existente. En ese caso, se incrementa la versión del SDK (por ejemplo, a 2.1.2) y, luego, el entorno de ejecución la alcanza la siguiente vez que se distribuye (por ejemplo, el entorno de ejecución y el SDK se distribuyen como 2.1.3 la siguiente vez).

## <a name="semantic-versioning"></a>Control de versiones semántico

.NET Core usa [Versionamiento Semántico (SemVer)](http://semver.org/), que adopta el uso del control de versiones `MAJOR.MINOR.PATCH` y emplea las distintas partes del número de versión para describir el grado y el tipo de cambio.

```
MAJOR.MINOR.PATCH[-PRERELEASE-BUILDNUMBER]
```

Los elementos opcionales `PRERELEASE` y `BUILDNUMBER` nunca forman parte de las versiones compatibles y solo están presentes en las compilaciones nocturnas, en las compilaciones locales a partir de destinos de origen y en las versiones preliminares no compatibles.

### <a name="how-version-numbers-are-incremented"></a>¿Cómo se incrementan los números de versión?

`MAJOR` se incrementa cuando:

- Ya no se admite una versión antigua.
- Se adopta una versión `MAJOR` más reciente de una dependencia existente.
- El valor predeterminado de una peculiaridad de compatibilidad se cambia a "desactivado".

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

### <a name="preview-versions"></a>Versiones preliminares

Las versiones preliminares tienen un elemento `-preview[number]-([build]|"final")` anexado a la versión. Por ejemplo: `2.0.0-preview1-final`.

### <a name="servicing-versions"></a>Versiones de mantenimiento

Cuando se lanza una versión, las ramas de la versión generalmente dejan de producir compilaciones diarias y, en su lugar, empiezan a generar compilaciones de mantenimiento. Las versiones de mantenimiento tienen un elemento `-servicing-[number]` anexado a la versión. Por ejemplo: `2.0.1-servicing-006924`.

### <a name="lts-vs-current"></a>LTS y actual

Hay dos tipos de versiones de .NET Core: compatibilidad a largo plazo (LTS) y actual. Esto permite a los usuarios elegir el nivel de estabilidad y las nuevas características que quieren y, a la vez, seguir manteniendo la compatibilidad.

- LTS significa que las nuevas características se obtienen con menos frecuencia, pero que se dispone de una plataforma más madura. LTS también tiene un período más largo de compatibilidad.
- La actual implica que se obtienen nuevas características y API con más frecuencia, con el inconveniente de que se tiene un período de tiempo más corto para instalar actualizaciones y que esas actualizaciones se producen con más frecuencia. La actual también es totalmente compatible, aunque el período de compatibilidad es más corto que el de LTS.

Una versión "actual" puede convertirse en LTS.

"LTS" y "actual" se deben considerar como etiquetas que se colocan en versiones concretas para realizar una declaración sobre el nivel de compatibilidad asociado.

Para obtener más información, vea [.NET Core Support Lifecycle Fact Sheet (Hoja de información sobre el ciclo de vida de compatibilidad de .NET Core)](https://www.microsoft.com/net/core/support).

## <a name="versioning-scheme-details"></a>Detalles del esquema de control de versiones

.NET Core consta de los siguientes elementos:

- Un host: *dotnet.exe* para aplicaciones que dependen del marco o *\<nombreAplicación>.exe* para aplicaciones independientes.
- SDK (el conjunto de herramientas necesario en un equipo de desarrollador, pero no en producción).
- Entorno de ejecución.
- Implementación de marco de trabajo compartido, distribuida como paquetes. Cada paquete tiene una versión independiente, en especial para el control de versiones de revisión.
- Opcionalmente, un conjunto de [metapaquetes](../packages.md) que hacen referencia a paquetes específicos como una unidad con versión. Las versiones de los metapaquetes se pueden controlar independientemente de los paquetes.

.NET Core también incluye un conjunto de versiones de .NET Framework de destino (por ejemplo, `netstandard` o `netcoreapp`) que representan un conjunto de API cada vez mayor a medida que se incrementan los números de versión.

### <a name="net-standard"></a>.NET Standard

.NET Standard ha estado usando un esquema de control de versiones `MAJOR.MINOR`. El nivel `PATCH` no es útil para .NET Standard porque expresa un conjunto de contratos que se repiten con menos frecuencia y no presenta los mismos requisitos de control de versiones que una implementación real.

No hay ningún emparejamiento real entre las versiones de .NET Standard y las de .NET Core: .NET Core 2.0 implementa .NET Standard 2.0, pero no hay ninguna garantía de que las futuras versiones de .NET Core se vayan a asignar a la misma versión de .NET Standard. .NET Core puede distribuir API que no están definidas por .NET Standard y, así, puede distribuir nuevas versiones sin necesidad de una nueva instancia de .NET Standard. .NET Standard también es un concepto que se aplica a otros destinos, como .NET Framework o Mono, incluso en el caso de que su expedición coincidiera con la de .NET Core.

### <a name="packages"></a>Paquetes

Los paquetes de biblioteca evolucionan y se les asignan versiones de forma independiente. Los paquetes que se superponen con ensamblados de .NET Framework System.\* usan normalmente versiones 4.x y se alinean con el control de versiones de .NET Framework 4.x (una opción histórica). Los paquetes que no se superponen con las bibliotecas de .NET Framework (por ejemplo, [`System.Reflection.Metadata`](https://www.nuget.org/packages/System.Reflection.Metadata)) normalmente empiezan en 1.0 y se incrementan a partir de ahí.

Los paquetes descritos por [`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library) se tratan de manera especial debido a que están en la base de la plataforma.

Los paquetes `NETStandard.Library` tendrán normalmente una versión de conjunto, puesto que tienen dependencias de nivel de implementación entre ellos.

### <a name="metapackages"></a>Metapaquetes

El control de versiones de los metapaquetes de .NET Core se basa en la versión de .NET Core de la que forman parte.

Por ejemplo, los metapaquetes de .NET Core 2.1.3 deben tener 2.1 como sus números de versión `MAJOR` y `MINOR`.

La versión de revisión del metapaquete se incrementa cada vez que se actualiza un paquete al que se hace referencia. Las versiones de revisión no incluyen una versión del marco de trabajo actualizada. Como consecuencia, los metapaquetes no son compatibles de forma estricta con SemVer porque su esquema de control de versiones no representa el grado de cambio en los paquetes subyacentes, sino principalmente del nivel de API.

Actualmente hay dos metapaquetes principales de .NET Core:

**Microsoft.NETCore.App**

- v1.0 a partir de .NET Core 1.0 (estas versiones coinciden).
- Se asigna al marco `netcoreapp`.
- Describe los paquetes de la distribución de .NET Core.

Nota: [`Microsoft.NETCore.Portable.Compatibility`](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility) es otro metapaquete de .NET Core que existe para habilitar la compatibilidad con la implementación previa a .NET Standard de .NET. No se asigna a un marco de trabajo determinado, así que realiza el control de versiones como un paquete.

**NETStandard.Library**

[`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library) describe las bibliotecas que forman parte de [.NET Standard](../../standard/library.md). Se aplica a todas las implementaciones de .NET que admiten .NET Standard, como .NET Framework, .NET Core y Mono.

### <a name="target-frameworks"></a>Versiones de .NET Framework de destino

Las versiones de .NET Framework de destino se actualizan cuando se agregan nuevas API. No tienen ningún concepto de versión de revisión, ya que representan la forma de API y no los problemas de implementación. El control de versiones principal y secundaria sigue las reglas de SemVer especificadas anteriormente y coincide con los números `MAJOR` y `MINOR` de las distribuciones de .NET Core que las implementan.

## <a name="versioning-in-practice"></a>Control de versiones en la práctica

Al descargar .NET Core, el nombre del archivo descargado incluye la versión, por ejemplo, `dotnet-sdk-2.0.4-win10-x64.exe`.

Cada día hay confirmaciones y solicitudes de incorporación de cambios en repositorios de .NET Core en GitHub, lo que da lugar a nuevas compilaciones de muchas bibliotecas. No resulta práctico crear nuevas versiones públicas de .NET Core para cada cambio. Así, los cambios se agregan durante un período de tiempo indefinido (por ejemplo, semanas o meses) antes de crear una nueva versión de .NET Core pública que sea estable.

Una nueva versión de .NET Core podría significar varias cosas:

- Nuevas versiones de paquetes y metapaquetes.
- Nuevas versiones de distintos marcos, contando con la adición de nuevas API.
- Nueva versión de la distribución de .NET Core.

### <a name="shipping-a-patch-release"></a>Envío de una versión de revisión

Después de distribuir una versión principal de .NET Core, como 2.0.0, se realizan cambios en el nivel de revisión en las bibliotecas de .NET Core para corregir errores y mejorar el rendimiento y la confiabilidad. Eso significa que no se incluye ninguna API nueva. Los diversos metapaquetes se actualizan para hacer referencia a los paquetes de biblioteca de .NET Core actualizados. Los metapaquetes tienen la versión de las actualizaciones de revisión (`MAJOR.MINOR.PATCH`). Las versiones de .NET Framework de destino nunca se actualizan como parte de versiones de revisión. Se publica una nueva distribución de .NET Core con un número de versión que coincide con el del metapaquete `Microsoft.NETCore.App`.

### <a name="shipping-a-minor-release"></a>Envío de una versión secundaria

Después de distribuir una versión de .NET Core con un número de versión incrementado `MAJOR`, se agregan nuevas API a las bibliotecas de .NET Core para permitir nuevos escenarios. Los diversos metapaquetes se actualizan para hacer referencia a los paquetes de biblioteca de .NET Core actualizados. Las versiones de los metapaquetes se controlan como actualizaciones de revisión con números de versión `MAJOR` y `MINOR` que coinciden con la nueva versión del marco de trabajo. Se agregan nuevas versiones de .NET Framework de destino con la nueva versión `MAJOR.MINOR` para describir las nuevas API (por ejemplo, `netcoreapp2.1`). Se lanza una nueva distribución de .NET Core con un número de versión que coincide con el metapaquete `Microsoft.NETCore.App`.

### <a name="shipping-a-major-release"></a>Envío de una versión principal

Cada vez que se distribuye una nueva versión principal de .NET Core, se incrementa el número de versión `MAJOR` y el número de versión `MINOR` se restablece a cero. La nueva versión principal contiene al menos todas las API agregadas en versiones secundarias después de la versión principal anterior. Una nueva versión principal debe habilitar nuevos escenarios importantes y también puede anular la compatibilidad con una plataforma anterior.

Los diversos metapaquetes se actualizan para hacer referencia a los paquetes de biblioteca de .NET Core actualizados. Las versiones del metapaquete [`Microsoft.NETCore.App`](https://www.nuget.org/packages/Microsoft.NETCore.App) y la versión de .NET Framework de destino `netcore` se controlan como una actualización principal que coincide con el número de versión `MAJOR` de la nueva versión.

## <a name="see-also"></a>Vea también

[Marcos de trabajo de destino](../../standard/frameworks.md)  
[Empaquetado de distribución de .NET Core](../build/distribution-packaging.md)  
[Hoja de información sobre el ciclo de vida de compatibilidad de .NET Core](https://www.microsoft.com/net/core/support)  
[.NET Core 2+ Version Binding (Enlace de versión de .NET Core 2+)](https://github.com/dotnet/designs/issues/3)  
