---
title: Versiones, revisiones y compatibilidad de .NET
description: Obtenga información sobre las versiones, las revisiones y la compatibilidad con .NET 5 (incluido .NET Core) y versiones posteriores.
ms.date: 10/07/2020
ms.topic: overview
ms.author: tdykstra
author: tdykstra
ms.openlocfilehash: 896b88cbf1f7f31d2d26d69ec7d219da6b27ceff
ms.sourcegitcommit: 6d1ae17e60384f3b5953ca7b45ac859ec6d4c3a0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "97866398"
---
# <a name="releases-and-support-for-net-core-and-net-5"></a>Versiones y compatibilidad con .NET Core y .NET 5.

Microsoft incluye versiones principales, versiones secundarias y actualizaciones de mantenimiento (revisiones) para .NET 5.0 (y .NET Core) y versiones posteriores. En este artículo se explican los tipos de versión, las actualizaciones de mantenimiento, las bandas de características de SDK, y los períodos y opciones de compatibilidad.

## <a name="release-types"></a>Tipos de versión

La información sobre el tipo de cada versión está codificado en el número de versión con el formato *principal.secundaria.revisión*.

Por ejemplo:

* .NET Core 3.0 y NET 5.0 son versiones principales.
* .NET Core 3.1 es la primera versión secundaria después de la versión principal de .NET Core 3.0.
* .NET Core 3.1.7 es la séptima revisión para .NET Core 3.1.

### <a name="major-releases"></a>Versiones principales:

Las versiones principales incluyen nuevas características, una nueva área expuesta de API pública y correcciones de errores. Algunos ejemplos son .NET Core 3.0 y .NET 5.0.  Debido a la naturaleza de los cambios, se espera que se realicen cambios importantes en estas versiones. Las versiones principales se instalan en paralelo con las versiones principales anteriores.

### <a name="minor-releases"></a>Versiones secundarias

Las versiones secundarias también incluyen nuevas características, un área expuesta de API pública y correcciones de errores, y también pueden tener cambios importantes. Algunos ejemplos son .NET Core 2.1 y .NET 3.1. La diferencia entre estas y versiones principales es que la magnitud de los cambios es menor. El avance que realiza una aplicación que se actualiza desde .NET Core 3.0 a 3.1 es menor. Las versiones secundarias se instalan en paralelo con las versiones secundarias anteriores.

### <a name="servicing-updates"></a>Actualizaciones de mantenimiento

Las actualizaciones de mantenimiento (revisiones) se envían casi todos los meses y estas actualizaciones llevan a cabo tanto correcciones de errores que son de seguridad como que no. Por ejemplo, .NET Core 3.1.8 es la octava actualización para .NET Core 3.1. Cuando estas actualizaciones incluyen correcciones de seguridad, se publican en un "Patch Tuesday", que siempre es el segundo martes del mes. Se espera que las actualizaciones de servicio mantengan la compatibilidad. A partir de .NET Core 3.1, las actualizaciones de mantenimiento son actualizaciones que quitan la actualización anterior. Por ejemplo, la actualización de servicio más reciente de 3.1 quita la actualización de 3.1 anterior tras una instalación correcta.

### <a name="feature-bands-sdk-only"></a>Bandas de características (solo SDK)

El control de versiones del SDK de .NET funciona de forma ligeramente diferente del entorno de ejecución de .NET. Para alinearse con las nuevas versiones de Visual Studio, las actualizaciones del SDK de .NET a veces incluyen nuevas características o nuevas versiones de componentes como MSBuild y NuGet. Estas nuevas características o componentes pueden no ser compatibles con las versiones incluidas en las actualizaciones anteriores del SDK para la misma versión principal o secundaria.

Para diferenciar estas actualizaciones, el SDK de .NET usa el concepto de bandas de características. Por ejemplo, el primer SDK de .NET Core 3.1 era 3.1.100. Esta versión corresponde a la *banda de características* 3.1.1 XX. Las bandas de características se definen en los grupos de centenas de la tercera sección del número de versión. Por ejemplo, 3.1.101 y 3.1.201 son versiones de dos bandas de características distintas mientras que 3.1.101 y 3.1.199 están en la misma banda de características. Cuando se instale el SDK 3.1.101 de .NET Core, se quitará el SDK 3.1.100 de .NET Core de la máquina, si existe. Cuando se instale el SDK 3.1.200 de .NET Core en la misma máquina, no se quitará el SDK 3.1.101 de .NET Core.

### <a name="runtime-roll-forward-and-compatibility"></a>Puesta al día y compatibilidad del entorno de ejecución

Las actualizaciones principales y secundarias se instalan en paralelo con las versiones anteriores. Una aplicación que esté compilada para tener como destino una versión *principal.secundaria* específica sigue usando ese entorno de ejecución de destino, incluso si se instala una versión más reciente. La aplicación no se pone al día automáticamente para usar una versión más reciente de la versión *principal.secundaria* del entorno de ejecución, a menos que elija este comportamiento. Una aplicación que se compiló para tener como destino .NET Core 3.0 no empieza a ejecutarse automáticamente en .NET Core 3.1. Se recomienda recompilar la aplicación y realizar pruebas en una versión del entorno de ejecución principal o secundaria más reciente antes de implementarla en producción. Para obtener más información, vea [Puesta al día de las aplicaciones dependientes de la plataforma](versions/selection.md#framework-dependent-apps-roll-forward) y [Puesta al día del entorno de ejecución de implementación autocontenida](deploying/runtime-patch-selection.md).

Las actualizaciones de mantenimiento se tratan de forma diferente a las versiones principales y secundarias. Una aplicación compilada para tener como destino .NET Core 3.1 se ejecuta de forma predeterminada en el entorno de ejecución de 3.1.0. y se pone al día automáticamente para usar un entorno de ejecución en versión 3.1.1 más reciente cuando se instala esa actualización de mantenimiento. Este comportamiento es el predeterminado porque queremos que las correcciones de seguridad se usen en cuanto se instalen sin necesidad de realizar ninguna otra acción. Puede cambiar este comportamiento de puesta al día predeterminado.

## <a name="net-core-and-net-5-version-lifecycles"></a>Ciclos de vida de la versión de .NET Core y .NET 5

.NET Core, .NET 5 y las versiones posteriores adoptan el [ciclo de vida moderno](/lifecycle/policies/modern) en lugar del [ciclo de vida fijo](/lifecycle/policies/fixed) que se ha usado para las versiones .NET Framework. Los productos con ciclos de vida fijos ofrecen un amplio período de soporte técnico, por ejemplo, 5 años de soporte estándar y otros 5 años de soporte extendido. El soporte estándar incluye correcciones de seguridad y que no son de seguridad, mientras que el soporte extendido solo proporciona correcciones de seguridad. Los productos que adoptan un ciclo de vida moderno tienen un modelo de soporte técnico más similar al servicio, con períodos de soporte técnico más cortos y versiones más frecuentes.

### <a name="release-tracks"></a>Seguimiento de las versiones

Hay dos pistas de soporte técnico de las versiones:

* Versiones *actuales*

  Estas versiones tienen soporte técnico hasta 3 meses después de que se lance la siguiente versión principal o secundaria.

  Ejemplo:

  * .NET Core 3.0 se lanzó en septiembre de 2019 y le siguió .NET Core 3.1 en diciembre de 2019.
  * El soporte técnico de .NET Core 3.0 finalizó el 2020 de marzo, 3 meses después del lanzamiento de la 3.1.

* Versiones de *soporte técnico a largo plazo* (LTS)

  Estas versiones tienen soporte técnico durante un mínimo de 3 años, o un año después de que se lance la siguiente versión de LTS, si esa fecha es posterior.

  Ejemplo:

  * .NET Core 2.1 se lanzó en mayo de 2018 y se consideró una versión de LTS en agosto de 2018.
  * .NET Core 3.1 era la siguiente versión de LTS y se lanzó en diciembre de 2019.
  * Dado que agosto de 2021 (3 años) es posterior a diciembre de 2020 (un año después de la versión 3.1), .NET Core 2.1 tiene soporte técnico hasta agosto de 2021.

Las versiones alternan entre actuales y LTS, por lo que es posible que una versión anterior tenga soporte técnico durante más tiempo que una versión posterior. Por ejemplo, .NET Core 2.1 es una versión de LTS con compatibilidad hasta agosto de 2021. La versión 3.0 se lanzó más de un año más tarde, pero su soporte técnico finalizó antes, en diciembre de 2019.

Las actualizaciones de mantenimiento se envían mensualmente e incluyen tanto correcciones de seguridad como que no son de seguridad (confiabilidad, compatibilidad y estabilidad). Las actualizaciones de mantenimiento se admiten hasta que se lance la siguiente actualización de servicio. Las actualizaciones de mantenimiento tienen un comportamiento de puesta al día del entorno de ejecución. Esto significa que las aplicaciones se ejecutan de forma predeterminada en la actualización de servicio de entorno de ejecución instalada más reciente.

## <a name="how-to-choose-a-release"></a>Cómo elegir una versión

Si va a compilar un servicio y espera seguir actualizándolos periódicamente, una versión actual como .NET 5.0 puede ser la mejor opción para mantenerse al día con las características más recientes que ofrece .NET.

Si va a compilar una aplicación cliente que se distribuirá a los consumidores, es posible que la estabilidad sea más importante que el acceso a las características más recientes. Es posible que la aplicación necesite tener soporte técnico durante un período determinado antes de que el consumidor pueda actualizar a la versión siguiente de la aplicación. En ese caso, una versión de LTS como .NET Core 3.1 podría ser la opción correcta.

### <a name="servicing-updates"></a>Actualizaciones de mantenimiento

Las actualizaciones de mantenimiento de .NET hasta se admiten hasta que se lance la siguiente actualización de servicio. El ritmo de lanzamiento es mensual.

Debe instalar periódicamente las actualizaciones de mantenimiento para asegurarse de que las aplicaciones están en un estado seguro y con soporte técnico. Por ejemplo, si la actualización de servicio más reciente de .NET Core 3.1 es la 3.1.8 y se lanza la 3.1.9, entonces la 3.1.8 ya no es la más reciente. El nivel de servicio de soporte técnico para la 3.1 es 3.1.9.

Para obtener información sobre las actualizaciones de servicio más recientes para cada versión principal y secundaria, consulte la página de [descargas de .NET](https://dotnet.microsoft.com/download/dotnet-core).

## <a name="end-of-support"></a>Finalización del soporte técnico

La finalización del soporte técnico se refiere a la fecha a partir de la cual Microsoft ya no proporciona correcciones, actualizaciones o asistencia técnica para una versión del producto. Antes de esta fecha, asegúrese de que ha pasado a usar una versión con soporte técnico. Las versiones que no tienen soporte técnico ya no reciben actualizaciones de seguridad que protejan sus aplicaciones y sus datos.

## <a name="supported-operating-systems"></a>Sistemas operativos admitidos

.NET 5 (y .NET Core) y versiones posteriores se pueden ejecutar en una variedad de sistemas operativos. Cada uno de estos sistemas operativos tiene un ciclo de vida definido por su organización patrocinadora (por ejemplo, Microsoft, Red Hat o Apple). Estas programaciones de ciclo de vida se tienen en cuenta al agregar y quitar el soporte técnico a las versiones de sistema operativo.

Cuando una versión de sistema operativo deja de tener soporte técnico, se deja de probar esa versión y de proporcionar soporte técnico para ella. Los usuarios deben avanzar a una versión del sistema operativo con soporte técnico para obtener asistencia.

Para obtener más información, consulte la [directiva de ciclo de vida del sistema operativo de .NET Core](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md).

## <a name="get-support"></a>Obtener soporte técnico

Puede elegir entre soporte técnico asistido de Microsoft y soporte técnico de la comunidad.

### <a name="microsoft-support"></a>Soporte técnico de Microsoft

Para obtener soporte técnico asistido, [póngase en contacto con un profesional de soporte técnico de Microsoft](https://support.microsoft.com/supportforbusiness/productselection/?sapid=4fd4947b-15ea-ce01-080f-97f2ca3c76e8).

Debe estar en un nivel de servicio compatible (la actualización de servicio disponible más reciente) para poder optar al soporte técnico. Si un sistema ejecuta la versión 3.1 y se ha publicado la actualización de servicio 3.1.8, el primer paso que debe dar es instalar la 3.1.8.

### <a name="community-support"></a>Soporte técnico de la comunidad

Para obtener soporte técnico de la comunidad, vea la [página de la comunidad](https://dotnet.microsoft.com/platform/community).

## <a name="see-also"></a>Consulte también

Para obtener más información, incluidos los intervalos de fechas de soporte técnico para cada versión de .NET Core y para .NET 5, vea la [Directiva de soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).
