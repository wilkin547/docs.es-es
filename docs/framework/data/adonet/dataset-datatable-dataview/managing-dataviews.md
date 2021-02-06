---
description: Más información acerca de cómo administrar las vistas de los
title: Administrar objetos DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b67fab5-1722-4d2b-bfc1-247a75f0f1ee
ms.openlocfilehash: cdd9da9c4f67321dba36d22610704fc2e2561930
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652099"
---
# <a name="managing-dataviews"></a><span data-ttu-id="18def-103">Administrar objetos DataView</span><span class="sxs-lookup"><span data-stu-id="18def-103">Managing DataViews</span></span>

<span data-ttu-id="18def-104">Puede utilizar un <xref:System.Data.DataViewManager> para administrar la configuración de vista para todas las tablas de un <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="18def-104">You can use a <xref:System.Data.DataViewManager> to manage view settings for all the tables in a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="18def-105">Si tiene un control que desea enlazar a varias tablas, como una cuadrícula que navega por las relaciones, un **DataViewManager** es ideal.</span><span class="sxs-lookup"><span data-stu-id="18def-105">If you have a control that you want to bind to multiple tables, such as a grid that navigates relationships, a **DataViewManager** is ideal.</span></span>  
  
 <span data-ttu-id="18def-106">El objeto **DataViewManager** contiene una colección de <xref:System.Data.DataViewSetting> objetos que se utilizan para establecer la configuración de vista de las tablas de <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="18def-106">The **DataViewManager** contains a collection of <xref:System.Data.DataViewSetting> objects that are used to set the view setting of the tables in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="18def-107"><xref:System.Data.DataViewSettingCollection>Contiene un <xref:System.Data.DataViewSetting> objeto para cada tabla de un **conjunto** de objetos.</span><span class="sxs-lookup"><span data-stu-id="18def-107">The <xref:System.Data.DataViewSettingCollection> contains one <xref:System.Data.DataViewSetting> object for each table in a **DataSet**.</span></span> <span data-ttu-id="18def-108">Puede establecer las propiedades **ApplyDefaultSort**, **Sort**, **RowFilter** y **RowStateFilter** predeterminadas de la tabla a la que se hace referencia mediante su **DataViewSetting**.</span><span class="sxs-lookup"><span data-stu-id="18def-108">You can set the default **ApplyDefaultSort**, **Sort**, **RowFilter**, and **RowStateFilter** properties of the referenced table by using its **DataViewSetting**.</span></span> <span data-ttu-id="18def-109">Puede hacer referencia al **DataViewSetting** para una tabla determinada por nombre o referencia ordinal, o pasando una referencia a ese objeto de tabla específico.</span><span class="sxs-lookup"><span data-stu-id="18def-109">You can reference the **DataViewSetting** for a particular table by name or ordinal reference, or by passing a reference to that specific table object.</span></span> <span data-ttu-id="18def-110">Puede tener acceso a la colección de objetos **DataViewSetting** en un **DataViewManager** mediante la propiedad **DataViewSettings** .</span><span class="sxs-lookup"><span data-stu-id="18def-110">You can access the collection of **DataViewSetting** objects in a **DataViewManager** by using the **DataViewSettings** property.</span></span>  
  
 <span data-ttu-id="18def-111">En el ejemplo de código siguiente se rellena un **conjunto** de datos con las tablas de base de datos SQL Server **Northwind** **Customers**, **Orders** y **Order Details**, se crean las relaciones entre las tablas, se usa un **DataViewManager** para establecer la configuración predeterminada de **DataView** y se enlaza un **control DataGrid** a **DataViewManager**.</span><span class="sxs-lookup"><span data-stu-id="18def-111">The following code example fills a **DataSet** with the SQL Server **Northwind** database tables **Customers**, **Orders**, and **Order Details**, creates the relationships between the tables, uses a **DataViewManager** to set default **DataView** settings, and binds a **DataGrid** to the **DataViewManager**.</span></span> <span data-ttu-id="18def-112">En el ejemplo se establece la configuración predeterminada de **DataView** para todas las tablas del **conjunto** de los criterios de ordenación por la clave principal de la tabla (**ApplyDefaultSort**  =  **true**) y, a continuación, se modifica el criterio de ordenación de la tabla **Customers** para ordenar por **CompanyName**.</span><span class="sxs-lookup"><span data-stu-id="18def-112">The example sets the default **DataView** settings for all tables in the **DataSet** to sort by the primary key of the table (**ApplyDefaultSort** = **true**), and then modifies the sort order of the **Customers** table to sort by **CompanyName**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection to Northwind.  
' Create a Connection, DataAdapters, and a DataSet.  
Dim custDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID FROM Orders", connection)  
Dim ordDetDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection)  
  
Dim custDS As DataSet = New DataSet()  
  
' Open the Connection.  
connection.Open()  
  
    ' Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
  
    custDA.Fill(custDS, "Customers")  
    orderDA.Fill(custDS, "Orders")  
    ordDetDA.Fill(custDS, "OrderDetails")  
  
    ' Close the Connection.  
    connection.Close()  
  
    ' Create relationships.  
    custDS.Relations.Add("CustomerOrders", _  
          custDS.Tables("Customers").Columns("CustomerID"), _  
          custDS.Tables("Orders").Columns("CustomerID"))  
  
    custDS.Relations.Add("OrderDetails", _  
          custDS.Tables("Orders").Columns("OrderID"), _  
          custDS.Tables("OrderDetails").Columns("OrderID"))  
  
' Create default DataView settings.  
Dim viewManager As DataViewManager = New DataViewManager(custDS)  
  
Dim viewSetting As DataViewSetting  
For Each viewSetting In viewManager.DataViewSettings  
  viewSetting.ApplyDefaultSort = True  
Next  
  
viewManager.DataViewSettings("Customers").Sort = "CompanyName"  
  
' Bind to a DataGrid.  
Dim grid As System.Windows.Forms.DataGrid = New System.Windows.Forms.DataGrid()  
grid.SetDataBinding(viewManager, "Customers")  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection to Northwind.  
// Create a Connection, DataAdapters, and a DataSet.  
SqlDataAdapter custDA = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderDA = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID FROM Orders", connection);  
SqlDataAdapter ordDetDA = new SqlDataAdapter(  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection);  
  
DataSet custDS = new DataSet();  
  
// Open the Connection.  
connection.Open();  
  
    // Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
  
    custDA.Fill(custDS, "Customers");  
    orderDA.Fill(custDS, "Orders");  
    ordDetDA.Fill(custDS, "OrderDetails");  
  
    // Close the Connection.  
    connection.Close();  
  
    // Create relationships.  
    custDS.Relations.Add("CustomerOrders",  
          custDS.Tables["Customers"].Columns["CustomerID"],  
          custDS.Tables["Orders"].Columns["CustomerID"]);  
  
    custDS.Relations.Add("OrderDetails",  
          custDS.Tables["Orders"].Columns["OrderID"],  
          custDS.Tables["OrderDetails"].Columns["OrderID"]);  
  
// Create default DataView settings.  
DataViewManager viewManager = new DataViewManager(custDS);  
  
foreach (DataViewSetting viewSetting in viewManager.DataViewSettings)  
  viewSetting.ApplyDefaultSort = true;  
  
viewManager.DataViewSettings["Customers"].Sort = "CompanyName";  
  
// Bind to a DataGrid.  
System.Windows.Forms.DataGrid grid = new System.Windows.Forms.DataGrid();  
grid.SetDataBinding(viewManager, "Customers");  
```  
  
## <a name="see-also"></a><span data-ttu-id="18def-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="18def-113">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataViewManager>
- <xref:System.Data.DataViewSetting>
- <xref:System.Data.DataViewSettingCollection>
- [<span data-ttu-id="18def-114">Objetos DataView</span><span class="sxs-lookup"><span data-stu-id="18def-114">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="18def-115">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="18def-115">ADO.NET Overview</span></span>](../ado-net-overview.md)
