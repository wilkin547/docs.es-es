---
title: Objetos DataTable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52ff0e32-3e5a-41de-9a3b-7b04ea52b83e
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d1222d3df30bf2b3de1761b8fa5c702dc687d0a0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="datatables"></a><span data-ttu-id="9f742-102">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="9f742-102">DataTables</span></span>
<span data-ttu-id="9f742-103">Un objeto <xref:System.Data.DataSet> está formado por una colección de tablas, relaciones y restricciones.</span><span class="sxs-lookup"><span data-stu-id="9f742-103">A <xref:System.Data.DataSet> is made up of a collection of tables, relationships, and constraints.</span></span> <span data-ttu-id="9f742-104">En ADO.NET, <xref:System.Data.DataTable> objetos se utilizan para representar las tablas en un **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="9f742-104">In ADO.NET, <xref:System.Data.DataTable> objects are used to represent the tables in a **DataSet**.</span></span> <span data-ttu-id="9f742-105">A **DataTable** representa una tabla de datos relacionales en memoria; los datos están locales para el. Aplicación de red en el que reside, pero se pueden llenar desde un origen de datos como Microsoft SQL Server mediante un **DataAdapter** para obtener más información, consulte [llenar un DataSet desde un DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md) .</span><span class="sxs-lookup"><span data-stu-id="9f742-105">A **DataTable** represents one table of in-memory relational data; the data is local to the .NET-based application in which it resides, but can be populated from a data source such as Microsoft SQL Server using a **DataAdapter** For more information, see [Populating a DataSet from a DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md).</span></span>  
  
 <span data-ttu-id="9f742-106">El **DataTable** clase es un miembro de la **System.Data** espacio de nombres dentro de la biblioteca de clases de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9f742-106">The **DataTable** class is a member of the **System.Data** namespace within the .NET Framework class library.</span></span> <span data-ttu-id="9f742-107">Puede crear y utilizar un **DataTable** por separado o como un miembro de un **conjunto de datos**, y **DataTable** objetos también pueden utilizarse junto con otros objetos de .NET Framework incluidas la <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="9f742-107">You can create and use a **DataTable** independently or as a member of a **DataSet**, and **DataTable** objects can also be used in conjunction with other .NET Framework objects, including the <xref:System.Data.DataView>.</span></span> <span data-ttu-id="9f742-108">Obtener acceso a la colección de tablas en un **conjunto de datos** a través de la **tablas** propiedad de la **conjunto de datos** objeto.</span><span class="sxs-lookup"><span data-stu-id="9f742-108">You access the collection of tables in a **DataSet** through the **Tables** property of the **DataSet** object.</span></span>  
  
 <span data-ttu-id="9f742-109">El esquema, o estructura, de una tabla se representa con columnas y restricciones.</span><span class="sxs-lookup"><span data-stu-id="9f742-109">The schema, or structure of a table is represented by columns and constraints.</span></span> <span data-ttu-id="9f742-110">Definir el esquema de un **DataTable** con <xref:System.Data.DataColumn> objetos como <xref:System.Data.ForeignKeyConstraint> y <xref:System.Data.UniqueConstraint> objetos.</span><span class="sxs-lookup"><span data-stu-id="9f742-110">You define the schema of a **DataTable** using <xref:System.Data.DataColumn> objects as well as <xref:System.Data.ForeignKeyConstraint> and <xref:System.Data.UniqueConstraint> objects.</span></span> <span data-ttu-id="9f742-111">Las columnas de una tabla se pueden asignar a columnas de un origen de datos, pueden contener valores calculados de expresiones, aumentar sus valores automáticamente o contener valores de clave principal.</span><span class="sxs-lookup"><span data-stu-id="9f742-111">The columns in a table can map to columns in a data source, contain calculated values from expressions, automatically increment their values, or contain primary key values.</span></span>  
  
 <span data-ttu-id="9f742-112">Además del esquema, un **DataTable** debe tener también filas para albergar y ordenar los datos.</span><span class="sxs-lookup"><span data-stu-id="9f742-112">In addition to a schema, a **DataTable** must also have rows to contain and order data.</span></span> <span data-ttu-id="9f742-113">La clase <xref:System.Data.DataRow> representa los datos reales que contiene una tabla.</span><span class="sxs-lookup"><span data-stu-id="9f742-113">The <xref:System.Data.DataRow> class represents the actual data contained in a table.</span></span> <span data-ttu-id="9f742-114">Usa el **DataRow** y sus propiedades y métodos para recuperar, evaluar y manipular los datos en una tabla.</span><span class="sxs-lookup"><span data-stu-id="9f742-114">You use the **DataRow** and its properties and methods to retrieve, evaluate, and manipulate the data in a table.</span></span> <span data-ttu-id="9f742-115">Que tenga acceso y cambiar los datos dentro de una fila, el **DataRow** objeto mantiene su estado actual y original.</span><span class="sxs-lookup"><span data-stu-id="9f742-115">As you access and change the data within a row, the **DataRow** object maintains both its current and original state.</span></span>  
  
 <span data-ttu-id="9f742-116">Se pueden crear relaciones primarias-secundarias entre tablas utilizando una o varias columnas relacionadas de las tablas.</span><span class="sxs-lookup"><span data-stu-id="9f742-116">You can create parent-child relationships between tables using one or more related columns in the tables.</span></span> <span data-ttu-id="9f742-117">Crear una relación entre **DataTable** objetos mediante un <xref:System.Data.DataRelation>.</span><span class="sxs-lookup"><span data-stu-id="9f742-117">You create a relationship between **DataTable** objects using a <xref:System.Data.DataRelation>.</span></span> <span data-ttu-id="9f742-118">**DataRelation** objetos, a continuación, se pueden usar para devolver las filas secundarias o primarias relacionadas de una fila determinada.</span><span class="sxs-lookup"><span data-stu-id="9f742-118">**DataRelation** objects can then be used to return the related child or parent rows of a particular row.</span></span> <span data-ttu-id="9f742-119">Para obtener más información, consulte [agregar objetos DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).</span><span class="sxs-lookup"><span data-stu-id="9f742-119">For more information, see [Adding DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/adding-datarelations.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f742-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9f742-120">In This Section</span></span>  
 [<span data-ttu-id="9f742-121">Crear un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="9f742-121">Creating a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datatable.md)  
 <span data-ttu-id="9f742-122">Explica cómo crear un **DataTable** y agréguelo a un **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="9f742-122">Explains how to create a **DataTable** and add it to a **DataSet**.</span></span>  
  
 [<span data-ttu-id="9f742-123">Definición de esquema de DataTable</span><span class="sxs-lookup"><span data-stu-id="9f742-123">DataTable Schema Definition</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 <span data-ttu-id="9f742-124">Proporciona información sobre cómo crear y usar **DataColumn** objetos y las restricciones.</span><span class="sxs-lookup"><span data-stu-id="9f742-124">Provides information about creating and using **DataColumn** objects and constraints.</span></span>  
  
 [<span data-ttu-id="9f742-125">Manipular datos en un objeto DataTable</span><span class="sxs-lookup"><span data-stu-id="9f742-125">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 <span data-ttu-id="9f742-126">Explica cómo se agregan, modifican y eliminan datos en una tabla.</span><span class="sxs-lookup"><span data-stu-id="9f742-126">Explains how to add, modify, and delete data in a table.</span></span> <span data-ttu-id="9f742-127">Explica cómo usar **DataTable** eventos para examinar los cambios a los datos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="9f742-127">Explains how to use **DataTable** events to examine changes to data in the table.</span></span>  
  
 [<span data-ttu-id="9f742-128">Control de eventos de DataTable</span><span class="sxs-lookup"><span data-stu-id="9f742-128">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 <span data-ttu-id="9f742-129">Proporciona información acerca de los eventos disponibles para su uso con un **DataTable**, incluidos los eventos cuando se modifican los valores de columna y se agregan o eliminan filas.</span><span class="sxs-lookup"><span data-stu-id="9f742-129">Provides information about the events available for use with a **DataTable**, including events when column values are modified and rows are added or deleted.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9f742-130">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="9f742-130">Related Sections</span></span>  
 [<span data-ttu-id="9f742-131">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9f742-131">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 <span data-ttu-id="9f742-132">Describe la arquitectura y los componentes de ADO.NET, así como su uso para tener acceso a orígenes de datos existentes y para administrar los datos de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="9f742-132">Describes the ADO.NET architecture and components, and how to use them to access existing data sources and manage application data.</span></span>  
  
 [<span data-ttu-id="9f742-133">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="9f742-133">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 <span data-ttu-id="9f742-134">Proporciona información acerca de ADO.NET **conjunto de datos** incluido cómo crear relaciones entre tablas.</span><span class="sxs-lookup"><span data-stu-id="9f742-134">Provides information about the ADO.NET **DataSet** including how to create relationships between tables.</span></span>  
  
 <xref:System.Data.Constraint>  
 <span data-ttu-id="9f742-135">Proporciona información de referencia sobre la **restricción** objeto.</span><span class="sxs-lookup"><span data-stu-id="9f742-135">Provides reference information about the **Constraint** object.</span></span>  
  
 <xref:System.Data.DataColumn>  
 <span data-ttu-id="9f742-136">Proporciona información de referencia sobre la **DataColumn** objeto.</span><span class="sxs-lookup"><span data-stu-id="9f742-136">Provides reference information about the **DataColumn** object.</span></span>  
  
 <xref:System.Data.DataSet>  
 <span data-ttu-id="9f742-137">Proporciona información de referencia sobre la **conjunto de datos** objeto.</span><span class="sxs-lookup"><span data-stu-id="9f742-137">Provides reference information about the **DataSet** object.</span></span>  
  
 <xref:System.Data.DataTable>  
 <span data-ttu-id="9f742-138">Proporciona información de referencia sobre la **DataTable** objeto.</span><span class="sxs-lookup"><span data-stu-id="9f742-138">Provides reference information about the **DataTable** object.</span></span>  
  
 [<span data-ttu-id="9f742-139">Información general de la biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="9f742-139">Class Library Overview</span></span>](../../../../../docs/standard/class-library-overview.md)  
 <span data-ttu-id="9f742-140">Proporciona información general de la biblioteca de clases de .NET Framework, incluido el **System** espacio de nombres, así como su espacio de nombres de segundo nivel, **System.Data**.</span><span class="sxs-lookup"><span data-stu-id="9f742-140">Provides an overview of the .NET Framework class library, including the **System** namespace as well as its second-level namespace, **System.Data**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f742-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f742-141">See Also</span></span>  
 [<span data-ttu-id="9f742-142">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="9f742-142">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
