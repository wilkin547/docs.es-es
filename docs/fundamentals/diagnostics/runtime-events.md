---
title: Eventos en tiempo de ejecución
description: Revise los eventos de diagnóstico emitidos por el tiempo de ejecución de .NET (CoreCLR) que se pueden usar con ETW, LTTng o EventPipe.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- runtime events (CoreCLR)
- ETW, EventPipe runtime events (CoreCLR)
ms.openlocfilehash: 33fa7275ce40934ce043b4d0dba5749c37515755
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594705"
---
# <a name="net-runtime-events"></a>Eventos de tiempo de ejecución de .NET

El entorno de tiempo de ejecución de .NET (CoreCLR) emite varios eventos que se pueden usar para diagnosticar problemas con la aplicación .NET que se pueden consumir a través de varios mecanismos como `ETW` , `LTTng` y `EventPipe` .

Este documento sirve como referencia en los eventos desencadenados por el tiempo de ejecución de .NET Core.

Para eventos en tiempo de ejecución en .NET Framework, vea [eventos ETW de CLR](../../framework/performance/clr-etw-events.md).

## <a name="in-this-section"></a>En esta sección

[Eventos de contención](runtime-contention-events.md)\
Estos eventos recopilan información acerca de las contenciones de bloqueo de monitor.

[Eventos de recolección de elementos no utilizados](runtime-garbage-collection-events.md)\
Estos eventos recopilan información sobre la recolección de elementos no utilizados. Ayudan en el diagnóstico y la depuración, incluida la determinación de cuántas veces se realizó la recolección de elementos no utilizados, cuánta memoria se liberó durante la recolección de elementos no utilizados, etc.

[Eventos de excepción](runtime-exception-events.md)\
Estos eventos en tiempo de ejecución capturan información sobre las excepciones que se producen.

[Eventos de interoperabilidad](runtime-interop-events.md)\
Estos eventos en tiempo de ejecución capturan información sobre la generación de código auxiliar del lenguaje intermedio común (CIL).

[Eventos de cargador y enlazador](runtime-loader-binder-events.md)\
Estos eventos recopilan información relacionada con la carga y descarga de ensamblados y módulos.

[Eventos de método](runtime-method-events.md)\
Estos eventos recopilan información que es específica de los métodos. La carga de estos eventos es necesaria para la resolución de símbolos. Además, estos eventos proporcionan información útil como el número de veces que se llama a un método.

[Eventos de subproceso](runtime-thread-events.md)\
Estos eventos recopilan información sobre los subprocesos de E/S y de trabajo.

[Eventos de tipo](runtime-type-events.md)\
Estos eventos recopilan información sobre el sistema de tipos.
