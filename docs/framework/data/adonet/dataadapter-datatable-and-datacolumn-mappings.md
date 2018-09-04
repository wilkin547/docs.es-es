---
title: Correspondencias de DataTable y DataColumn en un objeto DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 9f33ae085bef2b611d1ce95bed1b26f9101a10b9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505247"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a><span data-ttu-id="860fc-102">Correspondencias de DataTable y DataColumn en un objeto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="860fc-102">DataAdapter DataTable and DataColumn Mappings</span></span>
<span data-ttu-id="860fc-103">Un **DataAdapter** contiene una colección de cero o más <xref:System.Data.Common.DataTableMapping> objetos en su **TableMappings** propiedad.</span><span class="sxs-lookup"><span data-stu-id="860fc-103">A **DataAdapter** contains a collection of zero or more <xref:System.Data.Common.DataTableMapping> objects in its **TableMappings** property.</span></span> <span data-ttu-id="860fc-104">Un **DataTableMapping** proporciona una asignación principal entre los datos devueltos por una consulta en un origen de datos y un <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="860fc-104">A **DataTableMapping** provides a master mapping between the data returned from a query against a data source, and a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="860fc-105">El **DataTableMapping** puede pasar el nombre en lugar de la **DataTable** nombre a la **rellenar** método de la **DataAdapter**.</span><span class="sxs-lookup"><span data-stu-id="860fc-105">The **DataTableMapping** name can be passed in place of the **DataTable** name to the **Fill** method of the **DataAdapter**.</span></span> <span data-ttu-id="860fc-106">En el ejemplo siguiente se crea un **DataTableMapping** denominado **AuthorsMapping** para el **autores** tabla.</span><span class="sxs-lookup"><span data-stu-id="860fc-106">The following example creates a **DataTableMapping** named **AuthorsMapping** for the **Authors** table.</span></span>  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 <span data-ttu-id="860fc-107">Un **DataTableMapping** le permite usar nombres de columna en un **DataTable** que son diferentes de los de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="860fc-107">A **DataTableMapping** enables you to use column names in a **DataTable** that are different from those in the database.</span></span> <span data-ttu-id="860fc-108">El **DataAdapter** usa la asignación para hacer coincidir las columnas cuando se actualiza la tabla.</span><span class="sxs-lookup"><span data-stu-id="860fc-108">The **DataAdapter** uses the mapping to match the columns when the table is updated.</span></span>  
  
 <span data-ttu-id="860fc-109">Si no especifica un **TableName** o un **DataTableMapping** nombre cuando se llama a la **rellenar** o **actualización** método de la  **DataAdapter**, **DataAdapter** busca un **DataTableMapping** denominado "Table".</span><span class="sxs-lookup"><span data-stu-id="860fc-109">If you do not specify a **TableName** or a **DataTableMapping** name when calling the **Fill** or **Update** method of the **DataAdapter**, the **DataAdapter** looks for a **DataTableMapping** named "Table".</span></span> <span data-ttu-id="860fc-110">Si ese **DataTableMapping** no existe, el **TableName** de la **DataTable** es "Table".</span><span class="sxs-lookup"><span data-stu-id="860fc-110">If that **DataTableMapping** does not exist, the **TableName** of the **DataTable** is "Table".</span></span> <span data-ttu-id="860fc-111">Puede especificar un valor predeterminado **DataTableMapping** mediante la creación de un **DataTableMapping** con el nombre "Table".</span><span class="sxs-lookup"><span data-stu-id="860fc-111">You can specify a default **DataTableMapping** by creating a **DataTableMapping** with the name of "Table".</span></span>  
  
 <span data-ttu-id="860fc-112">En el ejemplo de código siguiente se crea un **DataTableMapping** (desde el <xref:System.Data.Common> espacio de nombres) y hace que la asignación predeterminada para el elemento especificado **DataAdapter** asignándole "Table".</span><span class="sxs-lookup"><span data-stu-id="860fc-112">The following code example creates a **DataTableMapping** (from the <xref:System.Data.Common> namespace) and makes it the default mapping for the specified **DataAdapter** by naming it "Table".</span></span> <span data-ttu-id="860fc-113">El ejemplo, a continuación, asignan las columnas de la primera tabla en el resultado de la consulta (el **clientes** tabla de la **Northwind** base de datos) a un conjunto de nombres más descriptivos existentes en el **Customers de Northwind**  de tabla en la <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="860fc-113">The example then maps the columns from the first table in the query result (the **Customers** table of the **Northwind** database) to a set of more user-friendly names in the **Northwind Customers** table in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="860fc-114">En las columnas que no se asignan se usa el nombre de la columna en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="860fc-114">For columns that are not mapped, the name of the column from the data source is used.</span></span>  
  
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
  
 <span data-ttu-id="860fc-115">En situaciones más avanzadas, puede decidir que quiere que el mismo **DataAdapter** para admitir la carga de tablas diferentes con sus propias asignaciones.</span><span class="sxs-lookup"><span data-stu-id="860fc-115">In more advanced situations, you may decide that you want the same **DataAdapter** to support loading different tables with different mappings.</span></span> <span data-ttu-id="860fc-116">Para ello, basta con agregar más **DataTableMapping** objetos.</span><span class="sxs-lookup"><span data-stu-id="860fc-116">To do this, simply add additional **DataTableMapping** objects.</span></span>  
  
 <span data-ttu-id="860fc-117">Cuando el **rellenar** método se pasa una instancia de un **DataSet** y un **DataTableMapping** nombre, si existe una asignación con ese nombre, se usa; en caso contrario, un  **DataTable** con el que se usa el nombre.</span><span class="sxs-lookup"><span data-stu-id="860fc-117">When the **Fill** method is passed an instance of a **DataSet** and a **DataTableMapping** name, if a mapping with that name exists it is used; otherwise, a **DataTable** with that name is used.</span></span>  
  
 <span data-ttu-id="860fc-118">Los ejemplos siguientes crean un **DataTableMapping** con el nombre de **clientes** y un **DataTable** nombre de **BizTalkSchema**.</span><span class="sxs-lookup"><span data-stu-id="860fc-118">The following examples create a **DataTableMapping** with a name of **Customers** and a **DataTable** name of **BizTalkSchema**.</span></span> <span data-ttu-id="860fc-119">En el ejemplo, a continuación, asigna las filas devueltas por la instrucción SELECT para la **BizTalkSchema** **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="860fc-119">The example then maps the rows returned by the SELECT statement to the **BizTalkSchema** **DataTable**.</span></span>  
  
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
>  <span data-ttu-id="860fc-120">Si no se proporciona un nombre de columna de origen en una asignación de columnas o no se identifica un nombre de tabla de origen en una asignación de tablas, se generan nombres predeterminados de forma automática.</span><span class="sxs-lookup"><span data-stu-id="860fc-120">If a source column name is not supplied for a column mapping or a source table name is not supplied for a table mapping, default names will be automatically generated.</span></span> <span data-ttu-id="860fc-121">Si no hay ninguna columna de origen se proporciona una asignación de columnas, la asignación de columnas tiene un nombre predeterminado incremental del **SourceColumn** *N,* a partir de **SourceColumn1**.</span><span class="sxs-lookup"><span data-stu-id="860fc-121">If no source column is supplied for a column mapping, the column mapping is given an incremental default name of **SourceColumn** *N,* starting with **SourceColumn1**.</span></span> <span data-ttu-id="860fc-122">Si no se proporciona ningún nombre de tabla de origen para una asignación de tabla, la asignación de tabla tiene un nombre predeterminado incremental del **SourceTable** *N*, comenzando por **SourceTable1**.</span><span class="sxs-lookup"><span data-stu-id="860fc-122">If no source table name is supplied for a table mapping, the table mapping is given an incremental default name of **SourceTable** *N*, starting with **SourceTable1**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="860fc-123">Se recomienda evitar la convención de nomenclatura de **SourceColumn** *N* para una asignación de columna, o **SourceTable** *N* para una tabla asignación, porque el nombre que se proporcione podría entrar en conflicto con un nombre de asignación de columna predeterminado existente en el **ColumnMappingCollection** o nombre de la asignación de tabla en la **DataTableMappingCollection** .</span><span class="sxs-lookup"><span data-stu-id="860fc-123">We recommend that you avoid the naming convention of **SourceColumn** *N* for a column mapping, or **SourceTable** *N* for a table mapping, because the name you supply may conflict with an existing default column mapping name in the **ColumnMappingCollection** or table mapping name in the **DataTableMappingCollection**.</span></span> <span data-ttu-id="860fc-124">Si el nombre proporcionado ya existe, se iniciará una excepción.</span><span class="sxs-lookup"><span data-stu-id="860fc-124">If the supplied name already exists, an exception will be thrown.</span></span>  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="860fc-125">Controlar varios conjuntos de resultados</span><span class="sxs-lookup"><span data-stu-id="860fc-125">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="860fc-126">Si su **SelectCommand** devuelve varias tablas, **rellenar** genera automáticamente nombres de tabla con valores incrementales para las tablas de la **DataSet**, empezando por el Especifica el nombre de tabla y continuar en el formulario **TableName** *N*, comenzando por **TableName1**.</span><span class="sxs-lookup"><span data-stu-id="860fc-126">If your **SelectCommand** returns multiple tables, **Fill** automatically generates table names with incremental values for the tables in the **DataSet**, starting with the specified table name and continuing on in the form **TableName** *N*, starting with **TableName1**.</span></span> <span data-ttu-id="860fc-127">Puede usar asignaciones de tabla para asignar el nombre generado automáticamente a un nombre que desee especificar para la tabla en la **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="860fc-127">You can use table mappings to map the automatically generated table name to a name you want specified for the table in the **DataSet**.</span></span> <span data-ttu-id="860fc-128">Por ejemplo, para un **SelectCommand** que devuelve dos tablas, **clientes** y **pedidos**, emita la siguiente llamada a **rellenar**.</span><span class="sxs-lookup"><span data-stu-id="860fc-128">For example, for a **SelectCommand** that returns two tables, **Customers** and **Orders**, issue the following call to **Fill**.</span></span>  
  
```  
adapter.Fill(customersDataSet, "Customers")  
```  
  
 <span data-ttu-id="860fc-129">Se crean dos tablas en el **DataSet**: **clientes** y **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="860fc-129">Two tables are created in the **DataSet**: **Customers** and **Customers1**.</span></span> <span data-ttu-id="860fc-130">Puede usar asignaciones de tabla para asegurarse de que la segunda tabla se denomina **pedidos** en lugar de **Customers1**.</span><span class="sxs-lookup"><span data-stu-id="860fc-130">You can use table mappings to ensure that the second table is named **Orders** instead of **Customers1**.</span></span> <span data-ttu-id="860fc-131">Para ello, asigne la tabla de origen de **Customers1** a la **DataSet** tabla **pedidos**, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="860fc-131">To do this, map the source table of **Customers1** to the **DataSet** table **Orders**, as shown in the following example.</span></span>  
  
```  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  
  
## <a name="see-also"></a><span data-ttu-id="860fc-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="860fc-132">See Also</span></span>  
 [<span data-ttu-id="860fc-133">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="860fc-133">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="860fc-134">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="860fc-134">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="860fc-135">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="860fc-135">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
