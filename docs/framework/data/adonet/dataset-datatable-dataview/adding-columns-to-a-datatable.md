---
title: Agregar columnas a un objeto DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 77bf117b8835623d768f8b8b0ec3e4195174cad7
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70043950"
---
# <a name="adding-columns-to-a-datatable"></a><span data-ttu-id="61a67-102">Agregar columnas a un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="61a67-102">Adding Columns to a DataTable</span></span>
<span data-ttu-id="61a67-103">Un <xref:System.Data.DataTable> objeto contiene una colección <xref:System.Data.DataColumn> de objetos a los que hace referencia la propiedad Columns de la tabla.</span><span class="sxs-lookup"><span data-stu-id="61a67-103">A <xref:System.Data.DataTable> contains a collection of <xref:System.Data.DataColumn> objects referenced by the **Columns** property of the table.</span></span> <span data-ttu-id="61a67-104">Esta colección de columnas, junto con las restricciones que haya, define el esquema, o estructura, de la tabla.</span><span class="sxs-lookup"><span data-stu-id="61a67-104">This collection of columns, along with any constraints, defines the schema, or structure, of the table.</span></span>  
  
 <span data-ttu-id="61a67-105">Puede crear objetos **DataColumn** dentro de una tabla mediante el constructor **DataColumn** o llamando al método **Add** de la propiedad **Columns** <xref:System.Data.DataColumnCollection>de la tabla, que es.</span><span class="sxs-lookup"><span data-stu-id="61a67-105">You create **DataColumn** objects within a table by using the **DataColumn** constructor, or by calling the **Add** method of the **Columns** property of the table, which is a <xref:System.Data.DataColumnCollection>.</span></span> <span data-ttu-id="61a67-106">El método **Add** acepta argumentos **columnName**, **DataType**y **Expression** opcionales y crea una nueva **DataColumn** como miembro de la colección.</span><span class="sxs-lookup"><span data-stu-id="61a67-106">The **Add** method accepts optional **ColumnName**, **DataType**, and **Expression** arguments and creates a new **DataColumn** as a member of the collection.</span></span> <span data-ttu-id="61a67-107">También acepta un objeto **DataColumn** existente y lo agrega a la colección y devuelve una referencia a la **DataColumn** agregada si se solicita.</span><span class="sxs-lookup"><span data-stu-id="61a67-107">It also accepts an existing **DataColumn** object and adds it to the collection, and returns a reference to the added **DataColumn** if requested.</span></span> <span data-ttu-id="61a67-108">Dado que los objetos **DataTable** no son específicos de ningún origen de datos, se usan .NET Framework tipos al especificar el tipo de datos de un objeto **DataColumn**.</span><span class="sxs-lookup"><span data-stu-id="61a67-108">Because **DataTable** objects are not specific to any data source, .NET Framework types are used when specifying the data type of a **DataColumn**.</span></span>  
  
 <span data-ttu-id="61a67-109">En el ejemplo siguiente se agregan cuatro columnas a **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="61a67-109">The following example adds four columns to a **DataTable**.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
  
Dim workCol As DataColumn = workTable.Columns.Add( _  
    "CustID", Type.GetType("System.Int32"))  
workCol.AllowDBNull = false  
workCol.Unique = true  
  
workTable.Columns.Add("CustLName", Type.GetType("System.String"))  
workTable.Columns.Add("CustFName", Type.GetType("System.String"))  
workTable.Columns.Add("Purchases", Type.GetType("System.Double"))  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
  
DataColumn workCol = workTable.Columns.Add("CustID", typeof(Int32));  
workCol.AllowDBNull = false;  
workCol.Unique = true;  
  
workTable.Columns.Add("CustLName", typeof(String));  
workTable.Columns.Add("CustFName", typeof(String));  
workTable.Columns.Add("Purchases", typeof(Double));  
```  
  
 <span data-ttu-id="61a67-110">En el ejemplo, observe que las propiedades de la columna **CustID** están configuradas para no permitir valores **DBNull** y para restringir los valores de forma que sean únicos.</span><span class="sxs-lookup"><span data-stu-id="61a67-110">In the example, notice that the properties for the **CustID** column are set to not allow **DBNull** values and to constrain values to be unique.</span></span> <span data-ttu-id="61a67-111">Sin embargo, si define la columna **CustID** como columna de clave principal de la tabla, la propiedad **AllowDBNull** se establecerá automáticamente en **false** y la propiedad **Unique** se establecerá automáticamente en **true**.</span><span class="sxs-lookup"><span data-stu-id="61a67-111">However, if you define the **CustID** column as the primary key column of the table, the **AllowDBNull** property will automatically be set to **false** and the **Unique** property will automatically be set to **true**.</span></span> <span data-ttu-id="61a67-112">Para obtener más información, vea [definir claves principales](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="61a67-112">For more information, see [Defining Primary Keys](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="61a67-113">Si no se proporciona un nombre de columna para una columna, a la columna se le asigna un nombre predeterminado incremental de la columna*N,* empezando por "Column1", cuando se agrega a la **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="61a67-113">If a column name is not supplied for a column, the column is given an incremental default name of Column*N,* starting with "Column1", when it is added to the **DataColumnCollection**.</span></span> <span data-ttu-id="61a67-114">Se recomienda evitar la Convención de nomenclatura de "Column*N*" al proporcionar un nombre de columna, porque el nombre proporcionado puede entrar en conflicto con un nombre de columna predeterminado existente en **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="61a67-114">We recommend that you avoid the naming convention of "Column*N*" when you supply a column name, because the name you supply may conflict with an existing default column name in the **DataColumnCollection**.</span></span> <span data-ttu-id="61a67-115">Si el nombre proporcionado ya existe, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="61a67-115">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="61a67-116">Si está utilizando <xref:System.Xml.Linq.XElement> como <xref:System.Data.DataColumn.DataType%2A> de una <xref:System.Data.DataColumn> en la <xref:System.Data.DataTable>, la serialización XML no funcionará cuando lea los datos.</span><span class="sxs-lookup"><span data-stu-id="61a67-116">If you are using <xref:System.Xml.Linq.XElement> as the <xref:System.Data.DataColumn.DataType%2A> of a <xref:System.Data.DataColumn> in the <xref:System.Data.DataTable>, XML serialization will not work when you read in data.</span></span> <span data-ttu-id="61a67-117">Por ejemplo, si escribe un <xref:System.Xml.XmlDocument> utilizando el método `DataTable.WriteXml`, durante la serialización a XML hay un nodo primario adicional en el <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="61a67-117">For example, if you write out a <xref:System.Xml.XmlDocument> by using the `DataTable.WriteXml` method, upon serialization to XML there is an additional parent node in the <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="61a67-118">Para solucionar este problema, utilice el tipo <xref:System.Data.SqlTypes.SqlXml> en lugar de <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="61a67-118">To work around this problem, use the <xref:System.Data.SqlTypes.SqlXml> type instead of <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="61a67-119">`ReadXml` y `WriteXml` funcionan correctamente con <xref:System.Data.SqlTypes.SqlXml>.</span><span class="sxs-lookup"><span data-stu-id="61a67-119">`ReadXml` and `WriteXml` work correctly with <xref:System.Data.SqlTypes.SqlXml>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a67-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="61a67-120">See also</span></span>

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="61a67-121">Definición del esquema de DataTable</span><span class="sxs-lookup"><span data-stu-id="61a67-121">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [<span data-ttu-id="61a67-122">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="61a67-122">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="61a67-123">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="61a67-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
