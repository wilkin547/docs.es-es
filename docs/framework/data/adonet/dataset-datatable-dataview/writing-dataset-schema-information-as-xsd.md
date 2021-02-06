---
description: Más información acerca de cómo escribir información de esquema de conjunto de datos como XSD
title: Escribir información del esquema de un conjunto de datos como XSD
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: e05188c74ca21e73ee5151da817e143102640a13
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651358"
---
# <a name="writing-dataset-schema-information-as-xsd"></a><span data-ttu-id="50d9f-103">Escribir información del esquema de un conjunto de datos como XSD</span><span class="sxs-lookup"><span data-stu-id="50d9f-103">Writing DataSet Schema Information as XSD</span></span>

<span data-ttu-id="50d9f-104">Puede escribir el esquema de un <xref:System.Data.DataSet> como un esquema de lenguaje de definición de esquemas XML (XSD), de forma que pueda transportarlo, con o sin datos relacionados, a un documento XML.</span><span class="sxs-lookup"><span data-stu-id="50d9f-104">You can write the schema of a <xref:System.Data.DataSet> as XML Schema definition language (XSD) schema, so that you can transport it, with or without related data, in an XML document.</span></span> <span data-ttu-id="50d9f-105">El esquema XML se puede escribir en un archivo, una secuencia, un <xref:System.Xml.XmlWriter> o una cadena; resulta útil para generar un **conjunto** de un DataSet fuertemente tipado.</span><span class="sxs-lookup"><span data-stu-id="50d9f-105">XML Schema can be written to a file, a stream, an <xref:System.Xml.XmlWriter>, or a string; it is useful for generating a strongly typed **DataSet**.</span></span> <span data-ttu-id="50d9f-106">Para obtener más información sobre los objetos de **conjunto** de datos fuertemente tipados, vea [conjuntos de datos con tipo](typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="50d9f-106">For more information about strongly typed **DataSet** objects, see [Typed DataSets](typed-datasets.md).</span></span>  
  
 <span data-ttu-id="50d9f-107">Puede especificar cómo se representa una columna de una tabla en el esquema XML mediante la propiedad **ColumnMapping** del <xref:System.Data.DataColumn> objeto.</span><span class="sxs-lookup"><span data-stu-id="50d9f-107">You can specify how a column of a table is represented in XML Schema using the **ColumnMapping** property of the <xref:System.Data.DataColumn> object.</span></span> <span data-ttu-id="50d9f-108">Para obtener más información, vea "asignar columnas a elementos, atributos y texto XML" al [escribir el contenido del conjunto de datos como datos XML](writing-dataset-contents-as-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="50d9f-108">For more information, see "Mapping Columns to XML Elements, Attributes, and Text" in [Writing DataSet Contents as XML Data](writing-dataset-contents-as-xml-data.md).</span></span>  
  
 <span data-ttu-id="50d9f-109">Para escribir el esquema de un **DataSet** como esquema XML, en un archivo, una secuencia o **XmlWriter**, utilice el método **WriteXmlSchema** del **conjunto** de archivos.</span><span class="sxs-lookup"><span data-stu-id="50d9f-109">To write the schema of a **DataSet** as XML Schema, to a file, stream, or **XmlWriter**, use the **WriteXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="50d9f-110">**WriteXmlSchema** toma un parámetro que especifica el destino del esquema XML resultante.</span><span class="sxs-lookup"><span data-stu-id="50d9f-110">**WriteXmlSchema** takes one parameter that specifies the destination of the resulting XML Schema.</span></span> <span data-ttu-id="50d9f-111">En los siguientes ejemplos de código se muestra cómo escribir el esquema XML de un **conjunto** de objetos en un archivo pasando una cadena que contiene un nombre de archivo y un <xref:System.IO.StreamWriter> objeto.</span><span class="sxs-lookup"><span data-stu-id="50d9f-111">The following code examples demonstrate how to write the XML Schema of a **DataSet** to a file by passing a string containing a file name and a <xref:System.IO.StreamWriter> object.</span></span>  
  
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
  
 <span data-ttu-id="50d9f-112">Para obtener el esquema de un **DataSet** y escribirlo como una cadena de esquema XML, use el método **GetXmlSchema** , como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="50d9f-112">To obtain the schema of a **DataSet** and write it as an XML Schema string, use the **GetXmlSchema** method, as shown in the following example.</span></span>  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a><span data-ttu-id="50d9f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="50d9f-113">See also</span></span>

- [<span data-ttu-id="50d9f-114">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="50d9f-114">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="50d9f-115">Escribir el contenido de un conjunto de datos como datos XML</span><span class="sxs-lookup"><span data-stu-id="50d9f-115">Writing DataSet Contents as XML Data</span></span>](writing-dataset-contents-as-xml-data.md)
- [<span data-ttu-id="50d9f-116">Objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="50d9f-116">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="50d9f-117">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="50d9f-117">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="50d9f-118">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="50d9f-118">ADO.NET Overview</span></span>](../ado-net-overview.md)
