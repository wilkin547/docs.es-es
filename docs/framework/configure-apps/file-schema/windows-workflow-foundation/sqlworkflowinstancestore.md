---
title: <sqlWorkflowInstanceStore>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8a4e4214-fc51-4f4d-b968-0427c37a9520
ms.openlocfilehash: 581da860a490c95d5d621194c7f6643fc15118fe
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398678"
---
# <a name="sqlworkflowinstancestore"></a>\<sqlWorkflowInstanceStore>
Un comportamiento del servicio que permite configurar la característica <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> , que admite la persistencia de la información de estado de las instancias del servicio de flujo de trabajo en una base de datos SQL Server 2005 o SQL Server 2008. Para obtener más información sobre esta característica, consulte [almacén de instancias de flujo de trabajo de SQL](../../../windows-workflow-foundation/sql-workflow-instance-store.md).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamientos >** ](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comportamiento >** ](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> sqlWorkflowInstanceStore**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sqlWorkflowInstanceStore connectionStringName="String" 
                                hostLockRenewalPeriod="TimeSpan" 
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
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|connectionString|Una cadena que contiene una cadena de conexión utilizada para conectarse a una base de datos de persistencia subyacente.|  
|connectionStringName|Cadena que contiene una cadena de conexión con nombre para el servidor de base de datos. Un ejemplo de una cadena de conexión con nombre es "DefaultConnectionString".|  
|hostLockRenewalPeriod|Valor de Timespan que especifica el período de tiempo en el que el host debe renovar el bloqueo en una instancia. Si el host no renueva el bloqueo en el período de tiempo especificado, la instancia se desbloquea y se puede escoger a por otro host.<br /><br /> Descargar un flujo de trabajo implica que también se conserva. Si este atributo se establece en cero, la instancia de flujo de trabajo se conserva y se descarga inmediatamente después de que el flujo de trabajo se vuelva inactivo. Si se establece este atributo en TimeSpan. MaxValue, se deshabilita la operación de descarga. Las instancias de flujo de trabajo inactivas nunca se descargan.|  
|instanceCompletionAction|Un valor que especifica si los datos de la instancia de flujo de trabajo se mantienen en el almacén de persistencia después de que la instancia de flujo de trabajo se complete o si se ha eliminado en ese punto. Este valor es del tipo <xref:System.Activities.DurableInstancing.InstanceCompletionAction>.<br /><br /> Las acciones enumeradas consisten en eliminar los datos de instancia del almacén de persistencia o en no eliminar los datos de instancia del almacén de persistencia cuando la instancia haya completado su operación.<br /><br /> Mantener las instancias una vez completadas provoca que la base de datos de persistencia crezca rápidamente y esto afecta al rendimiento de la base de datos. Debería configurar una directiva de purga de base de datos para eliminar estos registros de forma periódica para asegurarse de que el rendimiento de la base de datos está en el nivel que satisface sus requisitos de rendimiento.|  
|instanceEncodingOption|Un valor opcional que especifica si la información de estado de la instancia se comprime utilizando el algoritmo Gzip antes de que la información se guarde en el almacén de persistencia. Este valor es del tipo <xref:System.Activities.DurableInstancing.InstanceEncodingOption>. Los valores posibles para esta propiedad <xref:System.Activities.DurableInstancing.InstanceEncodingOption.None>son, que no especifica ninguna compresión <xref:System.Activities.DurableInstancing.InstanceEncodingOption.GZip>, y, que especifica que los datos de instancia se comprimen y usan el algoritmo gzip.|  
|instanceLockedExceptionAction|Un valor que especifica la acción que se produce en respuesta a una excepción que se produce cuando el host intenta bloquear una instancia porque otro host bloquea actualmente la instancia. Este valor es del tipo <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.<br /><br /> Las opciones permitidas para este campo son: Ninguno, reintento básico y reintento agresivo. El valor predeterminado es Ninguno. La siguiente lista proporciona las descripciones de estas tres opciones:<br /><br /> -   Ninguno. El host del servicio no intenta bloquear la instancia y pasa el objeto <xref:System.Runtime.DurableInstancing.InstanceLockedException> al autor de la llamada.<br />-Reintento básico. El host del servicio vuelve a intentar bloquear la instancia con un intervalo de reintento lineal y pasa la excepción al autor de la llamada al final de la secuencia.<br />-Reintento agresivo. El host del servicio vuelve a intentar bloquear la instancia con un retraso en aumento exponencial y pasa el objeto <xref:System.Runtime.DurableInstancing.InstanceLockedException> al autor de llamada al final de la secuencia.|  
|runnableInstancesDetectionPeriod||  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<comportamiento > de \<serviceBehaviors >](behavior-of-servicebehaviors-of-workflow.md)|Especifica un elemento de comportamiento.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>
- <xref:System.ServiceModel.Activities.Configuration.SqlWorkflowInstanceStoreElement>
- <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>
- [Almacén de instancias de flujo de trabajo de SQL](../../../windows-workflow-foundation/sql-workflow-instance-store.md)
