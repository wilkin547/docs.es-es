---
title: Elección de la versión adecuada de .NET Core
description: ¿Cómo se debe determinar la versión de .NET Core a la que se va a dirigir?
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 401eead986ee8b67ed15be609d0b5d228773312d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "102401525"
---
# <a name="choose-the-right-net-core-version"></a>Elección de la versión adecuada de .NET Core

La mayor consideración para la mayoría de las organizaciones al elegir una versión de .NET Core como destino es el ciclo de vida de soporte técnico. Las versiones de soporte a largo plazo (LTS) se distribuyen con menos frecuencia pero tienen una ventana de soporte más larga que las versiones actuales (no LTS). Actualmente, las versiones de LTS están programadas para distribuirse cada dos años. Los clientes pueden elegir las versiones de destino y pueden instalar diferentes versiones de .NET Core en paralelo en el mismo equipo. Las versiones de LTS recibirán solo correcciones críticas y compatibles a lo largo de su ciclo de vida. Las versiones actuales recibirán estas mismas correcciones y también se actualizarán con las innovaciones y características compatibles. Las versiones de LTS se admiten durante tres años después de la versión inicial. Las versiones actuales se admiten durante tres meses después de la versión actual o LTS posterior.

La mayoría de los clientes que desean migrar una aplicación de gran .NET Framework a .NET Core actualmente están buscando un destino estable, dado que aún no han realizado el cambio a una versión anterior de .NET Core. En este caso, la mejor versión de .NET Core como destino para la migración es .NET Core 3,1, que es la versión actual de LTS. La compatibilidad con .NET Core 3,1 finaliza en diciembre de 2022. La siguiente versión de LTS planeada será .NET 6,0, que se enviará a la entrega en noviembre de 2021.

La actualización de .NET Core 3,1 a .NET 5,0 (la versión siguiente) requiere mucho menos esfuerzo que migrar desde .NET Framework a .NET Core. Por esta razón, la recomendación para la mayoría de los clientes es actualizar primero a .NET Core 3,1. Después, decida si la siguiente actualización debe ser la última versión actual (.NET 5,0) o esperar a la próxima versión de LTS (.NET 6,0) antes de actualizar.

En este libro se supone .NET Framework aplicaciones se actualizarán a .NET Core 3,1.

## <a name="references"></a>Referencias

[Directiva de compatibilidad de .net Core y .NET 5](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)

>[!div class="step-by-step"]
>[Anterior](migrate-aspnet-core-2-1.md)
>[Siguiente](incremental-migration-strategies.md)
