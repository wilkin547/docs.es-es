---
title: MDA de notMarshalable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed debugging assistants (MDAs), interface pointer not marshalable
- interface pointer not marshalable MDA
- MDAs (managed debugging assistants), interface pointer not marshalable
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- marshalable interface pointers
- MDAs (managed debugging assistants), marshaling
- notMarshalable MDA
ms.assetid: 96e7b2c1-843f-4d64-b519-740c3a18b50a
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c5de75130acab30c4f73522728c00b69c1c3e8d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="notmarshalable-mda"></a>MDA de notMarshalable
El asistente para la depuración administrada (MDA) `notMarshalable` se activa cuando Common Language Runtime (CLR) encuentra un puntero a interfaz COM sin un servidor proxy/código auxiliar válido registrado o una implementación de interfaz `IMarshal` incorrecta al intentar calcular las referencias de la interfaz entre contextos.  
  
## <a name="symptoms"></a>Síntomas  
 No se da servicio a las llamadas o las llamadas se producen en un contexto incorrecto para los punteros a interfaz COM.  
  
## <a name="cause"></a>Motivo  
 No hay ningún servidor proxy/código auxiliar registrado válido o `IMarshal` incorrecta intentando calcular las referencias de la interfaz entre los contextos.  
  
## <a name="resolution"></a>Resolución  
 Asegúrese de que tiene registrado un código auxiliar de servidor proxy y de que la implementación de `IMarshal` es válida.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el tiempo de ejecución.  
  
## <a name="output"></a>Resultado  
 Un mensaje que describe el problema.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <notMarshalable/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Serialización para interoperabilidad](../../../docs/framework/interop/interop-marshaling.md)
