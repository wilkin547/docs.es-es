---
title: Compatibilidad de aplicaciones en .NET Framework
ms.date: 05/19/2017
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 154640499e99767f73a148c6980e6a2a4cfbce2f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623790"
---
# <a name="application-compatibility-in-the-net-framework"></a>Compatibilidad de aplicaciones en .NET Framework

## <a name="introduction"></a>Introducción
La compatibilidad es un objetivo muy importante de cada versión .NET. La compatibilidad garantiza que cada versión es adicional, por lo que las versiones anteriores siguen funcionando. Por otro lado, los cambios en las funciones anteriores (para mejorar el rendimiento, tratar los problemas de seguridad o corregir errores) pueden provocar problemas de compatibilidad en el código existente o en las aplicaciones existentes que se ejecutan en una versión posterior. .NET Framework reconoce los cambios de redestinación y los cambios en tiempo de ejecución. Los cambios de redestinación afectan a las aplicaciones que se refieren a una versión específica de .NET Framework pero se ejecutan en una versión posterior. Los cambios en tiempo de ejecución afectan a todas las aplicaciones que se ejecutan en una versión determinada.

Cada aplicación se refiere a una versión específica de .NET Framework, que puede especificarse:

* Al definir una plataforma de destino en Visual Studio.
* Al especificar la plataforma de destino en un archivo de proyecto.
* Al aplicar <xref:System.Runtime.Versioning.TargetFrameworkAttribute> en el código fuente.

Al ejecutarse en una versión más reciente que a la que se refería, .NET Framework usará un comportamiento anómalo para imitar la versión de destino anterior. En otras palabras, la aplicación se ejecutará en la versión más reciente de Framework pero actuará como si se estuviera ejecutando en la versión anterior. Muchos de los problemas de compatibilidad entre versiones de .NET Framework se mitigan a través de este peculiar modelo. La versión de .NET Framework a la que se destina una aplicación se determina por la versión de destino del ensamblado de entrada para el dominio de aplicación en el que se ejecuta el código. Todos los ensamblados adicionales que se cargan en ese dominio de aplicación tienen como destino esa versión de .NET Framework. Por ejemplo, en el caso de un archivo ejecutable, el marco de trabajo de destino del archivo ejecutable es el modo de compatibilidad en el que se ejecutarán todos los ensamblados de ese AppDomain.

## <a name="runtime-changes"></a>Cambios en tiempo de ejecución

Los problemas en tiempo de ejecución son los que aparecen cuando se coloca un nuevo runtime en un equipo y se ejecutan los mismos binarios, pero se observa un comportamiento diferente. Si un binario se ha compilado para .NET Framework 4.0 se ejecutará en el modo de compatibilidad de .NET Framework 4.0 en 4.5 o en versiones posteriores. Muchos de los cambios que afectan a la versión 4.5 no afectarán a un binario compilado para 4.0. Esto es específico del AppDomain y depende de la configuración del ensamblado de entrada.

## <a name="retargeting-changes"></a>Cambios de redestinación

Los problemas de redestinación son los que aparecen cuando un ensamblado que se refería a la versión 4.0 ahora se establece para referirse a la versión 4.5. Ahora el ensamblado participa en las características nuevas así como en los problemas de compatibilidad potenciales de las características antiguas. De nuevo, esto lo indica el ensamblado de entrada; es decir, la aplicación de consola que usa el ensamblado, o el sitio web que hace referencia a este.

## <a name="net-compatibility-diagnostics"></a>Diagnósticos de compatibilidad de .NET

Los diagnósticos de compatibilidad de .NET son analizadores de Roslyn que ayudan a identificar problemas de compatibilidad de aplicaciones entre versiones de .NET Framework. Esta lista contiene todos los analizadores disponibles, aunque solo se aplicará un subconjunto de ellos a una migración determinada. Los analizadores determinarán qué problemas son aplicables para la migración planeada y serán los únicos que muestren.

Cada problema incluye la siguiente información:

- La descripción de los cambios con respecto a una versión anterior.

- Cómo afecta el cambio a los clientes y si hay alguna solución alternativa disponible para mantener la compatibilidad entre versiones.

- Una valoración de la importancia que tiene el cambio. Los problemas de compatibilidad de aplicaciones se dividen en las siguientes categorías:

    |   |   |
    |---|---|
    |Major|Un cambio significativo que afecta a un gran número de aplicaciones o que requiere una modificación sustancial del código.|
    |Secundaria|Un cambio que afecta a un pequeño número de aplicaciones o que requiere una leve modificación del código.|
    |Caso avanzado|Un cambio que afecta a aplicaciones en situaciones muy concretas y poco frecuentes.|
    |Transparente|Un cambio que no tiene ningún efecto apreciable para el desarrollador o el usuario de la aplicación.|

- La versión, que indica la primera aparición del cambio en .NET Framework. Algunos de los cambios se presentan en una versión determinada y se revierten en una versión posterior; que también se indica.

- El tipo de cambio:

    |   |   |
    |---|---|
    |Redestinación|El cambio afecta a aplicaciones que se vuelven a compilar para tener como destino una nueva versión de .NET Framework.|
    |Tiempo de ejecución|El cambio afecta a una aplicación existente que tiene como destino una versión anterior de .NET Framework, pero que se ejecuta en una versión posterior.|

- Las API afectadas, si las hubiera.

- Los identificadores de los diagnósticos disponibles.

## <a name="usage"></a>Uso
Para comenzar, seleccione el tipo de cambio de compatibilidad a continuación:

* [Cambios de redestinación](./retargeting/index.md)
* [Cambios en el runtime](./runtime/index.md)

## <a name="see-also"></a>Vea también

- [Versiones y dependencias](../../../docs/framework/migration-guide/versions-and-dependencies.md)
- [Novedades](../../../docs/framework/whats-new/index.md)
- [Lo obsoleto en la biblioteca de clases](../../../docs/framework/whats-new/whats-obsolete.md)
