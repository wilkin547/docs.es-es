---
title: Limitaciones de inferencia
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: 9d8191be137661200e1a6b84d68328c1202880ca
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172780"
---
# <a name="inference-limitations"></a><span data-ttu-id="594d7-102">Limitaciones de inferencia</span><span class="sxs-lookup"><span data-stu-id="594d7-102">Inference Limitations</span></span>

<span data-ttu-id="594d7-103">El proceso de inferencia de un esquema de <xref:System.Data.DataSet> a partir de XML puede dar como resultado esquemas diferentes, dependiendo de los elementos XML contenidos en cada documento.</span><span class="sxs-lookup"><span data-stu-id="594d7-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="594d7-104">Por ejemplo, considere los siguientes documentos XML.</span><span class="sxs-lookup"><span data-stu-id="594d7-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="594d7-105">Document1:</span><span class="sxs-lookup"><span data-stu-id="594d7-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="594d7-106">Document2:</span><span class="sxs-lookup"><span data-stu-id="594d7-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="594d7-107">Para "Documento1", el proceso de inferencia produce un **DataSet** denominado "DocumentElement" y una tabla denominada "Element1", ya que "Element1" es un elemento que se repite.</span><span class="sxs-lookup"><span data-stu-id="594d7-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="594d7-108">**Conjunto** de los: DocumentElement</span><span class="sxs-lookup"><span data-stu-id="594d7-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="594d7-109">**Tabla:** Elemento1</span><span class="sxs-lookup"><span data-stu-id="594d7-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="594d7-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="594d7-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="594d7-111">Text1</span><span class="sxs-lookup"><span data-stu-id="594d7-111">Text1</span></span>|  
|<span data-ttu-id="594d7-112">Text2</span><span class="sxs-lookup"><span data-stu-id="594d7-112">Text2</span></span>|  
  
 <span data-ttu-id="594d7-113">Sin embargo, para "Document2", el proceso de inferencia produce un **DataSet** denominado "NewDataSet" y una tabla denominada "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="594d7-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="594d7-114">"Element1" se deduce como una columna porque no tiene atributos ni elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="594d7-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="594d7-115">**Conjunto** de los: NewDataSet</span><span class="sxs-lookup"><span data-stu-id="594d7-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="594d7-116">**Tabla:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="594d7-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="594d7-117">Element1</span><span class="sxs-lookup"><span data-stu-id="594d7-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="594d7-118">Text1</span><span class="sxs-lookup"><span data-stu-id="594d7-118">Text1</span></span>|  
  
 <span data-ttu-id="594d7-119">Podría parecer que estos dos documentos XML producirían el mismo esquema, pero el proceso de inferencia genera resultados muy diferentes basándose en los elementos contenidos en cada documento.</span><span class="sxs-lookup"><span data-stu-id="594d7-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="594d7-120">Para evitar las discrepancias que pueden producirse al generar el esquema a partir de un documento XML, se recomienda especificar explícitamente un esquema mediante el lenguaje de definición de esquemas XML (XSD) o el reducido de datos XML (XDR) al cargar un **DataSet** desde XML.</span><span class="sxs-lookup"><span data-stu-id="594d7-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="594d7-121">Para obtener más información sobre cómo especificar explícitamente un esquema de **conjunto** de datos con un esquema XML, vea [derivar una estructura relacional de conjunto de datos a partir de un esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="594d7-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="594d7-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="594d7-122">See also</span></span>

- [<span data-ttu-id="594d7-123">Inferir una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="594d7-123">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="594d7-124">Cargar un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="594d7-124">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="594d7-125">Cargar información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="594d7-125">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="594d7-126">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="594d7-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="594d7-127">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="594d7-127">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="594d7-128">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="594d7-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
