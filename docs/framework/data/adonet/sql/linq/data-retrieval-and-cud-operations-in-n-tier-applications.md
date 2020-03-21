---
title: Recuperación de datos y operaciones CUD en aplicaciones de n niveles (LINQ to SQL)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c3133d53-83ed-4a4d-af8b-82edcf3831db
ms.openlocfilehash: 5ab829993b8f8faa6dcb91d3f23e8442b8aa95bd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148418"
---
# <a name="data-retrieval-and-cud-operations-in-n-tier-applications-linq-to-sql"></a>Recuperación de datos y operaciones CUD en aplicaciones de n niveles (LINQ to SQL)
Al serializar objetos entidad, como Clientes o Pedidos, con destino a un cliente a través de una red, esas entidades se desasocian de su contexto de datos. El contexto de datos ya no realiza un seguimiento de sus cambios o sus asociaciones con otros objetos. Esto no constituye un problema mientras los clientes solo estén leyendo los datos. También es relativamente sencillo permitir a los clientes agregar nuevas filas a una base de datos. Sin embargo, si su aplicación requiere que los clientes pueden actualizar o eliminar datos, deberá asociar las entidades a un nuevo contexto de datos antes de llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=nameWithType>. Además, si está utilizando una comprobación de simultaneidad optimista con valores originales, también necesitará un medio para proporcionar a la base de datos la entidad original y la entidad modificada. Los métodos `Attach` se utilizan para colocar las entidades en un nuevo contexto de datos después de haber sido desasociadas.  
  
 Incluso si está serializando objetos [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] proxy en lugar de las entidades, todavía tiene que construir una entidad <xref:System.Data.Linq.DataContext?displayProperty=nameWithType>en la capa de acceso a datos (DAL) y adjuntarla a una nueva , para enviar los datos a la base de datos.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]es completamente indiferente acerca de cómo se serializan las entidades. Para obtener más información acerca de cómo usar el Diseñador relacional de objetos y SQLMetal herramientas para generar clases que son serializables mediante Windows Communication Foundation (WCF), vea Cómo: hacer que [las entidades serializables](how-to-make-entities-serializable.md).  
  
> [!NOTE]
> Solo llame a los métodos `Attach` para entidades nuevas o deserializadas. La única manera de desasociar una entidad de su contexto de datos original es deserializarla. Si intenta asociar una entidad no desasociada a un nuevo contexto de datos, y esa entidad todavía tiene cargadores diferidos procedentes de su contexto de datos anterior, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] producirá una excepción. Una entidad con cargadores diferidos de dos contextos de datos diferentes podría producir resultados no deseados al realizar operaciones de inserción, actualización y eliminación sobre esa entidad. Para obtener más información acerca de los cargadores diferidos, vea [Carga diferida frente a carga inmediata](deferred-versus-immediate-loading.md).  
  
## <a name="retrieving-data"></a>Recuperación de datos  
  
### <a name="client-method-call"></a>Llamada a método del cliente  
 Los ejemplos siguientes muestran un ejemplo de llamada a método en la capa DAL desde un cliente de Windows Forms. En este ejemplo, la capa DAL se implementa como una Biblioteca de servicios de Windows:  
  
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
  
### <a name="middle-tier-implementation"></a>Implementación del nivel intermedio  
 El ejemplo siguiente muestra una implementación del método de interfaz en el nivel intermedio. Deberá tener en cuenta los dos puntos principales siguientes:  
  
- El objeto <xref:System.Data.Linq.DataContext> se declara en el ámbito del método.  
  
- El método devuelve una colección <xref:System.Collections.IEnumerable> de los resultados reales. El serializador ejecutará la consulta para devolver los resultados al nivel de presentación o cliente. Para obtener acceso localmente a los resultados de la consulta en el nivel intermedio, puede forzar la ejecución llamando a `ToList` o `ToArray` para la variable de consulta. A continuación, puede devolver esa lista o matriz como un `IEnumerable`.  
  
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
  
 Una instancia de un contexto de datos debería tener la duración de una "unidad de trabajo". En un entorno débilmente acoplado, una unidad de trabajo es generalmente pequeña, quizá una transacción optimista, incluida una única llamada a `SubmitChanges`. Por consiguiente, el contexto de los datos se crea y se deshace en el ámbito del método. Si la unidad de trabajo incluye llamadas a la lógica de reglas de empresa, entonces generalmente deseará mantener la instancia de `DataContext` para esa operación completa. En cualquier caso, las instancias de `DataContext` no deberían mantenerse activas durante largos períodos de tiempo a lo largo de un número arbitrario de transacciones.  
  
 Este método devolverá objetos Product, pero no la colección de los objetos Order_Detail asociados a cada objeto Product. Use el objeto <xref:System.Data.Linq.DataLoadOptions> para cambiar este comportamiento predeterminado. Para obtener más información, vea [Cómo: controlar cuántos datos relacionados se recuperan](how-to-control-how-much-related-data-is-retrieved.md).  
  
## <a name="inserting-data"></a>Insertar datos  
 Para insertar un nuevo objeto, el nivel de presentación simplemente llama al método pertinente en la interfaz de nivel intermedio y pasa el nuevo objeto que se va a insertar. En algunos casos, puede ser más eficiente para el cliente pasar solo algunos valores y hacer que el nivel intermedio construya el objeto completo.  
  
### <a name="middle-tier-implementation"></a>Implementación del nivel intermedio  
 En el nivel intermedio, se crea un nuevo <xref:System.Data.Linq.DataContext>, se asocia el objeto al <xref:System.Data.Linq.DataContext> mediante el método <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>, y se inserta el objeto al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. Se pueden administrar excepciones, devoluciones de llamada y condiciones de error al igual que en cualquier otro escenario de servicio Web.  
  
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
  
## <a name="deleting-data"></a>Eliminar datos  
 Para eliminar un objeto existente de la base de datos, el nivel de presentación llama al método pertinente en la interfaz de nivel intermedio y pasa su copia que incluye los valores originales del objeto que se va a eliminar.  
  
 Las operaciones de eliminación implican comprobaciones de simultaneidad optimista, y el objeto que se va a eliminar debe estar primero asociado al nuevo contexto de datos. En este ejemplo, el parámetro `Boolean` está establecido en `false` para indicar que el objeto no tiene marca de tiempo (RowVersion). Si la tabla de la base de datos genera marcas de tiempo para cada registro, entonces las comprobaciones de simultaneidad son mucho más simples, sobre todo para el cliente. Simplemente pase el objeto original o el objeto modificado y establezca el parámetro `Boolean` en `true`. En cualquier caso, en el nivel intermedio es necesario generalmente capturar la excepción <xref:System.Data.Linq.ChangeConflictException>. Para obtener más información acerca de cómo controlar los conflictos de simultaneidad optimista, vea [Simultaneidad optimista: información general](optimistic-concurrency-overview.md).  
  
 Al eliminar entidades que tienen restricciones de clave externa sobre tablas asociadas, deberá eliminar primero todos los objetos en sus colecciones <xref:System.Data.Linq.EntitySet%601>.  
  
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
  
## <a name="updating-data"></a>Actualización de datos  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite actualizaciones en estos escenarios que presentan simultaneidad optimista:  
  
- Simultaneidad optimista basada en marcas de tiempo o números RowVersion.  
  
- Simultaneidad optimista basada en valores originales de un subconjunto de propiedades de entidad.  
  
- Simultaneidad optimista basada en las entidades completas originales y modificadas.  
  
 Puede también realizar actualizaciones o eliminaciones conjuntas sobre una entidad y sus relaciones; por ejemplo, un Cliente y una colección de sus objetos Pedido asociados. Cuando realiza modificaciones sobre el cliente en un grafo de objetos entidad y sus colecciones (`EntitySet`) secundarias, y las comprobaciones de simultaneidad optimista requieren valores originales, el cliente debe proporcionar esos valores originales para cada entidad y cada objeto <xref:System.Data.Linq.EntitySet%601>. Si desea permitir a los clientes realizar, en una única llamada al método, un conjunto de actualizaciones, eliminaciones e inserciones relacionadas, deberá proporcionar al cliente una manera de indicar qué tipo de operación va a realizar sobre cada entidad. En el nivel intermedio, deberá llamar al método <xref:System.Data.Linq.ITable.Attach%2A> apropiado y, a continuación, a <xref:System.Data.Linq.ITable.InsertOnSubmit%2A>, <xref:System.Data.Linq.ITable.DeleteAllOnSubmit%2A> o <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> (sin `Attach`, para las inserciones) para cada entidad antes de llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. No recupere datos de la base de datos como una manera de obtener valores originales antes de probar las actualizaciones.  
  
 Para obtener más información acerca de la simultaneidad optimista, vea [Simultaneidad optimista: información general](optimistic-concurrency-overview.md). Para obtener información detallada sobre cómo resolver conflictos de cambio de simultaneidad optimista, vea [Cómo: administrar conflictos](how-to-manage-change-conflicts.md)de cambio .  
  
 Los ejemplos siguientes explican los distintos escenarios:  
  
### <a name="optimistic-concurrency-with-timestamps"></a>Simultaneidad optimista con marcas de tiempo  
  
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
  
### <a name="with-subset-of-original-values"></a>Con subconjunto de valores originales  
 En este enfoque, el cliente devuelve el objeto completo serializado, junto con los valores que se van a modificar.  
  
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
  
### <a name="with-complete-entities"></a>Con entidades completas  
  
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
  
 Para actualizar una colección, llame a <xref:System.Data.Linq.ITable.AttachAll%2A> en lugar de a `Attach`.  
  
### <a name="expected-entity-members"></a>Miembros de entidad esperados  
 Como ya se ha dicho anteriormente, solo es necesario establecer ciertos miembros del objeto entidad antes de llamar a los métodos `Attach`. Los miembros de entidad que es necesario establecer deben cumplir los siguientes criterios:  
  
- Formar parte de la identidad de la entidad.  
  
- Se debe esperar que sean modificados.  
  
- Ser una marca de tiempo o tener su atributo <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> establecido en un valor distinto de `Never`.  
  
 Si una tabla utiliza una marca de tiempo o un número de versión para una comprobación de simultaneidad optimista, se deberán establecer esos miembros antes de llamar a <xref:System.Data.Linq.ITable.Attach%2A>. Un miembro está designado para la comprobación de simultaneidad optimista cuando la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> está establecida como verdadera (true) para ese atributo de columna. Cualquier actualización solicitada solo se enviará si los valores de número de versión o marca de tiempo son los mismos en la base de datos.  
  
 Un miembro también se utiliza en la comprobación de simultaneidad optimista siempre que el miembro no tenga la propiedad <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> establecida con el valor `Never`. El valor predeterminado es `Always` si no se especifica ningún otro valor.  
  
 Si falta cualquiera de estos miembros necesarios, se producirá una excepción <xref:System.Data.Linq.ChangeConflictException> durante <xref:System.Data.Linq.DataContext.SubmitChanges%2A> ("Fila no encontrada o cambiada").  
  
### <a name="state"></a>State  
 Una vez que un objeto entidad se asocia a la instancia <xref:System.Data.Linq.DataContext>, el objeto se considerará en el estado `PossiblyModified`. Existen tres maneras de obligar a que un objeto asociado se considere `Modified`.  
  
1. Asociarlo como no modificado y, a continuación, modificar directamente los campos.  
  
2. Asociarlo mediante la sobrecarga <xref:System.Data.Linq.Table%601.Attach%2A> que acepta instancias de objeto actuales y originales. Esto proporciona al seguidor de cambios valores antiguos y nuevos para que sepa automáticamente qué campos han cambiado.  
  
3. Asociarlo mediante la sobrecarga <xref:System.Data.Linq.Table%601.Attach%2A> que acepta un segundo parámetro booleano (con el valor true). Esto indicará al seguidor de cambios que considere el objeto modificado sin tener que proporcionar ningún valor original. En este enfoque, el objeto debe tener un campo de versión o marca de tiempo.  
  
 Para obtener más información, consulte [Estados de objeto y Seguimiento de cambios](object-states-and-change-tracking.md).  
  
 Si ya existe un objeto entidad en la caché de identificadores con la misma identidad que el objeto que se va a asociar, se producirá la excepción <xref:System.Data.Linq.DuplicateKeyException>.  
  
 Al asociar con un conjunto de objetos `IEnumerable`, se producirá una excepción <xref:System.Data.Linq.DuplicateKeyException> cuando esté presente una clave existente. Los objetos restantes no se asociarán.  
  
## <a name="see-also"></a>Consulte también

- [Aplicaciones de n niveles y remotas con LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md)
- [Información de antecedentes](background-information.md)
