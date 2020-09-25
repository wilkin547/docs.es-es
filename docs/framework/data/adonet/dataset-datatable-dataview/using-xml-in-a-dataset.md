---
title: Usar XML en un conjunto de datos
ms.date: 03/30/2017
ms.assetid: 35138159-e199-49ec-baf7-1ec6777e171e
ms.openlocfilehash: e133da727887271af3bc5330a5779df4af58a37e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201192"
---
# <a name="using-xml-in-a-dataset"></a><span data-ttu-id="b75ba-102">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="b75ba-102">Using XML in a DataSet</span></span>

<span data-ttu-id="b75ba-103">Con ADO.NET es posible llenar un <xref:System.Data.DataSet> a partir de una secuencia o un documento XML.</span><span class="sxs-lookup"><span data-stu-id="b75ba-103">With ADO.NET you can fill a <xref:System.Data.DataSet> from an XML stream or document.</span></span> <span data-ttu-id="b75ba-104">Se puede utilizar la secuencia o el documento XML para suministrar datos al <xref:System.Data.DataSet>, información de esquema o ambas cosas.</span><span class="sxs-lookup"><span data-stu-id="b75ba-104">You can use the XML stream or document to supply to the <xref:System.Data.DataSet> either data, schema information, or both.</span></span> <span data-ttu-id="b75ba-105">La información suministrada desde la secuencia o el documento XML puede combinarse con datos o información de esquema existente ya presente en el <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="b75ba-105">The information supplied from the XML stream or document can be combined with existing data or schema information already present in the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="b75ba-106">ADO.NET también permite crear una representación XML de un <xref:System.Data.DataSet>, con o sin su esquema, para transportar el <xref:System.Data.DataSet> a través de HTTP con el fin de que lo utilice otra aplicación u otra plataforma compatible con XML.</span><span class="sxs-lookup"><span data-stu-id="b75ba-106">ADO.NET also allows you to create an XML representation of a <xref:System.Data.DataSet>, with or without its schema, in order to transport the <xref:System.Data.DataSet> across HTTP for use by another application or XML-enabled platform.</span></span> <span data-ttu-id="b75ba-107">En una representación XML de un <xref:System.Data.DataSet>, los datos se escriben en XML y el esquema, si está incluido alineado en la representación, se escribe utilizando el lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="b75ba-107">In an XML representation of a <xref:System.Data.DataSet>, the data is written in XML and the schema, if it is included inline in the representation, is written using the XML Schema definition language (XSD).</span></span> <span data-ttu-id="b75ba-108">XML y el esquema XML proporcionan un formato cómodo para transferir el contenido de un <xref:System.Data.DataSet> a y desde clientes remotos.</span><span class="sxs-lookup"><span data-stu-id="b75ba-108">XML and XML Schema provide a convenient format for transferring the contents of a <xref:System.Data.DataSet> to and from remote clients.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b75ba-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b75ba-109">In This Section</span></span>  

 [<span data-ttu-id="b75ba-110">Objetos DiffGram</span><span class="sxs-lookup"><span data-stu-id="b75ba-110">DiffGrams</span></span>](diffgrams.md)  
 <span data-ttu-id="b75ba-111">Proporciona detalles acerca de DiffGram, un formato XML utilizado para leer y escribir el contenido de un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="b75ba-111">Provides details on the DiffGram, an XML format used to read and write the contents of a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="b75ba-112">Cargar un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="b75ba-112">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)  
 <span data-ttu-id="b75ba-113">Describe las distintas opciones que hay que tener en cuenta al cargar el contenido de un <xref:System.Data.DataSet> desde un documento XML.</span><span class="sxs-lookup"><span data-stu-id="b75ba-113">Discusses different options to consider when loading the contents of a <xref:System.Data.DataSet> from an XML document.</span></span>  
  
 [<span data-ttu-id="b75ba-114">Escribir el contenido de un conjunto de datos como datos XML</span><span class="sxs-lookup"><span data-stu-id="b75ba-114">Writing DataSet Contents as XML Data</span></span>](writing-dataset-contents-as-xml-data.md)  
 <span data-ttu-id="b75ba-115">Describe cómo generar el contenido de un <xref:System.Data.DataSet> como datos XML y las distintas opciones de formato XML que se pueden utilizar.</span><span class="sxs-lookup"><span data-stu-id="b75ba-115">Discusses how to generate the contents of a <xref:System.Data.DataSet> as XML data, and the different XML format options you can use.</span></span>  
  
 [<span data-ttu-id="b75ba-116">Cargar información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="b75ba-116">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)  
 <span data-ttu-id="b75ba-117">Describe los métodos <xref:System.Data.DataSet> utilizados para cargar el esquema de un <xref:System.Data.DataSet> desde XML.</span><span class="sxs-lookup"><span data-stu-id="b75ba-117">Discusses the <xref:System.Data.DataSet> methods used to load the schema of a <xref:System.Data.DataSet> from XML.</span></span>  
  
 [<span data-ttu-id="b75ba-118">Escribir información del esquema de un conjunto de datos como XSD</span><span class="sxs-lookup"><span data-stu-id="b75ba-118">Writing DataSet Schema Information as XSD</span></span>](writing-dataset-schema-information-as-xsd.md)  
 <span data-ttu-id="b75ba-119">Describe los usos de un esquema XML y cómo generar uno a partir de un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="b75ba-119">Discusses the uses for an XML Schema and how to generate one from a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="b75ba-120">Sincronización de DataSet y XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="b75ba-120">DataSet and XmlDataDocument Synchronization</span></span>](dataset-and-xmldatadocument-synchronization.md)  
 <span data-ttu-id="b75ba-121">Describe la posibilidad existente en .NET Framework de tener acceso sincrónicamente a las vistas relacional y jerárquica de un único conjunto de datos, a la vez que muestra cómo crear una relación sincrónica entre un <xref:System.Data.DataSet> y un <xref:System.Xml.XmlDataDocument>.</span><span class="sxs-lookup"><span data-stu-id="b75ba-121">Discusses the capability available in the .NET Framework of synchronous access to both relational and hierarchical views of a single set of data, and shows how to create a synchronous relationship between a <xref:System.Data.DataSet> and an <xref:System.Xml.XmlDataDocument>.</span></span>  
  
 [<span data-ttu-id="b75ba-122">Anidar objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="b75ba-122">Nesting DataRelations</span></span>](nesting-datarelations.md)  
 <span data-ttu-id="b75ba-123">Explica la importancia de los objetos <xref:System.Data.DataRelation> anidados al representar el contenido de un <xref:System.Data.DataSet> como datos XML y describe cómo crearlos.</span><span class="sxs-lookup"><span data-stu-id="b75ba-123">Discusses the importance of nested <xref:System.Data.DataRelation> objects when representing the contents of a <xref:System.Data.DataSet> as XML data, and describes how to create them.</span></span>  
  
 [<span data-ttu-id="b75ba-124">Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="b75ba-124">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="b75ba-125">Describe la estructura relacional, o esquema, de un <xref:System.Data.DataSet> creado a partir de un esquema XML.</span><span class="sxs-lookup"><span data-stu-id="b75ba-125">Describes the relational structure, or schema, of a <xref:System.Data.DataSet> that is created from XML Schema.</span></span>  
  
 [<span data-ttu-id="b75ba-126">Inferir una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="b75ba-126">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)  
 <span data-ttu-id="b75ba-127">Describe la estructura relacional, o esquema, resultante de un <xref:System.Data.DataSet> que se crea por inferencia a partir de elementos XML.</span><span class="sxs-lookup"><span data-stu-id="b75ba-127">Describes the resulting relational structure, or schema, of a <xref:System.Data.DataSet> that is created when inferred from XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b75ba-128">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="b75ba-128">Related Sections</span></span>  

 [<span data-ttu-id="b75ba-129">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b75ba-129">ADO.NET Overview</span></span>](../ado-net-overview.md)  
 <span data-ttu-id="b75ba-130">Describe la arquitectura y los componentes de ADO.NET, así como su uso para tener acceso a orígenes de datos existentes y administrar los datos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b75ba-130">Describes the ADO.NET architecture and components, and how to use them to access existing data sources as well as to manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b75ba-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b75ba-131">See also</span></span>

- [<span data-ttu-id="b75ba-132">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="b75ba-132">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="b75ba-133">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b75ba-133">ADO.NET Overview</span></span>](../ado-net-overview.md)
