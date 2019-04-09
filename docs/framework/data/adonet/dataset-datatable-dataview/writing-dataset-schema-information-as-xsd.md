---
title: Escribir información del esquema de un conjunto de datos como XSD
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: 8403f9d9be88f34e473fd3512f5499193245d227
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099448"
---
# <a name="writing-dataset-schema-information-as-xsd"></a><span data-ttu-id="f2e83-102">Escribir información del esquema de un conjunto de datos como XSD</span><span class="sxs-lookup"><span data-stu-id="f2e83-102">Writing DataSet Schema Information as XSD</span></span>
<span data-ttu-id="f2e83-103">Puede escribir el esquema de un <xref:System.Data.DataSet> como un esquema de lenguaje de definición de esquemas XML (XSD), de forma que pueda transportarlo, con o sin datos relacionados, a un documento XML.</span><span class="sxs-lookup"><span data-stu-id="f2e83-103">You can write the schema of a <xref:System.Data.DataSet> as XML Schema definition language (XSD) schema, so that you can transport it, with or without related data, in an XML document.</span></span> <span data-ttu-id="f2e83-104">Esquema XML se puede escribir en un archivo, una secuencia, un <xref:System.Xml.XmlWriter>, o una cadena; es útil para generar un fuertemente tipado **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="f2e83-104">XML Schema can be written to a file, a stream, an <xref:System.Xml.XmlWriter>, or a string; it is useful for generating a strongly typed **DataSet**.</span></span> <span data-ttu-id="f2e83-105">Para obtener más información acerca de establecimiento inflexible de tipos **DataSet** objetos, vea [DataSets con tipo](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="f2e83-105">For more information about strongly typed **DataSet** objects, see [Typed DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>  
  
 <span data-ttu-id="f2e83-106">Puede especificar cómo se representa una columna de una tabla de esquema XML utilizando el **ColumnMapping** propiedad de la <xref:System.Data.DataColumn> objeto.</span><span class="sxs-lookup"><span data-stu-id="f2e83-106">You can specify how a column of a table is represented in XML Schema using the **ColumnMapping** property of the <xref:System.Data.DataColumn> object.</span></span> <span data-ttu-id="f2e83-107">Para obtener más información, vea "Asignar columnas a elementos, atributos y texto XML" en [escribir contenido de DataSet como datos XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="f2e83-107">For more information, see "Mapping Columns to XML Elements, Attributes, and Text" in [Writing DataSet Contents as XML Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span></span>  
  
 <span data-ttu-id="f2e83-108">Para escribir el esquema de un **conjunto de datos** como un esquema XML a un archivo, secuencia, o **XmlWriter**, utilice el **WriteXmlSchema** método de la **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="f2e83-108">To write the schema of a **DataSet** as XML Schema, to a file, stream, or **XmlWriter**, use the **WriteXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="f2e83-109">**WriteXmlSchema** toma un parámetro que especifica el destino del esquema XML resultante.</span><span class="sxs-lookup"><span data-stu-id="f2e83-109">**WriteXmlSchema** takes one parameter that specifies the destination of the resulting XML Schema.</span></span> <span data-ttu-id="f2e83-110">Los ejemplos de código siguientes muestran cómo escribir el esquema XML de un **DataSet** a un archivo pasando una cadena que contiene un nombre de archivo y un <xref:System.IO.StreamWriter> objeto.</span><span class="sxs-lookup"><span data-stu-id="f2e83-110">The following code examples demonstrate how to write the XML Schema of a **DataSet** to a file by passing a string containing a file name and a <xref:System.IO.StreamWriter> object.</span></span>  
  
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
  
 <span data-ttu-id="f2e83-111">Para obtener el esquema de un **DataSet** y escribirlo como una cadena de esquema XML, utilice el **GetXmlSchema** método, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f2e83-111">To obtain the schema of a **DataSet** and write it as an XML Schema string, use the **GetXmlSchema** method, as shown in the following example.</span></span>  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2e83-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2e83-112">See also</span></span>

- [<span data-ttu-id="f2e83-113">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="f2e83-113">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="f2e83-114">Escribir el contenido de un conjunto de datos como datos XML</span><span class="sxs-lookup"><span data-stu-id="f2e83-114">Writing DataSet Contents as XML Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)
- [<span data-ttu-id="f2e83-115">Objetos DataSet con tipo</span><span class="sxs-lookup"><span data-stu-id="f2e83-115">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)
- [<span data-ttu-id="f2e83-116">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="f2e83-116">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="f2e83-117">Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="f2e83-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
