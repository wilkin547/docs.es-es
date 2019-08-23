---
title: Procedimiento para configurar la persistencia con WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
ms.openlocfilehash: 2cae73bd503afec6ddd1faf435645ebc21f4fc76
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968482"
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a>Procedimiento para configurar la persistencia con WorkflowServiceHost
En este tema, se describe cómo configurar la característica Almacén de instancias de flujo de trabajo de SQL para habilitar la persistencia de los flujos de trabajo hospedados en <xref:System.ServiceModel.Activities.WorkflowServiceHost> mediante un archivo de configuración. Antes de utilizar la característica Almacén de instancias de flujo de trabajo de SQL, cree una base de datos SQL que se use para guardar instancias de flujo de trabajo. Para obtener más información, consulte [Cómo Habilitar la persistencia de SQL para flujos de trabajo](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)y servicios de flujo de trabajo.  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a>Para configurar el Almacén de instancias de flujo de trabajo de SQL en Configuración  
  
1. Las propiedades del Almacén de instancias de flujo de trabajo de SQL se pueden configurar a través de <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, un comportamiento del servicio que le permite cambiar la configuración a través de la configuración de XML. En el ejemplo de configuración siguiente se muestra cómo configurar el almacén de instancias de flujo de`sqlWorkflowInstanceStore`trabajo de SQL mediante el elemento de comportamiento < > en un archivo de configuración.  
  
    ```xml  
    <serviceBehaviors>  
        <behavior name="">  
            <sqlWorkflowInstanceStore   
                 connectionString="provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"  
                 instanceEncodingOption="GZip | None"  
                 instanceCompletionAction="DeleteAll | DeleteNothing"  
                 instanceLockedExceptionAction="NoRetry | SimpleRetry | AggressiveRetry"  
                 hostLockRenewalPeriod="00:00:30"   
                 runnableInstancesDetectionPeriod="00:00:05">  
            <sqlWorkflowInstanceStore/>  
        </behavior>  
    </serviceBehaviors>  
    ```  
  
     Para obtener más información sobre cómo configurar el almacén de instancias de flujo de [trabajo de SQL, consulte Cómo: Habilitar la persistencia de SQL para flujos de trabajo](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)y servicios de flujo de trabajo. Para obtener más información sobre la configuración individual del elemento`sqlWorkflowInstanceStore`< > Behavior, vea [almacén de instancias de flujo de trabajo de SQL](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md). Windows Server App Fabric proporciona su propio almacén de persistencia. Para obtener más información, consulte [persistencia de Windows Server App fabric](https://go.microsoft.com/fwlink/?LinkId=193121).  
  
    > [!NOTE]
    > El ejemplo de configuración anterior usa una configuración simplificada. Para obtener más información, vea [configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md) .  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-code"></a>Para configurar el Almacén de instancias de flujo de trabajo de SQL en el código  
  
1. Las propiedades del Almacén de instancias de flujo de trabajo de SQL se pueden configurar a través de <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, un comportamiento del servicio que le permite cambiar la configuración a través de código. El siguiente ejemplo muestra cómo configurar el almacén de instancias de flujo de trabajo de SQL mediante el elemento de comportamiento <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> en un código.  
  
    ```csharp  
    host.Description.Behaviors.Add(new SqlWorkflowInstanceStoreBehavior  
    {  
       ConnectionString = "provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true",  
       InstanceEncodingOption = "GZip | None",  
       InstanceCompletionAction = "DeleteAll | DeleteNothing",  
       InstanceLockedExceptionAction = "NoRetry | SimpleRetry | AggressiveRetry",  
       HostLockRenewalPeriod = new TimeSpan(00, 00, 30),  
       RunnableInstancesDetectionPeriod = new TimeSpan(00, 00, 05)  
    });  
    ```  
  
     Para obtener más información sobre cómo configurar el almacén de instancias de flujo de [trabajo de SQL, consulte Cómo: Habilitar la persistencia de SQL para flujos de trabajo](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)y servicios de flujo de trabajo. Para obtener más información sobre la configuración individual del <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> elemento de comportamiento, vea [almacén de instancias de flujo de trabajo de SQL](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md). Windows Server App Fabric proporciona su propio almacén de persistencia. Para obtener más información, consulte [persistencia de Windows Server App fabric](https://go.microsoft.com/fwlink/?LinkId=193121).  
  
    > [!NOTE]
    > El ejemplo de configuración anterior usa una configuración simplificada. Para obtener más información, vea [configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md) .  
  
     Para obtener un ejemplo de cómo configurar la persistencia mediante programación [, vea cómo: Habilitar la persistencia para flujos de trabajo y](../../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md)servicios de flujo de trabajo.  
  
## <a name="see-also"></a>Vea también

- [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Persistencia del flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)
- [Persistencia de Windows Server App fabric](https://go.microsoft.com/fwlink/?LinkId=193121)
