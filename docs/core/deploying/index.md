---
title: Implementación de aplicaciones .NET Core
description: Conozca las formas de implementar una aplicación .NET Core.
ms.date: 12/03/2018
ms.openlocfilehash: 41c5285f2a9ddf38e4be7326bd5cba1c58370fe7
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740809"
---
# <a name="net-core-application-deployment"></a>Implementación de aplicaciones .NET Core

Puede crear tres tipos de implementaciones para aplicaciones .NET Core:

- Implementación dependiente de Framework. Como su nombre indica, la implementación dependiente de marco de trabajo (FDD) se basa en la presencia de una versión compartida de .NET Core en todo el sistema en el sistema de destino. Como .NET Core ya está presente, la aplicación también es portátil entre instalaciones de .NET Core. La aplicación solo contiene su propio código y dependencias de terceros que están fuera de las bibliotecas .NET Core. FDD contiene archivos *.dll* que se pueden iniciar utilizando la [utilidad dotnet](../tools/dotnet.md) desde la línea de comandos. Por ejemplo, `dotnet app.dll` ejecuta una aplicación denominada `app`.

- Implementación autocontenida. A diferencia de FDD, una implementación autocontenida (SCD) no depende de la presencia de los componentes compartidos en el sistema de destino. Todos los componentes, incluidas las bibliotecas y el entorno de ejecución de .NET Core, se incluyen con la aplicación y están aislados de otras aplicaciones .NET Core. Las SCD incluyen un archivo ejecutable (como *app.exe* en plataformas de Windows para una aplicación denominada `app`), que es una versión con otro nombre del host de .NET Core específico de la plataforma y un archivo *.dll* (como *app.dll*), que es la aplicación real.

- Archivos ejecutables dependiente de la plataforma. Genera un archivo ejecutable que se ejecuta en una plataforma de destino. De manera parecida a las FDD, los archivos ejecutables dependientes de la plataforma (FDE) son específicos de la plataforma y no son independientes. Estas implementaciones aún dependen de la presencia de una versión compartida de .NET Core en todo el sistema para ejecutarse. A diferencia de una SCD, la aplicación solo contiene su código y las dependencias de terceros que están fuera de las bibliotecas .NET Core. Las FDE generan un archivo ejecutable que se ejecuta en la plataforma de destino.

## <a name="framework-dependent-deployments-fdd"></a>Implementaciones dependientes de Framework (FDD)

En una implementación dependiente del marco de trabajo, solo se implementa la aplicación y las dependencias de terceros. La aplicación usará la versión de .NET Core que exista en el sistema de destino. Este es el modelo de implementación predeterminado para las aplicaciones .NET Core y ASP.NET Core que tienen como destino .NET Core.

### <a name="why-create-a-framework-dependent-deployment"></a>¿Por qué crear una implementación dependiente del marco?

La implementación de FDD tienen varias ventajas:

- No es necesario definir por adelantado los sistemas operativos de destino en los que se ejecutará la aplicación .NET Core. Como .NET Core usa un formato de archivo PE común para archivos ejecutables y bibliotecas independientemente del sistema operativo, .NET Core puede ejecutar la aplicación con independencia del sistema operativo subyacente. Para más información sobre el formato de archivo PE, consulte [.NET Assembly File Format](../../standard/assembly/file-format.md) (Formato de archivo de ensamblado .NET).

- El tamaño de su paquete de implementación es pequeño. Solo tendrá que implementar la aplicación y sus dependencias, .NET Core propiamente dicho.

- A menos que se reemplace, las FDD usarán el entorno de ejecución atendido más reciente instalado en el sistema de destino. De esta forma, la aplicación puede usar la versión revisada más reciente del entorno de ejecución de .NET Core. 

- Varias aplicaciones usan la misma instalación de .NET Core, lo que reduce tanto el espacio en disco y el uso de memoria en sistemas host.

Hay también algunas desventajas:

- Su aplicación solo se puede ejecutar si la versión de .NET Core de destino de la aplicación, [o una versión posterior](../versions/selection.md#framework-dependent-apps-roll-forward), ya está instalada en el sistema host.

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

  A partir de .NET Core 2.0, puede reducir el tamaño de la implementación en sistemas Linux en 28 MB aproximadamente con el [*modo invariable global*](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md) de .NET Core. Normalmente, .NET Core en Linux se basa en las [bibliotecas ICU](http://icu-project.org) para la compatibilidad global. En modo invariable, las bibliotecas no se incluyen con la implementación y todas las referencias culturales se comportan como la [referencia cultural invariable](xref:System.Globalization.CultureInfo.InvariantCulture?displayProperty=nameWithType).

- La implementación de numerosas aplicaciones .NET Core autocontenidas en un sistema puede consumir importantes cantidades de espacio en disco, puesto que cada aplicación duplica archivos de .NET Core.

## <a name="framework-dependent-executables-fde"></a>Archivos ejecutables dependiente de la plataforma (FDE)

A partir de .NET Core 2.2, puede implementar la aplicación como una FDE, junto con cualquier dependencia de terceros necesaria. La aplicación usará la versión de .NET Core que está instalada en el sistema de destino.

### <a name="why-deploy-a-framework-dependent-executable"></a>¿Por qué implementar un archivo ejecutable dependiente de la plataforma?

La implementación de un FDE tiene una serie de ventajas:

- El tamaño de su paquete de implementación es pequeño. Solo tendrá que implementar la aplicación y sus dependencias, .NET Core propiamente dicho.

- Varias aplicaciones usan la misma instalación de .NET Core, lo que reduce tanto el espacio en disco y el uso de memoria en sistemas host.

- Para ejecutar la aplicación se puede llamar al archivo ejecutable publicado sin invocar la utilidad `dotnet` directamente.

Hay también algunas desventajas:

- Su aplicación solo se puede ejecutar si la versión de .NET Core de destino de la aplicación, [o una versión posterior](../versions/selection.md#framework-dependent-apps-roll-forward), ya está instalada en el sistema host.

- Es posible que el entorno de tiempo de ejecución y las bibliotecas .NET Core cambien en futuras versiones sin su conocimiento. En raras ocasiones, esto puede cambiar el comportamiento de la aplicación.

- Se debe publicar la aplicación para cada plataforma de destino.

## <a name="step-by-step-examples"></a>Ejemplos paso a paso

Para ver ejemplos paso a paso de la implementación de aplicaciones .NET Core con herramientas de la CLI, consulte [Deploying .NET Core Apps with CLI Tools](deploy-with-cli.md) (Implementación de aplicaciones de .NET Core con herramientas de la CLI). Para ver ejemplos paso a paso de la implementación de aplicaciones .NET Core con herramientas de la CLI, consulte [Deploying .NET Core Apps with Visual Studio](deploy-with-vs.md) (Implementación de aplicaciones de .NET Core con Visual Studio). 

## <a name="see-also"></a>Vea también

- [Implementación de aplicaciones .NET Core con herramientas de la CLI](deploy-with-cli.md)
- [Implementación de aplicaciones de .NET Core con Visual Studio](deploy-with-vs.md)
- [Paquetes, metapaquetes y marcos de trabajo](../packages.md)
- [Catálogo de identificadores de entorno de ejecución (RID) de .NET Core](../rid-catalog.md)
