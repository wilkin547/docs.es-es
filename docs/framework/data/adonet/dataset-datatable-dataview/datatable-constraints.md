---
description: 'Más información sobre: restricciones de DataTable'
title: Restricciones de DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 0c712115fd87fefae3578b2f3fc0adfc416f412e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724913"
---
# <a name="datatable-constraints"></a><span data-ttu-id="8798c-103">Restricciones de DataTable</span><span class="sxs-lookup"><span data-stu-id="8798c-103">DataTable Constraints</span></span>

<span data-ttu-id="8798c-104">Se pueden utilizar restricciones para exigir restricciones sobre los datos de un objeto <xref:System.Data.DataTable> con el fin de mantener la integridad de los datos.</span><span class="sxs-lookup"><span data-stu-id="8798c-104">You can use constraints to enforce restrictions on the data in a <xref:System.Data.DataTable>, in order to maintain the integrity of the data.</span></span> <span data-ttu-id="8798c-105">Una restricción es una regla automática que se aplica a una columna, o a varias columnas relacionadas, que determina cómo proceder cuando se modifica de alguna manera el valor de una fila.</span><span class="sxs-lookup"><span data-stu-id="8798c-105">A constraint is an automatic rule, applied to a column or related columns, that determines the course of action when the value of a row is somehow altered.</span></span> <span data-ttu-id="8798c-106">Las restricciones se aplican cuando la `System.Data.DataSet.EnforceConstraints` propiedad de <xref:System.Data.DataSet> es **true**.</span><span class="sxs-lookup"><span data-stu-id="8798c-106">Constraints are enforced when the `System.Data.DataSet.EnforceConstraints` property of the <xref:System.Data.DataSet> is **true**.</span></span> <span data-ttu-id="8798c-107">Para ver un ejemplo de código que muestre cómo establecer la propiedad `EnforceConstraints`, vea el tema de referencia <xref:System.Data.DataSet.EnforceConstraints%2A>.</span><span class="sxs-lookup"><span data-stu-id="8798c-107">For a code example that shows how to set the `EnforceConstraints` property, see the <xref:System.Data.DataSet.EnforceConstraints%2A> reference topic.</span></span>  
  
 <span data-ttu-id="8798c-108">Existen dos tipos de restricciones en ADO.NET: <xref:System.Data.ForeignKeyConstraint> y <xref:System.Data.UniqueConstraint>.</span><span class="sxs-lookup"><span data-stu-id="8798c-108">There are two kinds of constraints in ADO.NET: the <xref:System.Data.ForeignKeyConstraint> and the <xref:System.Data.UniqueConstraint>.</span></span> <span data-ttu-id="8798c-109">De forma predeterminada, las dos restricciones se crean automáticamente cuando se crea una relación entre dos o más tablas agregando un <xref:System.Data.DataRelation> al **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="8798c-109">By default, both constraints are created automatically when you create a relationship between two or more tables by adding a <xref:System.Data.DataRelation> to the **DataSet**.</span></span> <span data-ttu-id="8798c-110">Sin embargo, puede deshabilitar este comportamiento especificando **createConstraints**  =  **false** al crear la relación.</span><span class="sxs-lookup"><span data-stu-id="8798c-110">However, you can disable this behavior by specifying **createConstraints** = **false** when creating the relation.</span></span>  
  
## <a name="foreignkeyconstraint"></a><span data-ttu-id="8798c-111">ForeignKeyConstraint</span><span class="sxs-lookup"><span data-stu-id="8798c-111">ForeignKeyConstraint</span></span>  

 <span data-ttu-id="8798c-112">Una **ForeignKeyConstraint** exige reglas sobre cómo se propagan las actualizaciones y eliminaciones a las tablas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="8798c-112">A **ForeignKeyConstraint** enforces rules about how updates and deletes to related tables are propagated.</span></span> <span data-ttu-id="8798c-113">Por ejemplo, si se actualiza o elimina un valor de una fila de una tabla, y el mismo valor también se usa en una o varias tablas relacionadas, una **ForeignKeyConstraint** determina lo que sucede en las tablas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="8798c-113">For example, if a value in a row of one table is updated or deleted, and that same value is also used in one or more related tables, a **ForeignKeyConstraint** determines what happens in the related tables.</span></span>  
  
 <span data-ttu-id="8798c-114">Las <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> propiedades y de **ForeignKeyConstraint** definen la acción que se debe realizar cuando el usuario intenta eliminar o actualizar una fila en una tabla relacionada.</span><span class="sxs-lookup"><span data-stu-id="8798c-114">The <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> and <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> properties of the **ForeignKeyConstraint** define the action to be taken when the user attempts to delete or update a row in a related table.</span></span> <span data-ttu-id="8798c-115">En la tabla siguiente se describen las distintas configuraciones disponibles para las propiedades **DeleteRule** y **UpdateRule** de **ForeignKeyConstraint**.</span><span class="sxs-lookup"><span data-stu-id="8798c-115">The following table describes the different settings available for the **DeleteRule** and **UpdateRule** properties of the **ForeignKeyConstraint**.</span></span>  
  
|<span data-ttu-id="8798c-116">Establecimiento de reglas</span><span class="sxs-lookup"><span data-stu-id="8798c-116">Rule setting</span></span>|<span data-ttu-id="8798c-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="8798c-117">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="8798c-118">**Cascade**</span><span class="sxs-lookup"><span data-stu-id="8798c-118">**Cascade**</span></span>|<span data-ttu-id="8798c-119">Elimina o actualiza las filas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="8798c-119">Delete or update related rows.</span></span>|  
|<span data-ttu-id="8798c-120">**SetNull**</span><span class="sxs-lookup"><span data-stu-id="8798c-120">**SetNull**</span></span>|<span data-ttu-id="8798c-121">Establezca los valores de las filas relacionadas en **DBNull**.</span><span class="sxs-lookup"><span data-stu-id="8798c-121">Set values in related rows to **DBNull**.</span></span>|  
|<span data-ttu-id="8798c-122">**SetDefault**</span><span class="sxs-lookup"><span data-stu-id="8798c-122">**SetDefault**</span></span>|<span data-ttu-id="8798c-123">Establece los valores de las filas relacionadas en el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8798c-123">Set values in related rows to the default value.</span></span>|  
|<span data-ttu-id="8798c-124">**Ninguno**</span><span class="sxs-lookup"><span data-stu-id="8798c-124">**None**</span></span>|<span data-ttu-id="8798c-125">No realiza ninguna acción en las filas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="8798c-125">Take no action on related rows.</span></span> <span data-ttu-id="8798c-126">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8798c-126">This is the default.</span></span>|  
  
 <span data-ttu-id="8798c-127">Una **ForeignKeyConstraint** puede restringir y propagar los cambios en las columnas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="8798c-127">A **ForeignKeyConstraint** can restrict, as well as propagate, changes to related columns.</span></span> <span data-ttu-id="8798c-128">En función de las propiedades establecidas para la **ForeignKeyConstraint** de una columna, si la propiedad **EnforceConstraints** del **DataSet** es **true**, realizar determinadas operaciones en la fila primaria producirá una excepción.</span><span class="sxs-lookup"><span data-stu-id="8798c-128">Depending on the properties set for the **ForeignKeyConstraint** of a column, if the **EnforceConstraints** property of the **DataSet** is **true**, performing certain operations on the parent row will result in an exception.</span></span> <span data-ttu-id="8798c-129">Por ejemplo, si la propiedad **DeleteRule** de **ForeignKeyConstraint** es **None**, no se puede eliminar una fila primaria si tiene filas secundarias.</span><span class="sxs-lookup"><span data-stu-id="8798c-129">For example, if the **DeleteRule** property of the **ForeignKeyConstraint** is **None**, a parent row cannot be deleted if it has any child rows.</span></span>  
  
 <span data-ttu-id="8798c-130">Puede crear una restricción de clave externa entre columnas individuales o entre una matriz de columnas mediante el constructor **ForeignKeyConstraint** .</span><span class="sxs-lookup"><span data-stu-id="8798c-130">You can create a foreign key constraint between single columns or between an array of columns by using the **ForeignKeyConstraint** constructor.</span></span> <span data-ttu-id="8798c-131">Pase el objeto **ForeignKeyConstraint** resultante al método **Add** de la propiedad **Constraints** de la tabla, que es una **ConstraintCollection**.</span><span class="sxs-lookup"><span data-stu-id="8798c-131">Pass the resulting **ForeignKeyConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="8798c-132">También puede pasar argumentos de constructor a varias sobrecargas del método **Add** de una **ConstraintCollection** para crear una **ForeignKeyConstraint**.</span><span class="sxs-lookup"><span data-stu-id="8798c-132">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **ForeignKeyConstraint**.</span></span>  
  
 <span data-ttu-id="8798c-133">Al crear una **ForeignKeyConstraint**, puede pasar los valores **DeleteRule** y **UpdateRule** al constructor como argumentos, o bien puede establecerlos como propiedades como en el ejemplo siguiente (donde el valor **DeleteRule** se establece en **None**).</span><span class="sxs-lookup"><span data-stu-id="8798c-133">When creating a **ForeignKeyConstraint**, you can pass the **DeleteRule** and **UpdateRule** values to the constructor as arguments, or you can set them as properties as in the following example (where the **DeleteRule** value is set to **None**).</span></span>  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### <a name="acceptrejectrule"></a><span data-ttu-id="8798c-134">AcceptRejectRule</span><span class="sxs-lookup"><span data-stu-id="8798c-134">AcceptRejectRule</span></span>  

 <span data-ttu-id="8798c-135">Los cambios en las filas se pueden aceptar con el método **AcceptChanges** o cancelarse con el método **RejectChanges** del **DataSet**, **DataTable** o **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="8798c-135">Changes to rows can be accepted using the **AcceptChanges** method or canceled using the **RejectChanges** method of the **DataSet**, **DataTable**, or **DataRow**.</span></span> <span data-ttu-id="8798c-136">Cuando un **conjunto de DataSet** contiene **ForeignKeyConstraints**, al invocar los métodos **AcceptChanges** o **RejectChanges** se aplica el método **AcceptRejectRule**.</span><span class="sxs-lookup"><span data-stu-id="8798c-136">When a **DataSet** contains **ForeignKeyConstraints**, invoking the **AcceptChanges** or **RejectChanges** methods enforces the **AcceptRejectRule**.</span></span> <span data-ttu-id="8798c-137">La propiedad **AcceptRejectRule** de **ForeignKeyConstraint** determina la acción que se realizará en las filas secundarias cuando se llame a **AcceptChanges** o **RejectChanges** en la fila primaria.</span><span class="sxs-lookup"><span data-stu-id="8798c-137">The **AcceptRejectRule** property of the **ForeignKeyConstraint** determines which action will be taken on the child rows when **AcceptChanges** or **RejectChanges** is called on the parent row.</span></span>  
  
 <span data-ttu-id="8798c-138">En la tabla siguiente se enumeran los valores disponibles para **AcceptRejectRule**.</span><span class="sxs-lookup"><span data-stu-id="8798c-138">The following table lists the available settings for the **AcceptRejectRule**.</span></span>  
  
|<span data-ttu-id="8798c-139">Establecimiento de reglas</span><span class="sxs-lookup"><span data-stu-id="8798c-139">Rule setting</span></span>|<span data-ttu-id="8798c-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="8798c-140">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="8798c-141">**Cascade**</span><span class="sxs-lookup"><span data-stu-id="8798c-141">**Cascade**</span></span>|<span data-ttu-id="8798c-142">Acepta o rechaza los cambios en filas secundarias.</span><span class="sxs-lookup"><span data-stu-id="8798c-142">Accept or reject changes to child rows.</span></span>|  
|<span data-ttu-id="8798c-143">**Ninguno**</span><span class="sxs-lookup"><span data-stu-id="8798c-143">**None**</span></span>|<span data-ttu-id="8798c-144">No realiza ninguna acción en las filas secundarias.</span><span class="sxs-lookup"><span data-stu-id="8798c-144">Take no action on child rows.</span></span> <span data-ttu-id="8798c-145">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8798c-145">This is the default.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="8798c-146">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8798c-146">Example</span></span>  

 <span data-ttu-id="8798c-147">En el ejemplo siguiente se crea un <xref:System.Data.ForeignKeyConstraint>, se establecen varias de sus propiedades, incluida la <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, y se añade a la <xref:System.Data.ConstraintCollection> de un objeto <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="8798c-147">The following example creates a <xref:System.Data.ForeignKeyConstraint>, sets several of its properties, including the <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, and adds it to the <xref:System.Data.ConstraintCollection> of a <xref:System.Data.DataTable> object.</span></span>  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a><span data-ttu-id="8798c-148">UniqueConstraint</span><span class="sxs-lookup"><span data-stu-id="8798c-148">UniqueConstraint</span></span>  

 <span data-ttu-id="8798c-149">El objeto **UniqueConstraint** , que se puede asignar a una sola columna o a una matriz de columnas de un **objeto DataTable**, garantiza que todos los datos de la columna o columnas especificadas sean únicos por fila.</span><span class="sxs-lookup"><span data-stu-id="8798c-149">The **UniqueConstraint** object, which can be assigned either to a single column or to an array of columns in a **DataTable**, ensures that all data in the specified column or columns is unique per row.</span></span> <span data-ttu-id="8798c-150">Puede crear una restricción UNIQUE para una columna o matriz de columnas mediante el constructor **UniqueConstraint** .</span><span class="sxs-lookup"><span data-stu-id="8798c-150">You can create a unique constraint for a column or array of columns by using the **UniqueConstraint** constructor.</span></span> <span data-ttu-id="8798c-151">Pase el objeto **UniqueConstraint** resultante al método **Add** de la propiedad **Constraints** de la tabla, que es una **ConstraintCollection**.</span><span class="sxs-lookup"><span data-stu-id="8798c-151">Pass the resulting **UniqueConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="8798c-152">También puede pasar argumentos de constructor a varias sobrecargas del método **Add** de una **ConstraintCollection** para crear una **UniqueConstraint**.</span><span class="sxs-lookup"><span data-stu-id="8798c-152">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **UniqueConstraint**.</span></span> <span data-ttu-id="8798c-153">Al crear una **UniqueConstraint** para una o varias columnas, puede especificar opcionalmente si la columna o columnas son una clave principal.</span><span class="sxs-lookup"><span data-stu-id="8798c-153">When creating a **UniqueConstraint** for a column or columns, you can optionally specify whether the column or columns are a primary key.</span></span>  
  
 <span data-ttu-id="8798c-154">También puede crear una restricción UNIQUE para una columna estableciendo la propiedad **Unique** de la columna en **true**.</span><span class="sxs-lookup"><span data-stu-id="8798c-154">You can also create a unique constraint for a column by setting the **Unique** property of the column to **true**.</span></span> <span data-ttu-id="8798c-155">Como alternativa, si se establece la propiedad **Unique** de una sola columna en **false** , se quita cualquier restricción única que pueda existir.</span><span class="sxs-lookup"><span data-stu-id="8798c-155">Alternatively, setting the **Unique** property of a single column to **false** removes any unique constraint that may exist.</span></span> <span data-ttu-id="8798c-156">Si se define una o varias columnas como clave principal de una tabla se creará automáticamente una restricción única para la columna o columnas especificadas.</span><span class="sxs-lookup"><span data-stu-id="8798c-156">Defining a column or columns as the primary key for a table will automatically create a unique constraint for the specified column or columns.</span></span> <span data-ttu-id="8798c-157">Si quita una columna de la propiedad **PrimaryKey** de una **DataTable**, se quita la **UniqueConstraint** .</span><span class="sxs-lookup"><span data-stu-id="8798c-157">If you remove a column from the **PrimaryKey** property of a **DataTable**, the **UniqueConstraint** is removed.</span></span>  
  
 <span data-ttu-id="8798c-158">En el ejemplo siguiente se crea una **UniqueConstraint** para dos columnas de **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="8798c-158">The following example creates a **UniqueConstraint** for two columns of a **DataTable**.</span></span>  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]
    {custTable.Columns["CustomerID"],
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## <a name="see-also"></a><span data-ttu-id="8798c-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="8798c-159">See also</span></span>

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [<span data-ttu-id="8798c-160">Definición del esquema de DataTable</span><span class="sxs-lookup"><span data-stu-id="8798c-160">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="8798c-161">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="8798c-161">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="8798c-162">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8798c-162">ADO.NET Overview</span></span>](../ado-net-overview.md)
