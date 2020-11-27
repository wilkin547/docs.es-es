---
title: MDA de reportAVOnComRelease
description: Revise el Asistente para la depuración administrada (MDA) de reportAvOnComRelease, que puede activarse debido a infracciones de acceso y a daños en la memoria en .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), reference counting errors
- exceptions, reference counting errors
- ReportAvOnComRelease MDA
- COM release access violations
- user reference counting errors
- managed debugging assistants (MDAs), reference counting errors
- report access violation on Com release
- reference counting errors
ms.assetid: a2b86b63-08b2-4943-b344-3c2cf46ccd31
ms.openlocfilehash: c5047aa4005cdaa9ae6aabe8dcd7ee838ee13f58
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267122"
---
# <a name="reportavoncomrelease-mda"></a>MDA de reportAVOnComRelease

El asistente para la depuración administrada (MDA, por sus siglas en inglés) `reportAvOnComRelease` se activa cuando se producen excepciones que se deben a errores de recuento de referencias de usuario mientras se realiza la interoperabilidad COM y se usan los métodos <xref:System.Runtime.InteropServices.Marshal.Release%2A> o <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> en combinación con llamadas COM sin formato.  
  
## <a name="symptoms"></a>Síntomas  

 Infracciones de acceso y deterioro de la memoria.  
  
## <a name="cause"></a>Causa  

 En ocasiones, se produce una excepción debido a errores de recuento de referencias de usuario mientras se realiza la interoperabilidad COM y se usan los métodos <xref:System.Runtime.InteropServices.Marshal.Release%2A> o <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> en combinación con llamadas COM sin formato. Normalmente, esta excepción se descarta porque, de lo contrario, se produciría una infracción de acceso en el CLR y la caída del mismo. Cuando se habilita el asistente, esas excepciones se pueden detectar y notificar en vez de simplemente descartarlas.  
  
## <a name="resolution"></a>Solución  

 Examine el código de recuento de referencias, busque errores y examine los clientes nativos de su objeto para comprobar si existen errores de recuento de referencias.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  

 Hay dos modos disponibles. Si el atributo `allowAv` es `true`, el asistente evita que el runtime descarte la infracción de acceso. Si `allowAv` es `false` —que es el valor predeterminado—, el runtime descarta la infracción de acceso, pero el usuario recibe un mensaje de advertencia donde se le indica que se produjo una excepción y se descartó.  
  
## <a name="output"></a>Resultados  

 Si es posible, el resultado contiene la vtable original del puntero de interfaz COM. De lo contrario, aparece un mensaje con información.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [Diagnóstico de errores con asistentes de depuraciones administradas](diagnosing-errors-with-managed-debugging-assistants.md)
- [Serialización de interoperabilidad](../interop/interop-marshaling.md)
