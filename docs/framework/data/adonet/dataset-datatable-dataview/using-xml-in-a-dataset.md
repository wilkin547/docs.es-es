---
description: 'Más información sobre: usar XML en un conjunto de'
title: Usar XML en un conjunto de datos
ms.date: 03/30/2017
ms.assetid: 35138159-e199-49ec-baf7-1ec6777e171e
ms.openlocfilehash: 5c4216fce9c1512c95da8e27a622ba228411b641
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651423"
---
# <a name="using-xml-in-a-dataset"></a><span data-ttu-id="11bbe-103">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="11bbe-103">Using XML in a DataSet</span></span>

<span data-ttu-id="11bbe-104">Con ADO.NET es posible llenar un <xref:System.Data.DataSet> a partir de una secuencia o un documento XML.</span><span class="sxs-lookup"><span data-stu-id="11bbe-104">With ADO.NET you can fill a <xref:System.Data.DataSet> from an XML stream or document.</span></span> <span data-ttu-id="11bbe-105">Se puede utilizar la secuencia o el documento XML para suministrar datos al <xref:System.Data.DataSet>, información de esquema o ambas cosas.</span><span class="sxs-lookup"><span data-stu-id="11bbe-105">You can use the XML stream or document to supply to the <xref:System.Data.DataSet> either data, schema information, or both.</span></span> <span data-ttu-id="11bbe-106">La información suministrada desde la secuencia o el documento XML puede combinarse con datos o información de esquema existente ya presente en el <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="11bbe-106">The information supplied from the XML stream or document can be combined with existing data or schema information already present in the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="11bbe-107">ADO.NET también permite crear una representación XML de un <xref:System.Data.DataSet>, con o sin su esquema, para transportar el <xref:System.Data.DataSet> a través de HTTP con el fin de que lo utilice otra aplicación u otra plataforma compatible con XML.</span><span class="sxs-lookup"><span data-stu-id="11bbe-107">ADO.NET also allows you to create an XML representation of a <xref:System.Data.DataSet>, with or without its schema, in order to transport the <xref:System.Data.DataSet> across HTTP for use by another application or XML-enabled platform.</span></span> <span data-ttu-id="11bbe-108">En una representación XML de un <xref:System.Data.DataSet>, los datos se escriben en XML y el esquema, si está incluido alineado en la representación, se escribe utilizando el lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="11bbe-108">In an XML representation of a <xref:System.Data.DataSet>, the data is written in XML and the schema, if it is included inline in the representation, is written using the XML Schema definition language (XSD).</span></span> <span data-ttu-id="11bbe-109">XML y el esquema XML proporcionan un formato cómodo para transferir el contenido de un <xref:System.Data.DataSet> a y desde clientes remotos.</span><span class="sxs-lookup"><span data-stu-id="11bbe-109">XML and XML Schema provide a convenient format for transferring the contents of a <xref:System.Data.DataSet> to and from remote clients.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="11bbe-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="11bbe-110">In This Section</span></span>  

 [<span data-ttu-id="11bbe-111">Objetos DiffGram</span><span class="sxs-lookup"><span data-stu-id="11bbe-111">DiffGrams</span></span>](diffgrams.md)  
 <span data-ttu-id="11bbe-112">Proporciona detalles acerca de DiffGram, un formato XML utilizado para leer y escribir el contenido de un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="11bbe-112">Provides details on the DiffGram, an XML format used to read and write the contents of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="11bbe-113">Cargar un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="11bbe-113">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)  
 <span data-ttu-id="11bbe-114">Describe las distintas opciones que hay que tener en cuenta al cargar el contenido de un <xref:System.Data.DataSet> desde un documento XML.</span><span class="sxs-lookup"><span data-stu-id="11bbe-114">Discusses different options to consider when loading the contents of a <xref:System.Data.DataSet> from an XML document.</span></span>  
  
 [<span data-ttu-id="11bbe-115">Escribir el contenido de un conjunto de datos como datos XML</span><span class="sxs-lookup"><span data-stu-id="11bbe-115">Writing DataSet Contents as XML Data</span></span>](writing-dataset-contents-as-xml-data.md)  
 <span data-ttu-id="11bbe-116">Describe cómo generar el contenido de un <xref:System.Data.DataSet> como datos XML y las distintas opciones de formato XML que se pueden utilizar.</span><span class="sxs-lookup"><span data-stu-id="11bbe-116">Discusses how to generate the contents of a <xref:System.Data.DataSet> as XML data, and the different XML format options you can use.</span></span>  
  
 [<span data-ttu-id="11bbe-117">Cargar información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="11bbe-117">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)  
 <span data-ttu-id="11bbe-118">Describe los métodos <xref:System.Data.DataSet> utilizados para cargar el esquema de un <xref:System.Data.DataSet> desde XML.</span><span class="sxs-lookup"><span data-stu-id="11bbe-118">Discusses the <xref:System.Data.DataSet> methods used to load the schema of a <xref:System.Data.DataSet> from XML.</span></span>  
  
 [<span data-ttu-id="11bbe-119">Escribir información del esquema de un conjunto de datos como XSD</span><span class="sxs-lookup"><span data-stu-id="11bbe-119">Writing DataSet Schema Information as XSD</span></span>](writing-dataset-schema-information-as-xsd.md)  
 <span data-ttu-id="11bbe-120">Describe los usos de un esquema XML y cómo generar uno a partir de un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="11bbe-120">Discusses the uses for an XML Schema and how to generate one from a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="11bbe-121">Sincronización de DataSet y XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="11bbe-121">DataSet and XmlDataDocument Synchronization</span></span>](dataset-and-xmldatadocument-synchronization.md)  
 <span data-ttu-id="11bbe-122">Describe la posibilidad existente en .NET Framework de tener acceso sincrónicamente a las vistas relacional y jerárquica de un único conjunto de datos, a la vez que muestra cómo crear una relación sincrónica entre un <xref:System.Data.DataSet> y un <xref:System.Xml.XmlDataDocument>.</span><span class="sxs-lookup"><span data-stu-id="11bbe-122">Discusses the capability available in the .NET Framework of synchronous access to both relational and hierarchical views of a single set of data, and shows how to create a synchronous relationship between a <xref:System.Data.DataSet> and an <xref:System.Xml.XmlDataDocument>.</span></span>  
  
 [<span data-ttu-id="11bbe-123">Anidar objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="11bbe-123">Nesting DataRelations</span></span>](nesting-datarelations.md)  
 <span data-ttu-id="11bbe-124">Explica la importancia de los objetos <xref:System.Data.DataRelation> anidados al representar el contenido de un <xref:System.Data.DataSet> como datos XML y describe cómo crearlos.</span><span class="sxs-lookup"><span data-stu-id="11bbe-124">Discusses the importance of nested <xref:System.Data.DataRelation> objects when representing the contents of a <xref:System.Data.DataSet> as XML data, and describes how to create them.</span></span>  
  
 [<span data-ttu-id="11bbe-125">Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="11bbe-125">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="11bbe-126">Describe la estructura relacional, o esquema, de un <xref:System.Data.DataSet> creado a partir de un esquema XML.</span><span class="sxs-lookup"><span data-stu-id="11bbe-126">Describes the relational structure, or schema, of a <xref:System.Data.DataSet> that is created from XML Schema.</span></span>  
  
 [<span data-ttu-id="11bbe-127">Inferir una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="11bbe-127">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)  
 <span data-ttu-id="11bbe-128">Describe la estructura relacional, o esquema, resultante de un <xref:System.Data.DataSet> que se crea por inferencia a partir de elementos XML.</span><span class="sxs-lookup"><span data-stu-id="11bbe-128">Describes the resulting relational structure, or schema, of a <xref:System.Data.DataSet> that is created when inferred from XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="11bbe-129">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="11bbe-129">Related Sections</span></span>  

 [<span data-ttu-id="11bbe-130">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="11bbe-130">ADO.NET Overview</span></span>](../ado-net-overview.md)  
 <span data-ttu-id="11bbe-131">Describe la arquitectura y los componentes de ADO.NET, así como su uso para tener acceso a orígenes de datos existentes y administrar los datos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="11bbe-131">Describes the ADO.NET architecture and components, and how to use them to access existing data sources as well as to manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11bbe-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="11bbe-132">See also</span></span>

- [<span data-ttu-id="11bbe-133">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="11bbe-133">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="11bbe-134">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="11bbe-134">ADO.NET Overview</span></span>](../ado-net-overview.md)
