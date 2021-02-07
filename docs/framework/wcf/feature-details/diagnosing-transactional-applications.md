---
description: Más información acerca de cómo diagnosticar aplicaciones transaccionales
title: Diagnóstico de aplicaciones transaccionales
ms.date: 03/30/2017
ms.assetid: 4a993492-1088-4d10-871b-0c09916af05f
ms.openlocfilehash: 4b80dd5273781feaad0ef1c964c737a1cd470c75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756453"
---
# <a name="diagnosing-transactional-applications"></a>Diagnóstico de aplicaciones transaccionales

En este tema se describe cómo usar la característica de diagnóstico y administración de Windows Communication Foundation (WCF) para solucionar problemas de una aplicación transaccional.  
  
## <a name="performance-counters"></a>Contadores de rendimiento  

 WCF proporciona un conjunto estándar de contadores de rendimiento para medir el rendimiento de la aplicación transaccional. Para más información, consulte [Performance Counters](../diagnostics/performance-counters/index.md).  
  
 Los contadores de rendimiento tienen tres niveles de alcance diferentes: servicio, punto de conexión y operación, tal y como se describe en las tablas siguientes.  
  
### <a name="service-performance-counters"></a>Contadores de rendimiento de los servicios  
  
|Contador de rendimiento|Descripción|  
|-------------------------|-----------------|  
|Flujo de transacciones|Número de transacciones que fluyen a las operaciones de este servicio. Este contador se incrementa siempre que se encuentra una transacción en el mensaje enviado al servicio.|  
|Flujo de transacciones por segundo|El número de transacciones que fluyeron a las operaciones en este servicio en cada segundo. Este contador se incrementa siempre que se encuentra una transacción en el mensaje enviado al servicio.|  
|Operaciones de transacción confirmadas|El número de operaciones confirmadas realizadas, cuya transacción se ha completado con el resultado confirmado en este servicio. Se confirma totalmente el trabajo hecho bajo tales operaciones. Los recursos se actualizan de acuerdo con el trabajo hecho en la operación.|  
|Operaciones de transacción confirmadas por segundo|El número de operaciones confirmadas realizadas, cuya transacción se ha completado con el resultado confirmado en este servicio en cada segundo. Se confirma totalmente el trabajo hecho bajo tales operaciones. Los recursos se actualizan de acuerdo con el trabajo hecho en la operación.|  
|Operaciones de transacción anuladas|El número de operaciones confirmadas realizadas, cuya transacción se ha completado con el resultado anulado en este servicio. El trabajo hecho bajo tales operaciones se deshace. Los recursos se devuelven a su estado anterior.|  
|Operaciones de transacción anuladas por segundo|El número de operaciones confirmadas realizadas, cuya transacción se ha completado con el resultado anulado en este servicio en cada segundo. El trabajo hecho bajo tales operaciones se deshace. Los recursos se devuelven a su estado anterior.|  
|Operaciones de transacción dudosas|El número de operaciones confirmadas realizadas, cuya transacción se ha completado con un resultado bajo duda en este servicio. El trabajo hecho con un resultado bajo duda está en un estado indeterminado. Los recursos se mantienen pendientes del resultado.|  
|Operaciones de transacción dudosas por segundo|El número de operaciones confirmadas realizadas, cuya transacción se ha completado con un resultado bajo duda en este servicio en cada segundo. El trabajo hecho con un resultado bajo duda está en un estado indeterminado. Los recursos se mantienen pendientes del resultado.|  
  
### <a name="endpoint-performance-counters"></a>Contadores de rendimiento del extremo  
  
|Contador de rendimiento|Descripción|  
|-------------------------|-----------------|  
|Flujo de transacciones|Número de transacciones de flujo a las operaciones en este punto de conexión. Este contador se incrementa siempre que se encuentra una transacción en el mensaje enviado al punto de conexión.|  
|Flujo de transacciones por segundo|El número de transacciones que fluyeron a operaciones en este punto de conexión en cada segundo. Este contador se incrementa siempre que se encuentra una transacción en el mensaje enviado al punto de conexión.|  
  
### <a name="operation-performance-counters"></a>Contadores del rendimiento de las operaciones  
  
|Contador de rendimiento|Descripción|  
|-------------------------|-----------------|  
|Flujo de transacciones|Número de transacciones de flujo a las operaciones en este punto de conexión. Este contador se incrementa siempre que se encuentra una transacción en el mensaje enviado al punto de conexión.|  
|Flujo de transacciones por segundo|El número de transacciones que fluyeron a operaciones en este punto de conexión en cada segundo. Este contador se incrementa siempre que se encuentra una transacción en el mensaje enviado al punto de conexión.|  
  
## <a name="windows-management-instrumentation"></a>Instrumental de administración de Windows  

 WCF expone datos de inspección de un servicio en tiempo de ejecución a través de un proveedor de WCF Instrumental de administración de Windows (WMI). Para obtener más información sobre el acceso a los datos de WMI, vea [uso de instrumental de administración de Windows para diagnósticos](../diagnostics/wmi/index.md).  
  
 Varias propiedades WMI de solo lectura indican los valores de transacción aplicados para un servicio. Las tablas siguientes hacen una lista de todos estos valores.  
  
 En un servicio, `ServiceBehaviorAttribute` tiene las propiedades siguientes.  
  
|Nombre|Tipo|Descripción|  
|----------|----------|-----------------|  
|ReleaseServiceInstanceOnTransactionComplete|Boolean|Especifica si el objeto de servicio se recicla cuando la transacción actual completa.|  
|TransactionAutoCompleteOnSessionClose|Boolean|Especifica si las transacciones pendientes se completan cuando la sesión actual se cierra.|  
|TransactionIsolationLevel|Una cadena que contiene un valor válido de la enumeración <xref:System.Transactions.IsolationLevel>.|Especifica el nivel de aislamiento de transacción que este servicio admite.|  
|TransactionTimeout|<xref:System.DateTime>|Especifica el período dentro del que una transacción se debe completar.|  
  
 El `ServiceTimeoutsBehavior` tiene la siguiente propiedad.  
  
|Nombre|Tipo|Descripción|  
|----------|----------|-----------------|  
|TransactionTimeout|<xref:System.DateTime>|Especifica el período dentro del que una transacción se debe completar.|  
  
 En un enlace, el `TransactionFlowBindingElement` tiene las propiedades siguientes.  
  
|Nombre|Tipo|Descripción|  
|----------|----------|-----------------|  
|TransactionProtocol|Una cadena que contiene un valor válido del tipo <xref:System.ServiceModel.TransactionProtocol>.|Especifica el protocolo de transacción a utilizar para que una transacción fluya.|  
|TransactionFlow|Boolean|Especifica si el flujo de transacciones entrantes está habilitado.|  
  
 En una operación, el `OperationBehaviorAttribute` tiene las propiedades siguientes:  
  
|Nombre|Tipo|Descripción|  
|----------|----------|-----------------|  
|TransactionAutoComplete|Boolean|Especifica si confirmar automáticamente la transacción actual si no se produce ninguna excepción no controlada.|  
|TransactionScopeRequired|Boolean|Especifica si la operación requiere una transacción.|  
  
 En una operación, el `TransactionFlowAttribute` tiene las propiedades siguientes:  
  
|Nombre|Tipo|Descripción|  
|----------|----------|-----------------|  
|TransactionFlowOption|Una cadena que contiene un valor válido de la enumeración <xref:System.ServiceModel.TransactionFlowOption>.|Especifica hasta qué punto se requiere el flujo de la transacción.|  
  
## <a name="tracing"></a>Seguimiento  

 Las trazas le permiten supervisar y analizar los errores de sus aplicaciones transaccionales. Puede habilitar el seguimiento mediante las maneras siguientes:  
  
- Seguimiento de WCF estándar  
  
     Este tipo de seguimiento es el mismo que el de cualquier aplicación WCF. Para obtener más información, consulta [Configuring Tracing](../diagnostics/tracing/configuring-tracing.md).  
  
- Trazado de WS-AtomicTransaction  
  
     WS-AtomicTransaction el seguimiento se puede habilitar mediante la [utilidad de configuración de WS-AtomicTransaction (wsatConfig.exe)](../ws-atomictransaction-configuration-utility-wsatconfig-exe.md). Tal seguimiento proporciona una visión sobre el estado de las transacciones y participantes de un sistema. Para también permitir el seguimiento de Service Model, puede establecer la clave del Registro`HKLM\SOFTWARE\Microsoft\WSAT\3.0\ServiceModelDiagnosticTracing` en un valor válido de la enumeración <xref:System.Diagnostics.SourceLevels>. Puede habilitar el registro de mensajes de la misma manera que otras aplicaciones WCF.  
  
- Seguimiento de `System.Transactions`  
  
     Si se usa el protocolo OleTransactions, no se pueden seguir los mensajes de protocolos. La compatibilidad de seguimiento que proporciona la infraestructura <xref:System.Transactions> (que utiliza OleTransactions) permite a los usuarios ver eventos que ocurrieron a las transacciones. Para habilitar el seguimiento para una aplicación <xref:System.Transactions>, incluya el siguiente código en el archivo de configuración `App.config`.  
  
    ```xml  
    <configuration>  
      <system.diagnostics>  
         <sources>  
            <source name="System.Transactions" switchValue="Verbose, ActivityTracing">  
               <listeners>  
                  <add name="Text"  
                     type="System.Diagnostics.XmlWriterTraceListener"  
                     initializeData="SysTx.log"  
                     traceOutputOptions="Callstack" />  
               </listeners>  
            </source>  
         </sources>  
         <trace autoflush="true" indentsize="4">  
         </trace>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
     Esto también habilita el seguimiento de WCF, ya que WCF también emplea la <xref:System.Transactions> infraestructura.  
  
## <a name="see-also"></a>Vea también

- [Administración y diagnóstico](../diagnostics/index.md)
- [Configurar seguimiento](../diagnostics/tracing/configuring-tracing.md)
- [Utilidad de configuración de WS-AtomicTransaction (wsatConfig.exe)](../ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
