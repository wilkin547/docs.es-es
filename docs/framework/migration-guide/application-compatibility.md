---
title: 'Cambios de runtime y redestinación: .NET Framework'
description: Obtenga información sobre la compatibilidad de las aplicaciones en .NET Framework y cómo se ve afectada por los cambios del entorno de ejecución y la redestinación al migrar a otra versión.
ms.date: 10/29/2019
helpviewer_keywords:
- application compatibility
- .NET Framework application compatibility
- .NET Framework changes
ms.assetid: c4ba3ff2-fe59-4c5d-9e0b-86bba3cd865c
ms.openlocfilehash: 26f36dd34c6c5ecae8fc5ab373ff60d9e56f8245
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475494"
---
# <a name="application-compatibility-in-the-net-framework"></a>Compatibilidad de aplicaciones en .NET Framework

La compatibilidad es un objetivo importante de todas las versiones de .NET. La compatibilidad garantiza que cada versión es aditiva, para que las versiones anteriores sigan funcionando. Por otro lado, los cambios en las funciones anteriores (por ejemplo para mejorar el rendimiento, abordar problemas de seguridad o corregir errores) pueden provocar problemas de compatibilidad en el código o las aplicaciones existentes que se ejecutan en una versión posterior.

Cada aplicación se destina a una versión específica de .NET Framework de esta forma:

- Al definir una plataforma de destino en Visual Studio.
- Al especificar la plataforma de destino en un archivo de proyecto.
- Al aplicar <xref:System.Runtime.Versioning.TargetFrameworkAttribute> en el código fuente.

Al migrar desde una versión de .NET Framework a otra, hay dos tipos de cambios que se deben tener en cuenta:

- [Cambios en el runtime](#runtime-changes)
- [Cambios de redestinación](#retargeting-changes)

## <a name="runtime-changes"></a>Cambios en tiempo de ejecución

Los problemas en tiempo de ejecución son los que aparecen cuando se coloca un nuevo runtime en un equipo y cambia el comportamiento de una aplicación. Al ejecutarse en una versión más reciente que la seleccionada como destino, .NET Framework usa un comportamiento *anómalo* para imitar la versión de destino anterior. La aplicación se ejecuta en la versión más reciente, pero actúa como si se ejecutara en la versión anterior. Muchos de los problemas de compatibilidad entre versiones de .NET Framework se mitigan a través de este peculiar modelo. Por ejemplo, si un binario se ha compilado para .NET Framework 4.0 pero se ejecuta en un equipo con .NET Framework 4.5 o posterior, se ejecuta en el modo de compatibilidad de .NET Framework 4.0. Esto significa que muchos de los cambios de la versión posterior no afectan al binario.

La versión de .NET Framework a la que se destina una aplicación se determina por la versión de destino del ensamblado de entrada para el dominio de aplicación en el que se ejecuta el código. Todos los ensamblados adicionales que se cargan en ese dominio de aplicación tienen como destino esa versión. Por ejemplo, en el caso de un archivo ejecutable, la versión de destino del archivo ejecutable es el modo de compatibilidad en el que se ejecutan todos los ensamblados de ese dominio de aplicación.

Para ver una lista de los cambios en tiempo de ejecución que se aplican al entorno, seleccione la versión de .NET Framework que tenga actualmente como destino y, después, la versión a la que quiera migrar:

[!INCLUDE[versionselector](../../../includes/migration-guide/runtime/versionselector.md)]

## <a name="retargeting-changes"></a>Cambios de redestinación

Los cambios de redestinación son los que surgen cuando se vuelve a compilar un ensamblado para destinarlo a una versión más reciente. Destinarlo a una versión más reciente significa que el ensamblado participa en las características nuevas así como en los problemas de compatibilidad potenciales de las características antiguas.

Para ver una lista de los cambios de redestinación que se aplican al entorno, seleccione la versión de .NET Framework que tenga actualmente como destino y, después, la versión a la que quiera migrar:

[!INCLUDE[versionselector](../../../includes/migration-guide/retargeting/versionselector.md)]

## <a name="impact-classification"></a>Clasificación de impacto

En los temas en los que se describen los cambios en tiempo de ejecución y de redestinación, por ejemplo [Cambios de redestinación para migrar de 4.7.2 a 4.8](retargeting/4.7.2-4.8.md), los elementos individuales se clasifican por su impacto esperado, como sigue:

**Major**\
Cambio significativo que afecta a un gran número de aplicaciones o que requiere una modificación sustancial del código.

**Minor**\
Un cambio que afecta a un pequeño número de aplicaciones o que requiere una leve modificación del código.

**Caso avanzado**\
Cambio que afecta a aplicaciones de escenarios muy concretos que no son frecuentes.

**Transparente**\
Cambio que no tiene ningún efecto apreciable en el programador o el usuario de la aplicación. No es necesario modificar la aplicación debido a este cambio.

## <a name="see-also"></a>Consulte también

- [Versiones y dependencias](versions-and-dependencies.md)
- [Novedades](../whats-new/index.md)
- [Lo obsoleto](../whats-new/whats-obsolete.md)
