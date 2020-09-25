---
title: Correspondencias de DataTable y DataColumn en un objeto DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: b979431836b55b23ac9ba6ec4535f33765dce555
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177740"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="788b3-102">Correspondencias de DataTable y DataColumn en un objeto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="788b3-102">DataAdapter DataTable and DataColumn Mappings</span></span>

<span data-ttu-id="788b3-103">Un objeto **DataAdapter** contiene una colección de cero o más <xref:System.Data.Common.DataTableMapping> objetos en la propiedad **TableMappings** .</span><span class="sxs-lookup"><span data-stu-id="788b3-103">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="788b3-104">Un **DataTableMapping** proporciona una asignación maestra entre los datos devueltos de una consulta en un origen de datos y un <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="788b3-104">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="788b3-105">Se puede pasar el nombre de **DataTableMapping** en lugar del nombre de **DataTable** al método **Fill** de **DataAdapter**.</span><span class="sxs-lookup"><span data-stu-id="788b3-105">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="788b3-106">En el ejemplo siguiente se crea un **DataTableMapping** denominado **AuthorsMapping** para la tabla **authors** .</span><span class="sxs-lookup"><span data-stu-id="788b3-106">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="788b3-107">Un objeto **DataTableMapping** permite usar nombres de columna en un **DataTable** que son diferentes de los de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="788b3-107">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="788b3-108">El **DataAdapter** utiliza la asignación para buscar coincidencias con las columnas cuando se actualiza la tabla.</span><span class="sxs-lookup"><span data-stu-id="788b3-108">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="788b3-109">Si no especifica un nombre **TableName** o **DataTableMapping** al llamar al método **Fill** o **Update** de **DataAdapter**, el **DataAdapter** busca un **DataTableMapping** denominado "Table".</span><span class="sxs-lookup"><span data-stu-id="788b3-109">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="788b3-110">Si ese objeto **DataTableMapping** no existe, el **TableName** de la **DataTable** es "Table".</span><span class="sxs-lookup"><span data-stu-id="788b3-110">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="788b3-111">Puede especificar un **DataTableMapping** predeterminado mediante la creación de un **DataTableMapping** con el nombre "Table".</span><span class="sxs-lookup"><span data-stu-id="788b3-111">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="788b3-112">En el ejemplo de código siguiente se crea un **DataTableMapping** (a partir del <xref:System.Data.Common> espacio de nombres) y se convierte en la asignación predeterminada para el **DataAdapter** especificado asignándole el nombre "Table".</span><span class="sxs-lookup"><span data-stu-id="788b3-112">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="788b3-113">A continuación, en el ejemplo se asignan las columnas de la primera tabla del resultado de la consulta (la tabla **Customers** de la base de datos **Northwind** ) a un conjunto de nombres más descriptivos de la tabla **Customers de Northwind** en el <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="788b3-113">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="788b3-114">En las columnas que no se asignan se usa el nombre de la columna en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="788b3-114">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
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
  
 <span data-ttu-id="788b3-115">En situaciones más avanzadas, puede decidir que desea que el mismo **DataAdapter** admita la carga de tablas diferentes con asignaciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="788b3-115">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="788b3-116">Para ello, basta con agregar objetos de **DataTableMapping** adicionales.</span><span class="sxs-lookup"><span data-stu-id="788b3-116">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="788b3-117">Cuando se pasa al método **Fill** una instancia de un **DataSet** y un nombre de **DataTableMapping** , si existe una asignación con ese nombre, se utiliza; de lo contrario, se utiliza un **objeto DataTable** con ese nombre.</span><span class="sxs-lookup"><span data-stu-id="788b3-117">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="788b3-118">En los ejemplos siguientes se crea un objeto **DataTableMapping** con un nombre de **Customers** y un nombre **DataTable** de **BizTalkSchema**.</span><span class="sxs-lookup"><span data-stu-id="788b3-118">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="788b3-119">A continuación, en el ejemplo se asignan las filas devueltas por la instrucción SELECT a la **DataTable** **BizTalkSchema** .</span><span class="sxs-lookup"><span data-stu-id="788b3-119">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
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
> <span data-ttu-id="788b3-120">Si no se proporciona un nombre de columna de origen en una asignación de columnas o no se identifica un nombre de tabla de origen en una asignación de tablas, se generan nombres predeterminados de forma automática.</span><span class="sxs-lookup"><span data-stu-id="788b3-120">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="788b3-121">Si no se proporciona ninguna columna de origen para una asignación de columnas, a la asignación de columnas se le asigna un nombre predeterminado incremental de **SourceColumn** *N,* comenzando por **SourceColumn1**.</span><span class="sxs-lookup"><span data-stu-id="788b3-121">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="788b3-122">Si no se proporciona ningún nombre de tabla de origen para una asignación de tabla, la asignación de tabla recibe un nombre predeterminado incremental de **SourceTable** *N*, comenzando por **SourceTable1**.</span><span class="sxs-lookup"><span data-stu-id="788b3-122">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="788b3-123">Se recomienda evitar la Convención de nomenclatura de **SourceColumn** *n* para una asignación de columnas o **SourceTable** *n* para una asignación de tabla, ya que el nombre proporcionado puede entrar en conflicto con un nombre de asignación de columna predeterminado existente en el nombre de asignación de tabla o **ColumnMappingCollection** en **DataTableMappingCollection**.</span><span class="sxs-lookup"><span data-stu-id="788b3-123">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="788b3-124">Si el nombre proporcionado ya existe, se iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="788b3-124">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="788b3-125">Controlar varios conjuntos de resultados</span><span class="sxs-lookup"><span data-stu-id="788b3-125">Handling Multiple Result Sets</span></span>  

 <span data-ttu-id="788b3-126">Si **SelectCommand** devuelve varias tablas, **Fill** genera automáticamente nombres de tabla con valores incrementales para las tablas del **conjunto de DataSet**, comenzando por el nombre de tabla especificado y continuando en el formulario **TableName** *N*, comenzando por **TableName1**.</span><span class="sxs-lookup"><span data-stu-id="788b3-126">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="788b3-127">Puede usar asignaciones de tabla para asignar el nombre de tabla generado automáticamente a un nombre que desee especificar para la tabla en el **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="788b3-127">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="788b3-128">Por ejemplo, para un **SelectCommand** que devuelve dos tablas, **Customers** y **Orders**, emita la siguiente llamada a **Fill**.</span><span class="sxs-lookup"><span data-stu-id="788b3-128">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 <span data-ttu-id="788b3-129">Se crean dos tablas en el **conjunto de DataSet**: **Customers** y **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="788b3-129">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="788b3-130">Puede usar asignaciones de tabla para asegurarse de que la segunda tabla se denomina **Orders** en lugar de **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="788b3-130">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="788b3-131">Para ello, asigne la tabla de origen de **Customers1** a los **pedidos**de la tabla del **conjunto** de elementos, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="788b3-131">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a><span data-ttu-id="788b3-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="788b3-132">See also</span></span>

- [<span data-ttu-id="788b3-133">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="788b3-133">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="788b3-134">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="788b3-134">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="788b3-135">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="788b3-135">ADO.NET Overview</span></span>](ado-net-overview.md)
