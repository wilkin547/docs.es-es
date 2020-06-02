---
title: Objetos DataSet, DataTable y DataView
description: Aprenda varias maneras de trabajar con un conjunto de datos de ADO.NET, una representación residente en memoria de los datos que proporciona un modelo de programación relacional coherente.
ms.date: 03/30/2017
ms.assetid: 6d4c4b69-8919-4224-8a65-6cca1c61b48f
ms.openlocfilehash: f6562452261cbc1f7ee36fb264b858646a42e4f5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286900"
---
# <a name="datasets-datatables-and-dataviews"></a><span data-ttu-id="12102-103">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="12102-103">DataSets, DataTables, and DataViews</span></span>
<span data-ttu-id="12102-104">El <xref:System.Data.DataSet> de ADO.NET es una representación de datos residente en memoria que proporciona un modelo de programación relacional coherente independientemente del origen de datos que contiene.</span><span class="sxs-lookup"><span data-stu-id="12102-104">The ADO.NET <xref:System.Data.DataSet> is a memory-resident representation of data that provides a consistent relational programming model regardless of the source of the data it contains.</span></span> <span data-ttu-id="12102-105">Un <xref:System.Data.DataSet> representa un conjunto completo de datos, incluyendo las tablas que contienen, ordenan y restringen los datos, así como las relaciones entre las tablas.</span><span class="sxs-lookup"><span data-stu-id="12102-105">A <xref:System.Data.DataSet> represents a complete set of data including the tables that contain, order, and constrain the data, as well as the relationships between the tables.</span></span>  
  
 <span data-ttu-id="12102-106">Hay varias maneras de trabajar con un <xref:System.Data.DataSet>, que se pueden aplicar de forma independiente o conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="12102-106">There are several ways of working with a <xref:System.Data.DataSet>, which can be applied independently or in combination.</span></span> <span data-ttu-id="12102-107">Puede:</span><span class="sxs-lookup"><span data-stu-id="12102-107">You can:</span></span>  
  
- <span data-ttu-id="12102-108">Crear mediante programación una <xref:System.Data.DataTable>, <xref:System.Data.DataRelation> y una <xref:System.Data.Constraint> en un <xref:System.Data.DataSet> y rellenar las tablas con datos.</span><span class="sxs-lookup"><span data-stu-id="12102-108">Programmatically create a <xref:System.Data.DataTable>, <xref:System.Data.DataRelation>, and <xref:System.Data.Constraint> within a <xref:System.Data.DataSet> and populate the tables with data.</span></span>  
  
- <span data-ttu-id="12102-109">Llenar el <xref:System.Data.DataSet> con tablas de datos de un origen de datos relacional existente mediante `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="12102-109">Populate the <xref:System.Data.DataSet> with tables of data from an existing relational data source using a `DataAdapter`.</span></span>  
  
- <span data-ttu-id="12102-110">Cargar y hacer persistente el contenido de <xref:System.Data.DataSet> mediante XML.</span><span class="sxs-lookup"><span data-stu-id="12102-110">Load and persist the <xref:System.Data.DataSet> contents using XML.</span></span> <span data-ttu-id="12102-111">Para obtener más información, vea [Using XML in a DataSet](using-xml-in-a-dataset.md) (Usar XML en un conjunto de datos).</span><span class="sxs-lookup"><span data-stu-id="12102-111">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
 <span data-ttu-id="12102-112">También se puede transportar un <xref:System.Data.DataSet> fuertemente tipado mediante un servicio Web XML.</span><span class="sxs-lookup"><span data-stu-id="12102-112">A strongly typed <xref:System.Data.DataSet> can also be transported using an XML Web service.</span></span> <span data-ttu-id="12102-113">El diseño del <xref:System.Data.DataSet> lo convierte en idóneo para el transporte de datos mediante servicios Web XML.</span><span class="sxs-lookup"><span data-stu-id="12102-113">The design of the <xref:System.Data.DataSet> makes it ideal for transporting data using XML Web services.</span></span> <span data-ttu-id="12102-114">Para obtener información general sobre servicios Web XML, vea [Información general de servicios Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="12102-114">For an overview of XML Web services, see [XML Web Services Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w9fdtx28(v=vs.100)).</span></span> <span data-ttu-id="12102-115">Para obtener un ejemplo sobre cómo usar un objeto <xref:System.Data.DataSet> desde un servicio Web XML, vea [Consuming a DataSet from an XML Web Service](consuming-a-dataset-from-an-xml-web-service.md) (Usar un conjunto de datos desde un servicio Web XML).</span><span class="sxs-lookup"><span data-stu-id="12102-115">For an example of consuming a <xref:System.Data.DataSet> from an XML Web service, see [Consuming a DataSet from an XML Web Service](consuming-a-dataset-from-an-xml-web-service.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="12102-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="12102-116">In This Section</span></span>  
 [<span data-ttu-id="12102-117">Creación de un conjunto de DataSet</span><span class="sxs-lookup"><span data-stu-id="12102-117">Creating a DataSet</span></span>](creating-a-dataset.md)  
 <span data-ttu-id="12102-118">Describe la sintaxis para crear una instancia de <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="12102-118">Describes the syntax for creating an instance of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="12102-119">Agregar un objeto DataTable a un objeto DataSet</span><span class="sxs-lookup"><span data-stu-id="12102-119">Adding a DataTable to a DataSet</span></span>](adding-a-datatable-to-a-dataset.md)  
 <span data-ttu-id="12102-120">Describe cómo crear tablas y columnas y cómo agregarlas a un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="12102-120">Describes how to create and add tables and columns to a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="12102-121">Agregar objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="12102-121">Adding DataRelations</span></span>](adding-datarelations.md)  
 <span data-ttu-id="12102-122">Describe cómo se crean las relaciones entre tablas en un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="12102-122">Describes how to create relations between tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="12102-123">Navegar por objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="12102-123">Navigating DataRelations</span></span>](navigating-datarelations.md)  
 <span data-ttu-id="12102-124">Describe cómo se utilizan las relaciones entre tablas en un <xref:System.Data.DataSet> para devolver la filas secundarias o primarias de una relación primaria-secundaria.</span><span class="sxs-lookup"><span data-stu-id="12102-124">Describes how to use the relations between tables in a <xref:System.Data.DataSet> to return the child or parent rows of a parent-child relationship.</span></span>  
  
 [<span data-ttu-id="12102-125">Combinar contenido de DataSet</span><span class="sxs-lookup"><span data-stu-id="12102-125">Merging DataSet Contents</span></span>](merging-dataset-contents.md)  
 <span data-ttu-id="12102-126">Describe cómo se fusiona mediante combinación el contenido de una matriz de <xref:System.Data.DataSet>, <xref:System.Data.DataTable> o <xref:System.Data.DataRow> con otro <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="12102-126">Describes how to merge the contents of one <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, or <xref:System.Data.DataRow> array into another <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="12102-127">Copiar el contenido de DataSet</span><span class="sxs-lookup"><span data-stu-id="12102-127">Copying DataSet Contents</span></span>](copying-dataset-contents.md)  
 <span data-ttu-id="12102-128">Describe cómo se crea una copia de un <xref:System.Data.DataSet> que puede contener datos de esquema y datos especificados.</span><span class="sxs-lookup"><span data-stu-id="12102-128">Describes how to create a copy of a <xref:System.Data.DataSet> that can contain schema as well as specified data.</span></span>  
  
 [<span data-ttu-id="12102-129">Controlar eventos de DataSet</span><span class="sxs-lookup"><span data-stu-id="12102-129">Handling DataSet Events</span></span>](handling-dataset-events.md)  
 <span data-ttu-id="12102-130">Describe los eventos de un <xref:System.Data.DataSet> y cómo utilizarlos.</span><span class="sxs-lookup"><span data-stu-id="12102-130">Describes the events of a <xref:System.Data.DataSet> and how to use them.</span></span>  
  
 [<span data-ttu-id="12102-131">Objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="12102-131">Typed DataSets</span></span>](typed-datasets.md)  
 <span data-ttu-id="12102-132">Explica lo que es un <xref:System.Data.DataSet> con información de tipos y cómo crearlo y utilizarlo.</span><span class="sxs-lookup"><span data-stu-id="12102-132">Discusses what a typed <xref:System.Data.DataSet> is and how to create and use it.</span></span>  
  
 [<span data-ttu-id="12102-133">Objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="12102-133">DataTables</span></span>](datatables.md)  
 <span data-ttu-id="12102-134">Describe cómo se crea una <xref:System.Data.DataTable>, cómo se define el esquema y cómo se manipulan los datos.</span><span class="sxs-lookup"><span data-stu-id="12102-134">Describes how to create a <xref:System.Data.DataTable>, define the schema, and manipulate data.</span></span>  
  
 [<span data-ttu-id="12102-135">Objetos DataTableReader</span><span class="sxs-lookup"><span data-stu-id="12102-135">DataTableReaders</span></span>](datatablereaders.md)  
 <span data-ttu-id="12102-136">Describe cómo crear y utilizar un objeto <xref:System.Data.DataTableReader>.</span><span class="sxs-lookup"><span data-stu-id="12102-136">Describes how to create and use a <xref:System.Data.DataTableReader>.</span></span>  
  
 [<span data-ttu-id="12102-137">Objetos DataView</span><span class="sxs-lookup"><span data-stu-id="12102-137">DataViews</span></span>](dataviews.md)  
 <span data-ttu-id="12102-138">Describe cómo se crean `DataViews` y cómo se trabaja con ellas, así como con eventos <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="12102-138">Describes how to create and work with `DataViews` and work with <xref:System.Data.DataView> events.</span></span>  
  
 [<span data-ttu-id="12102-139">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="12102-139">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="12102-140">Describe cómo interactúa el <xref:System.Data.DataSet> con XML como origen de datos, incluyendo cómo cargar y hacer persistente el contenido de un <xref:System.Data.DataSet> como datos XML.</span><span class="sxs-lookup"><span data-stu-id="12102-140">Describes how the <xref:System.Data.DataSet> interacts with XML as a data source, including loading and persisting the contents of a <xref:System.Data.DataSet> as XML data.</span></span>  
  
 [<span data-ttu-id="12102-141">Utilizar un conjunto de datos desde un servicio Web XML</span><span class="sxs-lookup"><span data-stu-id="12102-141">Consuming a DataSet from an XML Web Service</span></span>](consuming-a-dataset-from-an-xml-web-service.md)  
 <span data-ttu-id="12102-142">Describe cómo crear un servicio Web XML que utilice un <xref:System.Data.DataSet> para transportar los datos.</span><span class="sxs-lookup"><span data-stu-id="12102-142">Describes how to create an XML Web service that uses a <xref:System.Data.DataSet> to transport data.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="12102-143">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="12102-143">Related Sections</span></span>  
 [<span data-ttu-id="12102-144">Novedades de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="12102-144">What's New in ADO.NET</span></span>](../whats-new.md)  
 <span data-ttu-id="12102-145">Presenta características nuevas en ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="12102-145">Introduces features that are new in ADO.NET.</span></span>  
  
 [<span data-ttu-id="12102-146">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="12102-146">ADO.NET Overview</span></span>](../ado-net-overview.md)  
 <span data-ttu-id="12102-147">Proporciona una introducción al diseño y a los componentes de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="12102-147">Provides an introduction to the design and components of ADO.NET.</span></span>  
  
 [<span data-ttu-id="12102-148">Rellenar un conjunto de datos desde un objeto DataAdapter</span><span class="sxs-lookup"><span data-stu-id="12102-148">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)  
 <span data-ttu-id="12102-149">Describe cómo se carga un objeto **DataSet** con datos desde un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="12102-149">Describes how to load a **DataSet** with data from a data source.</span></span>  
  
 [<span data-ttu-id="12102-150">Actualizar orígenes de datos con objetos DataAdapter</span><span class="sxs-lookup"><span data-stu-id="12102-150">Updating Data Sources with DataAdapters</span></span>](../updating-data-sources-with-dataadapters.md)  
 <span data-ttu-id="12102-151">Describe cómo se resuelven los cambios relacionados con los datos de un **DataSet** en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="12102-151">Describes how to resolve changes to the data in a **DataSet** back to the data source.</span></span>  
  
 [<span data-ttu-id="12102-152">Agregar restricciones existentes a un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="12102-152">Adding Existing Constraints to a DataSet</span></span>](../adding-existing-constraints-to-a-dataset.md)  
 <span data-ttu-id="12102-153">Describe cómo se rellena un objeto **DataSet** con información de clave principal de un origen de datos.</span><span class="sxs-lookup"><span data-stu-id="12102-153">Describes how to populate a **DataSet** with primary key information from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12102-154">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12102-154">See also</span></span>

- [<span data-ttu-id="12102-155">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="12102-155">ADO.NET</span></span>](../index.md)
- [<span data-ttu-id="12102-156">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="12102-156">ADO.NET Overview</span></span>](../ado-net-overview.md)
