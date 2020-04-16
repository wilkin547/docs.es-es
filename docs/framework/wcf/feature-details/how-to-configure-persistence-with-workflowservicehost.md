---
title: Procedimiento para configurar la persistencia con WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
ms.openlocfilehash: 4bfa66a895ae9af9cb87ff110dc82c8a8a922b49
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463850"
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a>Procedimiento para configurar la persistencia con WorkflowServiceHost
En este tema, se describe cómo configurar la característica Almacén de instancias de flujo de trabajo de SQL para habilitar la persistencia de los flujos de trabajo hospedados en <xref:System.ServiceModel.Activities.WorkflowServiceHost> mediante un archivo de configuración. Antes de utilizar la característica Almacén de instancias de flujo de trabajo de SQL, cree una base de datos SQL que se use para guardar instancias de flujo de trabajo. Para obtener más información, vea [Cómo: Habilitar la persistencia de SQL para flujos de trabajo y servicios](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)de flujo de trabajo .  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a>Para configurar el Almacén de instancias de flujo de trabajo de SQL en Configuración  
  
1. Las propiedades del Almacén de instancias de flujo de trabajo de SQL se pueden configurar a través de <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, un comportamiento del servicio que le permite cambiar la configuración a través de la configuración de XML. En el ejemplo de configuración siguiente se muestra cómo `sqlWorkflowInstanceStore` configurar el almacén de instancias de flujo de trabajo de SQL mediante el <> elemento de comportamiento en un archivo de configuración.  
  
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
            </sqlWorkflowInstanceStore>  
        </behavior>  
    </serviceBehaviors>  
    ```  
  
     Para obtener más información acerca de cómo configurar el almacén de instancias de flujo de trabajo SQL, vea Cómo: habilitar la persistencia de [SQL para flujos de trabajo y servicios](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)de flujo de trabajo . Para obtener más información acerca `sqlWorkflowInstanceStore` de la configuración individual del <> elemento de comportamiento, vea Almacén de [instancias](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)de flujo de trabajo de SQL . Windows Server App Fabric proporciona su propio almacén de persistencia. Para obtener más información, vea [Persistencia](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))de Windows Server App Fabric .  
  
    > [!NOTE]
    > El ejemplo de configuración anterior usa una configuración simplificada. Para obtener más información, consulte [Configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md)  
  
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
  
     Para obtener más información acerca de cómo configurar el almacén de instancias de flujo de trabajo SQL, vea Cómo: habilitar la persistencia de [SQL para flujos de trabajo y servicios](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)de flujo de trabajo . Para obtener más información acerca <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> de la configuración individual del elemento de comportamiento, vea Almacén de [instancias](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)de flujo de trabajo de SQL . Windows Server App Fabric proporciona su propio almacén de persistencia. Para obtener más información, vea [Persistencia](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))de Windows Server App Fabric .  
  
    > [!NOTE]
    > El ejemplo de configuración anterior usa una configuración simplificada. Para obtener más información, consulte [Configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md)  
  
     Para obtener un ejemplo de cómo configurar la persistencia mediante programación, vea [Cómo: Habilitar la persistencia para flujos](../../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md)de trabajo y servicios de flujo de trabajo .  
  
## <a name="see-also"></a>Consulte también

- [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Persistencia del flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)
- [Persistencia de Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))
