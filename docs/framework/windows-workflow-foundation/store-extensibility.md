---
title: Extensibilidad de almacén
ms.date: 03/30/2017
ms.assetid: 7c3f4a46-4bac-4138-ae6a-a7c7ee0d28f5
ms.openlocfilehash: 0c6f67469db04705a9ac7827ef301ff226ea3bdb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465734"
---
# <a name="store-extensibility"></a><span data-ttu-id="06f86-102">Extensibilidad de almacén</span><span class="sxs-lookup"><span data-stu-id="06f86-102">Store Extensibility</span></span>

<span data-ttu-id="06f86-103"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> permite a los usuarios promover propiedades personalizadas, específicas de la aplicación que se pueden utilizar para consultar instancias en la base de datos de persistencia.</span><span class="sxs-lookup"><span data-stu-id="06f86-103"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> allows users to promote custom, application-specific properties that can be used to query for instances in the persistence database.</span></span> <span data-ttu-id="06f86-104">El acto de promover una propiedad hace que el valor esté disponible dentro de una vista especial en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="06f86-104">The act of promoting a property causes the value to be available within a special view in the database.</span></span> <span data-ttu-id="06f86-105">Estas propiedades promovidas (propiedades que se pueden usar en consultas de usuario) pueden ser de tipos simples como Int64, Guid, String y DateTime o de un tipo binario serializado (byte []).</span><span class="sxs-lookup"><span data-stu-id="06f86-105">These promoted properties (properties that can be used in user queries) can be of simple types such as Int64, Guid, String, and DateTime or of a serialized binary type (byte[]).</span></span>

<span data-ttu-id="06f86-106">La clase <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> tiene el método <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A> que puede usar para promover una propiedad que se puede usar en consultas.</span><span class="sxs-lookup"><span data-stu-id="06f86-106">The <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> class has the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A> method that you can use to promote a property as a property that can be used in queries.</span></span> <span data-ttu-id="06f86-107">El siguiente ejemplo es un ejemplo de un extremo a otro de extensibilidad del almacén.</span><span class="sxs-lookup"><span data-stu-id="06f86-107">The following example is an end-to-end example of store extensibility.</span></span>

1. <span data-ttu-id="06f86-108">En este escenario de ejemplo, una aplicación de procesamiento (DP) de documentos tiene flujos de trabajo, cada uno de los cuales usa actividades personalizadas para el procesamiento del documento.</span><span class="sxs-lookup"><span data-stu-id="06f86-108">In this example scenario, a document processing (DP) application has workflows, each of which uses custom activities for document processing.</span></span> <span data-ttu-id="06f86-109">Estos flujos de trabajo tienen un conjunto de variables de estado que deben hacerse visibles para el usuario final.</span><span class="sxs-lookup"><span data-stu-id="06f86-109">These workflows have a set of state variables that need to be made visible to the end user.</span></span> <span data-ttu-id="06f86-110">Para conseguirlo, la aplicación DP proporciona una extensión de instancia de tipo <xref:System.Activities.Persistence.PersistenceParticipant>, que las actividades usan para proporcionar variables de estado.</span><span class="sxs-lookup"><span data-stu-id="06f86-110">To achieve this, the DP application provides an instance extension of type <xref:System.Activities.Persistence.PersistenceParticipant>, which is used by activities to supply the state variables.</span></span>

    ```csharp
    class DocumentStatusExtension : PersistenceParticipant
    {
        public string DocumentId;
        public string ApprovalStatus;
        public string UserName;
        public DateTime LastUpdateTime;
    }
    ```

2. <span data-ttu-id="06f86-111">A continuación, la nueva extensión se agrega al host.</span><span class="sxs-lookup"><span data-stu-id="06f86-111">The new extension is then added to the host.</span></span>

    ```csharp
    static Activity workflow = CreateWorkflow();
    WorkflowApplication application = new WorkflowApplication(workflow);
    DocumentStatusExtension documentStatusExtension = new DocumentStatusExtension ();
    application.Extensions.Add(documentStatusExtension);
    ```

     <span data-ttu-id="06f86-112">Para obtener más información acerca de cómo agregar un participante de persistencia personalizado, consulte el [participantes de persistencia](../../../docs/framework/windows-workflow-foundation/persistence-participants.md) ejemplo.</span><span class="sxs-lookup"><span data-stu-id="06f86-112">For more details about adding a custom persistence participant, see the [Persistence Participants](../../../docs/framework/windows-workflow-foundation/persistence-participants.md) sample.</span></span>

3. <span data-ttu-id="06f86-113">Las actividades personalizadas en la aplicación DP rellenan varios campos de estado en el **Execute** método.</span><span class="sxs-lookup"><span data-stu-id="06f86-113">The custom activities in the DP application populate various status fields in the **Execute** method.</span></span>

    ```csharp
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

4. <span data-ttu-id="06f86-114">Cuando una instancia de flujo de trabajo alcanza un punto de persistencia, el **CollectValues** método de la **DocumentStatusExtension** participante de persistencia guarda estas propiedades en los datos de persistencia colección.</span><span class="sxs-lookup"><span data-stu-id="06f86-114">When a workflow instance reaches a persistence point, the **CollectValues** method of the **DocumentStatusExtension** persistence participant saves these properties into the persistence data collection.</span></span>

    ```csharp
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
    > <span data-ttu-id="06f86-115">Todas estas propiedades se pasan a **SqlWorkflowInstanceStore** por el marco de persistencia a través de la **SaveWorkflowCommand.InstanceData** colección.</span><span class="sxs-lookup"><span data-stu-id="06f86-115">All these properties are passed to **SqlWorkflowInstanceStore** by the persistence framework through the **SaveWorkflowCommand.InstanceData** collection.</span></span>

5. <span data-ttu-id="06f86-116">La aplicación DP inicializa el Store de instancia de flujo de trabajo de SQL e invoca el **promover** método para promover estos datos.</span><span class="sxs-lookup"><span data-stu-id="06f86-116">The DP application initializes the SQL Workflow Instance Store and invokes the **Promote** method to promote this data.</span></span>

    ```csharp
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

    <span data-ttu-id="06f86-117">Según esta información de promoción, **SqlWorkflowInstanceStore** coloca las propiedades de datos en las columnas de la [InstancePromotedProperties](#InstancePromotedProperties) vista.</span><span class="sxs-lookup"><span data-stu-id="06f86-117">Based on this promotion information, **SqlWorkflowInstanceStore** places the data properties in the columns of the [InstancePromotedProperties](#InstancePromotedProperties) view.</span></span>

6. <span data-ttu-id="06f86-118">Para consultar un subconjunto de datos en la tabla de promoción, la aplicación DP agrega una vista personalizada encima de la vista de promoción.</span><span class="sxs-lookup"><span data-stu-id="06f86-118">To query a subset of the data from the promotion table, the DP application adds a customized view on top of the promotion view.</span></span>

    ```sql
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

## <a name="InstancePromotedProperties"></a> <span data-ttu-id="06f86-119">[System.Activities.DurableInstancing.InstancePromotedProperties] view</span><span class="sxs-lookup"><span data-stu-id="06f86-119">[System.Activities.DurableInstancing.InstancePromotedProperties] view</span></span>

|<span data-ttu-id="06f86-120">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="06f86-120">Column Name</span></span>|<span data-ttu-id="06f86-121">Tipo de columna</span><span class="sxs-lookup"><span data-stu-id="06f86-121">Column Type</span></span>|<span data-ttu-id="06f86-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="06f86-122">Description</span></span>|
|-----------------|-----------------|-----------------|
|<span data-ttu-id="06f86-123">InstanceId</span><span class="sxs-lookup"><span data-stu-id="06f86-123">InstanceId</span></span>|<span data-ttu-id="06f86-124">GUID</span><span class="sxs-lookup"><span data-stu-id="06f86-124">GUID</span></span>|<span data-ttu-id="06f86-125">La instancia de flujo de trabajo a la que pertenece esta promoción.</span><span class="sxs-lookup"><span data-stu-id="06f86-125">The workflow instance that this promotion belongs to.</span></span>|
|<span data-ttu-id="06f86-126">PromotionName</span><span class="sxs-lookup"><span data-stu-id="06f86-126">PromotionName</span></span>|<span data-ttu-id="06f86-127">nvarchar(400)</span><span class="sxs-lookup"><span data-stu-id="06f86-127">nvarchar(400)</span></span>|<span data-ttu-id="06f86-128">El nombre de la propia promoción.</span><span class="sxs-lookup"><span data-stu-id="06f86-128">The name of the promotion itself.</span></span>|
|<span data-ttu-id="06f86-129">Value1, Value2, Value3..,Value32</span><span class="sxs-lookup"><span data-stu-id="06f86-129">Value1, Value2, Value3,..,Value32</span></span>|<span data-ttu-id="06f86-130">sql_variant</span><span class="sxs-lookup"><span data-stu-id="06f86-130">sql_variant</span></span>|<span data-ttu-id="06f86-131">El valor de la propia propiedad promovida.</span><span class="sxs-lookup"><span data-stu-id="06f86-131">The value of the promoted property itself.</span></span> <span data-ttu-id="06f86-132">La mayoría de los tipos de datos primitivos de SQL, excepto los blobs binarios, y las cadenas con más de 8000 bytes de longitud pueden adaptarse a sql_variant.</span><span class="sxs-lookup"><span data-stu-id="06f86-132">Most SQL primitive data types except binary blobs and strings over 8000 bytes in length can fit in sql_variant.</span></span>|
|<span data-ttu-id="06f86-133">Value33, Value34, Value35, …, Value64</span><span class="sxs-lookup"><span data-stu-id="06f86-133">Value33, Value34, Value35, …, Value64</span></span>|<span data-ttu-id="06f86-134">varbinary(max)</span><span class="sxs-lookup"><span data-stu-id="06f86-134">varbinary(max)</span></span>|<span data-ttu-id="06f86-135">El valor de propiedades promovidas que se declaran explícitamente como varbinary(max).</span><span class="sxs-lookup"><span data-stu-id="06f86-135">The value of promoted properties that are explicitly declared as varbinary(max).</span></span>|
