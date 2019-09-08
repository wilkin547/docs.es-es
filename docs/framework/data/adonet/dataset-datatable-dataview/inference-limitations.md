---
title: Limitaciones de inferencia
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: 10347abc5b01edb4ec6fbf97221d44f4bfb88f54
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784582"
---
# <a name="inference-limitations"></a><span data-ttu-id="a58e1-102">Limitaciones de inferencia</span><span class="sxs-lookup"><span data-stu-id="a58e1-102">Inference Limitations</span></span>
<span data-ttu-id="a58e1-103">El proceso de inferencia de un esquema de <xref:System.Data.DataSet> a partir de XML puede dar como resultado esquemas diferentes, dependiendo de los elementos XML contenidos en cada documento.</span><span class="sxs-lookup"><span data-stu-id="a58e1-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="a58e1-104">Por ejemplo, considere los siguientes documentos XML.</span><span class="sxs-lookup"><span data-stu-id="a58e1-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="a58e1-105">Document1:</span><span class="sxs-lookup"><span data-stu-id="a58e1-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a58e1-106">Document2:</span><span class="sxs-lookup"><span data-stu-id="a58e1-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a58e1-107">Para "Documento1", el proceso de inferencia produce un **DataSet** denominado "DocumentElement" y una tabla denominada "Element1", ya que "Element1" es un elemento que se repite.</span><span class="sxs-lookup"><span data-stu-id="a58e1-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="a58e1-108">**Authors1** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a58e1-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a58e1-109">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="a58e1-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a58e1-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="a58e1-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="a58e1-111">Text1</span><span class="sxs-lookup"><span data-stu-id="a58e1-111">Text1</span></span>|  
|<span data-ttu-id="a58e1-112">Text2</span><span class="sxs-lookup"><span data-stu-id="a58e1-112">Text2</span></span>|  
  
 <span data-ttu-id="a58e1-113">Sin embargo, para "Document2", el proceso de inferencia produce un **DataSet** denominado "NewDataSet" y una tabla denominada "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="a58e1-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="a58e1-114">"Element1" se deduce como una columna porque no tiene atributos ni elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="a58e1-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="a58e1-115">**Authors1** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="a58e1-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="a58e1-116">**Tabla:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a58e1-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="a58e1-117">Element1</span><span class="sxs-lookup"><span data-stu-id="a58e1-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="a58e1-118">Text1</span><span class="sxs-lookup"><span data-stu-id="a58e1-118">Text1</span></span>|  
  
 <span data-ttu-id="a58e1-119">Podría parecer que estos dos documentos XML producirían el mismo esquema, pero el proceso de inferencia genera resultados muy diferentes basándose en los elementos contenidos en cada documento.</span><span class="sxs-lookup"><span data-stu-id="a58e1-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="a58e1-120">Para evitar las discrepancias que pueden producirse al generar el esquema a partir de un documento XML, se recomienda especificar explícitamente un esquema mediante el lenguaje de definición de esquemas XML (XSD) o el reducido de datos XML (XDR) al cargar un **DataSet** desde XML.</span><span class="sxs-lookup"><span data-stu-id="a58e1-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="a58e1-121">Para obtener más información sobre cómo especificar explícitamente un esquema de **conjunto** de datos con un esquema XML, vea [derivar una estructura relacional de conjunto de datos a partir de un esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="a58e1-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a58e1-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a58e1-122">See also</span></span>

- [<span data-ttu-id="a58e1-123">Inferencia de una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="a58e1-123">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="a58e1-124">Carga de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="a58e1-124">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="a58e1-125">Carga de información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="a58e1-125">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="a58e1-126">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="a58e1-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="a58e1-127">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="a58e1-127">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="a58e1-128">Información general sobre ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a58e1-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
