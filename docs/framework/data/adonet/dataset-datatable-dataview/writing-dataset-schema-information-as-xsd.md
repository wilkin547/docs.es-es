---
title: "Escribir información del esquema de un conjunto de datos como XSD"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 95f8a5d4d03c349467cbd13976ca9023470735aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="writing-dataset-schema-information-as-xsd"></a><span data-ttu-id="21828-102">Escribir información del esquema de un conjunto de datos como XSD</span><span class="sxs-lookup"><span data-stu-id="21828-102">Writing DataSet Schema Information as XSD</span></span>
<span data-ttu-id="21828-103">Puede escribir el esquema de un <xref:System.Data.DataSet> como un esquema de lenguaje de definición de esquemas XML (XSD), de forma que pueda transportarlo, con o sin datos relacionados, a un documento XML.</span><span class="sxs-lookup"><span data-stu-id="21828-103">You can write the schema of a <xref:System.Data.DataSet> as XML Schema definition language (XSD) schema, so that you can transport it, with or without related data, in an XML document.</span></span> <span data-ttu-id="21828-104">Esquema XML se puede escribir en un archivo, una secuencia, un <xref:System.Xml.XmlWriter>, o una cadena; resulta útil para generar un fuertemente tipado **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="21828-104">XML Schema can be written to a file, a stream, an <xref:System.Xml.XmlWriter>, or a string; it is useful for generating a strongly typed **DataSet**.</span></span> <span data-ttu-id="21828-105">Para obtener más información acerca de establecimiento inflexible de tipos **conjunto de datos** los objetos, vea [conjuntos de datos con tipo](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="21828-105">For more information about strongly typed **DataSet** objects, see [Typed DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>  
  
 <span data-ttu-id="21828-106">Puede especificar cómo se representa una columna de una tabla en el esquema XML utilizando la **ColumnMapping** propiedad de la <xref:System.Data.DataColumn> objeto.</span><span class="sxs-lookup"><span data-stu-id="21828-106">You can specify how a column of a table is represented in XML Schema using the **ColumnMapping** property of the <xref:System.Data.DataColumn> object.</span></span> <span data-ttu-id="21828-107">Para obtener más información, vea "Asignar columnas a elementos, atributos y texto XML" en [escribir contenido de DataSet como datos XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="21828-107">For more information, see "Mapping Columns to XML Elements, Attributes, and Text" in [Writing DataSet Contents as XML Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span></span>  
  
 <span data-ttu-id="21828-108">Para escribir el esquema de un **conjunto de datos** como un esquema XML a un archivo, secuencia, o **XmlWriter**, use la **WriteXmlSchema** método de la **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="21828-108">To write the schema of a **DataSet** as XML Schema, to a file, stream, or **XmlWriter**, use the **WriteXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="21828-109">**WriteXmlSchema** toma un parámetro que especifica el destino del esquema XML resultante.</span><span class="sxs-lookup"><span data-stu-id="21828-109">**WriteXmlSchema** takes one parameter that specifies the destination of the resulting XML Schema.</span></span> <span data-ttu-id="21828-110">Los ejemplos de código siguientes muestran cómo escribir el esquema XML de un **conjunto de datos** a un archivo si se pasa una cadena que contiene un nombre de archivo y un <xref:System.IO.StreamWriter> objeto.</span><span class="sxs-lookup"><span data-stu-id="21828-110">The following code examples demonstrate how to write the XML Schema of a **DataSet** to a file by passing a string containing a file name and a <xref:System.IO.StreamWriter> object.</span></span>  
  
```vb  
dataSet.WriteXmlSchema("Customers.xsd")  
```  
  
```csharp  
dataSet.WriteXmlSchema("Customers.xsd");  
```  
  
```vb  
Dim writer As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xsd")  
dataSet.WriteXmlSchema(writer)  
writer.Close()  
```  
  
```csharp  
System.IO.StreamWriter writer = new System.IO.StreamWriter("Customers.xsd");  
dataSet.WriteXmlSchema(writer);  
writer.Close();  
```  
  
 <span data-ttu-id="21828-111">Para obtener el esquema de un **conjunto de datos** y escribirlo como una cadena de esquema XML, utilice el **GetXmlSchema** método, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="21828-111">To obtain the schema of a **DataSet** and write it as an XML Schema string, use the **GetXmlSchema** method, as shown in the following example.</span></span>  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a><span data-ttu-id="21828-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="21828-112">See Also</span></span>  
 [<span data-ttu-id="21828-113">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="21828-113">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="21828-114">Escritura de contenido de un conjunto de datos como datos XML</span><span class="sxs-lookup"><span data-stu-id="21828-114">Writing DataSet Contents as XML Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)  
 [<span data-ttu-id="21828-115">Objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="21828-115">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [<span data-ttu-id="21828-116">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="21828-116">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="21828-117">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="21828-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
