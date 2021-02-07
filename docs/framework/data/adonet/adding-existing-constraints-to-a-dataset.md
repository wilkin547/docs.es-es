---
description: Más información acerca de cómo agregar restricciones existentes a un conjunto de información
title: Agregar restricciones existentes a un conjunto de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
ms.openlocfilehash: cad0dd1bd16747a5e76e10784d00c14cd9aa8c2a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729578"
---
# <a name="adding-existing-constraints-to-a-dataset"></a><span data-ttu-id="93fe5-103">Agregar restricciones existentes a un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="93fe5-103">Adding Existing Constraints to a DataSet</span></span>

<span data-ttu-id="93fe5-104">El método **Fill** de **DataAdapter** rellena un <xref:System.Data.DataSet> solo con las columnas y filas de la tabla de un origen de datos; aunque el origen de datos suele establecer las restricciones, el método **Fill** no agrega esta información de esquema al **conjunto** de datos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="93fe5-104">The **Fill** method of the **DataAdapter** fills a <xref:System.Data.DataSet> only with table columns and rows from a data source; though constraints are commonly set by the data source, the **Fill** method does not add this schema information to the **DataSet** by default.</span></span> <span data-ttu-id="93fe5-105">Para rellenar un **conjunto** de datos con la información de restricciones PRIMARY KEY de un origen de datos, puede llamar al método **FillSchema** de **DataAdapter** o establecer la propiedad **MissingSchemaAction** de **DataAdapter** en **AddWithKey** antes de llamar a **Fill**.</span><span class="sxs-lookup"><span data-stu-id="93fe5-105">To populate a **DataSet** with existing primary key constraint information from a data source, you can either call the **FillSchema** method of the **DataAdapter**, or set the **MissingSchemaAction** property of the **DataAdapter** to **AddWithKey** before calling **Fill**.</span></span> <span data-ttu-id="93fe5-106">De esta forma se garantiza que las restricciones de clave principal del objeto **DataSet** reflejen las del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="93fe5-106">This will ensure that primary key constraints in the **DataSet** reflect those at the data source.</span></span> <span data-ttu-id="93fe5-107">La información de restricción de clave externa no se incluye y se debe crear explícitamente, como se muestra en [restricciones de DataTable](./dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="93fe5-107">Foreign key constraint information is not included and must be created explicitly, as shown in [DataTable Constraints](./dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
<span data-ttu-id="93fe5-108">Al agregar la información del esquema a un objeto **DataSet** antes de rellenarlo con datos, se garantiza que se incluyan las restricciones de clave principal con los objetos <xref:System.Data.DataTable> de **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="93fe5-108">Adding schema information to a **DataSet** before filling it with data ensures that primary key constraints are included with the <xref:System.Data.DataTable> objects in the **DataSet**.</span></span> <span data-ttu-id="93fe5-109">Como resultado, al realizar llamadas adicionales para rellenar el objeto **DataSet**, la información de la columna de clave principal se usa para hacer coincidir las nuevas filas del origen de datos con las filas actuales de cada instancia de **DataTable**, y los datos actuales de las tablas se sobrescriben con los del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="93fe5-109">As a result, when additional calls to fill the **DataSet** are made, the primary key column information is used to match new rows from the data source with current rows in each **DataTable**, and current data in the tables is overwritten with data from the data source.</span></span> <span data-ttu-id="93fe5-110">Sin la información del esquema, las filas nuevas del origen de datos se agregan al objeto **DataSet**, lo que genera filas duplicadas.</span><span class="sxs-lookup"><span data-stu-id="93fe5-110">Without the schema information, the new rows from the data source are appended to the **DataSet**, resulting in duplicate rows.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="93fe5-111">Si una columna de un origen de datos se identifica como de incremento automático, el método **FillSchema** o el método **Fill** con el valor **MissingSchemaAction** de **AddWithKey**, crea un **DataColumn** con una propiedad **AutoIncrement** establecida en `true` .</span><span class="sxs-lookup"><span data-stu-id="93fe5-111">If a column in a data source is identified as auto-incrementing, the **FillSchema** method, or the **Fill** method with a **MissingSchemaAction** of **AddWithKey**, creates a **DataColumn** with an **AutoIncrement** property set to `true`.</span></span> <span data-ttu-id="93fe5-112">Pero en este caso tendrá que definir manualmente los valores **AutoIncrementStep** y **AutoIncrementSeed**.</span><span class="sxs-lookup"><span data-stu-id="93fe5-112">However, you will need to set the **AutoIncrementStep** and **AutoIncrementSeed** values yourself.</span></span> <span data-ttu-id="93fe5-113">Para obtener más información acerca de las columnas de incremento automático, vea [crear columnas de incremento](./dataset-datatable-dataview/creating-autoincrement-columns.md)automático.</span><span class="sxs-lookup"><span data-stu-id="93fe5-113">For more information about auto-incrementing columns, see [Creating AutoIncrement Columns](./dataset-datatable-dataview/creating-autoincrement-columns.md).</span></span>  
  
<span data-ttu-id="93fe5-114">Al usar **FillSchema** o establecer **MissingSchemaAction** en **AddWithKey**, se necesita procesamiento adicional en el origen de datos para determinar la información de la columna de clave principal.</span><span class="sxs-lookup"><span data-stu-id="93fe5-114">Using **FillSchema** or setting the **MissingSchemaAction** to **AddWithKey** requires extra processing at the data source to determine primary key column information.</span></span> <span data-ttu-id="93fe5-115">Este proceso adicional puede reducir el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="93fe5-115">This additional processing can hinder performance.</span></span> <span data-ttu-id="93fe5-116">Si conoce en la fase de diseño la información de la clave principal, es aconsejable especificar de modo explícito la columna o columnas que la forman para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="93fe5-116">If you know the primary key information at design time, we recommend that you explicitly specify the primary key column or columns in order to achieve optimal performance.</span></span> <span data-ttu-id="93fe5-117">Para obtener información sobre cómo establecer explícitamente la información de clave principal de una tabla, vea [definir claves principales](./dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="93fe5-117">For information about explicitly setting primary key information for a table, see [Defining Primary Keys](./dataset-datatable-dataview/defining-primary-keys.md).</span></span>
  
<span data-ttu-id="93fe5-118">En el ejemplo de código siguiente se muestra cómo agregar información de esquema a un **conjunto** de datos mediante **FillSchema**:</span><span class="sxs-lookup"><span data-stu-id="93fe5-118">The following code example shows how to add schema information to a **DataSet** using **FillSchema**:</span></span>
  
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
  
<span data-ttu-id="93fe5-119">En el ejemplo de código siguiente se muestra cómo agregar información de esquema a un **conjunto** de datos mediante la propiedad **MissingSchemaAction. AddWithKey** del método **Fill** :</span><span class="sxs-lookup"><span data-stu-id="93fe5-119">The following code example shows how to add schema information to a **DataSet** using the **MissingSchemaAction.AddWithKey** property of the **Fill** method:</span></span>
  
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
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="93fe5-120">Control de varios conjuntos de resultados</span><span class="sxs-lookup"><span data-stu-id="93fe5-120">Handling multiple result sets</span></span>  

<span data-ttu-id="93fe5-121">Si el **DataAdapter** encuentra varios conjuntos de resultados devueltos por **SelectCommand**, creará varias tablas en el **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="93fe5-121">If the **DataAdapter** encounters multiple result sets returned from the **SelectCommand**, it will create multiple tables in the **DataSet**.</span></span> <span data-ttu-id="93fe5-122">Las tablas reciben de forma predeterminada un nombre secuencial de base cero **Table** *N*, comenzando por **Table** en lugar de "Table0".</span><span class="sxs-lookup"><span data-stu-id="93fe5-122">The tables will be given a zero-based incremental default name of **Table** *N*, starting with **Table** instead of "Table0".</span></span> <span data-ttu-id="93fe5-123">Si se pasa un nombre de tabla como argumento al método **FillSchema** , se asignará a las tablas un nombre incremental basado en cero de **TableName** *N*, comenzando por **TableName** en lugar de "representa tablename0".</span><span class="sxs-lookup"><span data-stu-id="93fe5-123">If a table name is passed as an argument to the **FillSchema** method, the tables will be given a zero-based incremental name of **TableName** *N*, starting with **TableName** instead of "TableName0".</span></span>  
  
> [!NOTE]
> <span data-ttu-id="93fe5-124">Si se llama al método **FillSchema** del objeto **OleDbDataAdapter** para un comando que devuelve varios conjuntos de resultados, solo se devuelve la información del esquema del primer conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="93fe5-124">If the **FillSchema** method of the **OleDbDataAdapter** object is called for a command that returns multiple result sets, only the schema information from the first result set is returned.</span></span> <span data-ttu-id="93fe5-125">Al devolver información de esquema para varios conjuntos de resultados mediante **OleDbDataAdapter**, se recomienda especificar el **MissingSchemaAction** de **AddWithKey** y obtener la información del esquema al llamar al método **Fill** .</span><span class="sxs-lookup"><span data-stu-id="93fe5-125">When returning schema information for multiple result sets using the **OleDbDataAdapter**, it is recommended that you specify a **MissingSchemaAction** of **AddWithKey** and obtain the schema information when calling the **Fill** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93fe5-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="93fe5-126">See also</span></span>

- [<span data-ttu-id="93fe5-127">Objetos DataAdapter y DataReader</span><span class="sxs-lookup"><span data-stu-id="93fe5-127">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="93fe5-128">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="93fe5-128">DataSets, DataTables, and DataViews</span></span>](./dataset-datatable-dataview/index.md)
- [<span data-ttu-id="93fe5-129">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="93fe5-129">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="93fe5-130">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="93fe5-130">ADO.NET Overview</span></span>](ado-net-overview.md)
