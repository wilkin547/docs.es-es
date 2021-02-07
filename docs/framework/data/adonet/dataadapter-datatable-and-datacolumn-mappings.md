---
description: Más información acerca de las asignaciones DataTable DataTable y DataColumn
title: Correspondencias de DataTable y DataColumn en un objeto DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 25007925afa57dd0cb6e75f808444f1bfaeea9b1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739743"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="106b3-103">Correspondencias de DataTable y DataColumn en un objeto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="106b3-103">DataAdapter DataTable and DataColumn Mappings</span></span>

<span data-ttu-id="106b3-104">Un objeto **DataAdapter** contiene una colección de cero o más <xref:System.Data.Common.DataTableMapping> objetos en la propiedad **TableMappings** .</span><span class="sxs-lookup"><span data-stu-id="106b3-104">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="106b3-105">Un **DataTableMapping** proporciona una asignación maestra entre los datos devueltos de una consulta en un origen de datos y un <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="106b3-105">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="106b3-106">Se puede pasar el nombre de **DataTableMapping** en lugar del nombre de **DataTable** al método **Fill** de **DataAdapter**.</span><span class="sxs-lookup"><span data-stu-id="106b3-106">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="106b3-107">En el ejemplo siguiente se crea un objeto **DataTableMapping** denominado **AuthorsMapping** en la tabla **Authors**.</span><span class="sxs-lookup"><span data-stu-id="106b3-107">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="106b3-108">Un objeto **DataTableMapping** permite usar en un objeto **DataTable** nombres de columna distintos a los de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="106b3-108">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="106b3-109">El objeto **DataAdapter** usa la asignación para hacer coincidir las columnas al actualizar la tabla.</span><span class="sxs-lookup"><span data-stu-id="106b3-109">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="106b3-110">Si no se especifica un nombre de **TableName** o **DataTableMapping** al llamar a los métodos **Fill** o **Update** del objeto **DataAdapter**, **DataAdapter** busca un objeto **DataTableMapping** denominado "Table".</span><span class="sxs-lookup"><span data-stu-id="106b3-110">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="106b3-111">Si ese objeto **DataTableMapping** no existe, el **TableName** de la **DataTable** es "Table".</span><span class="sxs-lookup"><span data-stu-id="106b3-111">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="106b3-112">Puede especificar un objeto **DataTableMapping** predeterminado si crea una instancia de **DataTableMapping** con el nombre "Table".</span><span class="sxs-lookup"><span data-stu-id="106b3-112">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="106b3-113">En el ejemplo de código siguiente se crea un objeto **DataTableMapping** (del espacio de nombres <xref:System.Data.Common>) y, al asignarle el nombre "Table", se convierte en la asignación predeterminada del objeto **DataAdapter** especificado.</span><span class="sxs-lookup"><span data-stu-id="106b3-113">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="106b3-114">Después, en el ejemplo se asignan las columnas de la primera tabla de los resultados de la consulta (la tabla **Customers** de la base de datos **Northwind**) a un conjunto de nombres más descriptivos existentes en la tabla **Northwind Customers** de <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="106b3-114">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="106b3-115">En las columnas que no se asignan se usa el nombre de la columna en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="106b3-115">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
```  
  
```csharp  
DataTableMapping mapping =
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 <span data-ttu-id="106b3-116">En situaciones más avanzadas, podría decidir que quiere que el mismo objeto **DataAdapter** permita la carga de otras tablas con otras asignaciones.</span><span class="sxs-lookup"><span data-stu-id="106b3-116">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="106b3-117">Para ello, basta con agregar objetos de **DataTableMapping** adicionales.</span><span class="sxs-lookup"><span data-stu-id="106b3-117">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="106b3-118">Cuando al método **Fill** se le pasa una instancia de un objeto **DataSet** y un nombre de **DataTableMapping**, se usa una asignación con ese nombre, si existe, o bien un objeto **DataTable** con ese nombre.</span><span class="sxs-lookup"><span data-stu-id="106b3-118">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="106b3-119">En los ejemplos siguientes se crea un objeto **DataTableMapping** denominado **Customers** y un objeto **DataTable** con el nombre **BizTalkSchema**.</span><span class="sxs-lookup"><span data-stu-id="106b3-119">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="106b3-120">Después, en el ejemplo se asignan las filas devueltas por la instrucción SELECT al objeto **DataTable** **BizTalkSchema**.</span><span class="sxs-lookup"><span data-stu-id="106b3-120">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
ITableMapping mapping =
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
> <span data-ttu-id="106b3-121">Si no se proporciona un nombre de columna de origen en una asignación de columnas o no se identifica un nombre de tabla de origen en una asignación de tablas, se generan nombres predeterminados de forma automática.</span><span class="sxs-lookup"><span data-stu-id="106b3-121">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="106b3-122">Si no se proporciona ninguna columna de origen para una asignación de columnas, a la asignación de columnas se le asigna un nombre predeterminado incremental de **SourceColumn** *N,* comenzando por **SourceColumn1**.</span><span class="sxs-lookup"><span data-stu-id="106b3-122">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="106b3-123">Si no se proporciona ningún nombre de tabla de origen para una asignación de tabla, la asignación de tabla recibe un nombre predeterminado incremental de **SourceTable** *N*, comenzando por **SourceTable1**.</span><span class="sxs-lookup"><span data-stu-id="106b3-123">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="106b3-124">Es recomendable evitar la convención de nomenclatura de **SourceColumn** *N* para una asignación de columnas, o bien de **SourceTable** *N* para una asignación de tablas, ya que es posible que el nombre proporcionado entre en conflicto con el nombre predeterminado de asignación de columnas de **ColumnMappingCollection** o con el nombre de asignación de tablas de **DataTableMappingCollection**.</span><span class="sxs-lookup"><span data-stu-id="106b3-124">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="106b3-125">Si el nombre proporcionado ya existe, se iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="106b3-125">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="106b3-126">Controlar varios conjuntos de resultados</span><span class="sxs-lookup"><span data-stu-id="106b3-126">Handling Multiple Result Sets</span></span>  

 <span data-ttu-id="106b3-127">Cuando **SelectCommand** devuelve varias tablas, **Fill** genera automáticamente nombres de tabla con valores secuenciales para todas las tablas del objeto **DataSet**, comenzando por el nombre de tabla especificado y continuando con el formato **TableName** *N*, a partir de **TableName1**.</span><span class="sxs-lookup"><span data-stu-id="106b3-127">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="106b3-128">Puede usar asignaciones de tabla para asignar el nombre generado automáticamente a un nombre que quiera especificar para la tabla en el objeto **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="106b3-128">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="106b3-129">Por ejemplo, cuando **SelectCommand** devuelve dos tablas, **Customers** y **Orders**, puede emitir la llamada siguiente a **Fill**.</span><span class="sxs-lookup"><span data-stu-id="106b3-129">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 <span data-ttu-id="106b3-130">Se crean dos tablas en el objeto **DataSet**: **Customers** y **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="106b3-130">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="106b3-131">Puede usar asignaciones de tabla para asegurarse de que la segunda se denomina **Orders** en lugar de **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="106b3-131">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="106b3-132">Para ello, asigne la tabla de origen de **Customers1** a la tabla **Orders** del objeto **DataSet**, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="106b3-132">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a><span data-ttu-id="106b3-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="106b3-133">See also</span></span>

- [<span data-ttu-id="106b3-134">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="106b3-134">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="106b3-135">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="106b3-135">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="106b3-136">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="106b3-136">ADO.NET Overview</span></span>](ado-net-overview.md)
