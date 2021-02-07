---
description: 'Más información acerca de cómo: crear un almacén de instancias personalizado'
title: Procedimiento para crear un almacén de instancias personalizado
ms.date: 03/30/2017
ms.assetid: 593c4e9d-8a49-4e12-8257-cee5e6b4c075
ms.openlocfilehash: 3a1a511e6a97dffe510c839aceec8c9d91a77ec1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742139"
---
# <a name="how-to-create-a-custom-instance-store"></a>Procedimiento para crear un almacén de instancias personalizado

[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] contiene <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, un almacén de instancias que usa SQL Server para conservar datos del flujo de trabajo. Si la aplicación necesita conservar los datos del flujo de trabajo en otro medio, como una base de datos diferente o un sistema de archivos, puede implementar un almacén de instancias personalizado. Un almacén de instancias personalizado se crea extendiendo la clase <xref:System.Runtime.DurableInstancing.InstanceStore> abstracta e implementando los métodos necesarios para la implementación. Para obtener una implementación completa de un almacén de instancias personalizado, vea el ejemplo de [proceso de compra corporativa](./samples/corporate-purchase-process.md) .

## <a name="implementing-the-begintrycommand-method"></a>Implementar el método BeginTryCommand

El motor de persistencia envía <xref:System.Runtime.DurableInstancing.InstanceStore.BeginTryCommand%2A> al almacén de instancias. El tipo del parámetro `command` indica qué comando se está ejecutando; este parámetro puede ser de los tipos siguientes:

- <xref:System.Activities.DurableInstancing.SaveWorkflowCommand>: el motor de persistencia envía este comando al almacén de instancias cuando un flujo de trabajo se va a conservar en el medio de almacenamiento. Los datos de persistencia del flujo de trabajo se proporcionan al método en el miembro <xref:System.Activities.DurableInstancing.SaveWorkflowCommand.InstanceData%2A> del parámetro `command`.

- <xref:System.Activities.DurableInstancing.LoadWorkflowCommand>: el motor de persistencia envía este comando al almacén de instancias cuando un flujo de trabajo se va a cargar desde el medio de almacenamiento. El identificador de instancia del flujo de trabajo que se va a cargar se proporciona al método en el parámetro `instanceId` de la propiedad <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.InstanceView%2A> del parámetro `context`.

- <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>: el motor de persistencia envía este comando al almacén de instancias cuando <xref:System.ServiceModel.Activities.WorkflowServiceHost> se debe registrar como propietario del bloqueo. El identificador de instancia del flujo de trabajo actual se debe proporcionar al almacén de instancias usando el método <xref:System.Runtime.DurableInstancing.InstancePersistenceContext.BindInstanceOwner%2A> del parámetro `context`.

     El fragmento de código siguiente muestra cómo implementar el comando CreateWorkflowOwner para asignar un propietario explícito de bloqueo.

    ```csharp
    XName WFInstanceScopeName = XName.Get(scopeName, "<namespace>");
    ...
    CreateWorkflowOwnerCommand createCommand = new CreateWorkflowOwnerCommand()
    {
        InstanceOwnerMetadata =
        {
            { WorkflowHostTypeName, new InstanceValue(WFInstanceScopeName) },
        }
    };
    InstanceHandle ownerHandle = store.CreateInstanceHandle();
    store.DefaultInstanceOwner = store.Execute(
                                   ownerHandle,
                                   createCommand,
                                   TimeSpan.FromSeconds(30)).InstanceOwner;
    childInstance.AddInitialInstanceValues(new Dictionary<XName, object>() { { WorkflowHostTypeName, WFInstanceScopeName } });
    ```

- <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>: el motor de persistencia envía este comando al almacén de instancias cuando el identificador de instancia de un propietario de bloqueo se puede quitar del almacén de instancias. Como en <xref:System.Activities.DurableInstancing.CreateWorkflowOwnerCommand>, la aplicación debe proporcionar el identificador del propietario de bloqueo.

     El fragmento de código siguiente muestra cómo liberar un bloqueo mediante <xref:System.Activities.DurableInstancing.DeleteWorkflowOwnerCommand>.

    ```csharp
    static void FreeHandleAndDeleteOwner(InstanceStore store, InstanceHandle handle)
    {
        handle.Free();
        handle = store.CreateInstanceHandle(store.DefaultInstanceOwner);
        try
        {
            // We need this sleep so that we dont prematurely delete the owner, we need time to update the database.
            Thread.Sleep(10000);
            store.Execute(handle, new DeleteWorkflowOwnerCommand(), TimeSpan.FromSeconds(10));
        }
        catch (InstancePersistenceCommandException ex) { Log.Inform(ex.Message); }
        catch (InstanceOwnerException ex) { Log.Inform(ex.Message); }
        catch (OperationCanceledException ex) { Log.Inform(ex.Message); }
        catch (Exception ex) { Log.Inform(ex.Message); }
        finally
        {
            handle.Free();
            store.DefaultInstanceOwner = null;
        }
    }
    ```

     Se debe llamar al método anterior en un bloque Try/Catch cuando se ejecute una instancia secundaria.

    ```csharp
    try
    {
        childInstance.Run();
    }
    catch (Exception)
    {
        throw ;
    }
    finally
    {
        FreeHandleAndDeleteOwner(store, ownerHandle);
    }
    ```

- <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand>: el motor de persistencia envía este comando al almacén de instancias cuando una instancia de flujo de trabajo se va a cargar mediante la clave de la instancia de flujo de trabajo. El identificador de la clave de instancia se puede determinar mediante el parámetro <xref:System.Activities.DurableInstancing.LoadWorkflowByInstanceKeyCommand.LookupInstanceKey%2A> del comando.

- <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand>: el motor de persistencia envía este comando al almacén de instancias para recuperar parámetros de activación para los flujos de trabajo conservados con el fin de crear un host de flujo de trabajo que pueda cargar flujos de trabajo. El motor envía este comando como respuesta al almacén de instancias que produce <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> en el host cuando encuentra una instancia que se puede activar. Se debe sondear el almacén de instancias para determinar si hay flujos de trabajo que se pueden activar.

- <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand>: el motor de persistencia envía este comando al almacén de instancias para cargar instancias de flujo de trabajo ejecutables. El motor envía este comando como respuesta al almacén de instancias que produce <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> en el host cuando encuentra una instancia que se puede ejecutar. Se debe sondear el almacén de instancias para ver qué flujos de trabajo se pueden ejecutar. El fragmento de código siguiente muestra cómo sondear un almacén de instancias para flujos de trabajo que se pueden ejecutar o activar.

    ```csharp
    public void PollForEvents()
    {
        InstanceOwner[] storeOwners = this.GetInstanceOwners();

        foreach (InstanceOwner owner in storeOwners)
        {
            foreach (InstancePersistenceEvent ppEvent in this.GetEvents(owner))
            {
                if (ppEvent.Equals(HasRunnableWorkflowEvent.Value))
                {
                    bool hasRunnable = GetRunnableEvents(this.StoreId, owner.InstanceOwnerId, isActivatable);
                    if (hasRunnable)
                    {
                        this.SignalEvent(ppEvent, owner);
                    }
                    else
                    {
                        this.ResetEvent(ppEvent, owner);
                    }
                }
                else if(ppEvent.Equals(HasActivatableWorkflowEvent.Value))
                {
                   bool hasActivatable = GetActivatableEvents(this.StoreId, owner.InstanceOwnerId);
                   if (hasActivatable)
                    {
                        this.SignalEvent(ppEvent, owner);
                    }
                    else
                    {
                        this.ResetEvent(ppEvent, owner);
                    }
                }
            }
        }
    }
    ```

     En el fragmento de código anterior, el almacén de instancias consulta los eventos disponibles y examina cada uno de ellos para determinar si es un evento <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent>. Si encuentra alguno, se llama a <xref:System.Runtime.DurableInstancing.InstanceStore.SignalEvent%2A> para notificar al host que envíe un comando al almacén de instancias. El fragmento de código siguiente muestra una implementación de un controlador para este comando.

    ```csharp
    If (command is TryLoadRunnableWorkflowCommand)
    {
        Owner owner;
        CheckOwner(context, command.Name, out owner);
        // Checking instance.Owner is like an InstanceLockQueryResult.
        context.QueriedInstanceStore(new InstanceLockQueryResult(context.InstanceView.InstanceId, context.InstanceView.InstanceOwner.InstanceOwnerId));

        XName ownerService = null;
        InstanceValue value;
        Instance runnableInstance = default(Instance);
        bool foundRunnableInstance = false;

        value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, owner.Data);
        if (value != null && value.Value is XName)
        {
            ownerService = (XName)value.Value;
        }

        foreach (KeyValuePair<Guid, Instance> instance in MemoryStore.instances)
        {
            if (instance.Value.Owner != Guid.Empty || instance.Value.Completed)
            {
                continue;
            }

            if (ownerService != null)
            {
                value = QueryPropertyBag(WorkflowNamespace.WorkflowHostType, instance.Value.Metadata);
                if (value == null || ((XName)value.Value) != ownerService)
                {
                    continue;
                }
            }

            value = QueryPropertyBag(WorkflowServiceNamespace.SuspendReason, instance.Value.Metadata);
            if (value != null && value.Value != null && value.Value is string)
            {
                continue;
            }

            value = QueryPropertyBag(WorkflowNamespace.Status, instance.Value.Data);
            if (value != null && value.Value is string && ((string)value.Value) == "Executing")
            {
                runnableInstance = instance.Value;
                foundRunnableInstance = true;
            }

            if (!foundRunnableInstance)
            {
                value = QueryPropertyBag(XNamespace.Get("urn:schemas-microsoft-com:System.Activities/4.0/properties").GetName("TimerExpirationTime"), instance.Value.Data);
                if (value != null && value.Value is DateTime && ((DateTime)value.Value) <= DateTime.UtcNow)
                {
                    runnableInstance = instance.Value;
                    foundRunnableInstance = true;
                }
            }

            if (foundRunnableInstance)
            {
                runnableInstance.LockVersion++;
                runnableInstance.Owner = context.InstanceView.InstanceOwner.InstanceOwnerId;
                MemoryStore.instances[instance.Key] = runnableInstance;
                context.BindInstance(instance.Key);
                context.BindAcquiredLock(runnableInstance.LockVersion);

                Dictionary<Guid, IDictionary<XName, InstanceValue>> associatedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();
                Dictionary<Guid, IDictionary<XName, InstanceValue>> completedKeys = new Dictionary<Guid, IDictionary<XName, InstanceValue>>();
                foreach (KeyValuePair<Guid, Key> keyEntry in MemoryStore.keys)
                {
                if (keyEntry.Value.Instance == context.InstanceView.InstanceId)
                {
                    if (keyEntry.Value.Completed)
                    {
                        completedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));
                    }
                    else
                    {
                        associatedKeys.Add(keyEntry.Key, DeserializePropertyBag(keyEntry.Value.Metadata));
                    }
                }
            }

            context.LoadedInstance(InstanceState.Initialized, DeserializePropertyBag(runnableInstance.Data), DeserializePropertyBag(runnableInstance.Metadata), associatedKeys, completedKeys);
            break;
        }
    }
    ```

    En el fragmento de código anterior, el almacén de instancias busca instancias ejecutables. Si se encuentra una instancia, se enlaza al contexto de ejecución y se carga.

## <a name="using-a-custom-instance-store"></a>Usar un almacén de instancias personalizado

Para implementar un almacén de instancias personalizado, asigne una instancia del almacén de instancias a <xref:System.Activities.WorkflowApplication.InstanceStore%2A> e implemente el método de <xref:System.Activities.WorkflowApplication.PersistableIdle%2A>. Consulte el tutorial [Cómo: crear y ejecutar un flujo de trabajo de ejecución prolongada](how-to-create-and-run-a-long-running-workflow.md) para obtener información específica.

## <a name="a-sample-instance-store"></a>Un almacén de instancias de ejemplo

El siguiente ejemplo de código es una implementación completa del almacén de instancias, tomada del ejemplo de [proceso de compra corporativa](./samples/corporate-purchase-process.md) . Este almacén de instancias conserva los datos del flujo de trabajo en un archivo mediante XML.

```csharp
using System;
using System.Activities.DurableInstancing;
using System.Collections.Generic;
using System.IO;
using System.Runtime.DurableInstancing;
using System.Runtime.Serialization;
using System.ServiceModel.Persistence;
using System.Xml;
using System.Xml.Linq;

namespace Microsoft.Samples.WF.PurchaseProcess
{

    public class XmlWorkflowInstanceStore : InstanceStore
    {
        Guid ownerInstanceID;

        public XmlWorkflowInstanceStore() : this(Guid.NewGuid())
        {

        }

        public XmlWorkflowInstanceStore(Guid id)
        {
            ownerInstanceID = id;
        }

        //Synchronous version of the Begin/EndTryCommand functions
        protected override bool TryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout)
        {
            return EndTryCommand(BeginTryCommand(context, command, timeout, null, null));
        }

        //The persistence engine will send a variety of commands to the configured InstanceStore,
        //such as CreateWorkflowOwnerCommand, SaveWorkflowCommand, and LoadWorkflowCommand.
        //This method is where we will handle those commands
        protected override IAsyncResult BeginTryCommand(InstancePersistenceContext context, InstancePersistenceCommand command, TimeSpan timeout, AsyncCallback callback, object state)
        {
            IDictionary<XName, InstanceValue> data = null;

            //The CreateWorkflowOwner command instructs the instance store to create a new instance owner bound to the instanace handle
            if (command is CreateWorkflowOwnerCommand)
            {
                context.BindInstanceOwner(ownerInstanceID, Guid.NewGuid());
            }
            //The SaveWorkflow command instructs the instance store to modify the instance bound to the instance handle or an instance key
            else if (command is SaveWorkflowCommand)
            {
                SaveWorkflowCommand saveCommand = (SaveWorkflowCommand)command;
                data = saveCommand.InstanceData;

                Save(data);
            }
            //The LoadWorkflow command instructs the instance store to lock and load the instance bound to the identifier in the instance handle
            else if (command is LoadWorkflowCommand)
            {
                string fileName = IOHelper.GetFileName(this.ownerInstanceID);

                try
                {
                    using (FileStream inputStream = new FileStream(fileName, FileMode.Open))
                    {
                        data = LoadInstanceDataFromFile(inputStream);
                        //load the data into the persistence Context
                        context.LoadedInstance(InstanceState.Initialized, data, null, null, null);
                    }
                }
                catch (Exception exception)
                {
                    throw new PersistenceException(exception.Message);
                }
            }

            return new CompletedAsyncResult<bool>(true, callback, state);
        }

        protected override bool EndTryCommand(IAsyncResult result)
        {
            return CompletedAsyncResult<bool>.End(result);
        }

        //Reads data from xml file and creates a dictionary based off of that.
        IDictionary<XName, InstanceValue> LoadInstanceDataFromFile(Stream inputStream)
        {
            IDictionary<XName, InstanceValue> data = new Dictionary<XName, InstanceValue>();

            NetDataContractSerializer s = new NetDataContractSerializer();

            XmlReader rdr = XmlReader.Create(inputStream);
            XmlDocument doc = new XmlDocument();
            doc.Load(rdr);

            XmlNodeList instances = doc.GetElementsByTagName("InstanceValue");
            foreach (XmlElement instanceElement in instances)
            {
                XmlElement keyElement = (XmlElement)instanceElement.SelectSingleNode("descendant::key");
                XName key = (XName)DeserializeObject(s, keyElement);

                XmlElement valueElement = (XmlElement)instanceElement.SelectSingleNode("descendant::value");
                object value = DeserializeObject(s, valueElement);
                InstanceValue instVal = new InstanceValue(value);

                data.Add(key, instVal);
            }

            return data;
        }

        object DeserializeObject(NetDataContractSerializer serializer, XmlElement element)
        {
            object deserializedObject = null;

            MemoryStream stm = new MemoryStream();
            XmlDictionaryWriter wtr = XmlDictionaryWriter.CreateTextWriter(stm);
            element.WriteContentTo(wtr);
            wtr.Flush();
            stm.Position = 0;

            deserializedObject = serializer.Deserialize(stm);

            return deserializedObject;
        }

        //Saves the persistence data to an xml file.
        void Save(IDictionary<XName, InstanceValue> instanceData)
        {
            string fileName = IOHelper.GetFileName(this.ownerInstanceID);
            XmlDocument doc = new XmlDocument();
            doc.LoadXml("<InstanceValues/>");

            foreach (KeyValuePair<XName,InstanceValue> valPair in instanceData)
            {
                XmlElement newInstance = doc.CreateElement("InstanceValue");

                XmlElement newKey = SerializeObject("key", valPair.Key, doc);
                newInstance.AppendChild(newKey);

                XmlElement newValue = SerializeObject("value", valPair.Value.Value, doc);
                newInstance.AppendChild(newValue);

                doc.DocumentElement.AppendChild(newInstance);
            }
            doc.Save(fileName);
       }

        XmlElement SerializeObject(string elementName, object o, XmlDocument doc)
        {
            NetDataContractSerializer s = new NetDataContractSerializer();
            XmlElement newElement = doc.CreateElement(elementName);
            MemoryStream stm = new MemoryStream();

            s.Serialize(stm, o);
            stm.Position = 0;
            StreamReader rdr = new StreamReader(stm);
            newElement.InnerXml = rdr.ReadToEnd();

            return newElement;
        }
    }
}
```
