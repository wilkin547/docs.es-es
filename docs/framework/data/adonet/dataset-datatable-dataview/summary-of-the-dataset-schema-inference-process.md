---
title: Resumen del proceso de inferencia del esquema de DataSet
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: 1eb12fd9c983bc0013b5dc528e0b3389250bdbe2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527658"
---
# <a name="summary-of-the-dataset-schema-inference-process"></a><span data-ttu-id="f2ef7-102">Resumen del proceso de inferencia del esquema de DataSet</span><span class="sxs-lookup"><span data-stu-id="f2ef7-102">Summary of the DataSet Schema Inference Process</span></span>
<span data-ttu-id="f2ef7-103">El proceso de inferencia determina en primer lugar, a partir del documento XML, qué elementos se inferirán como tablas.</span><span class="sxs-lookup"><span data-stu-id="f2ef7-103">The inference process first determines, from the XML document, which elements will be inferred as tables.</span></span> <span data-ttu-id="f2ef7-104">A partir del XML restante, el proceso de inferencia determina las columnas para dichas tablas.</span><span class="sxs-lookup"><span data-stu-id="f2ef7-104">From the remaining XML, the inference process determines the columns for those tables.</span></span> <span data-ttu-id="f2ef7-105">En el caso de las tablas anidadas, el proceso de inferencia genera objetos <xref:System.Data.DataRelation> y <xref:System.Data.ForeignKeyConstraint> anidados.</span><span class="sxs-lookup"><span data-stu-id="f2ef7-105">For nested tables, the inference process generates nested <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects.</span></span>  
  
 <span data-ttu-id="f2ef7-106">A continuación se resumen brevemente las reglas de inferencia:</span><span class="sxs-lookup"><span data-stu-id="f2ef7-106">Following is a brief summary of inference rules:</span></span>  
  
-   <span data-ttu-id="f2ef7-107">Los elementos que tienen atributos se deducen como tablas.</span><span class="sxs-lookup"><span data-stu-id="f2ef7-107">Elements that have attributes are inferred as tables.</span></span>  
  
-   <span data-ttu-id="f2ef7-108">Los elementos que tienen elementos secundarios se deducen como tablas.</span><span class="sxs-lookup"><span data-stu-id="f2ef7-108">Elements that have child elements are inferred as tables.</span></span>  
  
-   <span data-ttu-id="f2ef7-109">Los elementos que se repiten se deducen como una única tabla.</span><span class="sxs-lookup"><span data-stu-id="f2ef7-109">Elements that repeat are inferred as a single table.</span></span>  
  
-   <span data-ttu-id="f2ef7-110">Si el elemento de documento, o raíz, no tiene atributos y no se deduciría ningún elemento secundario como una columna, se deduce como un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="f2ef7-110">If the document, or root, element has no attributes, and no child elements that would be inferred as columns, it is inferred as a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="f2ef7-111">De lo contrario, el elemento de documento se deducirá como una tabla.</span><span class="sxs-lookup"><span data-stu-id="f2ef7-111">Otherwise, the document element is inferred as a table.</span></span>  
  
-   <span data-ttu-id="f2ef7-112">Los atributos se deducen como columnas.</span><span class="sxs-lookup"><span data-stu-id="f2ef7-112">Attributes are inferred as columns.</span></span>  
  
-   <span data-ttu-id="f2ef7-113">Los elementos que no tienen atributos o elementos secundarios, y que no se repiten, se deducen como columnas.</span><span class="sxs-lookup"><span data-stu-id="f2ef7-113">Elements that have no attributes or child elements, and that do not repeat, are inferred as columns.</span></span>  
  
-   <span data-ttu-id="f2ef7-114">Para los elementos que se deducen como tablas anidadas dentro de otros elementos que también se deducen como tablas, anidada **DataRelation** se crea entre las dos tablas.</span><span class="sxs-lookup"><span data-stu-id="f2ef7-114">For elements that are inferred as nested tables within other elements that are also inferred as tables, a nested **DataRelation** is created between the two tables.</span></span> <span data-ttu-id="f2ef7-115">Una nueva columna de clave principal denominada **TableName_Id** se agrega a ambas tablas y usa el **DataRelation**.</span><span class="sxs-lookup"><span data-stu-id="f2ef7-115">A new, primary key column named **TableName_Id** is added to both tables and used by the **DataRelation**.</span></span> <span data-ttu-id="f2ef7-116">Un **ForeignKeyConstraint** se crea entre las dos tablas mediante el **TableName_Id** columna.</span><span class="sxs-lookup"><span data-stu-id="f2ef7-116">A **ForeignKeyConstraint** is created between the two tables using the **TableName_Id** column.</span></span>  
  
-   <span data-ttu-id="f2ef7-117">Para los elementos que se deducen como tablas y que contienen texto pero no tener elementos secundarios, una nueva columna denominada **TableName_Text** se crea para el texto de cada uno de los elementos.</span><span class="sxs-lookup"><span data-stu-id="f2ef7-117">For elements that are inferred as tables and that contain text but have no child elements, a new column named **TableName_Text** is created for the text of each of the elements.</span></span> <span data-ttu-id="f2ef7-118">Si un elemento se deduce como una tabla y tiene texto, pero también tiene elementos secundarios, se pasa por alto el texto.</span><span class="sxs-lookup"><span data-stu-id="f2ef7-118">If an element is inferred as a table and has text, but also has child elements, the text is ignored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ef7-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2ef7-119">See also</span></span>
- [<span data-ttu-id="f2ef7-120">Inferencia de una estructura relacional de un conjunto de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="f2ef7-120">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="f2ef7-121">Carga de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="f2ef7-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="f2ef7-122">Carga de información del esquema de un conjunto de datos desde XML</span><span class="sxs-lookup"><span data-stu-id="f2ef7-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="f2ef7-123">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="f2ef7-123">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="f2ef7-124">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="f2ef7-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="f2ef7-125">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="f2ef7-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
