---
title: "Implementación de aplicaciones .NET Core | Microsoft Docs"
description: "Implementación de una aplicación .NET Core."
keywords: ".NET, .NET Core, implementación de .NET Core"
author: rpetrusha
ms.author: ronpet
ms.date: 04/18/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: da7a31a0-8072-4f23-82aa-8a19184cb701
ms.translationtype: Human Translation
ms.sourcegitcommit: 3ffe3909902659a22cb25bac6dc5aaa4f5b9fde2
ms.openlocfilehash: 31503e39d8a96092dbce03c17397e1adfec6421e
ms.contentlocale: es-es
ms.lasthandoff: 05/13/2017

---

# <a name="net-core-application-deployment"></a>Implementación de aplicaciones .NET Core

Puede crear dos tipos de implementaciones para aplicaciones .NET Core:

- Implementación dependiente de Framework. Como su nombre indica, la implementación dependiente de marco de trabajo (FDD) se basa en la presencia de una versión compartida de .NET Core en todo el sistema en el sistema de destino. Como .NET Core ya está presente, la aplicación también es portátil entre instalaciones de .NET Core. La aplicación solo contiene su propio código y dependencias de terceros que están fuera de las bibliotecas .NET Core. FDD contiene archivos *.dll* que se pueden iniciar utilizando la [utilidad dotnet](../tools/dotnet.md) desde la línea de comandos. Por ejemplo, `dotnet app.dll` ejecuta una aplicación denominada `app`.

- Implementación autocontenida. A diferencia de FDD, una implementación autocontenida (SCD) no depende de la presencia de los componentes compartidos en el sistema de destino. Todos los componentes, incluidas las bibliotecas y el entorno de ejecución de .NET Core, se incluyen con la aplicación y están aislados de otras aplicaciones .NET Core. Las SCD incluyen un archivo ejecutable (como *app.exe* en plataformas de Windows para una aplicación denominada `app`), que es una versión con otro nombre del host de .NET Core específico de la plataforma y un archivo *.dll* (como *app.dll*), que es la aplicación real.

## <a name="framework-dependent-deployments-fdd"></a>Implementaciones dependientes de Framework (FDD)

En una FDD, solo se implementa su aplicación y cualquier dependencia de terceros. No tiene que implementar .NET Core, puesto que la aplicación usará la versión de .NET Core que esté presente en el sistema de destino. Este es el modelo de implementación predeterminado para aplicaciones .NET Core.

### <a name="why-create-a-framework-dependent-deployment"></a>¿Por qué crear una implementación dependiente del marco?

La implementación de FDD tienen varias ventajas:

- No es necesario definir por adelantado los sistemas operativos de destino en los que se ejecutará la aplicación .NET Core. Como .NET Core usa un formato de archivo PE común para archivos ejecutables y bibliotecas independientemente del sistema operativo, .NET Core puede ejecutar la aplicación con independencia del sistema operativo subyacente. Para más información sobre el formato de archivo PE, consulte [.NET Assembly File Format](../../standard/assembly-format.md) (Formato de archivo de ensamblado .NET).

- El tamaño de su paquete de implementación es pequeño. Solo tendrá que implementar la aplicación y sus dependencias, .NET Core propiamente dicho.

- Varias aplicaciones usan la misma instalación de .NET Core, lo que reduce tanto el espacio en disco y el uso de memoria en sistemas host.

Hay también algunas desventajas:

- Su aplicación solo se puede ejecutar si la versión de .NET Core de destino, o una versión posterior, ya está instalada en el sistema host.

- Es posible que el entorno de tiempo de ejecución y las bibliotecas .NET Core cambien en futuras versiones sin su conocimiento. En raras ocasiones, esto puede cambiar el comportamiento de la aplicación.

## <a name="self-contained-deployments-scd"></a>Implementaciones autocontenidas (SCD)

En una implementación autocontenida, implementa su aplicación y cualquier dependencia de terceros junto con la versión de .NET Core que ha usado para compilar la aplicación. La creación de una SCD no incluye las [dependencias nativas de .NET Core](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) en diversas plataformas (por ejemplo, OpenSSL en macOS), así que es necesario que estén presentes antes de ejecutar la aplicación.

### <a name="why-deploy-a-self-contained-deployment"></a>¿Por qué realizar una implementación autocontenida?

La implementación de una implementación autocontenida tiene dos ventajas principales:

- Tiene el control exclusivo de la versión de .NET Core que se implementa con la aplicación. El mantenimiento de .NET Core solo puede realizarlo usted.

- Puede tener la seguridad de que el sistema de destino puede ejecutar su aplicación de .NET Core, dado que usted proporciona la versión de .NET Core en la que se ejecuta.

También tiene algunos inconvenientes:

- Como .NET Core se incluye en el paquete de implementación, debe seleccionar por adelantado las plataformas de destino en las que se compilan los paquetes de implementación.

- El tamaño de su paquete de implementación es relativamente grande, ya que tendrá que incluir .NET Core, así como la aplicación y sus dependencias de terceros.

- La implementación de numerosas aplicaciones .NET Core autocontenidas en un sistema puede consumir importantes cantidades de espacio en disco, puesto que cada aplicación duplica archivos de .NET Core.

## <a name="step-by-step-examples"></a>Ejemplos paso a paso

Para ver ejemplos paso a paso de la implementación de aplicaciones .NET Core con herramientas de la CLI, consulte [Deploying .NET Core Apps with CLI Tools](deploy-with-cli.md) (Implementación de aplicaciones de .NET Core con herramientas de la CLI). Para ver ejemplos paso a paso de la implementación de aplicaciones .NET Core con herramientas de la CLI, consulte [Deploying .NET Core Apps with Visual Studio](deploy-with-vs.md) (Implementación de aplicaciones de .NET Core con Visual Studio). Cada tema incluye ejemplos de las siguientes implementaciones:

- Implementación dependiente de marco de trabajo
- Implementación dependiente de marco de trabajo con dependencias de terceros
- Implementación autocontenida
- Implementación autocontenida con dependencias de terceros

# <a name="see-also"></a>Vea también

[Deploying .NET Core Apps with CLI Tools](deploy-with-cli.md)  (Implementación de aplicaciones de .NET Core con herramientas de la CLI)  
[Deploying .NET Core Apps with Visual Studio](deploy-with-vs.md)  (Implementación de aplicaciones de .NET Core con Visual Studio)  
[Paquetes, metapaquetes y marcos de trabajo](../packages.md)   
[Catálogo de identificadores de entorno de ejecución (RID) de .NET Core](../rid-catalog.md)

