---
title: "C&#243;mo: Habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ca7bf77f-3e5d-4b23-b17a-d0b60f46411d
caps.latest.revision: 36
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 36
---
# C&#243;mo: Habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo
En este tema se describe cómo configurar la característica Almacén de instancias de flujo de trabajo de SQL para habilitar la persistencia para los flujos de trabajo y servicios de flujo de trabajo, según la programación, o mediante un archivo de configuración.  
  
 Windows Server APp Fabric simplifica el proceso de configuración de persistencia.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Configuración de persistencia de App Fabric](http://go.microsoft.com/fwlink/?LinkId=201204)  
  
 Antes de usar la característica Almacén de instancias de flujo de trabajo de SQL, cree una base de datos que la característica usará para conservar las instancias de flujo de trabajo.El programa de instalación de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] copia los archivos de script de SQL asociados con la característica Almacén de instancias de flujo de trabajo en la carpeta %WINDIR%\\Microsoft.NET\\Framework\\v4.xxx\\SQL\\EN.Ejecute estos archivos de script en una base de datos de SQL Server 2005 o SQL Server 2008 que desea que el almacén de instancias de flujo de trabajo de SQL use para conservar las instancias de flujo de trabajo.Ejecute primero el archivo SqlWorkflowInstanceStoreSchema.sql y después SqlWorkflowInstanceStoreLogic.sql.  
  
> [!NOTE]
>  Para limpiar la base de datos de persistencia para tener una base de datos nueva, ejecute los scripts en %WINDIR%\\Microsoft.NET\\Framework\\v4.xxx\\SQL\\EN en el siguiente orden.  
>   
>  1.  SqlWorkflowInstanceStoreSchema.sql  
> 2.  SqlWorkflowInstanceStoreLogic.sql  
  
> [!IMPORTANT]
>  Si no crea una base de datos de persistencia, la característica Almacén de instancias de flujo de trabajo de SQL inicia una excepción similar a la siguiente cuando un host intenta mantener flujos de trabajo.  
>   
>  System.Data.SqlClient.SqlException: No se pudo encontrar el procedimiento almacenado 'System.Activities.DurableInstancing.CreateLockOwner'  
  
 En las siguientes secciones se describe cómo habilitar la persistencia para flujos de trabajo y servicios de flujo de trabajo que usen el almacén de instancias de flujo de trabajo de SQL.[!INCLUDE[crabout](../../../includes/crabout-md.md)] las propiedades del almacén de instancias de flujo de trabajo de SQL, vea [Propiedades del almacén de instancias de flujo de trabajo de SQL](../../../docs/framework/windows-workflow-foundation//properties-of-sql-workflow-instance-store.md).  
  
## Habilitar la persistencia para flujos de trabajo auto\-hospedados que usan WorkflowApplication  
 Puede habilitar la persistencia para los flujos de trabajo auto\-hospedados que usen <xref:System.Activities.WorkflowApplication> mediante programación al utilizar el modelo de objeto <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>.El siguiente procedimiento contiene los pasos para hacerlo.  
  
#### Para habilitar la persistencia para los flujos de trabajo auto\-hospedados  
  
1.  Agregue una referencia a System.Activites.DurableInstancing.dll.  
  
2.  Agregue la siguiente instrucción al principio del archivo de origen después de las instrucciones de uso existentes.  
  
    ```csharp  
    using System.Activities.DurableInstancing;  
    ```  
  
3.  Construya un objeto <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> y asígnelo a la propiedad <xref:System.Activities.WorkflowApplication.InstanceStore%2A> del objeto <xref:System.Activities.WorkflowApplication> como se muestra en el código de ejemplo siguiente.  
  
    ```csharp  
  
    SqlWorkflowInstanceStore store =   
        new SqlWorkflowInstanceStore("Server=.\\SQLEXPRESS;Initial Catalog=Persistence;Integrated Security=SSPI");  
  
    WorkflowApplication wfApp =  
        new WorkflowApplication(new Workflow1());  
  
    wfApp.InstanceStore = store;  
  
    ```  
  
    > [!NOTE]
    >  Según la edición de SQL Server, el nombre de servidor de cadena de conexión puede ser diferente.  
  
4.  Invoque el método <xref:System.Activities.WorkflowApplication.Persist%2A> en el objeto <xref:System.Activities.WorkflowApplication> para conservar un flujo de trabajo o el método <xref:System.Activities.WorkflowApplication.Unload%2A> para conservar y descargar un flujo de trabajo.También puede controlar el evento <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> emitido por el objeto <xref:System.Activities.WorkflowApplication> y devolver el miembro adecuado \(<xref:System.Activities.PersistableIdleAction> o <xref:System.Activities.PersistableIdleAction>\) de <xref:System.Activities.PersistableIdleAction>.  
  
    ```csharp  
    wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)  
    {  
        return PersistableIdleAction.Persist;  
    };  
    ```  
  
> [!NOTE]
>  Vea el ejemplo de [Conservar una aplicación de flujo de trabajo](../../../docs/framework/windows-workflow-foundation/samples/persisting-a-workflow-application.md) en [Persistencia](../../../docs/framework/windows-workflow-foundation/samples/persistence.md) para ver un ejemplo sobre cómo habilitar la persistencia para los flujos de trabajo con <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> y el paso [Cómo: Crear y ejecutar un flujo de trabajo de larga ejecución](../../../docs/framework/windows-workflow-foundation//how-to-create-and-run-a-long-running-workflow.md) de [Tutorial de introducción](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md) para obtener instrucciones paso a paso.  
  
## Habilitar la persistencia para los servicios del flujo de trabajo auto\-hospedados que usan WorkflowServiceHost  
 Puede habilitar la persistencia para los servicios de flujo de trabajo auto\-hospedados que usan <xref:System.ServiceModel.WorkflowServiceHost> mediante programación al usar la clase <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> o la clase <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A>.  
  
### Usar la clase SqlWorkflowInstanceStoreBehavior  
 El siguiente procedimiento detalla los pasos para usar la clase <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> a fin de habilitar la persistencia para los servicios de flujo de trabajo auto\-hospedados.  
  
##### Para habilitar la persistencia mediante SqlWorkflowInstanceStoreBehavior  
  
1.  Agregue una referencia a System.ServiceModel.dll.  
  
2.  Agregue la siguiente instrucción al principio del archivo de origen después de las instrucciones de uso existentes.  
  
    ```csharp  
    using System.ServiceModel.Activities.Description;  
    ```  
  
3.  Cree una instancia de `WorkflowServiceHost` y agregue los extremos para el servicio del flujo de trabajo.  
  
    ```  
  
    WorkflowServiceHost host = new WorkflowServiceHost(new CountingWorkflow(), new Uri(hostBaseAddress));  
    host.AddServiceEndpoint("ICountingWorkflow", new BasicHttpBinding(), "");  
  
    ```  
  
4.  Construya un objeto `SqlWorkflowInstanceStoreBehavior` y defina las propiedades del objeto de comportamiento.  
  
    ```csharp  
  
    SqlWorkflowInstanceStoreBehavior instanceStoreBehavior = new SqlWorkflowInstanceStoreBehavior(connectionString);  
    instanceStoreBehavior.HostLockRenewalPeriod = new TimeSpan(0, 0, 5);  
    instanceStoreBehavior.InstanceCompletionAction = InstanceCompletionAction.DeleteAll;  
    instanceStoreBehavior.InstanceLockedExceptionAction = InstanceLockedExceptionAction.AggressiveRetry;  
    instanceStoreBehavior.InstanceEncodingOption = InstanceEncodingOption.GZip;  
    instanceStoreBehavior.RunnableInstancesDetectionPeriod = new TimeSpan("00:00:02");  
    host.Description.Behaviors.Add(instanceStoreBehavior);  
  
    ```  
  
5.  Abra el host de servicio de flujo de trabajo.  
  
    ```vb  
  
    host.Open();  
  
    ```  
  
> [!IMPORTANT]
>  Vea el ejemplo [Configuración integrada](../../../docs/framework/windows-workflow-foundation/samples/built-in-configuration.md) en [Persistencia](../../../docs/framework/windows-workflow-foundation/samples/persistence.md) para saber cómo habilitar la persistencia para los servicios de flujo de trabajo mediante la clase `SqlWorkflowInstanceStoreBehavior`.  
  
### Usar la propiedad DurableInstancingOptions  
 Cuando se aplica `SqlWorkflowInstanceStoreBehavior`, `DurableInstancingOptions.InstanceStore` en `WorkflowServiceHost` está definida en el objeto `SqlWorkflowInstanceStore` creado con los valores de configuración.Puede hacer lo mismo mediante programación para definir la propiedad <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A> de `WorkflowServiceHost` sin usar la clase `SqlWorkflowInstanceStoreBehavior`, como se muestra en el siguiente código de ejemplo.  
  
```  
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;  
```  
  
## Habilitar la persistencia para los servicios de flujo de trabajo hospedados en WAS que usan WorkflowServiceHost mediante un archivo de configuración  
 Puede habilitar la persistencia para los servicios de flujo de trabajo auto\-hospedados u hospedados por Windows Process Activation Service \(WAS\) usando un archivo de configuración.Un servicio de flujo de trabajo hospedado en WAS usa WorkflowServiceHost tal y como lo hacen los servicios de flujo de trabajo auto\-hospedados.  
  
 `SqlWorkflowInstanceStoreBehavior`, un comportamiento de servicio que le permite cambiar las propiedades de [Almacén de instancias de flujo de trabajo de SQL](../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md) de manera adecuada mediante la configuración XML.En el caso de los servicios de flujo de trabajo hospedados por WAS, use el archivo Web.config.El siguiente ejemplo de configuración muestra cómo configurar el Almacén de instancias de flujo de trabajo de SQL mediante el elemento de comportamiento `sqlWorkflowInstanceStore` en un archivo de configuración.  
  
```  
  
<serviceBehaviors>  
    <behavior name="">  
        <sqlWorkflowInstanceStore   
                    connectionString="Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"  
                    instanceEncodingOption="GZip | None"  
                    instanceCompletionAction="DeleteAll | DeleteNothing"  
                    instanceLockedExceptionAction="NoRetry | BasicRetry |AggressiveRetry"  
                    hostLockRenewalPeriod="00:00:30"   
                    runnableInstancesDetectionPeriod="00:00:05">  
  
        <sqlWorkflowInstanceStore/>  
    </behavior>  
</serviceBehaviors>  
  
```  
  
 Si no establece los valores para las propiedades `connectionString` o `connectionStringName`, el almacén de instancias de flujo de trabajo de SQL usa la cadena de conexión con nombre predeterminada `DefaultSqlWorkflowInstanceStoreConnectionString`.  
  
 Cuando se aplica `SqlWorkflowInstanceStoreBehavior`, `DurableInstancingOptions.InstanceStore` en `WorkflowServiceHost` está definida en el objeto `SqlWorkflowInstanceStore` creado con los valores de configuración.Puede hacer lo mismo mediante programación para usar `SqlWorkflowInstanceStore` con `WorkflowServiceHost` sin usar el elemento de comportamiento del servicio.  
  
```  
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;  
```  
  
> [!IMPORTANT]
>  Se recomienda no almacenar la información confidencial, como nombres de usuario y contraseñas, en el archivo Web.config.Si no almacena información confidencial en el archivo Web.config, debería proteger el acceso al archivo Web.config mediante las lista de control de acceso \(ACL\) del sistema de archivos.Además, puede proteger los valores de configuración en un archivo de configuración tal y como se menciona en [Cifrar información de configuración mediante la configuración protegida](http://go.microsoft.com/fwlink/?LinkId=178419).  
  
### Elementos Machine.config relacionados con la característica Almacén de instancias de flujo de trabajo de SQL  
 La instalación de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] agrega los siguientes elementos relacionados con la característica Almacén de instancias de flujo de trabajo de SQL al archivo Machine.config:  
  
-   Agrega el siguiente elemento de extensión de comportamiento al archivo Machine.config para que pueda usar el elemento de comportamiento de servicio \<`sqlWorkflowInstanceStore`\> en el archivo de configuración para configurar la persistencia para los servicios.  
  
    ```  
  
    <configuration>  
        <system.serviceModel>  
            <extensions>  
                <behaviorExtensions>  
                    <add name="sqlWorkflowInstanceStore" type="System.Activities.DurableInstancing.SqlWorkflowInstanceStoreElement, System.Activities.DurableInstancing, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
                </behaviorExtensions>  
            </extensions>  
        <system.serviceModel>  
    <configuration>  
  
    ```