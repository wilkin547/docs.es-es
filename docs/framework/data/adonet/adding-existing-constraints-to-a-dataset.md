---
title: Agregar restricciones existentes a un conjunto de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: 90aa1e5dceb3cac87d330837496b9dc467dc1876
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44132706"
---
# <a name="adding-existing-constraints-to-a-dataset"></a><span data-ttu-id="95f07-102">Agregar restricciones existentes a un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="95f07-102">Adding Existing Constraints to a DataSet</span></span>
<span data-ttu-id="95f07-103">El **rellenar** método de la **DataAdapter** rellena un <xref:System.Data.DataSet> sólo con las columnas y filas de un origen de datos; sin embargo las restricciones se suelen establecer en el origen de datos, el **derelleno** método no agrega esta información de esquema para el **DataSet** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="95f07-103">The **Fill** method of the **DataAdapter** fills a <xref:System.Data.DataSet> only with table columns and rows from a data source; though constraints are commonly set by the data source, the **Fill** method does not add this schema information to the **DataSet** by default.</span></span> <span data-ttu-id="95f07-104">Para rellenar un **DataSet** con la información de restricción de clave principal existente desde un origen de datos, puede llamar a la **FillSchema** método de la **DataAdapter**, o establecer el **MissingSchemaAction** propiedad de la **DataAdapter** a **AddWithKey** antes de llamar a **rellenar**.</span><span class="sxs-lookup"><span data-stu-id="95f07-104">To populate a **DataSet** with existing primary key constraint information from a data source, you can either call the **FillSchema** method of the **DataAdapter**, or set the **MissingSchemaAction** property of the **DataAdapter** to **AddWithKey** before calling **Fill**.</span></span> <span data-ttu-id="95f07-105">Así asegurará de que la clave principal restricciones en el **DataSet** las del origen de datos reflejan.</span><span class="sxs-lookup"><span data-stu-id="95f07-105">This will ensure that primary key constraints in the **DataSet** reflect those at the data source.</span></span> <span data-ttu-id="95f07-106">Información de la restricción de clave externa no se incluye y deben ser creada explícitamente, como se muestra en [restricciones de DataTable](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="95f07-106">Foreign key constraint information is not included and must be created explicitly, as shown in [DataTable Constraints](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="95f07-107">Agregar información del esquema a un **DataSet** antes de llenarlo con datos garantiza que las restricciones primary key se incluyen con el <xref:System.Data.DataTable> objetos en el **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="95f07-107">Adding schema information to a **DataSet** before filling it with data ensures that primary key constraints are included with the <xref:System.Data.DataTable> objects in the **DataSet**.</span></span> <span data-ttu-id="95f07-108">Como resultado, cuando adicionales llamadas para rellenar el **DataSet** se realizan, el servidor principal información de columna de clave se usa para que coincidan con nuevas filas del origen de datos con las filas actuales en cada **DataTable**y datos actuales de las tablas se sobrescriben con datos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="95f07-108">As a result, when additional calls to fill the **DataSet** are made, the primary key column information is used to match new rows from the data source with current rows in each **DataTable**, and current data in the tables is overwritten with data from the data source.</span></span> <span data-ttu-id="95f07-109">Sin la información de esquema, las nuevas filas del origen de datos se anexan a la **DataSet**, con lo que las filas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="95f07-109">Without the schema information, the new rows from the data source are appended to the **DataSet**, resulting in duplicate rows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95f07-110">Si una columna de un origen de datos se identifica como incremento automático, el **FillSchema** método, o la **rellenar** método con un **MissingSchemaAction** de  **MissingSchemaAction**, crea un **DataColumn** con un **AutoIncrement** propiedad establecida en `true`.</span><span class="sxs-lookup"><span data-stu-id="95f07-110">If a column in a data source is identified as auto-incrementing, the **FillSchema** method, or the **Fill** method with a **MissingSchemaAction** of **AddWithKey**, creates a **DataColumn** with an **AutoIncrement** property set to `true`.</span></span> <span data-ttu-id="95f07-111">Sin embargo, deberá establecer el **AutoIncrementStep** y **AutoIncrementSeed** valores usted mismo.</span><span class="sxs-lookup"><span data-stu-id="95f07-111">However, you will need to set the **AutoIncrementStep** and **AutoIncrementSeed** values yourself.</span></span> <span data-ttu-id="95f07-112">Para obtener más información acerca de las columnas de incremento automático, consulte [crear columnas de incremento automático](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).</span><span class="sxs-lookup"><span data-stu-id="95f07-112">For more information about auto-incrementing columns, see [Creating AutoIncrement Columns](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).</span></span>  
  
 <span data-ttu-id="95f07-113">Mediante **FillSchema** o la configuración de la **MissingSchemaAction** a **AddWithKey** requiere un procesamiento adicional en el origen de datos para determinar la información de columna de clave principal.</span><span class="sxs-lookup"><span data-stu-id="95f07-113">Using **FillSchema** or setting the **MissingSchemaAction** to **AddWithKey** requires extra processing at the data source to determine primary key column information.</span></span> <span data-ttu-id="95f07-114">Este proceso adicional puede reducir el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="95f07-114">This additional processing can hinder performance.</span></span> <span data-ttu-id="95f07-115">Si conoce en la fase de diseño la información de la clave principal, es aconsejable especificar de modo explícito la columna o columnas que la forman para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="95f07-115">If you know the primary key information at design time, we recommend that you explicitly specify the primary key column or columns in order to achieve optimal performance.</span></span> <span data-ttu-id="95f07-116">Para obtener información acerca de cómo establecer explícitamente el información de clave principal para una tabla, vea [definir claves principales](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="95f07-116">For information about explicitly setting primary key information for a table, see [Defining Primary Keys](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
 <span data-ttu-id="95f07-117">En el ejemplo de código siguiente se muestra cómo agregar información del esquema a un **DataSet** mediante **FillSchema**.</span><span class="sxs-lookup"><span data-stu-id="95f07-117">The following code example shows how to add schema information to a **DataSet** using **FillSchema**.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 <span data-ttu-id="95f07-118">En el ejemplo de código siguiente se muestra cómo agregar información de esquema para un **DataSet** mediante el **MissingSchemaAction.AddWithKey** propiedad de la **rellenar** método.</span><span class="sxs-lookup"><span data-stu-id="95f07-118">The following code example shows how to add schema information to a **DataSet** using the **MissingSchemaAction.AddWithKey** property of the **Fill** method.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="95f07-119">Controlar varios conjuntos de resultados</span><span class="sxs-lookup"><span data-stu-id="95f07-119">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="95f07-120">Si el **DataAdapter** encuentra varios conjuntos de resultados devueltos por la **SelectCommand**, creará varias tablas en el **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="95f07-120">If the **DataAdapter** encounters multiple result sets returned from the **SelectCommand**, it will create multiple tables in the **DataSet**.</span></span> <span data-ttu-id="95f07-121">Las tablas se proporcionará un nombre predeterminado incremental basado en cero de **tabla** *N*, comenzando por **tabla** en lugar de "Table0".</span><span class="sxs-lookup"><span data-stu-id="95f07-121">The tables will be given a zero-based incremental default name of **Table** *N*, starting with **Table** instead of "Table0".</span></span> <span data-ttu-id="95f07-122">Si se pasa un nombre de tabla como argumento a la **FillSchema** método, las tablas le dará un nombre de base cero incremental de **TableName** *N*, comenzando por **TableName** en lugar de "TableName0".</span><span class="sxs-lookup"><span data-stu-id="95f07-122">If a table name is passed as an argument to the **FillSchema** method, the tables will be given a zero-based incremental name of **TableName** *N*, starting with **TableName** instead of "TableName0".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95f07-123">Si el **FillSchema** método de la **OleDbDataAdapter** objeto se llama para un comando que devuelve varios conjuntos de resultados, se devuelve la información de esquema del primer conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="95f07-123">If the **FillSchema** method of the **OleDbDataAdapter** object is called for a command that returns multiple result sets, only the schema information from the first result set is returned.</span></span> <span data-ttu-id="95f07-124">Al devolver la información de esquema de resultados múltiples establece utilizando la **OleDbDataAdapter**, se recomienda que especifique un **MissingSchemaAction** de **AddWithKey** y obtener la información del esquema al llamar a la **rellenar** método.</span><span class="sxs-lookup"><span data-stu-id="95f07-124">When returning schema information for multiple result sets using the **OleDbDataAdapter**, it is recommended that you specify a **MissingSchemaAction** of **AddWithKey** and obtain the schema information when calling the **Fill** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95f07-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="95f07-125">See Also</span></span>  
 [<span data-ttu-id="95f07-126">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="95f07-126">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="95f07-127">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="95f07-127">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="95f07-128">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="95f07-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="95f07-129">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="95f07-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
