---
title: '&lt;sqlWorkflowInstanceStore&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8a4e4214-fc51-4f4d-b968-0427c37a9520
ms.openlocfilehash: f0393cd4192ca7e775b4d311d6dd5de462155c43
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520950"
---
# <a name="ltsqlworkflowinstancestoregt"></a>&lt;sqlWorkflowInstanceStore&gt;
Un comportamiento del servicio que le permite configurar el <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> característica, que admite conservar información de estado para las instancias de servicio de flujo de trabajo en una base de datos de SQL Server 2005 o SQL Server 2008. Para obtener más información sobre esta característica, consulte [Store de instancia de flujo de trabajo de SQL](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).  
  
\<system.ServiceModel>  
\<comportamientos >  
\<serviceBehaviors>  
\<comportamiento >  
\<sqlWorkflowInstanceStore>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sqlWorkflowInstanceStore connectionStringName="String" 
                                honstLockRenewalPeriod="TimeSpan" 
                                instanceCompletionAction="DeleteNothing/DeleteAll" 
                                instanceEncodingAction="None/GZip" 
                                instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry" 
                                runnableInstancesDetectionPeriod="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|connectionString|Una cadena que contiene una cadena de conexión utilizada para conectarse a una base de datos de persistencia subyacente.|  
|connectionStringName|Una cadena que contiene una cadena de conexión con nombre en el servidor de base de datos. Un ejemplo de una cadena de conexión con nombre es "DefaultConnectionString".|  
|honstLockRenewalPeriod|Valor de Timespan que especifica el período de tiempo en el que el host debe renovar el bloqueo en una instancia. Si el host no renueva el bloqueo en el período de tiempo especificado, la instancia se desbloquea y se puede escoger a por otro host.<br /><br /> Descargar un flujo de trabajo implica que también se conserva. Si este atributo se establece en cero se conservan y se descargan inmediatamente después de la instancia de flujo de trabajo el flujo de trabajo se vuelve inactiva. Establecer este atributo en TimeSpan.MaxValue eficazmente, deshabilita la operación de descarga. Las instancias de flujo de trabajo inactivas nunca se descargan.|  
|instanceCompletionAction|Un valor que especifica si los datos de la instancia de flujo de trabajo se mantienen en el almacén de persistencia después de que la instancia de flujo de trabajo se complete o si se ha eliminado en ese punto. Este valor es del tipo <xref:System.Activities.DurableInstancing.InstanceCompletionAction>.<br /><br /> Las acciones enumeradas consisten en eliminar los datos de instancia del almacén de persistencia o en no eliminar los datos de instancia del almacén de persistencia cuando la instancia haya completado su operación.<br /><br /> Mantener las instancias una vez completadas provoca que la base de datos de persistencia crezca rápidamente y esto afecta al rendimiento de la base de datos. Debería configurar una directiva de purga de base de datos para eliminar estos registros de forma periódica para asegurarse de que el rendimiento de la base de datos está en el nivel que satisface sus requisitos de rendimiento.|  
|instanceEncodingOption|Un valor opcional que especifica si la información de estado de la instancia se comprime utilizando el algoritmo Gzip antes de que la información se guarde en el almacén de persistencia. Este valor es del tipo `System.Activities.DurableInstancing.InstanceEncodingAction`. Los valores posibles para esta propiedad son "None", donde no se especifica ninguna compresión y "GZip", que se especifica esa instancia de datos se comprimen y utilizan el algoritmo gzip.|  
|instanceLockedExceptionAction|Un valor que especifica la acción que se produce en respuesta a una excepción que se produce cuando el host intenta bloquear una instancia porque otro host bloquea actualmente la instancia. Este valor es del tipo <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.<br /><br /> Las opciones permitidas para este campo son: Ninguno, reintento básico y reintento agresivo. El valor predeterminado es None. La siguiente lista proporciona las descripciones de estas tres opciones:<br /><br /> -   Ninguno. El host del servicio no intenta bloquear la instancia y pasa el objeto <xref:System.Runtime.DurableInstancing.InstanceLockedException> al autor de la llamada.<br />-Básica de reintentos. El host del servicio vuelve a intentar bloquear la instancia con un intervalo de reintento lineal y pasa la excepción al autor de la llamada al final de la secuencia.<br />-Reintento agresiva. El host del servicio vuelve a intentar bloquear la instancia con un retraso en aumento exponencial y pasa el objeto <xref:System.Runtime.DurableInstancing.InstanceLockedException> al autor de llamada al final de la secuencia.|  
|runnableInstancesDetectionPeriod||  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<comportamiento > de \<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Especifica un elemento de comportamiento.|  
  
## <a name="see-also"></a>Vea también
- <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>
- <xref:System.ServiceModel.Activities.Configuration.SqlWorkflowInstanceStoreElement>
- <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>
- [Almacén de instancias de flujo de trabajo de SQL](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)
