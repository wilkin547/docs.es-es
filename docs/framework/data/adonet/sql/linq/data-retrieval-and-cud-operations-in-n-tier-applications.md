---
description: Más información acerca de las operaciones de recuperación de datos y CUD en aplicaciones de N niveles (LINQ to SQL)
title: Recuperación de datos y operaciones CUD en aplicaciones de n niveles (LINQ to SQL)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c3133d53-83ed-4a4d-af8b-82edcf3831db
ms.openlocfilehash: dbad65e1bd29227f434166dca364946a68256177
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672171"
---
# <a name="data-retrieval-and-cud-operations-in-n-tier-applications-linq-to-sql"></a><span data-ttu-id="da2d6-103">Recuperación de datos y operaciones CUD en aplicaciones de n niveles (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="da2d6-103">Data Retrieval and CUD Operations in N-Tier Applications (LINQ to SQL)</span></span>

<span data-ttu-id="da2d6-104">Al serializar objetos entidad, como Clientes o Pedidos, con destino a un cliente a través de una red, esas entidades se desasocian de su contexto de datos.</span><span class="sxs-lookup"><span data-stu-id="da2d6-104">When you serialize entity objects such as Customers or Orders to a client over a network, those entities are detached from their data context.</span></span> <span data-ttu-id="da2d6-105">El contexto de datos ya no realiza un seguimiento de sus cambios o sus asociaciones con otros objetos.</span><span class="sxs-lookup"><span data-stu-id="da2d6-105">The data context no longer tracks their changes or their associations with other objects.</span></span> <span data-ttu-id="da2d6-106">Esto no constituye un problema mientras los clientes solo estén leyendo los datos.</span><span class="sxs-lookup"><span data-stu-id="da2d6-106">This is not an issue as long as the clients are only reading the data.</span></span> <span data-ttu-id="da2d6-107">También es relativamente sencillo permitir a los clientes agregar nuevas filas a una base de datos.</span><span class="sxs-lookup"><span data-stu-id="da2d6-107">It is also relatively simple to enable clients to add new rows to a database.</span></span> <span data-ttu-id="da2d6-108">Sin embargo, si su aplicación requiere que los clientes pueden actualizar o eliminar datos, deberá asociar las entidades a un nuevo contexto de datos antes de llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="da2d6-108">However, if your application requires that clients be able to update or delete data, then you must attach the entities to a new data context before you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="da2d6-109">Además, si está utilizando una comprobación de simultaneidad optimista con valores originales, también necesitará un medio para proporcionar a la base de datos la entidad original y la entidad modificada.</span><span class="sxs-lookup"><span data-stu-id="da2d6-109">In addition, if you are using an optimistic concurrency check with original values, then you will also need a way to provide the database both the original entity and the entity as modified.</span></span> <span data-ttu-id="da2d6-110">Los métodos `Attach` se utilizan para colocar las entidades en un nuevo contexto de datos después de haber sido desasociadas.</span><span class="sxs-lookup"><span data-stu-id="da2d6-110">The `Attach` methods are provided to enable you to put entities into a new data context after they have been detached.</span></span>  
  
 <span data-ttu-id="da2d6-111">Incluso si está serializando objetos proxy en lugar de las [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] entidades, todavía tiene que construir una entidad en la capa de acceso a datos (dal) y asociarla a un nuevo para <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> enviar los datos a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="da2d6-111">Even if you are serializing proxy objects in place of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] entities, you still have to construct an entity on the data access layer (DAL), and attach it to a new <xref:System.Data.Linq.DataContext?displayProperty=nameWithType>, in order to submit the data to the database.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="da2d6-112">es completamente diferente de cómo se serializan las entidades.</span><span class="sxs-lookup"><span data-stu-id="da2d6-112">is completely indifferent about how entities are serialized.</span></span> <span data-ttu-id="da2d6-113">Para obtener más información sobre cómo usar las herramientas Object Relational Designer y SQLMetal para generar clases que se pueden serializar mediante Windows Communication Foundation (WCF), consulte [Cómo: hacer que las entidades sean serializables](how-to-make-entities-serializable.md).</span><span class="sxs-lookup"><span data-stu-id="da2d6-113">For more information about how to use the Object Relational Designer and SQLMetal tools to generate classes that are serializable by using Windows Communication Foundation (WCF), see [How to: Make Entities Serializable](how-to-make-entities-serializable.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da2d6-114">Solo llame a los métodos `Attach` para entidades nuevas o deserializadas.</span><span class="sxs-lookup"><span data-stu-id="da2d6-114">Only call the `Attach` methods on new or deserialized entities.</span></span> <span data-ttu-id="da2d6-115">La única manera de desasociar una entidad de su contexto de datos original es deserializarla.</span><span class="sxs-lookup"><span data-stu-id="da2d6-115">The only way for an entity to be detached from its original data context is for it to be serialized.</span></span> <span data-ttu-id="da2d6-116">Si intenta asociar una entidad no desasociada a un nuevo contexto de datos, y esa entidad todavía tiene cargadores diferidos procedentes de su contexto de datos anterior, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="da2d6-116">If you try to attach an undetached entity to a new data context, and that entity still has deferred loaders from its previous data context, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] will thrown an exception.</span></span> <span data-ttu-id="da2d6-117">Una entidad con cargadores diferidos de dos contextos de datos diferentes podría producir resultados no deseados al realizar operaciones de inserción, actualización y eliminación sobre esa entidad.</span><span class="sxs-lookup"><span data-stu-id="da2d6-117">An entity with deferred loaders from two different data contexts could cause unwanted results when you perform insert, update, and delete operations on that entity.</span></span> <span data-ttu-id="da2d6-118">Para obtener más información sobre los cargadores diferidos, vea [carga aplazada frente a carga inmediata](deferred-versus-immediate-loading.md).</span><span class="sxs-lookup"><span data-stu-id="da2d6-118">For more information about deferred loaders, see [Deferred versus Immediate Loading](deferred-versus-immediate-loading.md).</span></span>  
  
## <a name="retrieving-data"></a><span data-ttu-id="da2d6-119">Recuperación de datos</span><span class="sxs-lookup"><span data-stu-id="da2d6-119">Retrieving Data</span></span>  
  
### <a name="client-method-call"></a><span data-ttu-id="da2d6-120">Llamada a método del cliente</span><span class="sxs-lookup"><span data-stu-id="da2d6-120">Client Method Call</span></span>  

 <span data-ttu-id="da2d6-121">Los ejemplos siguientes muestran un ejemplo de llamada a método en la capa DAL desde un cliente de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="da2d6-121">The following examples show a sample method call to the DAL from a Windows Forms client.</span></span> <span data-ttu-id="da2d6-122">En este ejemplo, la capa DAL se implementa como una Biblioteca de servicios de Windows:</span><span class="sxs-lookup"><span data-stu-id="da2d6-122">In this example, the DAL is implemented as a Windows Service Library:</span></span>  
  
```vb  
Private Function GetProdsByCat_Click(ByVal sender As Object, ByVal e _  
    As EventArgs)  
  
    ' Create the WCF client proxy.  
    Dim proxy As New NorthwindServiceReference.Service1Client  
  
    ' Call the method on the service.  
    Dim products As NorthwindServiceReference.Product() = _  
        proxy.GetProductsByCategory(1)  
  
    ' If the database uses original values for concurrency checks,  
    ' the client needs to store them and pass them back to the  
    ' middle tier along with the new values when updating data.  
  
    For Each v As NorthwindClient1.NorthwindServiceReference.Product _  
        In products  
        ' Persist to a List(Of Product) declared at class scope.  
        ' Additional change-tracking logic is the responsibility  
        ' of the presentation tier and/or middle tier.  
        originalProducts.Add(v)  
    Next  
  
    ' (Not shown) Bind the products list to a control  
    ' and/or perform whatever processing is necessary.  
End Function  
```  
  
```csharp  
private void GetProdsByCat_Click(object sender, EventArgs e)  
{  
    // Create the WCF client proxy.  
    NorthwindServiceReference.Service1Client proxy =
    new NorthwindClient.NorthwindServiceReference.Service1Client();  
  
    // Call the method on the service.  
    NorthwindServiceReference.Product[] products =
    proxy.GetProductsByCategory(1);  
  
    // If the database uses original values for concurrency checks,
    // the client needs to store them and pass them back to the
    // middle tier along with the new values when updating data.  
    foreach (var v in products)  
    {  
        // Persist to a list<Product> declared at class scope.  
        // Additional change-tracking logic is the responsibility  
        // of the presentation tier and/or middle tier.  
        originalProducts.Add(v);  
    }  
  
    // (Not shown) Bind the products list to a control  
    // and/or perform whatever processing is necessary.  
    }  
```  
  
### <a name="middle-tier-implementation"></a><span data-ttu-id="da2d6-123">Implementación del nivel intermedio</span><span class="sxs-lookup"><span data-stu-id="da2d6-123">Middle Tier Implementation</span></span>  

 <span data-ttu-id="da2d6-124">El ejemplo siguiente muestra una implementación del método de interfaz en el nivel intermedio.</span><span class="sxs-lookup"><span data-stu-id="da2d6-124">The following example shows an implementation of the interface method on the middle tier.</span></span> <span data-ttu-id="da2d6-125">Deberá tener en cuenta los dos puntos principales siguientes:</span><span class="sxs-lookup"><span data-stu-id="da2d6-125">The following are the two main points to note:</span></span>  
  
- <span data-ttu-id="da2d6-126">El objeto <xref:System.Data.Linq.DataContext> se declara en el ámbito del método.</span><span class="sxs-lookup"><span data-stu-id="da2d6-126">The <xref:System.Data.Linq.DataContext> is declared at method scope.</span></span>  
  
- <span data-ttu-id="da2d6-127">El método devuelve una colección <xref:System.Collections.IEnumerable> de los resultados reales.</span><span class="sxs-lookup"><span data-stu-id="da2d6-127">The method returns an <xref:System.Collections.IEnumerable> collection of the actual results.</span></span> <span data-ttu-id="da2d6-128">El serializador ejecutará la consulta para devolver los resultados al nivel de presentación o cliente.</span><span class="sxs-lookup"><span data-stu-id="da2d6-128">The serializer will execute the query to send the results back to the client/presentation tier.</span></span> <span data-ttu-id="da2d6-129">Para obtener acceso localmente a los resultados de la consulta en el nivel intermedio, puede forzar la ejecución llamando a `ToList` o `ToArray` para la variable de consulta.</span><span class="sxs-lookup"><span data-stu-id="da2d6-129">To access the query results locally on the middle tier, you can force execution by calling `ToList` or `ToArray` on the query variable.</span></span> <span data-ttu-id="da2d6-130">A continuación, puede devolver esa lista o matriz como un `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="da2d6-130">You can then return that list or array as an `IEnumerable`.</span></span>  
  
```vb  
Public Function GetProductsByCategory(ByVal categoryID As Integer) _  
    As IEnumerable(Of Product)  
  
    Dim db As New NorthwindClasses1DataContext(connectionString)  
    Dim productQuery = _  
    From prod In db.Products _  
    Where prod.CategoryID = categoryID _  
    Select prod  
  
    Return productQuery.AsEnumerable()  
  
End Function  
```  
  
```csharp  
public IEnumerable<Product> GetProductsByCategory(int categoryID)  
{  
    NorthwindClasses1DataContext db =
    new NorthwindClasses1DataContext(connectionString);  
  
    IEnumerable<Product> productQuery =  
    from prod in db.Products  
    where prod.CategoryID == categoryID  
    select prod;  
  
    return productQuery.AsEnumerable();
}  
```  
  
 <span data-ttu-id="da2d6-131">Una instancia de un contexto de datos debería tener la duración de una "unidad de trabajo".</span><span class="sxs-lookup"><span data-stu-id="da2d6-131">An instance of a data context should have a lifetime of one "unit of work."</span></span> <span data-ttu-id="da2d6-132">En un entorno débilmente acoplado, una unidad de trabajo es generalmente pequeña, quizá una transacción optimista, incluida una única llamada a `SubmitChanges`.</span><span class="sxs-lookup"><span data-stu-id="da2d6-132">In a loosely-coupled environment, a unit of work is typically small, perhaps one optimistic transaction, including a single call to `SubmitChanges`.</span></span> <span data-ttu-id="da2d6-133">Por consiguiente, el contexto de los datos se crea y se deshace en el ámbito del método.</span><span class="sxs-lookup"><span data-stu-id="da2d6-133">Therefore, the data context is created and disposed at method scope.</span></span> <span data-ttu-id="da2d6-134">Si la unidad de trabajo incluye llamadas a la lógica de reglas de empresa, entonces generalmente deseará mantener la instancia de `DataContext` para esa operación completa.</span><span class="sxs-lookup"><span data-stu-id="da2d6-134">If the unit of work includes calls to business rules logic, then generally you will want to keep the `DataContext` instance for that whole operation.</span></span> <span data-ttu-id="da2d6-135">En cualquier caso, las instancias de `DataContext` no deberían mantenerse activas durante largos períodos de tiempo a lo largo de un número arbitrario de transacciones.</span><span class="sxs-lookup"><span data-stu-id="da2d6-135">In any case, `DataContext` instances are not intended to be kept alive for long periods of time across arbitrary numbers of transactions.</span></span>  
  
 <span data-ttu-id="da2d6-136">Este método devolverá objetos Product, pero no la colección de los objetos Order_Detail asociados a cada objeto Product.</span><span class="sxs-lookup"><span data-stu-id="da2d6-136">This method will return Product objects but not the collection of Order_Detail objects that are associated with each Product.</span></span> <span data-ttu-id="da2d6-137">Use el objeto <xref:System.Data.Linq.DataLoadOptions> para cambiar este comportamiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="da2d6-137">Use the <xref:System.Data.Linq.DataLoadOptions> object to change this default behavior.</span></span> <span data-ttu-id="da2d6-138">Para obtener más información, vea [Cómo: controlar la cantidad de datos relacionados que se recuperan](how-to-control-how-much-related-data-is-retrieved.md).</span><span class="sxs-lookup"><span data-stu-id="da2d6-138">For more information, see [How to: Control How Much Related Data Is Retrieved](how-to-control-how-much-related-data-is-retrieved.md).</span></span>  
  
## <a name="inserting-data"></a><span data-ttu-id="da2d6-139">Insertar datos</span><span class="sxs-lookup"><span data-stu-id="da2d6-139">Inserting Data</span></span>  

 <span data-ttu-id="da2d6-140">Para insertar un nuevo objeto, el nivel de presentación simplemente llama al método pertinente en la interfaz de nivel intermedio y pasa el nuevo objeto que se va a insertar.</span><span class="sxs-lookup"><span data-stu-id="da2d6-140">To insert a new object, the presentation tier just calls the relevant method on the middle tier interface, and passes in the new object to insert.</span></span> <span data-ttu-id="da2d6-141">En algunos casos, puede ser más eficiente para el cliente pasar solo algunos valores y hacer que el nivel intermedio construya el objeto completo.</span><span class="sxs-lookup"><span data-stu-id="da2d6-141">In some cases, it may be more efficient for the client to pass in only some values and have the middle tier construct the full object.</span></span>  
  
### <a name="middle-tier-implementation"></a><span data-ttu-id="da2d6-142">Implementación del nivel intermedio</span><span class="sxs-lookup"><span data-stu-id="da2d6-142">Middle Tier Implementation</span></span>  

 <span data-ttu-id="da2d6-143">En el nivel intermedio, se crea un nuevo <xref:System.Data.Linq.DataContext>, se asocia el objeto al <xref:System.Data.Linq.DataContext> mediante el método <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>, y se inserta el objeto al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="da2d6-143">On the middle tier, a new <xref:System.Data.Linq.DataContext> is created, the object is attached to the <xref:System.Data.Linq.DataContext> by using the <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> method, and the object is inserted when <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called.</span></span> <span data-ttu-id="da2d6-144">Se pueden administrar excepciones, devoluciones de llamada y condiciones de error al igual que en cualquier otro escenario de servicio Web.</span><span class="sxs-lookup"><span data-stu-id="da2d6-144">Exceptions, callbacks, and error conditions can be handled just as in any other Web service scenario.</span></span>  
  
```vb  
' No call to Attach is necessary for inserts.  
Public Sub InsertOrder(ByVal o As Order)  
  
    Dim db As New NorthwindClasses1DataContext(connectionString)  
    db.Orders.InsertOnSubmit(o)  
  
    ' Exception handling not shown.  
    db.SubmitChanges()  
  
End Sub  
```  
  
```csharp  
// No call to Attach is necessary for inserts.  
    public void InsertOrder(Order o)  
    {  
        NorthwindClasses1DataContext db = new NorthwindClasses1DataContext(connectionString);  
        db.Orders.InsertOnSubmit(o);  
  
        // Exception handling not shown.  
        db.SubmitChanges();  
    }  
```  
  
## <a name="deleting-data"></a><span data-ttu-id="da2d6-145">Eliminar datos</span><span class="sxs-lookup"><span data-stu-id="da2d6-145">Deleting Data</span></span>  

 <span data-ttu-id="da2d6-146">Para eliminar un objeto existente de la base de datos, el nivel de presentación llama al método pertinente en la interfaz de nivel intermedio y pasa su copia que incluye los valores originales del objeto que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="da2d6-146">To delete an existing object from the database, the presentation tier calls the relevant method on the middle tier interface, and passes in its copy that includes original values of the object to be deleted.</span></span>  
  
 <span data-ttu-id="da2d6-147">Las operaciones de eliminación implican comprobaciones de simultaneidad optimista, y el objeto que se va a eliminar debe estar primero asociado al nuevo contexto de datos.</span><span class="sxs-lookup"><span data-stu-id="da2d6-147">Delete operations involve optimistic concurrency checks, and the object to be deleted must first be attached to the new data context.</span></span> <span data-ttu-id="da2d6-148">En este ejemplo, el parámetro `Boolean` está establecido en `false` para indicar que el objeto no tiene marca de tiempo (RowVersion).</span><span class="sxs-lookup"><span data-stu-id="da2d6-148">In this example, the `Boolean` parameter is set to `false` to indicate that the object does not have a timestamp (RowVersion).</span></span> <span data-ttu-id="da2d6-149">Si la tabla de la base de datos genera marcas de tiempo para cada registro, entonces las comprobaciones de simultaneidad son mucho más simples, sobre todo para el cliente.</span><span class="sxs-lookup"><span data-stu-id="da2d6-149">If your database table does generate timestamps for each record, then concurrency checks are much simpler, especially for the client.</span></span> <span data-ttu-id="da2d6-150">Simplemente pase el objeto original o el objeto modificado y establezca el parámetro `Boolean` en `true`.</span><span class="sxs-lookup"><span data-stu-id="da2d6-150">Just pass in either the original or modified object and set the `Boolean` parameter to `true`.</span></span> <span data-ttu-id="da2d6-151">En cualquier caso, en el nivel intermedio es necesario generalmente capturar la excepción <xref:System.Data.Linq.ChangeConflictException>.</span><span class="sxs-lookup"><span data-stu-id="da2d6-151">In any case, on the middle tier it is typically necessary to catch the <xref:System.Data.Linq.ChangeConflictException>.</span></span> <span data-ttu-id="da2d6-152">Para obtener más información sobre cómo controlar los conflictos de simultaneidad optimista, vea [simultaneidad optimista: información general](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da2d6-152">For more information about how to handle optimistic concurrency conflicts, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
 <span data-ttu-id="da2d6-153">Al eliminar entidades que tienen restricciones de clave externa sobre tablas asociadas, deberá eliminar primero todos los objetos en sus colecciones <xref:System.Data.Linq.EntitySet%601>.</span><span class="sxs-lookup"><span data-stu-id="da2d6-153">When deleting entities that have foreign key constraints on associated tables, you must first delete all the objects in its <xref:System.Data.Linq.EntitySet%601> collections.</span></span>  
  
```vb  
' Attach is necessary for deletes.  
Public Sub DeleteOrder(ByVal order As Order)  
    Dim db As New NorthwindClasses1DataContext(connectionString)  
  
    db.Orders.Attach(order, False)  
    ' This will throw an exception if the order has order details.  
    db.Orders.DeleteOnSubmit(order)  
  
    Try  
        ' ConflictMode is an optional parameter.  
        db.SubmitChanges(ConflictMode.ContinueOnConflict)  
  
    Catch ex As ChangeConflictException  
        ' Get conflict information, and take actions  
        ' that are appropriate for your application.  
        ' See MSDN Article "How to: Manage Change  
        ' Conflicts (LINQ to SQL).  
  
    End Try  
End Sub  
```  
  
```csharp  
// Attach is necessary for deletes.  
public void DeleteOrder(Order order)  
{  
    NorthwindClasses1DataContext db = new NorthwindClasses1DataContext(connectionString);  
  
    db.Orders.Attach(order, false);  
    // This will throw an exception if the order has order details.  
    db.Orders.DeleteOnSubmit(order);  
    try  
    {  
        // ConflictMode is an optional parameter.  
        db.SubmitChanges(ConflictMode.ContinueOnConflict);  
    }  
    catch (ChangeConflictException e)  
    {  
       // Get conflict information, and take actions  
       // that are appropriate for your application.  
       // See MSDN Article How to: Manage Change Conflicts (LINQ to SQL).  
    }  
}  
```  
  
## <a name="updating-data"></a><span data-ttu-id="da2d6-154">Actualización de datos</span><span class="sxs-lookup"><span data-stu-id="da2d6-154">Updating Data</span></span>  

 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="da2d6-155">admite actualizaciones en estos escenarios que presentan simultaneidad optimista:</span><span class="sxs-lookup"><span data-stu-id="da2d6-155">supports updates in these scenarios involving optimistic concurrency:</span></span>  
  
- <span data-ttu-id="da2d6-156">Simultaneidad optimista basada en marcas de tiempo o números RowVersion.</span><span class="sxs-lookup"><span data-stu-id="da2d6-156">Optimistic concurrency based on timestamps or RowVersion numbers.</span></span>  
  
- <span data-ttu-id="da2d6-157">Simultaneidad optimista basada en valores originales de un subconjunto de propiedades de entidad.</span><span class="sxs-lookup"><span data-stu-id="da2d6-157">Optimistic concurrency based on original values of a subset of entity properties.</span></span>  
  
- <span data-ttu-id="da2d6-158">Simultaneidad optimista basada en las entidades completas originales y modificadas.</span><span class="sxs-lookup"><span data-stu-id="da2d6-158">Optimistic concurrency based on the complete original and modified entities.</span></span>  
  
 <span data-ttu-id="da2d6-159">Puede también realizar actualizaciones o eliminaciones conjuntas sobre una entidad y sus relaciones; por ejemplo, un Cliente y una colección de sus objetos Pedido asociados.</span><span class="sxs-lookup"><span data-stu-id="da2d6-159">You can also perform updates or deletes on an entity together with its relations, for example a Customer and a collection of its associated Order objects.</span></span> <span data-ttu-id="da2d6-160">Cuando realiza modificaciones sobre el cliente en un grafo de objetos entidad y sus colecciones (`EntitySet`) secundarias, y las comprobaciones de simultaneidad optimista requieren valores originales, el cliente debe proporcionar esos valores originales para cada entidad y cada objeto <xref:System.Data.Linq.EntitySet%601>.</span><span class="sxs-lookup"><span data-stu-id="da2d6-160">When you make modifications on the client to a graph of entity objects and their child (`EntitySet`) collections, and the optimistic concurrency checks require original values, the client must provide those original values for each entity and <xref:System.Data.Linq.EntitySet%601> object.</span></span> <span data-ttu-id="da2d6-161">Si desea permitir a los clientes realizar, en una única llamada al método, un conjunto de actualizaciones, eliminaciones e inserciones relacionadas, deberá proporcionar al cliente una manera de indicar qué tipo de operación va a realizar sobre cada entidad.</span><span class="sxs-lookup"><span data-stu-id="da2d6-161">If you want to enable clients to make a set of related updates, deletes, and insertions in a single method call, you must provide the client a way to indicate what type of operation to perform on each entity.</span></span> <span data-ttu-id="da2d6-162">En el nivel intermedio, deberá llamar al método <xref:System.Data.Linq.ITable.Attach%2A> apropiado y, a continuación, a <xref:System.Data.Linq.ITable.InsertOnSubmit%2A>, <xref:System.Data.Linq.ITable.DeleteAllOnSubmit%2A> o <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> (sin `Attach`, para las inserciones) para cada entidad antes de llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="da2d6-162">On the middle tier, you then must call the appropriate <xref:System.Data.Linq.ITable.Attach%2A> method and then <xref:System.Data.Linq.ITable.InsertOnSubmit%2A>, <xref:System.Data.Linq.ITable.DeleteAllOnSubmit%2A>, or <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> (without `Attach`, for insertions) for each entity before you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span> <span data-ttu-id="da2d6-163">No recupere datos de la base de datos como una manera de obtener valores originales antes de probar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="da2d6-163">Do not retrieve data from the database as a way to obtain original values before you try updates.</span></span>  
  
 <span data-ttu-id="da2d6-164">Para obtener más información sobre la simultaneidad optimista, vea [simultaneidad optimista: información general](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="da2d6-164">For more information about optimistic concurrency, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span> <span data-ttu-id="da2d6-165">Para obtener información detallada sobre cómo resolver conflictos de cambios de simultaneidad optimista, vea [Cómo: administrar conflictos de cambios](how-to-manage-change-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="da2d6-165">For detailed information about resolving optimistic concurrency change conflicts, see [How to: Manage Change Conflicts](how-to-manage-change-conflicts.md).</span></span>  
  
 <span data-ttu-id="da2d6-166">Los ejemplos siguientes explican los distintos escenarios:</span><span class="sxs-lookup"><span data-stu-id="da2d6-166">The following examples demonstrate each scenario:</span></span>  
  
### <a name="optimistic-concurrency-with-timestamps"></a><span data-ttu-id="da2d6-167">Simultaneidad optimista con marcas de tiempo</span><span class="sxs-lookup"><span data-stu-id="da2d6-167">Optimistic concurrency with timestamps</span></span>  
  
```vb  
' Assume that "customer" has been sent by client.  
' Attach with "true" to say this is a modified entity  
' and it can be checked for optimistic concurrency  
' because it has a column that is marked with the  
' "RowVersion" attribute.  
  
db.Customers.Attach(customer, True)  
  
Try  
    ' Optional: Specify a ConflictMode value  
    ' in call to SubmitChanges.  
    db.SubmitChanges()  
Catch ex As ChangeConflictException  
    ' Handle conflict based on options provided.  
    ' See MSDN article "How to: Manage Change  
    ' Conflicts (LINQ to SQL)".  
End Try  
```  
  
```csharp  
// Assume that "customer" has been sent by client.  
// Attach with "true" to say this is a modified entity  
// and it can be checked for optimistic concurrency because  
//  it has a column that is marked with "RowVersion" attribute  
db.Customers.Attach(customer, true)  
try  
{  
    // Optional: Specify a ConflictMode value  
    // in call to SubmitChanges.  
    db.SubmitChanges();  
}  
catch(ChangeConflictException e)  
{  
    // Handle conflict based on options provided  
    // See MSDN article How to: Manage Change Conflicts (LINQ to SQL).  
}  
```  
  
### <a name="with-subset-of-original-values"></a><span data-ttu-id="da2d6-168">Con subconjunto de valores originales</span><span class="sxs-lookup"><span data-stu-id="da2d6-168">With Subset of Original Values</span></span>  

 <span data-ttu-id="da2d6-169">En este enfoque, el cliente devuelve el objeto completo serializado, junto con los valores que se van a modificar.</span><span class="sxs-lookup"><span data-stu-id="da2d6-169">In this approach, the client returns the complete serialized object, together with the values to be modified.</span></span>  
  
```vb  
Public Sub UpdateProductInventory(ByVal p As Product, ByVal _  
    unitsInStock As Short?, ByVal unitsOnOrder As Short?)  
  
    Using db As New NorthwindClasses1DataContext(connectionString)  
        ' p is the original unmodified product  
        ' that was obtained from the database.  
        ' The client kept a copy and returns it now.  
        db.Products.Attach(p, False)  
  
        ' Now that the original values are in the data context,  
        ' apply the changes.  
        p.UnitsInStock = unitsInStock  
        p.UnitsOnOrder = unitsOnOrder  
  
        Try  
            ' Optional: Specify a ConflictMode value  
            ' in call to SubmitChanges.  
            db.SubmitChanges()  
  
        Catch ex As Exception  
            ' Handle conflict based on options provided.  
            ' See MSDN article "How to: Manage Change Conflicts  
            ' (LINQ to SQL)".  
        End Try  
    End Using  
End Sub  
```  
  
```csharp  
public void UpdateProductInventory(Product p, short? unitsInStock, short? unitsOnOrder)  
{  
    using (NorthwindClasses1DataContext db = new NorthwindClasses1DataContext(connectionString))  
    {  
        // p is the original unmodified product  
        // that was obtained from the database.  
        // The client kept a copy and returns it now.  
        db.Products.Attach(p, false);  
  
        // Now that the original values are in the data context, apply the changes.  
        p.UnitsInStock = unitsInStock;  
        p.UnitsOnOrder = unitsOnOrder;  
        try  
        {  
             // Optional: Specify a ConflictMode value  
             // in call to SubmitChanges.  
             db.SubmitChanges();  
        }  
        catch (ChangeConflictException e)  
        {  
            // Handle conflict based on provided options.  
            // See MSDN article How to: Manage Change Conflicts  
            // (LINQ to SQL).  
        }  
    }  
}  
```  
  
### <a name="with-complete-entities"></a><span data-ttu-id="da2d6-170">Con entidades completas</span><span class="sxs-lookup"><span data-stu-id="da2d6-170">With Complete Entities</span></span>  
  
```vb  
Public Sub UpdateProductInfo(ByVal newProd As Product, ByVal _  
    originalProd As Product)  
  
    Using db As New NorthwindClasses1DataContext(connectionString)  
        db.Products.Attach(newProd, originalProd)  
  
        Try  
            ' Optional: Specify a ConflictMode value  
            ' in call to SubmitChanges.  
            db.SubmitChanges()  
  
        Catch ex As Exception  
            ' Handle potential change conflicgt in whatever way  
            ' is appropriate for your application.  
            ' For more information, see the MSDN article  
            ' "How to: Manage Change Conflicts (LINQ to  
            ' SQL)".  
        End Try  
  
    End Using  
End Sub  
```  
  
```csharp  
public void UpdateProductInfo(Product newProd, Product originalProd)  
{  
     using (NorthwindClasses1DataContext db = new  
        NorthwindClasses1DataContext(connectionString))  
     {  
         db.Products.Attach(newProd, originalProd);  
         try  
         {  
               // Optional: Specify a ConflictMode value  
               // in call to SubmitChanges.  
               db.SubmitChanges();  
         }  
        catch (ChangeConflictException e)  
        {  
            // Handle potential change conflict in whatever way  
            // is appropriate for your application.  
            // For more information, see the MSDN article  
            // How to: Manage Change Conflicts (LINQ to SQL)/  
        }
    }  
}  
```  
  
 <span data-ttu-id="da2d6-171">Para actualizar una colección, llame a <xref:System.Data.Linq.ITable.AttachAll%2A> en lugar de a `Attach`.</span><span class="sxs-lookup"><span data-stu-id="da2d6-171">To update a collection, call <xref:System.Data.Linq.ITable.AttachAll%2A> instead of `Attach`.</span></span>  
  
### <a name="expected-entity-members"></a><span data-ttu-id="da2d6-172">Miembros de entidad esperados</span><span class="sxs-lookup"><span data-stu-id="da2d6-172">Expected Entity Members</span></span>  

 <span data-ttu-id="da2d6-173">Como ya se ha dicho anteriormente, solo es necesario establecer ciertos miembros del objeto entidad antes de llamar a los métodos `Attach`.</span><span class="sxs-lookup"><span data-stu-id="da2d6-173">As stated previously, only certain members of the entity object are required to be set before you call the `Attach` methods.</span></span> <span data-ttu-id="da2d6-174">Los miembros de entidad que es necesario establecer deben cumplir los siguientes criterios:</span><span class="sxs-lookup"><span data-stu-id="da2d6-174">Entity members that are required to be set must fulfill the following criteria:</span></span>  
  
- <span data-ttu-id="da2d6-175">Formar parte de la identidad de la entidad.</span><span class="sxs-lookup"><span data-stu-id="da2d6-175">Be part of the entity’s identity.</span></span>  
  
- <span data-ttu-id="da2d6-176">Se debe esperar que sean modificados.</span><span class="sxs-lookup"><span data-stu-id="da2d6-176">Be expected to be modified.</span></span>  
  
- <span data-ttu-id="da2d6-177">Ser una marca de tiempo o tener su atributo <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> establecido en un valor distinto de `Never`.</span><span class="sxs-lookup"><span data-stu-id="da2d6-177">Be a timestamp or have its <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> attribute set to something besides `Never`.</span></span>  
  
 <span data-ttu-id="da2d6-178">Si una tabla utiliza una marca de tiempo o un número de versión para una comprobación de simultaneidad optimista, se deberán establecer esos miembros antes de llamar a <xref:System.Data.Linq.ITable.Attach%2A>.</span><span class="sxs-lookup"><span data-stu-id="da2d6-178">If a table uses a timestamp or version number for an optimistic concurrency check, you must set those members before you call <xref:System.Data.Linq.ITable.Attach%2A>.</span></span> <span data-ttu-id="da2d6-179">Un miembro está designado para la comprobación de simultaneidad optimista cuando la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> está establecida como verdadera (true) para ese atributo de columna.</span><span class="sxs-lookup"><span data-stu-id="da2d6-179">A member is dedicated for optimistic concurrency checking when the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property is set to true on that Column attribute.</span></span> <span data-ttu-id="da2d6-180">Cualquier actualización solicitada solo se enviará si los valores de número de versión o marca de tiempo son los mismos en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="da2d6-180">Any requested updates will be submitted only if the version number or timestamp values are the same on the database.</span></span>  
  
 <span data-ttu-id="da2d6-181">Un miembro también se utiliza en la comprobación de simultaneidad optimista siempre que el miembro no tenga la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> establecida con el valor `Never`.</span><span class="sxs-lookup"><span data-stu-id="da2d6-181">A member is also used in the optimistic concurrency check as long as the member does not have <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> set to `Never`.</span></span> <span data-ttu-id="da2d6-182">El valor predeterminado es `Always` si no se especifica ningún otro valor.</span><span class="sxs-lookup"><span data-stu-id="da2d6-182">The default value is `Always` if no other value is specified.</span></span>  
  
 <span data-ttu-id="da2d6-183">Si falta cualquiera de estos miembros necesarios, se producirá una excepción <xref:System.Data.Linq.ChangeConflictException> durante <xref:System.Data.Linq.DataContext.SubmitChanges%2A> ("Fila no encontrada o cambiada").</span><span class="sxs-lookup"><span data-stu-id="da2d6-183">If any one of these required members is missing, a <xref:System.Data.Linq.ChangeConflictException> is thrown during <xref:System.Data.Linq.DataContext.SubmitChanges%2A> ("Row not found or changed").</span></span>  
  
### <a name="state"></a><span data-ttu-id="da2d6-184">Estado</span><span class="sxs-lookup"><span data-stu-id="da2d6-184">State</span></span>  

 <span data-ttu-id="da2d6-185">Una vez que un objeto entidad se asocia a la instancia <xref:System.Data.Linq.DataContext>, el objeto se considerará en el estado `PossiblyModified`.</span><span class="sxs-lookup"><span data-stu-id="da2d6-185">After an entity object is attached to the <xref:System.Data.Linq.DataContext> instance, the object is considered to be in the `PossiblyModified` state.</span></span> <span data-ttu-id="da2d6-186">Existen tres maneras de obligar a que un objeto asociado se considere `Modified`.</span><span class="sxs-lookup"><span data-stu-id="da2d6-186">There are three ways to force an attached object to be considered `Modified`.</span></span>  
  
1. <span data-ttu-id="da2d6-187">Asociarlo como no modificado y, a continuación, modificar directamente los campos.</span><span class="sxs-lookup"><span data-stu-id="da2d6-187">Attach it as unmodified, and then directly modify the fields.</span></span>  
  
2. <span data-ttu-id="da2d6-188">Asociarlo mediante la sobrecarga <xref:System.Data.Linq.Table%601.Attach%2A> que acepta instancias de objeto actuales y originales.</span><span class="sxs-lookup"><span data-stu-id="da2d6-188">Attach it with the <xref:System.Data.Linq.Table%601.Attach%2A> overload that takes current and original object instances.</span></span> <span data-ttu-id="da2d6-189">Esto proporciona al seguidor de cambios valores antiguos y nuevos para que sepa automáticamente qué campos han cambiado.</span><span class="sxs-lookup"><span data-stu-id="da2d6-189">This supplies the change tracker with old and new values so that it will automatically know which fields have changed.</span></span>  
  
3. <span data-ttu-id="da2d6-190">Asociarlo mediante la sobrecarga <xref:System.Data.Linq.Table%601.Attach%2A> que acepta un segundo parámetro booleano (con el valor true).</span><span class="sxs-lookup"><span data-stu-id="da2d6-190">Attach it with the <xref:System.Data.Linq.Table%601.Attach%2A> overload that takes a second Boolean parameter (set to true).</span></span> <span data-ttu-id="da2d6-191">Esto indicará al seguidor de cambios que considere el objeto modificado sin tener que proporcionar ningún valor original.</span><span class="sxs-lookup"><span data-stu-id="da2d6-191">This will tell the change tracker to consider the object modified without having to supply any original values.</span></span> <span data-ttu-id="da2d6-192">En este enfoque, el objeto debe tener un campo de versión o marca de tiempo.</span><span class="sxs-lookup"><span data-stu-id="da2d6-192">In this approach, the object must have a version/timestamp field.</span></span>  
  
 <span data-ttu-id="da2d6-193">Para obtener más información, vea [Estados de objetos y seguimiento de cambios](object-states-and-change-tracking.md).</span><span class="sxs-lookup"><span data-stu-id="da2d6-193">For more information, see [Object States and Change-Tracking](object-states-and-change-tracking.md).</span></span>  
  
 <span data-ttu-id="da2d6-194">Si ya existe un objeto entidad en la caché de identificadores con la misma identidad que el objeto que se va a asociar, se producirá la excepción <xref:System.Data.Linq.DuplicateKeyException>.</span><span class="sxs-lookup"><span data-stu-id="da2d6-194">If an entity object already occurs in the ID Cache with the same identity as the object being attached, a <xref:System.Data.Linq.DuplicateKeyException> is thrown.</span></span>  
  
 <span data-ttu-id="da2d6-195">Al asociar con un conjunto de objetos `IEnumerable`, se producirá una excepción <xref:System.Data.Linq.DuplicateKeyException> cuando esté presente una clave existente.</span><span class="sxs-lookup"><span data-stu-id="da2d6-195">When you attach with an `IEnumerable` set of objects, a <xref:System.Data.Linq.DuplicateKeyException> is thrown when an already existing key is present.</span></span> <span data-ttu-id="da2d6-196">Los objetos restantes no se asociarán.</span><span class="sxs-lookup"><span data-stu-id="da2d6-196">Remaining objects are not attached.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da2d6-197">Vea también</span><span class="sxs-lookup"><span data-stu-id="da2d6-197">See also</span></span>

- [<span data-ttu-id="da2d6-198">Aplicaciones de N niveles y remotas con LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="da2d6-198">N-Tier and Remote Applications with LINQ to SQL</span></span>](n-tier-and-remote-applications-with-linq-to-sql.md)
- [<span data-ttu-id="da2d6-199">Información general</span><span class="sxs-lookup"><span data-stu-id="da2d6-199">Background Information</span></span>](background-information.md)
