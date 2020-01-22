---
title: Excepciones en subprocesos administrados
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- unhandled exceptions,in managed threads
- threading [.NET Framework],unhandled exceptions
- threading [.NET Framework],exceptions in managed threads
- managed threading
ms.assetid: 11294769-2e89-43cb-890e-ad4ad79cfbee
ms.openlocfilehash: 2c3215fd42e8cf6d6427d23f94c14db4230ddd02
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138063"
---
# <a name="exceptions-in-managed-threads"></a>Excepciones en subprocesos administrados
A partir de .NET Framework versión 2.0, Common Language Runtime permite que la mayoría de las excepciones no controladas en subprocesos continúen naturalmente. En la mayoría de los casos, esto implica que la excepción no controlada provoque la finalización de la aplicación.  
  
> [!NOTE]
> Se trata de un cambio significativo con respecto a las versiones 1.0 y 1.1 de .NET Framework, que ofrecen un mecanismo de seguridad para muchas excepciones no controladas; por ejemplo, excepciones no controladas en subprocesos de grupo. Vea [Cambio con respecto a las versiones anteriores](#ChangeFromPreviousVersions) más adelante en este tema.  
  
 Common Language Runtime ofrece un mecanismo de seguridad para determinadas excepciones no controladas que se usan para controlar el flujo del programa:  
  
- Se genera <xref:System.Threading.ThreadAbortException> en un subproceso, porque se llamó a <xref:System.Threading.Thread.Abort%2A>.  
  
- Se inicia <xref:System.AppDomainUnloadedException> en un subproceso porque el dominio de aplicación donde se ejecuta el subproceso se está descargando.  
  
- Common Language Runtime o un proceso de host finalizan el subproceso iniciando una excepción interna.  
  
 Si alguna de estas excepciones no se controla en subprocesos que Common Language Runtime crea, la excepción finaliza el subproceso, pero Common Language Runtime no permite la excepción continúe.  
  
 Si no se controlan en el subproceso principal o en subprocesos que especifiquen el runtime desde código no administrado, estas excepciones continúan normalmente, lo que se traduce en la finalización de la aplicación.  
  
> [!NOTE]
> Es posible que el runtime inicie una excepción no controlada antes de que un código administrado haya tenido ocasión de instalar un controlador de excepciones. Aunque el código administrado no tuviera ninguna oportunidad de controlar la excepción, esta puede continuar normalmente.  
  
## <a name="exposing-threading-problems-during-development"></a>Exponer problemas de subprocesamiento durante el desarrollo  
 Cuando se permite que los subprocesos se interrumpan silenciosamente, sin finalizar la aplicación, graves problemas de programación pueden pasar inadvertidos. Se trata de un problema concreto de servicios y otras aplicaciones que se ejecutan durante períodos prolongados. A medida que los subprocesos dejan de ejecutarse, el estado del programa se daña gradualmente. Puede que el rendimiento de la aplicación se degrade o que la aplicación deje de responder.  
  
 Si se permite que las excepciones no controladas en subprocesos continúen naturalmente hasta que el sistema operativo finalice el programa, estos problemas se exponen durante el desarrollo y pruebas. Los informes de errores en la finalización de programas admiten la depuración.  
  
<a name="ChangeFromPreviousVersions"></a>   
## <a name="change-from-previous-versions"></a>Cambio con respecto a las versiones anteriores  
 El cambio más significativo está relacionado con los subprocesos administrados. En las versiones 1.0 y 1.1 de .NET Framework, Common Language Runtime ofrece un mecanismo de seguridad para las excepciones no controladas en las situaciones siguientes:  
  
- No hay ninguna excepción no controlada en un subproceso de grupo. Cuando una tarea inicia una excepción que no controla, el runtime imprime el seguimiento de la pila de excepciones en la consola y luego devuelve el subproceso al grupo de subprocesos.  
  
- Esto no se produce como una excepción no controlada en un subproceso creado con el método <xref:System.Threading.Thread.Start%2A> de la clase <xref:System.Threading.Thread>. Cuando un código que se ejecuta en ese tipo de subproceso inicia una excepción que no controla, el runtime imprime el seguimiento de la pila de excepciones en la consola y luego finaliza correctamente el subproceso.  
  
- No hay ninguna excepción no controlada en un subproceso el subproceso del finalizador. Cuando un finalizador inicia una excepción que no controla, el runtime imprime el seguimiento de la pila de excepciones en la consola y luego permite que el subproceso de finalizador reanude la ejecución de finalizadores.  
  
 El estado en primer plano o en segundo plano de un subproceso administrado no afecta a este comportamiento.  
  
 En el caso de excepciones no controladas en subprocesos que se originan en código no administrado, la diferencia es más sutil. El cuadro de diálogo de adjuntos JIT del runtime -se adelanta al cuadro de diálogo del sistema operativo en el caso de excepciones no controladas en subprocesos que han pasado por código nativo. El proceso finaliza siempre.  
  
### <a name="migrating-code"></a>Migrar código  
 En general, el cambio expondrá problemas de programación anteriormente no reconocidos para que se puedan corregir. Pero, en algunos casos, los programadores podrían haber aprovechado el mecanismo de seguridad de runtime; por ejemplo, para finalizar subprocesos. Según la situación, deben plantearse una de las estrategias de migración siguientes:  
  
- Reestructurar el código para que el subproceso salga correctamente cuando se reciba una señal.  
  
- Use el método <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> para anular el subproceso.  
  
- Si es preciso detener un subproceso para que la finalización del proceso pueda continuar, convierta el subproceso en un subproceso en segundo plano para que finalice automáticamente al salir del proceso.  
  
 En todos los casos, la estrategia debe seguir las instrucciones de diseño de excepciones. Vea [Instrucciones de diseño de excepciones](../../../docs/standard/design-guidelines/exceptions.md).  
  
### <a name="application-compatibility-flag"></a>Marca de compatibilidad de aplicaciones  
 Como medida temporal de compatibilidad, los administradores pueden colocar una marca de compatibilidad en la sección `<runtime>` del archivo de configuración de la aplicación. De ese modo, Common Language Runtime revierte al comportamiento de las versiones 1.0 y 1.1.  
  
```xml  
<legacyUnhandledExceptionPolicy enabled="1"/>  
```  
  
## <a name="host-override"></a>Invalidación de host  
 En la versión 2.0 de .NET Framework, un host no administrado puede usar la interfaz [ICLRPolicyManager](../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) de la API de hospedaje para invalidar la directiva de excepciones no controladas predeterminada de Common Language Runtime. Se usa la función [ICLRPolicyManager::SetUnhandledExceptionPolicy](../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md) para establecer la directiva de excepciones no controladas.  
  
## <a name="see-also"></a>Vea también

- [Principios básicos del subprocesamiento administrado](../../../docs/standard/threading/managed-threading-basics.md)
