---
description: Más información acerca de cómo deducir la estructura relacional de DataSet desde XML
title: Inferir una estructura relacional de un conjunto de datos a partir de XML
ms.date: 03/30/2017
ms.assetid: cd2f41c6-6785-420e-aa43-3ceb0bdccdce
ms.openlocfilehash: d89b6a42e7e1bc3d7514f180329e9c1d877a67ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652229"
---
# <a name="inferring-dataset-relational-structure-from-xml"></a><span data-ttu-id="441d1-103">Inferir una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="441d1-103">Inferring DataSet Relational Structure from XML</span></span>

<span data-ttu-id="441d1-104">La estructura relacional, o esquema, de un <xref:System.Data.DataSet> está compuesta por tablas, columnas, restricciones y relaciones.</span><span class="sxs-lookup"><span data-stu-id="441d1-104">The relational structure, or schema, of a <xref:System.Data.DataSet> is made up of tables, columns, constraints, and relations.</span></span> <span data-ttu-id="441d1-105">Al cargar un <xref:System.Data.DataSet> desde XML es posible predefinir el esquema, o bien crearlo, de forma explícita o por inferencia, a partir del código XML que se carga.</span><span class="sxs-lookup"><span data-stu-id="441d1-105">When loading a <xref:System.Data.DataSet> from XML, the schema can be predefined, or it can be created, either explicitly or through inference, from the XML being loaded.</span></span> <span data-ttu-id="441d1-106">Para obtener más información sobre cómo cargar el esquema y el contenido de un <xref:System.Data.DataSet> desde XML, vea [cargar un conjunto de datos desde XML](loading-a-dataset-from-xml.md) y [cargar información de esquema de conjunto de datos desde XML](loading-dataset-schema-information-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="441d1-106">For more information about loading the schema and contents of a <xref:System.Data.DataSet> from XML, see [Loading a DataSet from XML](loading-a-dataset-from-xml.md) and [Loading DataSet Schema Information from XML](loading-dataset-schema-information-from-xml.md).</span></span>  
  
 <span data-ttu-id="441d1-107">Si el esquema de un <xref:System.Data.DataSet> se crea a partir de XML, el método preferido consiste en especificar explícitamente el esquema mediante el lenguaje de definición de esquemas XML (XSD) (tal y como se describe en [derivar una estructura relacional de conjunto de objetos a partir de un esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)) o en el XML-Data reducido (XDR).</span><span class="sxs-lookup"><span data-stu-id="441d1-107">If the schema of a <xref:System.Data.DataSet> is being created from XML, the preferred method is to explicitly specify the schema using either the XML Schema definition language (XSD) (as described in [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)) or the XML-Data Reduced (XDR).</span></span> <span data-ttu-id="441d1-108">Si no hay ningún esquema XML o XDR disponible en XML, el esquema del <xref:System.Data.DataSet> se puede deducir de la estructura de los elementos y atributos XML.</span><span class="sxs-lookup"><span data-stu-id="441d1-108">If no XML Schema or XDR schema is available in the XML, the schema of the <xref:System.Data.DataSet> can be inferred from the structure of the XML elements and attributes.</span></span>  
  
 <span data-ttu-id="441d1-109">En esta sección se describen las reglas para deducir el esquema de un <xref:System.Data.DataSet>; para ello se muestran los elementos y atributos XML y su estructura, así como el esquema deducido del <xref:System.Data.DataSet> resultante.</span><span class="sxs-lookup"><span data-stu-id="441d1-109">This section describes the rules for <xref:System.Data.DataSet> schema inference by showing XML elements and attributes and their structure, and the resulting inferred <xref:System.Data.DataSet> schema.</span></span>  
  
 <span data-ttu-id="441d1-110">No todos los atributos presentes en un documento XML deben incluirse en el proceso de deducción.</span><span class="sxs-lookup"><span data-stu-id="441d1-110">Not all attributes present in an XML document should be included in the inference process.</span></span> <span data-ttu-id="441d1-111">Los atributos calificados por el espacio de nombres pueden incluir metadatos importantes para el documento XML, pero no para el esquema del <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="441d1-111">Namespace-qualified attributes can include metadata that is important for the XML document but not for the <xref:System.Data.DataSet> schema.</span></span> <span data-ttu-id="441d1-112">Mediante <xref:System.Data.DataSet.InferXmlSchema%2A> es posible especificar determinados espacios de nombres que desea pasar por alto durante el proceso de inferencia.</span><span class="sxs-lookup"><span data-stu-id="441d1-112">Using <xref:System.Data.DataSet.InferXmlSchema%2A>, you can specify namespaces to be ignored during the inference process.</span></span> <span data-ttu-id="441d1-113">Para obtener más información, vea [cargar información de esquema de conjunto de datos desde XML](loading-dataset-schema-information-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="441d1-113">For more information, see [Loading DataSet Schema Information from XML](loading-dataset-schema-information-from-xml.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="441d1-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="441d1-114">In This Section</span></span>  

 [<span data-ttu-id="441d1-115">Resumen del proceso de inferencia del esquema de DataSet</span><span class="sxs-lookup"><span data-stu-id="441d1-115">Summary of the DataSet Schema Inference Process</span></span>](summary-of-the-dataset-schema-inference-process.md)  
 <span data-ttu-id="441d1-116">Proporciona un resumen general de las reglas para deducir el esquema de un <xref:System.Data.DataSet> a partir de XML.</span><span class="sxs-lookup"><span data-stu-id="441d1-116">Provides a high-level summary of the rules for inferring the schema of a <xref:System.Data.DataSet> from XML.</span></span>  
  
 [<span data-ttu-id="441d1-117">Inferir tablas</span><span class="sxs-lookup"><span data-stu-id="441d1-117">Inferring Tables</span></span>](inferring-tables.md)  
 <span data-ttu-id="441d1-118">Describe los elementos XML que se deducen como tablas en un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="441d1-118">Describes the XML elements that are inferred as tables in a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="441d1-119">Inferir columnas</span><span class="sxs-lookup"><span data-stu-id="441d1-119">Inferring Columns</span></span>](inferring-columns.md)  
 <span data-ttu-id="441d1-120">Describe los elementos y atributos XML que se deducen como columnas de tabla.</span><span class="sxs-lookup"><span data-stu-id="441d1-120">Describes the XML elements and attributes that are inferred as table columns.</span></span>  
  
 [<span data-ttu-id="441d1-121">Inferir relaciones</span><span class="sxs-lookup"><span data-stu-id="441d1-121">Inferring Relationships</span></span>](inferring-relationships.md)  
 <span data-ttu-id="441d1-122">Describe los objetos <xref:System.Data.DataRelation> y <xref:System.Data.ForeignKeyConstraint> creados para tablas deducidas y anidadas.</span><span class="sxs-lookup"><span data-stu-id="441d1-122">Describes the <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects created for nested, inferred tables.</span></span>  
  
 [<span data-ttu-id="441d1-123">Inferir texto de elemento</span><span class="sxs-lookup"><span data-stu-id="441d1-123">Inferring Element Text</span></span>](inferring-element-text.md)  
 <span data-ttu-id="441d1-124">Describe las columnas que se crean para texto en los elementos XML y explica cuándo se pasa por alto el texto de los elementos XML.</span><span class="sxs-lookup"><span data-stu-id="441d1-124">Describes the columns that are created for text in XML elements, and explains when text in XML elements is ignored.</span></span>  
  
 [<span data-ttu-id="441d1-125">Limitaciones de inferencia</span><span class="sxs-lookup"><span data-stu-id="441d1-125">Inference Limitations</span></span>](inference-limitations.md)  
 <span data-ttu-id="441d1-126">Describe las limitaciones de la inferencia del esquema.</span><span class="sxs-lookup"><span data-stu-id="441d1-126">Discusses the limitations of schema inference.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="441d1-127">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="441d1-127">Related Sections</span></span>  

 [<span data-ttu-id="441d1-128">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="441d1-128">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="441d1-129">Describe cómo interactúa el objeto <xref:System.Data.DataSet> con los datos XML.</span><span class="sxs-lookup"><span data-stu-id="441d1-129">Describes how the <xref:System.Data.DataSet> object interacts with XML data.</span></span>  
  
 [<span data-ttu-id="441d1-130">Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="441d1-130">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="441d1-131">Describe la estructura relacional o un esquema de un <xref:System.Data.DataSet> que se crea a partir del esquema del lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="441d1-131">Describes the relational structure, or schema, of a <xref:System.Data.DataSet> that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="441d1-132">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="441d1-132">ADO.NET Overview</span></span>](../ado-net-overview.md)  
 <span data-ttu-id="441d1-133">Describe la arquitectura y los componentes de ADO.NET, así como su uso para obtener acceso a orígenes de datos existentes y para administrar los datos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="441d1-133">Describes the ADO.NET architecture and components and how to use them to access existing data sources and manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="441d1-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="441d1-134">See also</span></span>

- [<span data-ttu-id="441d1-135">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="441d1-135">ADO.NET Overview</span></span>](../ado-net-overview.md)
