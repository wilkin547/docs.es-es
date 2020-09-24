---
title: Agregar columnas a un objeto DataTable
description: Un objeto DataTable contiene objetos DataColumn a los que hace referencia la propiedad Columns de la tabla. Utilice este código de ejemplo para agregar columnas a una tabla de ADO.NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 7f220f5d8cbc4b1c12dec018a4497c6bc492f3c1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164888"
---
# <a name="adding-columns-to-a-datatable"></a><span data-ttu-id="46f2d-104">Agregar columnas a un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="46f2d-104">Adding Columns to a DataTable</span></span>

<span data-ttu-id="46f2d-105">Un <xref:System.Data.DataTable> objeto contiene una colección de <xref:System.Data.DataColumn> objetos a los que hace referencia la propiedad **Columns** de la tabla.</span><span class="sxs-lookup"><span data-stu-id="46f2d-105">A <xref:System.Data.DataTable> contains a collection of <xref:System.Data.DataColumn> objects referenced by the **Columns** property of the table.</span></span> <span data-ttu-id="46f2d-106">Esta colección de columnas, junto con las restricciones que haya, define el esquema, o estructura, de la tabla.</span><span class="sxs-lookup"><span data-stu-id="46f2d-106">This collection of columns, along with any constraints, defines the schema, or structure, of the table.</span></span>  
  
 <span data-ttu-id="46f2d-107">Puede crear objetos **DataColumn** dentro de una tabla mediante el constructor **DataColumn** o llamando al método **Add** de la propiedad **Columns** de la tabla, que es <xref:System.Data.DataColumnCollection> .</span><span class="sxs-lookup"><span data-stu-id="46f2d-107">You create **DataColumn** objects within a table by using the **DataColumn** constructor, or by calling the **Add** method of the **Columns** property of the table, which is a <xref:System.Data.DataColumnCollection>.</span></span> <span data-ttu-id="46f2d-108">El método **Add** acepta argumentos **columnName**, **DataType**y **Expression** opcionales y crea una nueva **DataColumn** como miembro de la colección.</span><span class="sxs-lookup"><span data-stu-id="46f2d-108">The **Add** method accepts optional **ColumnName**, **DataType**, and **Expression** arguments and creates a new **DataColumn** as a member of the collection.</span></span> <span data-ttu-id="46f2d-109">También acepta un objeto **DataColumn** existente y lo agrega a la colección y devuelve una referencia a la **DataColumn** agregada si se solicita.</span><span class="sxs-lookup"><span data-stu-id="46f2d-109">It also accepts an existing **DataColumn** object and adds it to the collection, and returns a reference to the added **DataColumn** if requested.</span></span> <span data-ttu-id="46f2d-110">Dado que los objetos **DataTable** no son específicos de ningún origen de datos, se usan .NET Framework tipos al especificar el tipo de datos de un objeto **DataColumn**.</span><span class="sxs-lookup"><span data-stu-id="46f2d-110">Because **DataTable** objects are not specific to any data source, .NET Framework types are used when specifying the data type of a **DataColumn**.</span></span>  
  
 <span data-ttu-id="46f2d-111">En el ejemplo siguiente se agregan cuatro columnas a **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="46f2d-111">The following example adds four columns to a **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="46f2d-112">En el ejemplo, observe que las propiedades de la columna **CustID** están configuradas para no permitir valores **DBNull** y para restringir los valores de forma que sean únicos.</span><span class="sxs-lookup"><span data-stu-id="46f2d-112">In the example, notice that the properties for the **CustID** column are set to not allow **DBNull** values and to constrain values to be unique.</span></span> <span data-ttu-id="46f2d-113">Sin embargo, si define la columna **CustID** como columna de clave principal de la tabla, la propiedad **AllowDBNull** se establecerá automáticamente en **false** y la propiedad **Unique** se establecerá automáticamente en **true**.</span><span class="sxs-lookup"><span data-stu-id="46f2d-113">However, if you define the **CustID** column as the primary key column of the table, the **AllowDBNull** property will automatically be set to **false** and the **Unique** property will automatically be set to **true**.</span></span> <span data-ttu-id="46f2d-114">Para obtener más información, vea [definir claves principales](defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="46f2d-114">For more information, see [Defining Primary Keys](defining-primary-keys.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="46f2d-115">Si no se proporciona un nombre de columna para una columna, a la columna se le asigna un nombre predeterminado incremental de la columna*N,* empezando por "Column1", cuando se agrega a la **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="46f2d-115">If a column name is not supplied for a column, the column is given an incremental default name of Column*N,* starting with "Column1", when it is added to the **DataColumnCollection**.</span></span> <span data-ttu-id="46f2d-116">Se recomienda evitar la Convención de nomenclatura de "Column*N*" al proporcionar un nombre de columna, porque el nombre proporcionado puede entrar en conflicto con un nombre de columna predeterminado existente en **DataColumnCollection**.</span><span class="sxs-lookup"><span data-stu-id="46f2d-116">We recommend that you avoid the naming convention of "Column*N*" when you supply a column name, because the name you supply may conflict with an existing default column name in the **DataColumnCollection**.</span></span> <span data-ttu-id="46f2d-117">Si el nombre proporcionado ya existe, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="46f2d-117">If the supplied name already exists, an exception is thrown.</span></span>  
  
 <span data-ttu-id="46f2d-118">Si está utilizando <xref:System.Xml.Linq.XElement> como <xref:System.Data.DataColumn.DataType%2A> de una <xref:System.Data.DataColumn> en la <xref:System.Data.DataTable>, la serialización XML no funcionará cuando lea los datos.</span><span class="sxs-lookup"><span data-stu-id="46f2d-118">If you are using <xref:System.Xml.Linq.XElement> as the <xref:System.Data.DataColumn.DataType%2A> of a <xref:System.Data.DataColumn> in the <xref:System.Data.DataTable>, XML serialization will not work when you read in data.</span></span> <span data-ttu-id="46f2d-119">Por ejemplo, si escribe un <xref:System.Xml.XmlDocument> utilizando el método `DataTable.WriteXml`, durante la serialización a XML hay un nodo primario adicional en el <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="46f2d-119">For example, if you write out a <xref:System.Xml.XmlDocument> by using the `DataTable.WriteXml` method, upon serialization to XML there is an additional parent node in the <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="46f2d-120">Para solucionar este problema, utilice el tipo <xref:System.Data.SqlTypes.SqlXml> en lugar de <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="46f2d-120">To work around this problem, use the <xref:System.Data.SqlTypes.SqlXml> type instead of <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="46f2d-121">`ReadXml` y `WriteXml` funcionan correctamente con <xref:System.Data.SqlTypes.SqlXml>.</span><span class="sxs-lookup"><span data-stu-id="46f2d-121">`ReadXml` and `WriteXml` work correctly with <xref:System.Data.SqlTypes.SqlXml>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46f2d-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="46f2d-122">See also</span></span>

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="46f2d-123">Definición del esquema de DataTable</span><span class="sxs-lookup"><span data-stu-id="46f2d-123">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="46f2d-124">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="46f2d-124">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="46f2d-125">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="46f2d-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
