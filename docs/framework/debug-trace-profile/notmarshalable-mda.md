---
title: MDA de notMarshalable
description: Revise el Asistente para la depuración administrada de notMarshalable, que puede activar si las llamadas no se realizan en el contexto incorrecto para los punteros de interfaz COM.
ms.date: 03/30/2017
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
ms.openlocfilehash: b464d914a8d83504daaf4cb276914da7798262dc
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803799"
---
# <a name="notmarshalable-mda"></a>MDA de notMarshalable
El asistente para la depuración administrada (MDA) `notMarshalable` se activa cuando Common Language Runtime (CLR) encuentra un puntero a interfaz COM sin un servidor proxy/código auxiliar válido registrado o una implementación de interfaz `IMarshal` incorrecta al intentar serializar la interfaz entre contextos.  
  
## <a name="symptoms"></a>Síntomas  
 No se da servicio a las llamadas o las llamadas se producen en un contexto incorrecto para los punteros a interfaz COM.  
  
## <a name="cause"></a>Causa  
 No hay ningún servidor proxy/código auxiliar registrado válido o `IMarshal` incorrecta intentando serializar la interfaz entre los contextos.  
  
## <a name="resolution"></a>Resolución  
 Asegúrese de que tiene registrado un código auxiliar de servidor proxy y de que la implementación de `IMarshal` es válida.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el tiempo de ejecución.  
  
## <a name="output"></a>Output  
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

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnóstico de errores con asistentes de depuraciones administradas](diagnosing-errors-with-managed-debugging-assistants.md)
- [Serialización de interoperabilidad](../interop/interop-marshaling.md)
