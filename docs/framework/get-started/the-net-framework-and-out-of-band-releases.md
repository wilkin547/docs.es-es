---
title: .NET Framework y versiones fuera de banda
description: Más información sobre .NET y versiones fuera de banda. Nuevas características fuera de banda (OOB) para mejorar el desarrollo multiplataforma o para incluir una nueva funcionalidad.
ms.date: 10/10/2018
ms.assetid: 721f10fa-3189-4124-a00d-56ddabd889b3
ms.openlocfilehash: 9653696f46279e0c23418f92030d64839cc20518
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618771"
---
# <a name="net-framework-and-out-of-band-releases"></a>.NET Framework y versiones fuera de banda

.NET Framework ha evolucionado para adaptarse a distintas plataformas (como aplicaciones para UWP y aplicaciones de escritorio y web tradicionales) y para maximizar la reutilización de código. Además de las versiones de .NET Framework habituales, se publican nuevas características fuera de banda (OOB) para mejorar el desarrollo multiplataforma o para incluir una nueva funcionalidad.

## <a name="advantages-of-oob-releases"></a>Ventajas de las versiones OOB

La publicación de nuevos componentes o actualizaciones de componentes fuera de banda permite a Microsoft proporcionar actualizaciones frecuentes a .NET Framework. Además, podemos recopilar los comentarios de clientes y responder a ellos más rápidamente.

Cuando se usa una característica de OOB en la aplicación, los usuarios no tendrán que instalar la versión más reciente de .NET Framework para ejecutar la aplicación, ya que los ensamblados de OOB se implementan con el paquete de aplicación.

## <a name="how-oob-packages-are-distributed"></a>Cómo se distribuyen los paquetes OOB

Las versiones OOB para componentes básicos de Common Language Runtime (CLR) se entregan a través de [NuGet](https://www.nuget.org/), que es el administrador de paquetes de .NET. NuGet permite examinar y agregar bibliotecas a los proyectos de .NET Framework con facilidad desde Visual Studio. El administrador de paquetes NuGet se incluye con todas las ediciones de Visual Studio a partir de Visual Studio 2012. Busque **Administrador de paquetes NuGet** en el menú **Herramientas** de Visual Studio. Si no está instalado, siga las instrucciones de [instalación de NuGet](/nuget/install-nuget-client-tools). Para obtener más información sobre NuGet, vea los [documentos sobre NuGet](/nuget).

## <a name="use-a-nuget-oob-package"></a>Uso de un paquete OOB de NuGet

Si el administrador de paquetes NuGet está instalado, puede buscar y agregar referencias a paquetes de NuGet utilizando el Explorador de soluciones de Visual Studio:

1. Abra el menú contextual para su proyecto en Visual Studio y, después, elija **Administrar paquetes NuGet**. (Esta opción también está disponible en el menú **Proyecto**).

2. En el panel de la izquierda, elija **En línea**.

3. Si desea utilizar los paquetes de versión preliminar, en el cuadro de lista desplegable del panel central, elija **Incluir versión preliminar** en lugar de **Solo estable**.

4. En el panel derecho, utilice el cuadro **Buscar** para buscar el paquete que desee usar. Algunos paquetes de Microsoft se identifican mediante el logotipo de Microsoft .NET Framework, y en todos ellos se identifica Microsoft como el editor.

![El administrador de paquetes de NuGet.](./media/the-net-framework-and-out-of-band-releases/nuget-package-manager-dialog.png)

Tal como se ha mencionado, al implementar una aplicación que utiliza un paquete de OOB, los ensamblados de OOB se distribuirán con el paquete de aplicación.

## <a name="types-of-oob-releases"></a>Tipos de versiones de OOB

Normalmente, un paquete de OOB tiene una o varias versiones preliminares y una versión estable. La licencia que acompaña a una versión preliminar no suele permitir la redistribución, pero permite probar un paquete y proporcionar comentarios. Los comentarios se incorporan en las actualizaciones realizadas en el paquete. NuGet se distribuye con una versión final como un paquete estable e incluye una licencia que permite redistribuir el paquete de NuGet con la aplicación. Microsoft admite los paquetes estables. Microsoft proporciona compatibilidad con IntelliSense y otros tipos de documentación (por ejemplo, entradas de blog y respuestas en foros) para todos los paquetes. Además, el código fuente puede estar disponible con algunos paquetes, pero no todos. Si quiere recibir anuncios relacionados con paquetes nuevos y actualizados, suscríbase al [Blog de .NET Framework](https://devblogs.microsoft.com/dotnet/).

Si quiere encontrar paquetes tanto de versiones preliminares como estables, elija **Incluir versión preliminar** en Administrador de paquetes NuGet.

## <a name="see-also"></a>Vea también

- [Introducción](index.md)
