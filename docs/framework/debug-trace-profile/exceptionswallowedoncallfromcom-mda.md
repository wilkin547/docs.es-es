---
title: MDA de exceptionSwallowedOnCallFromCom
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, informational
- informational messages
- managed debugging assistants (MDAs), exceptions
- exception handling, managed debugging assistants
- MDAs (managed debugging assistants), exceptions
- ExceptionSwallowedOnCallFromCOM MDA
ms.assetid: 55d6ab12-f251-4aab-aa64-aacbe9d9f974
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d68e3f8659b0d5fe212c58443fe9a8b42f9cef89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="exceptionswallowedoncallfromcom-mda"></a>MDA de exceptionSwallowedOnCallFromCom
El asistente para la depuración administrada (MDA, por sus siglas en inglés) `exceptionSwallowedOnCallFromCOM` se activa cuando se produce una excepción del código de Common Language Runtime (CLR) llamado desde COM a través de un método que no tiene un tipo de resultado HRESULT sin administrar.  
  
## <a name="symptoms"></a>Síntomas  
 Una llamada de COM a un componente administrado devuelve un valor FALSE o 0. También puede ser que, si el método tiene un tipo de valor devuelto void, no haya indicación de que se produjese una excepción durante la ejecución del método. En este caso, la excepción se detectará de forma silenciosa y la ejecución regresará al emisor de la llamada COM.  
  
## <a name="cause"></a>Motivo  
 Se produjo una excepción, pero no hay ningún modo válido de notificarla.  
  
## <a name="resolution"></a>Solución  
 Solo tiene carácter informativo, no es necesariamente indicativo de un error.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR. Solo recoge los datos sobre excepciones detectadas de forma silenciosa.  
  
## <a name="output"></a>Salida  
 Mensaje informativo que contiene el nombre del método, el nombre del tipo y el mensaje de la excepción.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <exceptionSwallowedOnCallFromCom />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Serialización para interoperabilidad](../../../docs/framework/interop/interop-marshaling.md)
