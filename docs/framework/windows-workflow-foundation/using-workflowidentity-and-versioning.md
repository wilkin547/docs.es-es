---
title: Usar WorkflowIdentity y el control de versiones
ms.date: 03/30/2017
ms.assetid: b8451735-8046-478f-912b-40870a6c0c3a
ms.openlocfilehash: 6b769224edcd9dfc51879c2c99e061a0e3f77e8d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958387"
---
# <a name="using-workflowidentity-and-versioning"></a>Usar WorkflowIdentity y el control de versiones

<xref:System.Activities.WorkflowIdentity> proporciona una manera para que los desarrolladores de aplicaciones de flujo de trabajo asocien un nombre y una <xref:System.Version> con una definición de flujo de trabajo, y para que esta información se asocie a una instancia de flujo de trabajo persistente. Los desarrolladores de aplicaciones de flujo de trabajo pueden usar esta información de identidad para habilitar escenarios como la ejecución en paralelo de varias versiones de una definición de flujo de trabajo; además esta información proporciona la piedra angular para otras funcionalidades como la actualización dinámica. Este tema proporciona información general sobre cómo usar <xref:System.Activities.WorkflowIdentity> con hospedaje de <xref:System.Activities.WorkflowApplication>. Para obtener información sobre la ejecución en paralelo de definiciones de flujo de trabajo en un servicio de flujo de trabajo, vea [control de versiones en paralelo en WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md). Para obtener información sobre la actualización dinámica, consulte [actualización dinámica](dynamic-update.md).

## <a name="in-this-topic"></a>En este tema

- [Usar WorkflowIdentity](using-workflowidentity-and-versioning.md#UsingWorkflowIdentity)

  - [Ejecución en paralelo mediante WorkflowIdentity](using-workflowidentity-and-versioning.md#SxS)

- [Actualización de bases de datos de persistencia de .NET Framework 4 para admitir el control de versiones del flujo de trabajo](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases)

  - [Para actualizar el esquema de la base de datos](using-workflowidentity-and-versioning.md#ToUpgrade)

## <a name="UsingWorkflowIdentity"></a>Usar WorkflowIdentity

Para usar <xref:System.Activities.WorkflowIdentity>, cree una instancia, configúrela y asóciela con una instancia de <xref:System.Activities.WorkflowApplication>. Una instancia de <xref:System.Activities.WorkflowIdentity> contiene tres elementos de identificación de información. <xref:System.Activities.WorkflowIdentity.Name%2A> y <xref:System.Activities.WorkflowIdentity.Version%2A> contienen un nombre y <xref:System.Version> y son necesarios, y <xref:System.Activities.WorkflowIdentity.Package%2A> es opcional y se puede usar para especificar una cadena adicional que contiene información como el nombre del ensamblado u otra información deseada. <xref:System.Activities.WorkflowIdentity> es único si cualquiera de sus tres propiedades son diferentes de otra <xref:System.Activities.WorkflowIdentity>.

> [!IMPORTANT]
> Un objeto <xref:System.Activities.WorkflowIdentity> no debe contener información de identificación personal (PII). El runtime emite la información acerca del elemento <xref:System.Activities.WorkflowIdentity> usado para crear una instancia a cualquier servicio de seguimiento configurado en diferentes puntos del ciclo de vida de actividad. El seguimiento de WF no tiene ningún mecanismo para ocultar la PII (datos de usuario confidenciales). Por lo tanto, una instancia de <xref:System.Activities.WorkflowIdentity> no debe contener datos PII ya que el runtime los emitirá en registros de seguimiento y serán visibles para cualquiera que tenga acceso para ver los registros de seguimiento.

En el ejemplo siguiente, se crea una <xref:System.Activities.WorkflowIdentity> y se asocia a una instancia de un flujo de trabajo creado mediante una definición de flujo de trabajo de `MortgageWorkflow`.

```csharp
WorkflowIdentity identityV1 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v1",
    Version = new Version(1, 0, 0, 0)
};

WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identity);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Run the workflow.
wfApp.Run();
```

Al recargar y al reanudar un flujo de trabajo, se debe usar una <xref:System.Activities.WorkflowIdentity> configurada para coincidir con la <xref:System.Activities.WorkflowIdentity> de la instancia de flujo de trabajo persistente.

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Load the workflow.
wfApp.Load(instanceId);

// Resume the workflow...
```

Si la <xref:System.Activities.WorkflowIdentity> usada al recargar la instancia de flujo de trabajo no coincide con la <xref:System.Activities.WorkflowIdentity> persistente, se producirá <xref:System.Activities.VersionMismatchException>. En el ejemplo siguiente se realiza un intento de carga en la instancia de `MortgageWorkflow` que se ha hecho persistente en el ejemplo anterior. Este intento de carga se realiza mediante una <xref:System.Activities.WorkflowIdentity> configurada para una versión más reciente del flujo de trabajo de hipotecas que no coincide con la instancia persistente.

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow_v2(), identityV2);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Attempt to load the workflow instance.
wfApp.Load(instanceId);

// Resume the workflow...
```

Cuando se ejecuta el código anterior, se produce la <xref:System.Activities.VersionMismatchException> siguiente.

```
The WorkflowIdentity ('MortgageWorkflow v1; Version=1.0.0.0') of the loaded instance does not match the WorkflowIdentity ('MortgageWorkflow v2; Version=2.0.0.0') of the provided workflow definition. The instance can be loaded using a different definition, or updated using Dynamic Update.
```

### <a name="SxS"></a>Ejecución en paralelo mediante WorkflowIdentity

<xref:System.Activities.WorkflowIdentity> se puede usar para facilitar la ejecución de varias versiones de un flujo de trabajo en paralelo. Un escenario común es cambiar los requisitos comerciales de un flujo de trabajo de ejecución prolongada. Pueden ejecutarse varias instancias de un flujo de trabajo cuando se implementa una versión actualizada. La aplicación host se puede configurar para usar la definición de flujo de trabajo actualizada al iniciar nuevas instancias y es responsabilidad de la aplicación host proporcionar la definición de flujo de trabajo correcta al reanudar las instancias. <xref:System.Activities.WorkflowIdentity> puede usarse para identificar y proporcionar la definición de flujo de trabajo coincidente al reanudar instancias de flujo de trabajo.

Para recuperar la <xref:System.Activities.WorkflowIdentity> de una instancia de flujo de trabajo persistente, se usa el método <xref:System.Activities.WorkflowApplication.GetInstance%2A>. El método <xref:System.Activities.WorkflowApplication.GetInstance%2A> toma el <xref:System.Activities.WorkflowApplication.Id%2A> de la instancia de flujo de trabajo persistente y el <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> que contiene la instancia persistente y devuelve una <xref:System.Activities.WorkflowApplicationInstance>. <xref:System.Activities.WorkflowApplicationInstance> contiene información sobre una instancia de flujo de trabajo persistente, incluida su <xref:System.Activities.WorkflowIdentity> asociada. El host puede usar esta <xref:System.Activities.WorkflowIdentity> asociada para proporcionar la definición de flujo de trabajo correcta al cargar y reanudar la instancia de flujo de trabajo.

> [!NOTE]
> Un objeto <xref:System.Activities.WorkflowIdentity> NULL es válido y el host puede usarlo para asignar las instancias persistentes sin ningún <xref:System.Activities.WorkflowIdentity> asociado a la definición de flujo de trabajo adecuada. Este escenario puede darse cuando una aplicación de flujo de trabajo no se escribió al principio con el control de versiones del flujo de trabajo o cuando una aplicación se actualiza desde [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]. Para obtener más información, consulte [actualización de bases de datos de persistencia de .NET Framework 4 para admitir el control de versiones de flujo de trabajo](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).

En el ejemplo `Dictionary<WorkflowIdentity, Activity>` siguiente, se usa para asociar <xref:System.Activities.WorkflowIdentity> instancias con sus definiciones de flujo de trabajo coincidentes, y `MortgageWorkflow` un flujo de trabajo se inicia utilizando la `identityV1` definición de flujo de trabajo, que está asociada al <xref:System.Activities.WorkflowIdentity>.

```csharp
WorkflowIdentity identityV1 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v1",
    Version = new Version(1, 0, 0, 0)
};

WorkflowIdentity identityV2 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v2",
    Version = new Version(2, 0, 0, 0)
};

Dictionary<WorkflowIdentity, Activity> WorkflowVersionMap = new Dictionary<WorkflowIdentity, Activity>();
WorkflowVersionMap.Add(identityV1, new MortgageWorkflow());
WorkflowVersionMap.Add(identityV2, new MortgageWorkflow_v2());

WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Run the workflow.
wfApp.Run();
```

En el ejemplo siguiente, la información sobre la instancia de flujo de trabajo persistente del ejemplo anterior se recupera mediante una llamada a <xref:System.Activities.WorkflowApplication.GetInstance%2A> y la información persistente de <xref:System.Activities.WorkflowIdentity> se usa para recuperar la definición de flujo de trabajo coincidente. Esta información se usa para configurar <xref:System.Activities.WorkflowApplication> y después se carga el flujo de trabajo. Tenga en cuenta que como se usa la sobrecarga de <xref:System.Activities.WorkflowApplication.Load%2A> que toma <xref:System.Activities.WorkflowApplicationInstance>, la <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> usa el <xref:System.Activities.WorkflowApplicationInstance> configurado en <xref:System.Activities.WorkflowApplication> y por tanto no es necesario configurar su propiedad <xref:System.Activities.WorkflowApplication.InstanceStore%2A>.

> [!NOTE]
> Si se establece la propiedad <xref:System.Activities.WorkflowApplication.InstanceStore%2A>, debe estar establecida con la misma instancia de <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> usada por <xref:System.Activities.WorkflowApplicationInstance> o se producirá una <xref:System.ArgumentException> con el mensaje siguiente: `The instance is configured with a different InstanceStore than this WorkflowApplication.`.

```csharp
// Get the WorkflowApplicationInstance of the desired workflow from the specified
// SqlWorkflowInstanceStore.
WorkflowApplicationInstance instance = WorkflowApplication.GetInstance(instanceId, store);

// Use the persisted WorkflowIdentity to retrieve the correct workflow
// definition from the dictionary.
Activity definition = WorkflowVersionMap[instance.DefinitionIdentity];

WorkflowApplication wfApp = new WorkflowApplication(definition, instance.DefinitionIdentity);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Load the persisted workflow instance.
wfApp.Load(instance);

// Resume the workflow...
```

## <a name="UpdatingWF4PersistenceDatabases"></a>Actualización de bases de datos de persistencia de .NET Framework 4 para admitir el control de versiones del flujo de trabajo

Se proporciona un script de base de datos SqlWorkflowInstanceStoreSchemaUpgrade.sql para actualizar las bases de datos de persistencia creadas mediante los scripts de base de datos de [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]. Este script actualiza las bases de datos para admitir las nuevas capacidades de control de versiones introducidas en .NET Framework 4,5. Cualquier instancia de flujo de trabajo persistente en las bases de datos recibe valores de control de versión predeterminados y puede participar en ejecuciones en paralelo y en actualizaciones dinámicas.

Si una aplicación de flujo de trabajo .NET Framework 4,5 intenta cualquier operación de persistencia que use las nuevas características de control de versiones en una base de datos de persistencia que no se haya <xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> actualizado mediante el script proporcionado, se produce una excepción con un mensaje similar al mensaje siguiente.

```
The SqlWorkflowInstanceStore has a database version of '4.0.0.0'. InstancePersistenceCommand 'System.Activities.DurableInstancing.CreateWorkflowOwnerWithIdentityCommand' cannot be run against this database version.  Please upgrade the database to '4.5.0.0'.
```

### <a name="ToUpgrade"></a>Para actualizar el esquema de la base de datos

1. Abra SQL Server Management Studio y conéctese al servidor de base de datos de persistencia, por ejemplo **.\SQLEXPRESS**.

2. Elija **abrir**, **archivo** en el menú **archivo** . Busque la siguiente carpeta: `C:\Windows\Microsoft.NET\Framework\4.0.30319\sql\en`

3. Seleccione **SqlWorkflowInstanceStoreSchemaUpgrade. SQL** y haga clic en **abrir**.

4. Seleccione el nombre de la base de datos de persistencia en el menú desplegable bases de datos **disponibles** .

5. Elija **Ejecutar** en el menú **consulta** .

Cuando la consulta se completa, el esquema de la base de datos se actualiza y, si lo desea, puede ver la identidad de flujo de trabajo predeterminada que se asignó a las instancias de flujo de trabajo persistentes. Expanda la base de datos de persistencia en el nodo **bases** de datos del **Explorador de objetos**y, a continuación, expanda el nodo **vistas** . Haga clic con el botón secundario en **System. Activities. DurableInstancing.** instances y elija **seleccionar las primeras 1000 filas**. Desplácese hasta el final de las columnas y observe que se han agregado seis columnas adicionales a la vista: **IdentityName**, **IdentityPackage**, **compilación**, **principal**, **secundaria**y **revisión**. Cualquier flujo de trabajo persistente tendrá un valor **null** para estos campos, que representa una identidad de flujo de trabajo nula.
