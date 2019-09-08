---
title: Objetos DataSet, DataTable y DataView
ms.date: 03/30/2017
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
ms.openlocfilehash: 1744f6c6d8ea3c28a8dab30c0d201ae1dacc7ee3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786193"
---
# <a name="datasets-datatables-and-dataviews"></a><span data-ttu-id="73f96-102">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="73f96-102">DataSets, DataTables, and DataViews</span></span>
<span data-ttu-id="73f96-103">El <xref:System.Data.DataSet> de ADO.NET es una representación de datos residente en memoria que proporciona un modelo de programación relacional coherente independientemente del origen de datos que contiene.</span><span class="sxs-lookup"><span data-stu-id="73f96-103">The ADO.NET <xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model regardless of the source of the data it contains.</span></span> <span data-ttu-id="73f96-104">Un <xref:System.Data.DataSet> representa un conjunto completo de datos, incluyendo las tablas que contienen, ordenan y restringen los datos, así como las relaciones entre las tablas.</span><span class="sxs-lookup"><span data-stu-id="73f96-104">A <xref:System.Data.DataSet> represents a complete set of data including the tables that contain, order, and constrain the data, as well as the relationships between the tables.</span></span>  
  
 <span data-ttu-id="73f96-105">Hay varias maneras de trabajar con un <xref:System.Data.DataSet>, que se pueden aplicar de forma independiente o conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="73f96-105">There are several ways of working with a <xref:System.Data.DataSet>, which can be applied independently or in combination.</span></span> <span data-ttu-id="73f96-106">Puede:</span><span class="sxs-lookup"><span data-stu-id="73f96-106">You can:</span></span>  
  
- <span data-ttu-id="73f96-107">Crear mediante programación una <xref:System.Data.DataTable>, <xref:System.Data.DataRelation> y una <xref:System.Data.Constraint> en un <xref:System.Data.DataSet> y rellenar las tablas con datos.</span><span class="sxs-lookup"><span data-stu-id="73f96-107">Programmatically create a <xref:System.Data.DataTable>, <xref:System.Data.DataRelation>, and <xref:System.Data.Constraint> within a <xref:System.Data.DataSet> and populate the tables with data.</span></span>  
  
- <span data-ttu-id="73f96-108">Llenar el <xref:System.Data.DataSet> con tablas de datos de un origen de datos relacional existente mediante `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="73f96-108">Populate the <xref:System.Data.DataSet> with tables of data from an existing relational data source using a `DataAdapter`.</span></span>  
  
- <span data-ttu-id="73f96-109">Cargar y hacer persistente el contenido de <xref:System.Data.DataSet> mediante XML.</span><span class="sxs-lookup"><span data-stu-id="73f96-109">Load and persist the <xref:System.Data.DataSet> contents using XML.</span></span> <span data-ttu-id="73f96-110">Para obtener más información, vea [Using XML in a DataSet](using-xml-in-a-dataset.md) (Usar XML en un conjunto de datos).</span><span class="sxs-lookup"><span data-stu-id="73f96-110">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
 <span data-ttu-id="73f96-111">También se puede transportar un <xref:System.Data.DataSet> fuertemente tipado mediante un servicio Web XML.</span><span class="sxs-lookup"><span data-stu-id="73f96-111">A strongly typed <xref:System.Data.DataSet> can also be transported using an XML Web service.</span></span> <span data-ttu-id="73f96-112">El diseño del <xref:System.Data.DataSet> lo convierte en idóneo para el transporte de datos mediante servicios Web XML.</span><span class="sxs-lookup"><span data-stu-id="73f96-112">The design of the <xref:System.Data.DataSet> makes it ideal for transporting data using XML Web services.</span></span> <span data-ttu-id="73f96-113">Para obtener información general sobre servicios Web XML, vea [Información general de servicios Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="73f96-113">For an overview of XML Web services, see [XML Web Services Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span></span> <span data-ttu-id="73f96-114">Para obtener un ejemplo sobre cómo usar un objeto <xref:System.Data.DataSet> desde un servicio Web XML, vea [Consuming a DataSet from an XML Web Service](consuming-a-dataset-from-an-xml-web-service.md) (Usar un conjunto de datos desde un servicio Web XML).</span><span class="sxs-lookup"><span data-stu-id="73f96-114">For an example of consuming a <xref:System.Data.DataSet> from an XML Web service, see [Consuming a DataSet from an XML Web Service](consuming-a-dataset-from-an-xml-web-service.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="73f96-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="73f96-115">In This Section</span></span>  
 [<span data-ttu-id="73f96-116">Crear un objeto DataSet</span><span class="sxs-lookup"><span data-stu-id="73f96-116">Creating a DataSet</span></span>](creating-a-dataset.md)  
 <span data-ttu-id="73f96-117">Describe la sintaxis para crear una instancia de <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="73f96-117">Describes the syntax for creating an instance of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="73f96-118">Agregar un objeto DataTable a un objeto DataSet</span><span class="sxs-lookup"><span data-stu-id="73f96-118">Adding a DataTable to a DataSet</span></span>](adding-a-datatable-to-a-dataset.md)  
 <span data-ttu-id="73f96-119">Describe cómo crear tablas y columnas y cómo agregarlas a un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="73f96-119">Describes how to create and add tables and columns to a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="73f96-120">Agregar objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="73f96-120">Adding DataRelations</span></span>](adding-datarelations.md)  
 <span data-ttu-id="73f96-121">Describe cómo se crean las relaciones entre tablas en un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="73f96-121">Describes how to create relations between tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="73f96-122">Navegar por objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="73f96-122">Navigating DataRelations</span></span>](navigating-datarelations.md)  
 <span data-ttu-id="73f96-123">Describe cómo se utilizan las relaciones entre tablas en un <xref:System.Data.DataSet> para devolver la filas secundarias o primarias de una relación primaria-secundaria.</span><span class="sxs-lookup"><span data-stu-id="73f96-123">Describes how to use the relations between tables in a <xref:System.Data.DataSet> to return the child or parent rows of a parent-child relationship.</span></span>  
  
 [<span data-ttu-id="73f96-124">Combinar contenido de DataSet</span><span class="sxs-lookup"><span data-stu-id="73f96-124">Merging DataSet Contents</span></span>](merging-dataset-contents.md)  
 <span data-ttu-id="73f96-125">Describe cómo se fusiona mediante combinación el contenido de una matriz de <xref:System.Data.DataSet>, <xref:System.Data.DataTable> o <xref:System.Data.DataRow> con otro <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="73f96-125">Describes how to merge the contents of one <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, or <xref:System.Data.DataRow> array into another <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="73f96-126">Copiar el contenido de DataSet</span><span class="sxs-lookup"><span data-stu-id="73f96-126">Copying DataSet Contents</span></span>](copying-dataset-contents.md)  
 <span data-ttu-id="73f96-127">Describe cómo se crea una copia de un <xref:System.Data.DataSet> que puede contener datos de esquema y datos especificados.</span><span class="sxs-lookup"><span data-stu-id="73f96-127">Describes how to create a copy of a <xref:System.Data.DataSet> that can contain schema as well as specified data.</span></span>  
  
 [<span data-ttu-id="73f96-128">Controlar eventos de DataSet</span><span class="sxs-lookup"><span data-stu-id="73f96-128">Handling DataSet Events</span></span>](handling-dataset-events.md)  
 <span data-ttu-id="73f96-129">Describe los eventos de un <xref:System.Data.DataSet> y cómo utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="73f96-129">Describes the events of a <xref:System.Data.DataSet> and how to use them.</span></span>  
  
 [<span data-ttu-id="73f96-130">Objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="73f96-130">Typed DataSets</span></span>](typed-datasets.md)  
 <span data-ttu-id="73f96-131">Explica lo que es un <xref:System.Data.DataSet> con información de tipos y cómo crearlo y utilizarlo.</span><span class="sxs-lookup"><span data-stu-id="73f96-131">Discusses what a typed <xref:System.Data.DataSet> is and how to create and use it.</span></span>  
  
 [<span data-ttu-id="73f96-132">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="73f96-132">DataTables</span></span>](datatables.md)  
 <span data-ttu-id="73f96-133">Describe cómo se crea una <xref:System.Data.DataTable>, cómo se define el esquema y cómo se manipulan los datos.</span><span class="sxs-lookup"><span data-stu-id="73f96-133">Describes how to create a <xref:System.Data.DataTable>, define the schema, and manipulate data.</span></span>  
  
 [<span data-ttu-id="73f96-134">Objetos DataTableReader</span><span class="sxs-lookup"><span data-stu-id="73f96-134">DataTableReaders</span></span>](datatablereaders.md)  
 <span data-ttu-id="73f96-135">Describe cómo crear y utilizar un objeto <xref:System.Data.DataTableReader>.</span><span class="sxs-lookup"><span data-stu-id="73f96-135">Describes how to create and use a <xref:System.Data.DataTableReader>.</span></span>  
  
 [<span data-ttu-id="73f96-136">Objetos DataView</span><span class="sxs-lookup"><span data-stu-id="73f96-136">DataViews</span></span>](dataviews.md)  
 <span data-ttu-id="73f96-137">Describe cómo se crean `DataViews` y cómo se trabaja con ellas, así como con eventos <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="73f96-137">Describes how to create and work with `DataViews` and work with <xref:System.Data.DataView> events.</span></span>  
  
 [<span data-ttu-id="73f96-138">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="73f96-138">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="73f96-139">Describe cómo interactúa el <xref:System.Data.DataSet> con XML como origen de datos, incluyendo cómo cargar y hacer persistente el contenido de un <xref:System.Data.DataSet> como datos XML.</span><span class="sxs-lookup"><span data-stu-id="73f96-139">Describes how the <xref:System.Data.DataSet> interacts with XML as a data source, including loading and persisting the contents of a <xref:System.Data.DataSet> as XML data.</span></span>  
  
 [<span data-ttu-id="73f96-140">Usar un conjunto de datos desde un servicio Web XML</span><span class="sxs-lookup"><span data-stu-id="73f96-140">Consuming a DataSet from an XML Web Service</span></span>](consuming-a-dataset-from-an-xml-web-service.md)  
 <span data-ttu-id="73f96-141">Describe cómo crear un servicio Web XML que utilice un <xref:System.Data.DataSet> para transportar los datos.</span><span class="sxs-lookup"><span data-stu-id="73f96-141">Describes how to create an XML Web service that uses a <xref:System.Data.DataSet> to transport data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="73f96-142">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="73f96-142">Related Sections</span></span>  
 [<span data-ttu-id="73f96-143">Novedades de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="73f96-143">What's New in ADO.NET</span></span>](../whats-new.md)  
 <span data-ttu-id="73f96-144">Presenta características nuevas en ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="73f96-144">Introduces features that are new in ADO.NET.</span></span>  
  
 [<span data-ttu-id="73f96-145">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="73f96-145">ADO.NET Overview</span></span>](../ado-net-overview.md)  
 <span data-ttu-id="73f96-146">Proporciona una introducción al diseño y a los componentes de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="73f96-146">Provides an introduction to the design and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="73f96-147">Rellenar un conjunto de datos desde un objeto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="73f96-147">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="73f96-148">Describe cómo se carga un objeto **DataSet** con datos desde un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="73f96-148">Describes how to load a **DataSet** with data from a data source.</span></span>  
  
 [<span data-ttu-id="73f96-149">Actualizar orígenes de datos con objetos DataAdapter</span><span class="sxs-lookup"><span data-stu-id="73f96-149">Updating Data Sources with DataAdapters</span></span>](../updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="73f96-150">Describe cómo se resuelven los cambios relacionados con los datos de un **DataSet** en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="73f96-150">Describes how to resolve changes to the data in a **DataSet** back to the data source.</span></span>  
  
 [<span data-ttu-id="73f96-151">Agregar restricciones existentes a un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="73f96-151">Adding Existing Constraints to a DataSet</span></span>](../adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="73f96-152">Describe cómo se rellena un objeto **DataSet** con información de clave principal de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="73f96-152">Describes how to populate a **DataSet** with primary key information from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73f96-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="73f96-153">See also</span></span>

- [<span data-ttu-id="73f96-154">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="73f96-154">ADO.NET</span></span>](../index.md)
- [<span data-ttu-id="73f96-155">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="73f96-155">ADO.NET Overview</span></span>](../ado-net-overview.md)
