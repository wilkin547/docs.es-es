---
title: "C&#243;mo: Configurar la persistencia con WorkflowServiceHost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# C&#243;mo: Configurar la persistencia con WorkflowServiceHost
En este tema, se describe cómo configurar la característica Almacén de instancias de flujo de trabajo de SQL para habilitar la persistencia de los flujos de trabajo hospedados en <xref:System.ServiceHost.Activities.WorkflowServiceHost> mediante un archivo de configuración.  Antes de utilizar la característica Almacén de instancias de flujo de trabajo de SQL, cree una base de datos SQL que se use para guardar instancias de flujo de trabajo.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Cómo: Habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo](../../../../docs/framework/windows-workflow-foundation//how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).  
  
### Para configurar el Almacén de instancias de flujo de trabajo de SQL en Configuración  
  
1.  Las propiedades del Almacén de instancias de flujo de trabajo de SQL se pueden configurar a través de <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, un comportamiento del servicio que le permite cambiar la configuración a través de la configuración de XML.  El siguiente ejemplo de configuración muestra cómo configurar el Almacén de instancias de flujo de trabajo de SQL mediante el elemento de comportamiento \<`sqlWorkflowInstanceStore`\> en un archivo de configuración.  
  
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
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo configurar el almacén de instancias de flujo de trabajo de SQL, vea [Cómo: Habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo](../../../../docs/framework/windows-workflow-foundation//how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] los valores individuales para el elemento de comportamiento \<`sqlWorkflowInstanceStore`\>, vea [Almacén de instancias de flujo de trabajo de SQL](../../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md).  Windows Server App Fabric proporciona su propio almacén de persistencia.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Persistencia de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193121).  
  
    > [!NOTE]
    >  El ejemplo de configuración anterior usa una configuración simplificada.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md)  
  
### Para configurar el Almacén de instancias de flujo de trabajo de SQL en el código  
  
1.  Las propiedades del Almacén de instancias de flujo de trabajo de SQL se pueden configurar a través de <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, un comportamiento del servicio que le permite cambiar la configuración a través de código.  El siguiente ejemplo muestra cómo configurar el almacén de instancias de flujo de trabajo de SQL mediante el elemento de comportamiento <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> en un código.  
  
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
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo configurar el almacén de instancias de flujo de trabajo de SQL, vea [Cómo: Habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo](../../../../docs/framework/windows-workflow-foundation//how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] los valores individuales para el elemento de comportamiento <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, vea [Almacén de instancias de flujo de trabajo de SQL](../../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md).  Windows Server App Fabric proporciona su propio almacén de persistencia.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Persistencia de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193121).  
  
    > [!NOTE]
    >  El ejemplo de configuración anterior usa una configuración simplificada.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md)  
  
     Para obtener un ejemplo de cómo configurar la persistencia mediante programación, vea [Cómo: Habilitar persistencia para flujos de trabajo y servicios de flujo de trabajo](../../../../docs/framework/windows-workflow-foundation//how-to-enable-persistence-for-workflows-and-workflow-services.md).  
  
## Vea también  
 [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)   
 [Persistencia del flujo de trabajo](../../../../docs/framework/windows-workflow-foundation//workflow-persistence.md)   
 [Persistencia de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=193121)