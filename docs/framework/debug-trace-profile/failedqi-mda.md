---
title: MDA de failedQI
description: Revise el Asistente para la depuración administrada (MDA) de failedQI en .NET, que se puede activar cuando se produce un error en una conversión on o en una llamada COM desde un contenedor RCW (Runtime Callable wrapper).
ms.date: 03/30/2017
helpviewer_keywords:
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
ms.openlocfilehash: 2d7f14c67d47e58bcb88eab4621df63d7c598a7a
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415945"
---
# <a name="failedqi-mda"></a>MDA de failedQI
El asistente para la depuración administrada (MDA) `failedQI` se activa cuando Runtime llama a `QueryInterface` en un puntero de interfaz COM en nombre de un contenedor al que se puede llamar en tiempo de ejecución (RCW) y la llamada `QueryInterface` falla.  
  
## <a name="symptoms"></a>Síntomas  
 No se puede realizar una conversión en un contenedor RCW o se produce un error inesperado en una llamada a COM desde un contenedor RCW  
  
## <a name="cause"></a>Causa  
  
- La llamada se realiza desde el contexto equivocado.  
  
- El servidor proxy registrado no puede realizar la llamada `QueryInterface` porque se intentó realizar en el contexto equivocado.  
  
- Un servidor proxy propiedad de OLE devolvió un valor HRESULT de error.   
  
## <a name="resolution"></a>Solución  
 Consulte la documentación sobre reglas COM recogida en el sitio de MSDN.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Si no se puede realizar la llamada `QueryInterface`, el contexto cambia y es necesario volver a intentar realizar la llamada `QueryInterface` para ver si el motivo del error era un contexto incorrecto.  
  
## <a name="output"></a>Output  
 El nombre administrado de la interfaz, el GUID de la interfaz y el valor HRESULT del error.   
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnóstico de errores con asistentes de depuraciones administradas](diagnosing-errors-with-managed-debugging-assistants.md)
- [Serialización de interoperabilidad](../interop/interop-marshaling.md)
