---
title: Agregar restricciones existentes a un conjunto de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: 267d6489d39f86fc06b35de8cf30dad74f501b0b
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523238"
---
# <a name="adding-existing-constraints-to-a-dataset"></a><span data-ttu-id="90e38-102">Agregar restricciones existentes a un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="90e38-102">Adding Existing Constraints to a DataSet</span></span>

<span data-ttu-id="90e38-103">El método **Fill** de **DataAdapter** rellena una <xref:System.Data.DataSet> solo con las columnas y filas de la tabla de un origen de datos; Aunque el origen de datos suele establecer restricciones, el método **Fill** no agrega esta información de esquema al **conjunto** de datos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="90e38-103">The **Fill** method of the **DataAdapter** fills a <xref:System.Data.DataSet> only with table columns and rows from a data source; though constraints are commonly set by the data source, the **Fill** method does not add this schema information to the **DataSet** by default.</span></span> <span data-ttu-id="90e38-104">Para rellenar un **conjunto** de datos con información de restricciones PRIMARY KEY de un origen de datos, puede llamar al método **FillSchema** de **DataAdapter**o establecer la propiedad **MissingSchemaAction** de **DataAdapter** . para que el método sea **AddWithKey** antes de llamar a **Fill**.</span><span class="sxs-lookup"><span data-stu-id="90e38-104">To populate a **DataSet** with existing primary key constraint information from a data source, you can either call the **FillSchema** method of the **DataAdapter**, or set the **MissingSchemaAction** property of the **DataAdapter** to **AddWithKey** before calling **Fill**.</span></span> <span data-ttu-id="90e38-105">Esto garantizará que las restricciones PRIMARY KEY del **conjunto** de datos reflejen las del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="90e38-105">This will ensure that primary key constraints in the **DataSet** reflect those at the data source.</span></span> <span data-ttu-id="90e38-106">La información de restricción de clave externa no se incluye y se debe crear explícitamente, como se muestra en [restricciones de DataTable](./dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="90e38-106">Foreign key constraint information is not included and must be created explicitly, as shown in [DataTable Constraints](./dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
<span data-ttu-id="90e38-107">Agregar información de esquema a un **conjunto** de datos antes de rellenarlo con datos garantiza que las restricciones PRIMARY KEY se incluyen con los objetos <xref:System.Data.DataTable> del **conjunto**de datos.</span><span class="sxs-lookup"><span data-stu-id="90e38-107">Adding schema information to a **DataSet** before filling it with data ensures that primary key constraints are included with the <xref:System.Data.DataTable> objects in the **DataSet**.</span></span> <span data-ttu-id="90e38-108">Como resultado, cuando se realizan llamadas adicionales para rellenar el **conjunto** de datos, la información de la columna de clave principal se utiliza para hacer coincidir las nuevas filas del origen de datos con las filas actuales de cada **DataTable**, y los datos actuales de las tablas se sobrescriben con los datos del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="90e38-108">As a result, when additional calls to fill the **DataSet** are made, the primary key column information is used to match new rows from the data source with current rows in each **DataTable**, and current data in the tables is overwritten with data from the data source.</span></span> <span data-ttu-id="90e38-109">Sin la información del esquema, las nuevas filas del origen de datos se anexan al **conjunto**de datos, lo que da lugar a filas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="90e38-109">Without the schema information, the new rows from the data source are appended to the **DataSet**, resulting in duplicate rows.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90e38-110">Si una columna de un origen de datos se identifica como de incremento automático, el método **FillSchema** o el método **Fill** con el **MissingSchemaAction** de **AddWithKey**, crea un **DataColumn** con una propiedad **AutoIncrement** . establezca en `true`.</span><span class="sxs-lookup"><span data-stu-id="90e38-110">If a column in a data source is identified as auto-incrementing, the **FillSchema** method, or the **Fill** method with a **MissingSchemaAction** of **AddWithKey**, creates a **DataColumn** with an **AutoIncrement** property set to `true`.</span></span> <span data-ttu-id="90e38-111">Sin embargo, tendrá que establecer los valores de **AutoIncrementStep** y **AutoIncrementSeed** .</span><span class="sxs-lookup"><span data-stu-id="90e38-111">However, you will need to set the **AutoIncrementStep** and **AutoIncrementSeed** values yourself.</span></span> <span data-ttu-id="90e38-112">Para obtener más información acerca de las columnas de incremento automático, vea [crear columnas de incremento](./dataset-datatable-dataview/creating-autoincrement-columns.md)automático.</span><span class="sxs-lookup"><span data-stu-id="90e38-112">For more information about auto-incrementing columns, see [Creating AutoIncrement Columns](./dataset-datatable-dataview/creating-autoincrement-columns.md).</span></span>  
  
<span data-ttu-id="90e38-113">El uso de **FillSchema** o el establecimiento de **MissingSchemaAction** en **AddWithKey** requiere un procesamiento adicional en el origen de datos para determinar la información de la columna de clave principal.</span><span class="sxs-lookup"><span data-stu-id="90e38-113">Using **FillSchema** or setting the **MissingSchemaAction** to **AddWithKey** requires extra processing at the data source to determine primary key column information.</span></span> <span data-ttu-id="90e38-114">Este proceso adicional puede reducir el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="90e38-114">This additional processing can hinder performance.</span></span> <span data-ttu-id="90e38-115">Si conoce en la fase de diseño la información de la clave principal, es aconsejable especificar de modo explícito la columna o columnas que la forman para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="90e38-115">If you know the primary key information at design time, we recommend that you explicitly specify the primary key column or columns in order to achieve optimal performance.</span></span> <span data-ttu-id="90e38-116">Para obtener información sobre cómo establecer explícitamente la información de clave principal de una tabla, vea [definir claves principales](./dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="90e38-116">For information about explicitly setting primary key information for a table, see [Defining Primary Keys](./dataset-datatable-dataview/defining-primary-keys.md).</span></span>
  
<span data-ttu-id="90e38-117">En el ejemplo de código siguiente se muestra cómo agregar información de esquema a un **conjunto** de datos mediante **FillSchema**:</span><span class="sxs-lookup"><span data-stu-id="90e38-117">The following code example shows how to add schema information to a **DataSet** using **FillSchema**:</span></span>
  
```vb  
Dim custDataSet As New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
var custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
<span data-ttu-id="90e38-118">En el ejemplo de código siguiente se muestra cómo agregar información de esquema a un **conjunto** de datos mediante la propiedad **MissingSchemaAction. AddWithKey** del método **Fill** :</span><span class="sxs-lookup"><span data-stu-id="90e38-118">The following code example shows how to add schema information to a **DataSet** using the **MissingSchemaAction.AddWithKey** property of the **Fill** method:</span></span>
  
```vb  
Dim custDataSet As New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
var custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="90e38-119">Controlar varios conjuntos de resultados</span><span class="sxs-lookup"><span data-stu-id="90e38-119">Handling multiple result sets</span></span>  

<span data-ttu-id="90e38-120">Si el **DataAdapter** encuentra varios conjuntos de resultados devueltos por **SelectCommand**, creará varias tablas en el **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="90e38-120">If the **DataAdapter** encounters multiple result sets returned from the **SelectCommand**, it will create multiple tables in the **DataSet**.</span></span> <span data-ttu-id="90e38-121">A las tablas se les asignará un nombre predeterminado incremental basado en cero de la **tabla** *N*, empezando por la **tabla** en lugar de "Table0".</span><span class="sxs-lookup"><span data-stu-id="90e38-121">The tables will be given a zero-based incremental default name of **Table** *N*, starting with **Table** instead of "Table0".</span></span> <span data-ttu-id="90e38-122">Si se pasa un nombre de tabla como argumento al método **FillSchema** , se asignará a las tablas un nombre incremental basado en cero de **TableName** *N*, comenzando por **TableName** en lugar de "representa tablename0".</span><span class="sxs-lookup"><span data-stu-id="90e38-122">If a table name is passed as an argument to the **FillSchema** method, the tables will be given a zero-based incremental name of **TableName** *N*, starting with **TableName** instead of "TableName0".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90e38-123">Si se llama al método **FillSchema** del objeto **OleDbDataAdapter** para un comando que devuelve varios conjuntos de resultados, solo se devuelve la información del esquema del primer conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="90e38-123">If the **FillSchema** method of the **OleDbDataAdapter** object is called for a command that returns multiple result sets, only the schema information from the first result set is returned.</span></span> <span data-ttu-id="90e38-124">Al devolver información de esquema para varios conjuntos de resultados mediante **OleDbDataAdapter**, se recomienda especificar el **MissingSchemaAction** de **AddWithKey** y obtener la información del esquema al llamar al método **Fill** . forma.</span><span class="sxs-lookup"><span data-stu-id="90e38-124">When returning schema information for multiple result sets using the **OleDbDataAdapter**, it is recommended that you specify a **MissingSchemaAction** of **AddWithKey** and obtain the schema information when calling the **Fill** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90e38-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="90e38-125">See also</span></span>

- [<span data-ttu-id="90e38-126">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="90e38-126">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="90e38-127">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="90e38-127">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="90e38-128">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="90e38-128">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="90e38-129">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="90e38-129">ADO.NET Overview</span></span>](ado-net-overview.md)
