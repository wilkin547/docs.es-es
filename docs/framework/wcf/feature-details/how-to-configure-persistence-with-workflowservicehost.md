---
title: Procedimiento para configurar la persistencia con WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
ms.openlocfilehash: b8839f42a9b8b5f4da0a1a8364c7eac5a4c06d4e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337167"
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a>Procedimiento para configurar la persistencia con WorkflowServiceHost
En este tema, se describe cómo configurar la característica Almacén de instancias de flujo de trabajo de SQL para habilitar la persistencia de los flujos de trabajo hospedados en <xref:System.ServiceModel.Activities.WorkflowServiceHost> mediante un archivo de configuración. Antes de utilizar la característica Almacén de instancias de flujo de trabajo de SQL, cree una base de datos SQL que se use para guardar instancias de flujo de trabajo. Para obtener más información, vea [Cómo: Habilitar la persistencia de SQL para flujos de trabajo y los servicios de flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a>Para configurar el Almacén de instancias de flujo de trabajo de SQL en Configuración  
  
1. Las propiedades del Almacén de instancias de flujo de trabajo de SQL se pueden configurar a través de <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, un comportamiento del servicio que le permite cambiar la configuración a través de la configuración de XML. El siguiente ejemplo de configuración muestra cómo configurar el almacén de instancias de flujo de trabajo SQL mediante el <`sqlWorkflowInstanceStore`> elemento de comportamiento en un archivo de configuración.  
  
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
  
     Para obtener más información sobre cómo configurar el almacén de instancias de flujo de trabajo SQL, vea [Cómo: Habilitar la persistencia de SQL para flujos de trabajo y los servicios de flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md). Para obtener más información sobre la configuración individual de la <`sqlWorkflowInstanceStore`> elemento de comportamiento, consulte [Store de instancia de flujo de trabajo de SQL](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md). Windows Server App Fabric proporciona su propio almacén de persistencia. Para obtener más información, consulte [persistencia de Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=193121).  
  
    > [!NOTE]
    >  El ejemplo de configuración anterior usa una configuración simplificada. Para obtener más información, consulte [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)  
  
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
  
     Para obtener más información sobre cómo configurar el almacén de instancias de flujo de trabajo SQL, vea [Cómo: Habilitar la persistencia de SQL para flujos de trabajo y los servicios de flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md). Para obtener más información acerca de los valores individuales para el <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> elemento de comportamiento, consulte [Store de instancia de flujo de trabajo de SQL](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md). Windows Server App Fabric proporciona su propio almacén de persistencia. Para obtener más información, consulte [persistencia de Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=193121).  
  
    > [!NOTE]
    >  El ejemplo de configuración anterior usa una configuración simplificada. Para obtener más información, consulte [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)  
  
     Para obtener un ejemplo de cómo configurar la persistencia mediante programación, vea [Cómo: Habilitar la persistencia para flujos de trabajo y los servicios de flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).  
  
## <a name="see-also"></a>Vea también

- [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Persistencia del flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)
- [Persistencia de Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=193121)
