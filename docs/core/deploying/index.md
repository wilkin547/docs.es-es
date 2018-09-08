---
title: Implementación de aplicaciones .NET Core
description: Implementación de una aplicación .NET Core.
author: rpetrusha
ms.author: ronpet
ms.date: 09/03/2018
ms.openlocfilehash: 2ef63ebd737739b2c8e671d982c3844135689ab4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891316"
---
# <a name="net-core-application-deployment"></a>Implementación de aplicaciones .NET Core

Puede crear dos tipos de implementaciones para aplicaciones .NET Core:

- Implementación dependiente de Framework. Como su nombre indica, la implementación dependiente de marco de trabajo (FDD) se basa en la presencia de una versión compartida de .NET Core en todo el sistema en el sistema de destino. Como .NET Core ya está presente, la aplicación también es portátil entre instalaciones de .NET Core. La aplicación solo contiene su propio código y dependencias de terceros que están fuera de las bibliotecas .NET Core. FDD contiene archivos *.dll* que se pueden iniciar utilizando la [utilidad dotnet](../tools/dotnet.md) desde la línea de comandos. Por ejemplo, `dotnet app.dll` ejecuta una aplicación denominada `app`.

- Implementación autocontenida. A diferencia de FDD, una implementación autocontenida (SCD) no depende de la presencia de los componentes compartidos en el sistema de destino. Todos los componentes, incluidas las bibliotecas y el entorno de ejecución de .NET Core, se incluyen con la aplicación y están aislados de otras aplicaciones .NET Core. Las SCD incluyen un archivo ejecutable (como *app.exe* en plataformas de Windows para una aplicación denominada `app`), que es una versión con otro nombre del host de .NET Core específico de la plataforma y un archivo *.dll* (como *app.dll*), que es la aplicación real.

## <a name="framework-dependent-deployments-fdd"></a>Implementaciones dependientes de Framework (FDD)

En una implementación dependiente del marco de trabajo, solo se implementa la aplicación y las dependencias de terceros. No tiene que implementar .NET Core, puesto que la aplicación usará la versión de .NET Core que esté presente en el sistema de destino. Este es el modelo de implementación predeterminado para las aplicaciones .NET Core y ASP.NET Core que tienen como destino .NET Core.

### <a name="why-create-a-framework-dependent-deployment"></a>¿Por qué crear una implementación dependiente del marco?

La implementación de FDD tienen varias ventajas:

- No es necesario definir por adelantado los sistemas operativos de destino en los que se ejecutará la aplicación .NET Core. Como .NET Core usa un formato de archivo PE común para archivos ejecutables y bibliotecas independientemente del sistema operativo, .NET Core puede ejecutar la aplicación con independencia del sistema operativo subyacente. Para más información sobre el formato de archivo PE, consulte [.NET Assembly File Format](../../standard/assembly-format.md) (Formato de archivo de ensamblado .NET).

- El tamaño de su paquete de implementación es pequeño. Solo tendrá que implementar la aplicación y sus dependencias, .NET Core propiamente dicho.

- Varias aplicaciones usan la misma instalación de .NET Core, lo que reduce tanto el espacio en disco y el uso de memoria en sistemas host.

Hay también algunas desventajas:

- Su aplicación solo se puede ejecutar si la versión de .NET Core de destino, o una versión posterior, ya está instalada en el sistema host.

- Es posible que el entorno de tiempo de ejecución y las bibliotecas .NET Core cambien en futuras versiones sin su conocimiento. En raras ocasiones, esto puede cambiar el comportamiento de la aplicación.

## <a name="self-contained-deployments-scd"></a>Implementaciones autocontenidas (SCD)

En una implementación autocontenida, implementa su aplicación y cualquier dependencia de terceros junto con la versión de .NET Core que ha usado para compilar la aplicación. La creación de una SCD no incluye las [dependencias nativas de .NET Core](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) en diversas plataformas, así que es necesario que estén presentes antes de ejecutar la aplicación. Para obtener más información sobre el enlace de versiones en un entorno de ejecución, vea el artículo sobre [enlace de versiones de .NET Core](../versions/selection.md).

A partir del SDK de .NET Core 2.1 (versión 2.1.300), .NET Core es compatible con la *puesta al día de la revisión de versiones*. Cuando se crea una implementación autocontenida, las herramientas de .NET Core incluyen automáticamente el último tiempo de ejecución con mantenimiento de la versión de .NET Core a la que se dirige su aplicación. (El último tiempo de ejecución con mantenimiento incluye revisiones de seguridad y otras correcciones de errores). El tiempo de ejecución con mantenimiento no tiene que estar presente en el sistema de compilación; se descarga automáticamente de NuGet.org. Para más información, incluidas las instrucciones sobre cómo dejar de recibir la puesta al día de la revisión de versiones, vea [Puesta al día del tiempo de ejecución de implementación autocontenida](runtime-patch-selection.md).

Las implementaciones de FDD y SCD usan ejecutables de host independientes, por lo que puede firmar un host ejecutable de un SCD con su firma de publicador.

### <a name="why-deploy-a-self-contained-deployment"></a>¿Por qué realizar una implementación autocontenida?

La implementación de una implementación autocontenida tiene dos ventajas principales:

- Tiene el control exclusivo de la versión de .NET Core que se implementa con la aplicación. El mantenimiento de .NET Core solo puede realizarlo usted.

- Puede tener la seguridad de que el sistema de destino puede ejecutar su aplicación de .NET Core, dado que usted proporciona la versión de .NET Core en la que se ejecuta.

También tiene algunos inconvenientes:

- Como .NET Core se incluye en el paquete de implementación, debe seleccionar por adelantado las plataformas de destino en las que se compilan los paquetes de implementación.

- El tamaño de su paquete de implementación es relativamente grande, ya que tendrá que incluir .NET Core, así como la aplicación y sus dependencias de terceros.

  A partir de .NET Core 2.0, puede reducir el tamaño de la implementación en sistemas Linux en 28 MB aproximadamente con el [*modo invariable global*](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md) de .NET Core. Normalmente, .NET Core en Linux se basa en las [bibliotecas ICU](https://github.com/dotnet/docs/issues/http%22//icu-project.org) para la compatibilidad global. En modo invariable, las bibliotecas no se incluyen con la implementación y todas las referencias culturales se comportan como la [referencia cultural invariable](xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType).

- La implementación de numerosas aplicaciones .NET Core autocontenidas en un sistema puede consumir importantes cantidades de espacio en disco, puesto que cada aplicación duplica archivos de .NET Core.

## <a name="step-by-step-examples"></a>Ejemplos paso a paso

Para ver ejemplos paso a paso de la implementación de aplicaciones .NET Core con herramientas de la CLI, consulte [Deploying .NET Core Apps with CLI Tools](deploy-with-cli.md) (Implementación de aplicaciones de .NET Core con herramientas de la CLI). Para ver ejemplos paso a paso de la implementación de aplicaciones .NET Core con herramientas de la CLI, consulte [Deploying .NET Core Apps with Visual Studio](deploy-with-vs.md) (Implementación de aplicaciones de .NET Core con Visual Studio). Cada tema incluye ejemplos de las siguientes implementaciones:

- Implementación dependiente de marco de trabajo
- Implementación dependiente de marco de trabajo con dependencias de terceros
- Implementación autocontenida
- Implementación autocontenida con dependencias de terceros

## <a name="see-also"></a>Vea también

* [Implementación de aplicaciones .NET Core con herramientas de la CLI](deploy-with-cli.md)
* [Implementación de aplicaciones de .NET Core con Visual Studio](deploy-with-vs.md)
* [Paquetes, metapaquetes y marcos de trabajo](../packages.md)
* [Catálogo de identificadores de entorno de ejecución (RID) de .NET Core](../rid-catalog.md)
