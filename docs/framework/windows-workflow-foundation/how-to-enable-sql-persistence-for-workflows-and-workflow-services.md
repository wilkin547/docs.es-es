---
title: Procedimiento para habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: ca7bf77f-3e5d-4b23-b17a-d0b60f46411d
ms.openlocfilehash: 5bcd37a654db35ba6e8af1b15d6c132a090b0579
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90547758"
---
# <a name="how-to-enable-sql-persistence-for-workflows-and-workflow-services"></a>Procedimiento para habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo

En este tema se describe cómo configurar la característica Almacén de instancias de flujo de trabajo de SQL para habilitar la persistencia para los flujos de trabajo y servicios de flujo de trabajo, según la programación, o mediante un archivo de configuración.

Windows Server APp Fabric simplifica el proceso de configuración de persistencia. Para obtener más información, consulte [configuración de persistencia de App fabric](/previous-versions/appfabric/ee790848(v=azure.10)).

Antes de usar la característica Almacén de instancias de flujo de trabajo de SQL, cree una base de datos que la característica usará para conservar las instancias de flujo de trabajo. El programa de instalación de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] copia los archivos de script de SQL asociados con la característica Almacén de instancias de flujo de trabajo en la carpeta %WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN. Ejecute estos archivos de script en una base de datos de SQL Server 2005 o SQL Server 2008 que desea que el almacén de instancias de flujo de trabajo de SQL use para conservar las instancias de flujo de trabajo. Ejecute primero el archivo SqlWorkflowInstanceStoreSchema.sql y después SqlWorkflowInstanceStoreLogic.sql.

> [!NOTE]
> Para limpiar la base de datos de persistencia para tener una base de datos nueva, ejecute los scripts en %WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN en el siguiente orden.
>
> 1. SqlWorkflowInstanceStoreSchema.sql
> 2. SqlWorkflowInstanceStoreLogic.sql

> [!IMPORTANT]
> Si no crea una base de datos de persistencia, la característica Almacén de instancias de flujo de trabajo de SQL inicia una excepción similar a la siguiente cuando un host intenta mantener flujos de trabajo.
>
> System.Data.SqlClient.SqlException: No se pudo encontrar el procedimiento almacenado 'System.Activities.DurableInstancing.CreateLockOwner'

En las siguientes secciones se describe cómo habilitar la persistencia para flujos de trabajo y servicios de flujo de trabajo que usen el almacén de instancias de flujo de trabajo de SQL. Para obtener más información sobre las propiedades del almacén de instancias de flujo de trabajo de SQL, vea [propiedades del almacén de instancias de flujo de trabajo de SQL](properties-of-sql-workflow-instance-store.md).

## <a name="enabling-persistence-for-self-hosted-workflows-that-use-workflowapplication"></a>Habilitar la persistencia para flujos de trabajo auto-hospedados que usan WorkflowApplication

Puede habilitar la persistencia para los flujos de trabajo auto-hospedados que usen <xref:System.Activities.WorkflowApplication> mediante programación al utilizar el modelo de objeto <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>. El siguiente procedimiento contiene los pasos para hacerlo.

#### <a name="to-enable-persistence-for-self-hosted-workflows"></a>Para habilitar la persistencia para los flujos de trabajo auto-hospedados

1. Agregue una referencia a System.Activities.DurableInstancing.dll.

2. Agregue la siguiente instrucción al principio del archivo de origen después de las instrucciones de uso existentes.

    ```csharp
    using System.Activities.DurableInstancing;
    ```

3. Construya un objeto <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> y asígnelo a la propiedad <xref:System.Activities.WorkflowApplication.InstanceStore%2A> del objeto <xref:System.Activities.WorkflowApplication> como se muestra en el código de ejemplo siguiente.

    ```csharp
    SqlWorkflowInstanceStore store =
        new SqlWorkflowInstanceStore("Server=.\\SQLEXPRESS;Initial Catalog=Persistence;Integrated Security=SSPI");

    WorkflowApplication wfApp =
        new WorkflowApplication(new Workflow1());

    wfApp.InstanceStore = store;
    ```

   > [!NOTE]
   > Según la edición de SQL Server, el nombre de servidor de cadena de conexión puede ser diferente.

4. Invoque el método <xref:System.Activities.WorkflowApplication.Persist%2A> en el objeto <xref:System.Activities.WorkflowApplication> para conservar un flujo de trabajo o el método <xref:System.Activities.WorkflowApplication.Unload%2A> para conservar y descargar un flujo de trabajo. También puede controlar el evento <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> emitido por el objeto <xref:System.Activities.WorkflowApplication> y devolver el miembro adecuado (<xref:System.Activities.PersistableIdleAction.Persist> o <xref:System.Activities.PersistableIdleAction.Unload>) de <xref:System.Activities.PersistableIdleAction>.

   ```csharp
   wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
   {
       return PersistableIdleAction.Persist;
   };
   ```

> [!NOTE]
> Consulte el paso [Cómo: crear y ejecutar un flujo de trabajo de ejecución prolongada](how-to-create-and-run-a-long-running-workflow.md) del [tutorial de introducción](getting-started-tutorial.md) para obtener instrucciones paso a paso.

## <a name="enabling-persistence-for-self-hosted-workflow-services-that-use-the-workflowservicehost"></a>Habilitar la persistencia para los servicios del flujo de trabajo auto-hospedados que usan WorkflowServiceHost

Puede habilitar la persistencia para los servicios de flujo de trabajo auto-hospedados que usan <xref:System.ServiceModel.WorkflowServiceHost> mediante programación al usar la clase <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> o la clase <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A>.

### <a name="using-the-sqlworkflowinstancestorebehavior-class"></a>Usar la clase SqlWorkflowInstanceStoreBehavior

El siguiente procedimiento detalla los pasos para usar la clase <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> a fin de habilitar la persistencia para los servicios de flujo de trabajo auto-hospedados.

#### <a name="to-enable-persistence-using-sqlworkflowinstancestorebehavior"></a>Para habilitar la persistencia mediante SqlWorkflowInstanceStoreBehavior

1. Agregue una referencia a System.ServiceModel.dll.

2. Agregue la siguiente instrucción al principio del archivo de origen después de las instrucciones de uso existentes.

    ```csharp
    using System.ServiceModel.Activities.Description;
    ```

3. Cree una instancia de `WorkflowServiceHost` y agregue los extremos para el servicio del flujo de trabajo.

    ```csharp
    WorkflowServiceHost host = new WorkflowServiceHost(new CountingWorkflow(), new Uri(hostBaseAddress));
    host.AddServiceEndpoint("ICountingWorkflow", new BasicHttpBinding(), "");
    ```

4. Construya un objeto `SqlWorkflowInstanceStoreBehavior` y defina las propiedades del objeto de comportamiento.

    ```csharp
    SqlWorkflowInstanceStoreBehavior instanceStoreBehavior = new SqlWorkflowInstanceStoreBehavior(connectionString);
    instanceStoreBehavior.HostLockRenewalPeriod = new TimeSpan(0, 0, 5);
    instanceStoreBehavior.InstanceCompletionAction = InstanceCompletionAction.DeleteAll;
    instanceStoreBehavior.InstanceLockedExceptionAction = InstanceLockedExceptionAction.AggressiveRetry;
    instanceStoreBehavior.InstanceEncodingOption = InstanceEncodingOption.GZip;
    instanceStoreBehavior.RunnableInstancesDetectionPeriod = new TimeSpan("00:00:02");
    host.Description.Behaviors.Add(instanceStoreBehavior);
    ```

5. Abra el host de servicio de flujo de trabajo.

    ```csharp
    host.Open();
    ```

### <a name="using-the-durableinstancingoptions-property"></a>Usar la propiedad DurableInstancingOptions

Cuando se aplica `SqlWorkflowInstanceStoreBehavior`, `DurableInstancingOptions.InstanceStore` en `WorkflowServiceHost` está definida en el objeto `SqlWorkflowInstanceStore` creado con los valores de configuración. Puede hacer lo mismo mediante programación para definir la propiedad <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A> de `WorkflowServiceHost` sin usar la clase `SqlWorkflowInstanceStoreBehavior`, como se muestra en el siguiente código de ejemplo.

```csharp
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;
```

## <a name="enabling-persistence-for-was-hosted-workflow-services-that-use-the-workflowservicehost-using-a-configuration-file"></a>Habilitar la persistencia para los servicios de flujo de trabajo hospedados en WAS que usan WorkflowServiceHost mediante un archivo de configuración

Puede habilitar la persistencia para los servicios de flujo de trabajo auto-hospedados u hospedados por Windows Process Activation Service (WAS) usando un archivo de configuración. Un servicio de flujo de trabajo hospedado en WAS usa WorkflowServiceHost tal y como lo hacen los servicios de flujo de trabajo auto-hospedados.

`SqlWorkflowInstanceStoreBehavior`, Un comportamiento de servicio que le permite cambiar las propiedades del [almacén de instancias de flujo de trabajo de SQL](sql-workflow-instance-store.md) de forma cómoda a través de la configuración XML. En el caso de los servicios de flujo de trabajo hospedados por WAS, use el archivo Web.config. El siguiente ejemplo de configuración muestra cómo configurar el Almacén de instancias de flujo de trabajo de SQL mediante el elemento de comportamiento `sqlWorkflowInstanceStore` en un archivo de configuración.

```xml
<serviceBehaviors>
    <behavior name="">
        <sqlWorkflowInstanceStore
                    connectionString="Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"
                    instanceEncodingOption="GZip | None"
                    instanceCompletionAction="DeleteAll | DeleteNothing"
                    instanceLockedExceptionAction="NoRetry | BasicRetry |AggressiveRetry"
                    hostLockRenewalPeriod="00:00:30"
                    runnableInstancesDetectionPeriod="00:00:05" />

    </behavior>
</serviceBehaviors>
```

Si no establece los valores para las propiedades `connectionString` o `connectionStringName`, el almacén de instancias de flujo de trabajo de SQL usa la cadena de conexión con nombre predeterminada `DefaultSqlWorkflowInstanceStoreConnectionString`.

Cuando se aplica `SqlWorkflowInstanceStoreBehavior`, `DurableInstancingOptions.InstanceStore` en `WorkflowServiceHost` está definida en el objeto `SqlWorkflowInstanceStore` creado con los valores de configuración. Puede hacer lo mismo mediante programación para usar `SqlWorkflowInstanceStore` con `WorkflowServiceHost` sin usar el elemento de comportamiento del servicio.

```csharp
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;
```

> [!IMPORTANT]
> Se recomienda no almacenar la información confidencial, como nombres de usuario y contraseñas, en el archivo Web.config. Si no almacena información confidencial en el archivo Web.config, debería proteger el acceso al archivo Web.config mediante las lista de control de acceso (ACL) del sistema de archivos. Además, también puede proteger los valores de configuración de un archivo de configuración, como se mencionó en [cifrar información de configuración mediante la configuración protegida](/previous-versions/aspnet/53tyfkaw(v=vs.100)).

### <a name="machineconfig-elements-related-to-the-sql-workflow-instance-store-feature"></a>Elementos Machine.config relacionados con la característica Almacén de instancias de flujo de trabajo de SQL

La instalación de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] agrega los siguientes elementos relacionados con la característica Almacén de instancias de flujo de trabajo de SQL al archivo Machine.config:

- Agrega el siguiente elemento de extensión de comportamiento al archivo Machine.config para que pueda usar el \<sqlWorkflowInstanceStore> elemento de comportamiento del servicio en el archivo de configuración para configurar la persistencia para los servicios.

    ```xml
    <configuration>
        <system.serviceModel>
            <extensions>
                <behaviorExtensions>
                    <add name="sqlWorkflowInstanceStore" type="System.Activities.DurableInstancing.SqlWorkflowInstanceStoreElement, System.Activities.DurableInstancing, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />
                </behaviorExtensions>
            </extensions>
        </system.serviceModel>
    </configuration>
    ```
