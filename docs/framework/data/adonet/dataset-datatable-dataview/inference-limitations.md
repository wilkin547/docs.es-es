---
title: Limitaciones de inferencia
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: d113df98cdd339300b3e75ceda49a56d4f346d3c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43417435"
---
# <a name="inference-limitations"></a><span data-ttu-id="4ba2b-102">Limitaciones de inferencia</span><span class="sxs-lookup"><span data-stu-id="4ba2b-102">Inference Limitations</span></span>
<span data-ttu-id="4ba2b-103">El proceso de inferencia de un esquema de <xref:System.Data.DataSet> a partir de XML puede dar como resultado esquemas diferentes, dependiendo de los elementos XML contenidos en cada documento.</span><span class="sxs-lookup"><span data-stu-id="4ba2b-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="4ba2b-104">Por ejemplo, considere los siguientes documentos XML.</span><span class="sxs-lookup"><span data-stu-id="4ba2b-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="4ba2b-105">Document1:</span><span class="sxs-lookup"><span data-stu-id="4ba2b-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="4ba2b-106">Document2:</span><span class="sxs-lookup"><span data-stu-id="4ba2b-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="4ba2b-107">"Document1", el proceso de inferencia produce un **DataSet** denominado "DocumentElement" y una tabla denominada "Element1", ya que "Element1" es un elemento repetitivo.</span><span class="sxs-lookup"><span data-stu-id="4ba2b-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="4ba2b-108">**Conjunto de datos:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="4ba2b-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="4ba2b-109">**Tabla:** Element1</span><span class="sxs-lookup"><span data-stu-id="4ba2b-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="4ba2b-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="4ba2b-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="4ba2b-111">Text1</span><span class="sxs-lookup"><span data-stu-id="4ba2b-111">Text1</span></span>|  
|<span data-ttu-id="4ba2b-112">Text2</span><span class="sxs-lookup"><span data-stu-id="4ba2b-112">Text2</span></span>|  
  
 <span data-ttu-id="4ba2b-113">Sin embargo, para "Document2", el proceso de inferencia produce un **DataSet** denominado "NewDataSet" y una tabla denominada "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="4ba2b-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="4ba2b-114">"Element1" se deduce como una columna porque no tiene atributos ni elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="4ba2b-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="4ba2b-115">**Conjunto de datos:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="4ba2b-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="4ba2b-116">**Tabla:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="4ba2b-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="4ba2b-117">Element1</span><span class="sxs-lookup"><span data-stu-id="4ba2b-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="4ba2b-118">Text1</span><span class="sxs-lookup"><span data-stu-id="4ba2b-118">Text1</span></span>|  
  
 <span data-ttu-id="4ba2b-119">Podría parecer que estos dos documentos XML producirían el mismo esquema, pero el proceso de inferencia genera resultados muy diferentes basándose en los elementos contenidos en cada documento.</span><span class="sxs-lookup"><span data-stu-id="4ba2b-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="4ba2b-120">Para evitar las discrepancias que pueden producirse al generar el esquema de un documento XML, se recomienda especificar explícitamente un esquema mediante el lenguaje de definición de esquemas XML (XSD) o datos XML reducidos (XDR) al cargar un **DataSet** desde XML.</span><span class="sxs-lookup"><span data-stu-id="4ba2b-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="4ba2b-121">Para obtener más información acerca de cómo especificar explícitamente un **DataSet** esquema con el esquema XML, vea [derivar estructura relacional de DataSet de esquemas XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="4ba2b-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ba2b-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ba2b-122">See Also</span></span>  
 [<span data-ttu-id="4ba2b-123">Inferencia de una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="4ba2b-123">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="4ba2b-124">Carga de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="4ba2b-124">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="4ba2b-125">Carga de información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="4ba2b-125">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="4ba2b-126">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="4ba2b-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="4ba2b-127">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="4ba2b-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="4ba2b-128">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="4ba2b-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
