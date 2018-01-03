---
title: MDA de contextSwitchDeadlock
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deadlocks [.NET Framework]
- pumping messages
- STA message pumping
- single-threaded COM components
- MDAs (managed debugging assistants), context switching deadlocks
- managed debugging assistants (MDAs), context switching deadlocks
- ContextSwitchDeadlock MDA
- message pumping
- context switching deadlocks
ms.assetid: 26dfaa15-9ddb-4b0a-b6da-999bba664fa6
caps.latest.revision: "22"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 816afbae0cca18de24c11152541a509b54c119b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="contextswitchdeadlock-mda"></a>MDA de contextSwitchDeadlock
El asistente para la depuración administrada (MDA, por sus siglas en inglés) `contextSwitchDeadlock` se activa cuando se detecta un interbloqueo durante un intento de transición de contexto COM.  
  
## <a name="symptoms"></a>Síntomas  
 El síntoma más común es que no se devuelve una llamada en un componente COM sin administrar de código administrado.  Otro síntoma es el aumento de uso de memoria con el tiempo.  
  
## <a name="cause"></a>Motivo  
 La causa más probable es que haya un subproceso de contenedor uniproceso (STA, por sus siglas en inglés) que no esté suministrando mensajes. El subproceso de STA está en espera sin suministrar mensajes o está realizando operaciones extensas y no permite que la cola de mensajes se suministre.  
  
 El incremento en el uso de memoria con el tiempo está causado por el subproceso de finalizador que intenta llamar a `Release` en un componente COM sin administrar y que ese componente no devuelve.  Esto impide que el finalizador pueda recuperar otros objetos.  
  
 De forma predeterminada, STA es el modelo de subprocesos del subproceso principal de aplicaciones de consola de Visual Basic. Este MDA se activa si un subproceso de STA usa la interoperabilidad de COM directa o indirectamente mediante Common Language Runtime o un control de terceros.  Para evitar la activación de este MDA en una aplicación de consola de Visual Basic, aplique el atributo <xref:System.MTAThreadAttribute> al método principal o modifique la aplicación para que suministre mensajes.  
  
 Es posible que el MDA se active equivocadamente si se cumplen todas las condiciones siguientes:  
  
-   Una aplicación crea componentes COM a partir de subprocesos de STA directa o indirectamente a través de bibliotecas.  
  
-   La aplicación se detuvo en el depurador y el usuario continuó con la aplicación o realizó una operación de paso.  
  
-   La depuración sin administrar no está habilitada.  
  
 Para determinar si el MDA se activa equivocadamente, deshabilite todos los puntos de interrupción, reinicie la aplicación y deje que se ejecute sin detenerla. Si el MDA no se activa, es probable que la activación inicial fuese falsa. En este caso, deshabilite el MDA para evitar interferencias con la sesión de depuración.  
  
> [!NOTE]
>  Este MDA está incluido de forma predeterminada en [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] y en versiones posteriores. Cuando el proceso de hospedaje está habilitado en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], no se pueden deshabilitar los MDA que vienen incluidos de serie. De forma predeterminada, el proceso de hospedaje está habilitado, por lo que debe deshabilitarse explícitamente. Para más información sobre cómo deshabilitar MDA, vea "Enabling and Disabling MDAs (Habilitar y deshabilitar MDA)" en [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).  
  
## <a name="resolution"></a>Resolución  
 Siga las reglas COM respecto al suministro de mensajes de STA.  
  
## <a name="effect-on-the-runtime"></a>Efecto en el Runtime  
 Este MDA no tiene ningún efecto en el CLR. Solo recoge datos sobre contextos COM.  
  
## <a name="output"></a>Salida  
 Mensaje que describe el contexto actual y el de destino.  
  
## <a name="configuration"></a>Configuración  
  
```xml  
<mdaConfig>  
  <assistants>  
    <contextSwitchDeadlock />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Serialización de interoperabilidad](../../../docs/framework/interop/interop-marshaling.md)
