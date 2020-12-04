---
title: Eventos de tiempo de ejecución del sistema de tipos
description: Vea eventos de tiempo de ejecución de .NET que recopilan información de diagnóstico específica del sistema de tipos .NET, como TypeLoadStart y TypeLoadStop.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- type system events (CoreCLR)
- ETW, EventPipe, LTTng type system events (CoreCLR)
ms.openlocfilehash: 8eee89cddb0098da2cb449a4be21945adac725e3
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "96594701"
---
# <a name="net-runtime-type-events"></a>Eventos de tipo en tiempo de ejecución .NET

Estos eventos recopilan información relacionada con la carga de tipos. Para obtener más información sobre cómo usar estos eventos con fines de diagnóstico, consulte [registro y seguimiento de aplicaciones .net](../../core/diagnostics/logging-tracing.md)

## <a name="typeloadstart-event"></a>Evento TypeLoadStart

|Palabra clave para generar el evento|Evento|Nivel|  
|-----------------------------------|-----------|-----------|  
|`TypeDiagnosticKeyword` (0x8000000000)|Informativo (4)|  

|Evento|Id. de evento|Descripción|  
|-----------|--------------|-----------------|  
|`TypeLoadStart`|73|Se ha iniciado una carga de tipos.|

|Nombre del campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|`TypeLoadStartID`|`win:UInt32`|IDENTIFICADOR de la operación de carga de tipo.|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|  

## <a name="typeloadstop-event"></a>Evento TypeLoadStop

|Palabra clave para generar el evento|Nivel|  
|-----------------------------------|-----------|-----------|  
|`TypeDiagnosticKeyword` (0x8000000000)|Informativo (4)|  

|Evento|Id. de evento|Descripción|  
|-----------|--------------|-----------------|  
|`TypeLoadStop`|74|Se ha completado una carga de tipos.|

|Nombre del campo|Tipo de datos|Descripción|  
|----------------|---------------|-----------------|  
|`TypeLoadStartID`|`win:UInt32`|IDENTIFICADOR de la operación de carga de tipo (coincide con el TypeLoadStartID del evento TypeLoadStart correspondiente).|
|`LoadLevel`|`win:UInt16`|Nivel de carga de tipo.|
|`TypeID`|`win:UInt64`|Puntero al identificador de tipo.|
|`TypeName`|`win:UnicodeString`|Nombre del tipo.|
|`ClrInstanceID`|`win:UInt16`|Identificador único para la instancia de CLR o CoreCLR.|  
