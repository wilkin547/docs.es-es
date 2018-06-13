---
title: Extensibilidad de almacén
ms.date: 03/30/2017
ms.assetid: 7c3f4a46-4bac-4138-ae6a-a7c7ee0d28f5
ms.openlocfilehash: 8cfbf96256d4b8416beb526875a1e9ac09c3bfbb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517925"
---
# <a name="store-extensibility"></a>Extensibilidad de almacén
<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> permite a los usuarios promover propiedades personalizadas, específicas de la aplicación que se pueden utilizar para consultar instancias en la base de datos de persistencia. El acto de promover una propiedad hace que el valor esté disponible dentro de una vista especial en la base de datos. Estas propiedades promovidas (propiedades que se pueden usar en consultas de usuario) pueden ser de tipos simples como Int64, Guid, String y DateTime o de un tipo binario serializado (byte []).  
  
 La clase <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> tiene el método <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A> que puede usar para promover una propiedad que se puede usar en consultas. El siguiente ejemplo es un ejemplo de un extremo a otro de extensibilidad del almacén.  
  
1.  En este escenario de ejemplo, una aplicación de procesamiento (DP) de documentos tiene flujos de trabajo, cada uno de los cuales usa actividades personalizadas para el procesamiento del documento. Estos flujos de trabajo tienen un conjunto de variables de estado que deben hacerse visibles para el usuario final. Para conseguirlo, la aplicación DP proporciona una extensión de instancia de tipo <xref:System.Activities.Persistence.PersistenceParticipant>, que las actividades usan para proporcionar variables de estado.  
  
    ```  
    class DocumentStatusExtension : PersistenceParticipant  
    {  
        public string DocumentId;  
        public string ApprovalStatus;  
        public string UserName;  
        public DateTime LastUpdateTime;  
    }  
    ```  
  
2.  A continuación, la nueva extensión se agrega al host.  
  
    ```  
    static Activity workflow = CreateWorkflow();  
    WorkflowApplication application = new WorkflowApplication(workflow);  
    DocumentStatusExtension documentStatusExtension = new DocumentStatusExtension ();  
    application.Extensions.Add(documentStatusExtension);  
    ```  
  
     Para obtener más información acerca de cómo agregar un participante de persistencia personalizado, consulte el [participantes de persistencia](../../../docs/framework/windows-workflow-foundation/persistence-participants.md) ejemplo.  
  
3.  Las actividades personalizadas en la aplicación DP rellenan varios campos de estado en el **Execute** método.  
  
    ```  
    public override void Execute(CodeActivityContext context)  
    {  
        // ...  
        context.GetExtension<DocumentStatusExtension>().DocumentId = Guid.NewGuid();  
        context.GetExtension<DocumentStatusExtension>().UserName = "John Smith";  
        context.GetExtension<DocumentStatusExtension>().ApprovalStatus = "Approved";  
        context.GetExtension<DocumentStatusExtension>().LastUpdateTime = DateTime.Now();  
        // ...  
    }  
    ```  
  
4.  Cuando una instancia de flujo de trabajo alcanza un punto de persistencia, el **CollectValues** método de la **DocumentStatusExtension** participante de persistencia guarda estas propiedades en los datos de persistencia colección.  
  
    ```  
    class DocumentStatusExtension : PersistenceParticipant  
    {  
        const XNamespace xNS = XNamespace.Get("http://contoso.com/DocumentStatus");  
  
        protected override void CollectValues(out IDictionary<XName, object> readWriteValues, out IDictionary<XName, object> writeOnlyValues)  
        {  
            readWriteValues = new Dictionary<XName, object>();  
            readWriteValues.Add(xNS.GetName("UserName"), this.UserName);  
            readWriteValues.Add(xNS.GetName("ApprovalStatus"), this.ApprovalStatus);  
            readWriteValues.Add(xNS.GetName("DocumentId"), this.DocumentId);  
            readWriteValues.Add(xNS.GetName("LastModifiedTime"), this.LastUpdateTime);  
  
            writeOnlyValues = null;  
        }  
        // ...  
    }  
    ```  
  
    > [!NOTE]
    >  Todas estas propiedades se pasan a **SqlWorkflowInstanceStore** mediante el marco de persistencia a través de la **SaveWorkflowCommand.InstanceData** colección.  
  
5.  La aplicación DP inicializa el almacén de instancias de flujo de trabajo de SQL e invoca el **promover** método para promover estos datos.  
  
    ```  
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);  
  
    List<XName> variantProperties = new List<XName>()   
    {   
        xNS.GetName("UserName"),   
        xNS.GetName("ApprovalStatus"),   
        xNS.GetName("DocumentId"),   
        xNS.GetName("LastModifiedTime")   
    };  
  
    store.Promote("DocumentStatus", variantProperties, null);  
    ```  
  
     En función de esta información de promociones, **SqlWorkflowInstanceStore** coloca las propiedades de datos en las columnas de la [InstancePromotedProperties](#InstancePromotedProperties) vista.
  
6.  Para consultar un subconjunto de datos en la tabla de promoción, la aplicación DP agrega una vista personalizada encima de la vista de promoción.  
  
    ```  
    create view [dbo].[DocumentStatus] with schemabinding  
    as  
        select  P.[InstanceId] as [InstanceId],  
            P.Value1 as [UserName],  
            P.Value2 as [ApprovalStatus],  
            P.Value3 as [DocumentId],  
            P.Value4 as [LastUpdatedTime]  
    from [System.Activities.DurableInstancing].[InstancePromotedProperties] as P  
    where P.PromotionName = N'DocumentStatus'  
    go  
    ```  
  
##  <a name="InstancePromotedProperties"></a> Vista [System.Activities.DurableInstancing.InstancePromotedProperties]  
  
|Nombre de columna|Tipo de columna|Descripción|  
|-----------------|-----------------|-----------------|  
|InstanceId|GUID|La instancia de flujo de trabajo a la que pertenece esta promoción.|  
|PromotionName|nvarchar(400)|El nombre de la propia promoción.|  
|Value1, Value2, Value3..,Value32|sql_variant|El valor de la propia propiedad promovida. La mayoría de los tipos de datos primitivos de SQL, excepto los blobs binarios, y las cadenas con más de 8000 bytes de longitud pueden adaptarse a sql_variant.|  
|Value33, Value34, Value35, …, Value64|varbinary(max)|El valor de propiedades promovidas que se declaran explícitamente como varbinary(max).|
