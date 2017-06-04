---
title: "Exceptions in Managed Threads | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "unhandled exceptions,in managed threads"
  - "threading [.NET Framework],unhandled exceptions"
  - "threading [.NET Framework],exceptions in managed threads"
  - "managed threading"
ms.assetid: 11294769-2e89-43cb-890e-ad4ad79cfbee
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Exceptions in Managed Threads
A partir de .NET Framework versión 2.0, Common Language Runtime permite que la mayoría de las excepciones no controladas en subprocesos avancen naturalmente.  En la mayor parte de los casos, esto significa que la excepción no controlada hace que finalice la aplicación.  
  
> [!NOTE]
>  Este hecho supone un cambio significativo respecto a las versiones 1.0 y 1.1 de .NET Framework, que proporcionaban parada para muchas excepciones no controladas, por ejemplo, las excepciones no controladas en subprocesos ThreadPool.  Vea más adelante el apartado [Cambiar desde versiones anteriores](#ChangeFromPreviousVersions) de este tema.  
  
 Common Language Runtime proporciona parada para ciertas excepciones no controladas que se utilizan para controlar el flujo del programa:  
  
-   Se produce una excepción <xref:System.Threading.ThreadAbortException> en un subproceso porque se llamó a <xref:System.Threading.Thread.Abort%2A>.  
  
-   Se inicia una excepción <xref:System.AppDomainUnloadedException> en un subproceso porque se descarga el dominio de aplicación en el que se está ejecutando el subproceso.  
  
-   Common Language Runtime o un proceso del host finaliza el subproceso iniciando una excepción interna.  
  
 Si cualquiera de estas excepciones no se controlan en los subprocesos creados por Common Language Runtime, la excepción finaliza el subproceso, pero Common Language Runtime no permite que la excepción continúe posteriormente.  
  
 Si no se controlan estas excepciones en el subproceso principal o en subprocesos que entraron en el tiempo de ejecución desde código no administrado, continúan normalmente, lo que hace que finalice la aplicación.  
  
> [!NOTE]
>  Ahora el motor en tiempo de ejecución puede iniciar una excepción no controlada antes de que cualquier código administrado haya tenido oportunidad de instalar un controlador de excepciones.  Aunque el código administrado no tuviera ninguna oportunidad para controlar este tipo de excepción, la excepción puede continuar naturalmente.  
  
## Exponer problemas de subprocesamiento durante el desarrollo  
 Cuando se permite que los subprocesos tengan errores no indicados, sin finalizar la aplicación, los problemas de programación serios pueden quedar sin detectar.  Éste es un problema concreto para los servicios y otras aplicaciones que se ejecutan durante períodos prolongados.  Cuando se producen errores en los subprocesos, el estado del programa se va dañando gradualmente.  El rendimiento de la aplicación se puede degradar o la aplicación podría no responder.  
  
 Permitir que las excepciones no controladas en subprocesos continúen naturalmente, hasta que el sistema operativo finalice el programa, expone tales problemas durante las fases de desarrollo y pruebas.  Los informes de errores creados al cerrarse los programas ayudan en las tareas de depuración.  
  
<a name="ChangeFromPreviousVersions"></a>   
## Cambiar desde versiones anteriores  
 El cambio más significativo se refiere a los subprocesos administrados.  En las versiones 1.0 y 1.1 de .NET Framework, Common Language Runtime proporciona una parada para las excepciones no controladas en las situaciones siguientes:  
  
-   No hay una excepción no controlada en un subproceso ThreadPool.  Cuando una tarea inicia una excepción que no controla, el motor en tiempo de ejecución imprime el seguimiento de pila de excepción en la consola y luego devuelve el subproceso al grupo de subprocesos.  
  
-   No hay ninguna excepción no controlada en un subproceso creado con el método <xref:System.Threading.Thread.Start%2A> de la clase <xref:System.Threading.Thread>.  Cuando el código que se ejecuta en un subproceso así inicia una excepción que no controla, el motor en tiempo de ejecución imprime el seguimiento de pila de la excepción en la consola y luego finaliza el subproceso sin problemas.  
  
-   No hay ninguna excepción no controlada en el subproceso finalizador.  Cuando un subproceso finalizador inicia una excepción que no controla, el motor en tiempo de ejecución imprime el seguimiento de pila de excepción en la consola y luego devuelve el subproceso finalizador para reanudar los subprocesos finalizadores en ejecución.  
  
 El estado de primer plano o de segundo plano de un subproceso administrado no afecta a este comportamiento.  
  
 Para las excepciones no controladas en subprocesos que se originan en código no administrado, la diferencia es más sutil.  El cuadro de diálogo de asociación JIT en tiempo de ejecución se apropia del cuadro de diálogo de sistema operativo para excepciones administradas o excepciones nativas en subprocesos que han pasado por el código nativo.  El proceso finaliza en todos los casos.  
  
### Migrar código  
 En general, el cambio expondrá los problemas de programación previamente no reconocidos para que se puedan corregir.  En algunos casos, sin embargo, los programadores podrían haber aprovechado la parada en tiempo de ejecución para, por ejemplo, finalizar subprocesos.  Dependiendo de la situación, deberían plantearse una de las estrategias de migración siguientes:  
  
-   Reestructurar el código para que el subproceso finalice sin problemas cuando se recibe una señal.  
  
-   Utilizar el método <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> para anular el subproceso.  
  
-   Si se debe detener un subproceso para que pueda continuar la finalización de procesos, convierta el subproceso en un subproceso de segundo plano para que finalice automáticamente al salir del proceso.  
  
 En todos los casos, la estrategia debería seguir las instrucciones de diseño para las excepciones.  Vea [Instrucciones de diseño para excepciones](../../../docs/standard/design-guidelines/exceptions.md).  
  
### Marcador de compatibilidad de aplicaciones  
 Como una medida de compatibilidad temporal, los administradores pueden colocar un marcador de compatibilidad en la sección `<runtime>` del archivo de configuración de la aplicación.  Esto hace que Common Language Runtime revierta al comportamiento de las versiones 1.0 y 1.1.  
  
```  
<legacyUnhandledExceptionPolicy enabled="1"/>  
```  
  
## Reemplazo de host  
 En la versión 2.0 de .NET Framework, un host no administrado puede utilizar la interfaz [ICLRPolicyManager](../../../ocs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) de la API de hospedaje para invalidar la directiva predeterminada de excepciones no controladas de Common Language Runtime.  La función [ICLRPolicyManager::SetUnhandledExceptionPolicy](../Topic/ICLRPolicyManager::SetUnhandledExceptionPolicy%20Method.md) se utiliza para establecer la directiva para las excepciones no controladas.  
  
## Vea también  
 [Managed Threading Basics](../../../docs/standard/threading/managed-threading-basics.md)