---
title: Eventos ETW de supervisión de recursos de dominio de aplicación (ARM)
description: Lea acerca de los eventos ETW de supervisión de recursos del dominio de aplicación (ARM) en .NET, como ThreadCreated (, AppDomainMemAllocated, AppDomainMemSurvived, etc.
ms.date: 03/30/2017
helpviewer_keywords:
- ETW, application domain monitoring events
- application domain monitoring events [.NET Framework]
ms.assetid: d38ff268-a2ee-434e-b504-d570880e0289
ms.openlocfilehash: d118b3196b019a804df5399464cb86f7492c61b0
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309786"
---
# <a name="application-domain-resource-monitoring-arm-etw-events"></a>Eventos ETW de supervisión de recursos de dominio de aplicación (ARM)

Estos eventos proporcionan información de diagnóstico detallada sobre el estado de un dominio de aplicación. Puede utilizar estos eventos o la característica de supervisión de recursos del dominio de aplicación (ARM) para obtener la misma información.

## <a name="threadcreated-event"></a>Evento ThreadCreated

Este evento también se genera con el proveedor de informe detallado como `ThreadDC` (con la palabra clave `AppDomainResourceManagementRundownKeyword` ). Es el único evento que se provoca con el proveedor de informe detallado en esta categoría.

En la tabla siguiente se muestra la palabra clave y el nivel. Para obtener más información, vea [palabras clave y niveles ETW de CLR](clr-etw-keywords-and-levels.md).

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`AppDomainResourceManagementKeyword` (0 x 800)|Informativo (4)|
|`ThreadingKeyword` (0x10000)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`ThreadCreated`|85|Se crea un subproceso para el dominio de aplicación.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|ThreadID|win:UInt64|Se creó el identificador del subproceso.|
|AppDomainID|win:UInt64|Identificador del dominio de la aplicación para el que se notifica la actividad de subproceso.|
|Marcas|win:UInt32|Marcas de creación de subproceso.|
|ManagedThreadIndex|win:UInt32|Se creó el índice administrado del subproceso.|
|OSThreadID|win:UInt32|Se creó el identificador del sistema operativo del subproceso.|
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="appdomainmemallocated-event"></a>Evento AppDomainMemAllocated

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`AppDomainResourceManagementKeyword` (0 x 800)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`AppDomainMemAllocated`|83|Cada vez que se asignan 4 MB de memoria (aproximadamente) en el dominio de aplicación.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|AppDomainID|win:UInt64|Identificador del dominio de la aplicación para el que se notifica el uso de recursos.|
|Allocated|win:UInt64|Número total de bytes asignado en este dominio de aplicación desde que se creó el dominio de aplicación (sin restar la cantidad de memoria liberada).|
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="appdomainmemsurvived-event"></a>Evento AppDomainMemSurvived

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`AppDomainResourceManagementKeyword` (0 x 800)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`AppDomainMemSurvived`|84|Fnalizadas todas las recolecciones de elementos no utilizados.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|AppDomainID|win:UInt64|Identificador del dominio para el que recurso que se notifica el uso de recursos.|
|Survived|win:UInt64|Número de bytes que sobrevivieron después de la última recolección de elementos no utilizados que se sabe que están contenidos en este dominio de aplicación. Este número es preciso y completo después de una recolección completa, pero puede estar incompleto después de una recolección efímera.|
|ProcessSurvived|win:UInt64|Bytes totales que sobrevivieron de la última recolección. Después de una recolección completa, este número representa el número de bytes que se mantienen activos en montones administrados. Después de una recolección efímera, este número representa el número de bytes que se mantienen activos en generaciones efímeras.|
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="threadappdomainenter-event"></a>Evento ThreadAppDomainEnter

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`AppDomainResourceManagementKeyword` (0 x 800)|Informativo (4)|
|`ThreadingKeyword` (0x10000)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`ThreadAppDomainEnter`|87|Un subproceso entra en un dominio de aplicación.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|ThreadID|win:UInt64|Identificador de subproceso.|
|AppDomainID|win:UInt64|Identificador del dominio de la aplicación.|
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="threadterminated-event"></a>Evento ThreadTerminated

En la tabla siguiente se muestra la palabra clave y el nivel.

|Palabra clave para generar el evento|Nivel|
|-----------------------------------|-----------|
|`AppDomainResourceManagementKeyword` (0 x 800)|Informativo (4)|
|`ThreadingKeyword` (0x10000)|Informativo (4)|

En la siguiente tabla se muestra la información del evento.

|Evento|Id. de evento|Se genera cuando|
|-----------|--------------|-----------------|
|`ThreadTerminated`|86|Finaliza un subproceso.|

En la siguiente tabla, se muestran los datos del evento:

|Nombre del campo|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|ThreadID|win:UInt64|Identificador de subproceso.|
|AppDomainID|win:UInt64|Identificador del dominio de la aplicación.|
|ClrInstanceID|win:UInt16|Identificador único para la instancia de CLR o CoreCLR.|

## <a name="see-also"></a>Consulte también

- [CLR ETW Events (Eventos ETW de CLR)](clr-etw-events.md)
