---
title: Compatibilidad de .NET Core
description: Más información sobre las diferentes compatibilidades de la serie de la versión (LTS y Actual) para .NET Core
author: kendrahavens
ms.author: mairaw
ms.date: 01/30/2017
ms.openlocfilehash: b61aa48451cee60be4968c151b97746a3aef85c0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="net-core-support"></a>Compatibilidad de .NET Core

Se trata de una descripción general de la compatibilidad de .NET Core.

## <a name="lts-and-current-release-trains"></a>LTS y series de las versiones actuales

Tener dos series de la versión de compatibilidad es un concepto común en uso en todo el mundo de software, especialmente para los proyectos de código abierto como .NET Core. .NET Core cuenta con las siguientes series de las versiones de compatibilidad: [Compatibilidad a largo plazo (LTS)](https://en.wikipedia.org/wiki/Long-term_support) y Actual. Las versiones LTS se mantienen por estabilidad durante su ciclo de vida, y reciben las revisiones de problemas importantes y revisiones de seguridad. El nuevo trabajo de la característica y las revisiones de errores adicionales tienen lugar en las versiones actuales. Desde una perspectiva de soporte técnico, estas series de la versión tienen los siguientes atributos de ciclo de vida de soporte técnico.

Las versiones LTS
* Se admiten durante tres años después de la fecha de disponibilidad general de una versión LTS.
* O un año después de la disponibilidad general de una versión posterior de LTS.

Las versiones actuales
* Se admiten dentro de la misma ventana de tres años que la versión principal de LTS.
* Se admiten durante tres meses después de la disponibilidad general de una versión posterior actual.
* Y un año después de la disponibilidad general de una versión posterior de LTS.

## <a name="versioning"></a>Control de versiones
Las nuevas versiones LTS están marcadas con un aumento en el número de versión principal. Las versiones actuales tienen el mismo número de versión principal que la serie LTS correspondiente y se marcan con un aumento en el número de versión secundaria. Por ejemplo, 1.0.3 sería LTS y 1.1.0 sería Actual. La corrección de errores se actualiza para cada incremento de la serie de la versión de revisión. Para más información sobre el esquema de control de versiones, consulte [Control de versiones de .NET Core](index.md).

## <a name="what-causes-updates-in-lts-and-current-trains"></a>¿Qué causa las actualizaciones en las series LTS y Actual?
Para comprender qué cambios específicos, como correcciones de errores o la adición de API, provocan actualizaciones en los números de versión, revise la sección del árbol de decisión en la [documentación de control de versiones](index.md). No hay ningún conjunto de reglas de oro que deciden qué cambios se extraen de Actual a la rama LTS. Normalmente, las actualizaciones de seguridad y las revisiones necesarias para corregir el comportamiento esperado son motivos para actualizar la rama LTS. También tenemos previsto admitir sistemas operativos del desarrollador de escritorio recientes en la rama LTS, aunque esto no siempre es posible. Una buena manera para ponerse al día sobre las API, correcciones y sistemas operativos admitidos en determinadas versiones es examinar las [notas de la versión](https://github.com/dotnet/core/tree/master/release-notes) correspondientes en GitHub.

### <a name="further-reading"></a>Información adicional
* [Hoja de información sobre el ciclo de vida de compatibilidad de .NET Core](https://www.microsoft.com/net/core/support)
* [Sistemas operativos y versiones compatibles actualmente](https://github.com/dotnet/core/blob/master/roadmap.md)
