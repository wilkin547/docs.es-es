---
description: Más información acerca de cómo escribir el contenido de un conjunto de datos como datos XML
title: Escribir el contenido de un conjunto de datos como datos XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
ms.openlocfilehash: 0ad232f744f69f822d09c0af6c4374b6e5f0147d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651371"
---
# <a name="writing-dataset-contents-as-xml-data"></a><span data-ttu-id="5a600-103">Escribir el contenido de un conjunto de datos como datos XML</span><span class="sxs-lookup"><span data-stu-id="5a600-103">Writing DataSet Contents as XML Data</span></span>

<span data-ttu-id="5a600-104">En ADO.NET es posible escribir una representación XML de un <xref:System.Data.DataSet>, con o sin su esquema.</span><span class="sxs-lookup"><span data-stu-id="5a600-104">In ADO.NET you can write an XML representation of a <xref:System.Data.DataSet>, with or without its schema.</span></span> <span data-ttu-id="5a600-105">Si la información de esquema está incluida alineada con el código XML, se escribirá con el lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="5a600-105">If schema information is included inline with the XML, it is written using the XML Schema definition language (XSD).</span></span> <span data-ttu-id="5a600-106">El esquema contiene las definiciones de tabla del <xref:System.Data.DataSet>, así como las definiciones de relaciones y restricciones.</span><span class="sxs-lookup"><span data-stu-id="5a600-106">The schema contains the table definitions of the <xref:System.Data.DataSet> as well as the relation and constraint definitions.</span></span>  
  
 <span data-ttu-id="5a600-107">Cuando un <xref:System.Data.DataSet> se escribe como datos XML, las filas del <xref:System.Data.DataSet> se escriben en sus versiones actuales.</span><span class="sxs-lookup"><span data-stu-id="5a600-107">When a <xref:System.Data.DataSet> is written as XML data, the rows in the <xref:System.Data.DataSet> are written in their current versions.</span></span> <span data-ttu-id="5a600-108">Sin embargo, el <xref:System.Data.DataSet> también se puede escribir como un DiffGram, de forma que se incluyan los valores actuales y originales de las filas.</span><span class="sxs-lookup"><span data-stu-id="5a600-108">However, the <xref:System.Data.DataSet> can also be written as a DiffGram so that both the current and the original values of the rows will be included.</span></span>  
  
 <span data-ttu-id="5a600-109">La representación XML de <xref:System.Data.DataSet> se puede escribir en un archivo, una secuencia, un **XmlWriter** o una cadena.</span><span class="sxs-lookup"><span data-stu-id="5a600-109">The XML representation of the <xref:System.Data.DataSet> can be written to a file, a stream, an **XmlWriter**, or a string.</span></span> <span data-ttu-id="5a600-110">Estas opciones ofrecen una gran flexibilidad en cuanto a la forma de transportar la representación XML del <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="5a600-110">These choices provide great flexibility for how you transport the XML representation of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="5a600-111">Para obtener la representación XML de <xref:System.Data.DataSet> como una cadena, utilice el método **GetXml** tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5a600-111">To obtain the XML representation of the <xref:System.Data.DataSet> as a string, use the **GetXml** method as shown in the following example.</span></span>  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 <span data-ttu-id="5a600-112">**GetXml** devuelve la representación XML de <xref:System.Data.DataSet> sin información del esquema.</span><span class="sxs-lookup"><span data-stu-id="5a600-112">**GetXml** returns the XML representation of the <xref:System.Data.DataSet> without schema information.</span></span> <span data-ttu-id="5a600-113">Para escribir la información de esquema del <xref:System.Data.DataSet> (como esquema XML) en una cadena, utilice **GetXmlSchema**.</span><span class="sxs-lookup"><span data-stu-id="5a600-113">To write the schema information from the <xref:System.Data.DataSet> (as XML Schema) to a string, use **GetXmlSchema**.</span></span>  
  
 <span data-ttu-id="5a600-114">Para escribir un <xref:System.Data.DataSet> en un archivo, una secuencia o **XmlWriter**, utilice el método **WriteXml** .</span><span class="sxs-lookup"><span data-stu-id="5a600-114">To write a <xref:System.Data.DataSet> to a file, stream, or **XmlWriter**, use the **WriteXml** method.</span></span> <span data-ttu-id="5a600-115">El primer parámetro que se pasa a **WriteXml** es el destino de la salida XML.</span><span class="sxs-lookup"><span data-stu-id="5a600-115">The first parameter you pass to **WriteXml** is the destination of the XML output.</span></span> <span data-ttu-id="5a600-116">Por ejemplo, pase una cadena que contenga un nombre de archivo, un objeto **System. IO. TextWriter** , etc.</span><span class="sxs-lookup"><span data-stu-id="5a600-116">For example, pass a string containing a file name, a **System.IO.TextWriter** object, and so on.</span></span> <span data-ttu-id="5a600-117">Puede pasar un segundo parámetro opcional de un **XmlWriteMode** para especificar cómo se escribirá la salida XML.</span><span class="sxs-lookup"><span data-stu-id="5a600-117">You can pass an optional second parameter of an **XmlWriteMode** to specify how the XML output is to be written.</span></span>  
  
 <span data-ttu-id="5a600-118">En la tabla siguiente se muestran las opciones de **XmlWriteMode**.</span><span class="sxs-lookup"><span data-stu-id="5a600-118">The following table shows the options for **XmlWriteMode**.</span></span>  
  
|<span data-ttu-id="5a600-119">Opción XmlWriteMode</span><span class="sxs-lookup"><span data-stu-id="5a600-119">XmlWriteMode option</span></span>|<span data-ttu-id="5a600-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a600-120">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="5a600-121">**IgnoreSchema**</span><span class="sxs-lookup"><span data-stu-id="5a600-121">**IgnoreSchema**</span></span>|<span data-ttu-id="5a600-122">Escribe el contenido actual del <xref:System.Data.DataSet> como datos XML, sin un esquema XML.</span><span class="sxs-lookup"><span data-stu-id="5a600-122">Writes the current contents of the <xref:System.Data.DataSet> as XML data, without an XML Schema.</span></span> <span data-ttu-id="5a600-123">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5a600-123">This is the default.</span></span>|  
|<span data-ttu-id="5a600-124">**WriteSchema**</span><span class="sxs-lookup"><span data-stu-id="5a600-124">**WriteSchema**</span></span>|<span data-ttu-id="5a600-125">Escribe el contenido actual del <xref:System.Data.DataSet> como datos XML con la estructura relacional como un esquema XML alineado.</span><span class="sxs-lookup"><span data-stu-id="5a600-125">Writes the current contents of the <xref:System.Data.DataSet> as XML data with the relational structure as inline XML Schema.</span></span>|  
|<span data-ttu-id="5a600-126">**DiffGram**</span><span class="sxs-lookup"><span data-stu-id="5a600-126">**DiffGram**</span></span>|<span data-ttu-id="5a600-127">Escribe el <xref:System.Data.DataSet> completo como un DiffGram, incluidos los valores originales y actuales.</span><span class="sxs-lookup"><span data-stu-id="5a600-127">Writes the entire <xref:System.Data.DataSet> as a DiffGram, including original and current values.</span></span> <span data-ttu-id="5a600-128">Para obtener más información, vea [DiffGrams](diffgrams.md).</span><span class="sxs-lookup"><span data-stu-id="5a600-128">For more information, see [DiffGrams](diffgrams.md).</span></span>|  
  
 <span data-ttu-id="5a600-129">Al escribir una representación XML de un <xref:System.Data.DataSet> objeto que contiene objetos **DataRelation** , lo más probable es que desee que el XML resultante tenga las filas secundarias de cada relación anidadas dentro de sus elementos primarios relacionados.</span><span class="sxs-lookup"><span data-stu-id="5a600-129">When writing an XML representation of a <xref:System.Data.DataSet> that contains **DataRelation** objects, you will most likely want the resulting XML to have the child rows of each relation nested within their related parent elements.</span></span> <span data-ttu-id="5a600-130">Para ello, establezca la propiedad **Nested** de la **DataRelation** en **true** cuando agregue la **DataRelation** a <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="5a600-130">To accomplish this, set the **Nested** property of the **DataRelation** to **true** when you add the **DataRelation** to the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="5a600-131">Para obtener más información, consulte anidamiento de objetos [DataRelation](nesting-datarelations.md).</span><span class="sxs-lookup"><span data-stu-id="5a600-131">For more information, see [Nesting DataRelations](nesting-datarelations.md).</span></span>  
  
 <span data-ttu-id="5a600-132">A continuación se muestran dos ejemplos de cómo escribir la representación XML de un <xref:System.Data.DataSet> en un archivo.</span><span class="sxs-lookup"><span data-stu-id="5a600-132">The following are two examples of how to write the XML representation of a <xref:System.Data.DataSet> to a file.</span></span> <span data-ttu-id="5a600-133">En el primer ejemplo se pasa el nombre de archivo para el XML resultante como una cadena a **WriteXml**.</span><span class="sxs-lookup"><span data-stu-id="5a600-133">The first example passes the file name for the resulting XML as a string to **WriteXml**.</span></span> <span data-ttu-id="5a600-134">En el segundo ejemplo se pasa un objeto **System. IO. StreamWriter** .</span><span class="sxs-lookup"><span data-stu-id="5a600-134">The second example passes a **System.IO.StreamWriter** object.</span></span>
  
```vb  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema)  
```  
  
```csharp  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema);  
```  
  
```vb  
Dim xmlSW As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xml")  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema)  
xmlSW.Close()  
```  
  
```csharp  
System.IO.StreamWriter xmlSW = new System.IO.StreamWriter("Customers.xml");  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema);  
xmlSW.Close();  
```  
  
## <a name="mapping-columns-to-xml-elements-attributes-and-text"></a><span data-ttu-id="5a600-135">Asignar columnas a elementos, atributos y texto XML</span><span class="sxs-lookup"><span data-stu-id="5a600-135">Mapping Columns to XML Elements, Attributes, and Text</span></span>  

 <span data-ttu-id="5a600-136">Puede especificar cómo se representa una columna de una tabla en XML mediante la propiedad **ColumnMapping** del objeto **DataColumn** .</span><span class="sxs-lookup"><span data-stu-id="5a600-136">You can specify how a column of a table is represented in XML using the **ColumnMapping** property of the **DataColumn** object.</span></span> <span data-ttu-id="5a600-137">En la tabla siguiente se muestran los diferentes valores de **MappingType** para la propiedad **ColumnMapping** de una columna de tabla y el XML resultante.</span><span class="sxs-lookup"><span data-stu-id="5a600-137">The following table shows the different **MappingType** values for the **ColumnMapping** property of a table column, and the resulting XML.</span></span>  
  
|<span data-ttu-id="5a600-138">Valor MappingType</span><span class="sxs-lookup"><span data-stu-id="5a600-138">MappingType value</span></span>|<span data-ttu-id="5a600-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a600-139">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="5a600-140">**Element**</span><span class="sxs-lookup"><span data-stu-id="5a600-140">**Element**</span></span>|<span data-ttu-id="5a600-141">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5a600-141">This is the default.</span></span> <span data-ttu-id="5a600-142">La columna se escribe como un elemento XML, donde ColumnName es el nombre del elemento y el contenido de la columna se escribe como el texto del elemento.</span><span class="sxs-lookup"><span data-stu-id="5a600-142">The column is written as an XML element where the ColumnName is the name of the element and the contents of the column are written as the text of the element.</span></span> <span data-ttu-id="5a600-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5a600-143">For example:</span></span><br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|<span data-ttu-id="5a600-144">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="5a600-144">**Attribute**</span></span>|<span data-ttu-id="5a600-145">La columna se escribe como un atributo XML del elemento XML para la fila actual, donde ColumnName es el nombre del atributo y el contenido de la columna se escribe como el valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="5a600-145">The column is written as an XML attribute of the XML element for the current row where the ColumnName is the name of the attribute and the contents of the column are written as the value of the attribute.</span></span> <span data-ttu-id="5a600-146">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5a600-146">For example:</span></span><br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|<span data-ttu-id="5a600-147">**SimpleContent**</span><span class="sxs-lookup"><span data-stu-id="5a600-147">**SimpleContent**</span></span>|<span data-ttu-id="5a600-148">El contenido de la columna se escribe como texto en el elemento XML de la fila actual.</span><span class="sxs-lookup"><span data-stu-id="5a600-148">The contents of the column are written as text in the XML element for the current row.</span></span> <span data-ttu-id="5a600-149">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5a600-149">For example:</span></span><br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> <span data-ttu-id="5a600-150">Tenga en cuenta que **SimpleContent** no se puede establecer para una columna de una tabla que tenga columnas de **elementos** o relaciones anidadas.</span><span class="sxs-lookup"><span data-stu-id="5a600-150">Note that **SimpleContent** cannot be set for a column of a table that has **Element** columns or nested relations.</span></span>|  
|<span data-ttu-id="5a600-151">**Oculto**</span><span class="sxs-lookup"><span data-stu-id="5a600-151">**Hidden**</span></span>|<span data-ttu-id="5a600-152">La columna no se escribe en el resultado XML.</span><span class="sxs-lookup"><span data-stu-id="5a600-152">The column is not written in the XML output.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a600-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a600-153">See also</span></span>

- [<span data-ttu-id="5a600-154">Usar XML en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="5a600-154">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="5a600-155">Objetos DiffGram</span><span class="sxs-lookup"><span data-stu-id="5a600-155">DiffGrams</span></span>](diffgrams.md)
- [<span data-ttu-id="5a600-156">Anidar objetos DataRelation</span><span class="sxs-lookup"><span data-stu-id="5a600-156">Nesting DataRelations</span></span>](nesting-datarelations.md)
- [<span data-ttu-id="5a600-157">Escribir información del esquema de un conjunto de datos como XSD</span><span class="sxs-lookup"><span data-stu-id="5a600-157">Writing DataSet Schema Information as XSD</span></span>](writing-dataset-schema-information-as-xsd.md)
- [<span data-ttu-id="5a600-158">Objetos DataSet, DataTable y DataView</span><span class="sxs-lookup"><span data-stu-id="5a600-158">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="5a600-159">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5a600-159">ADO.NET Overview</span></span>](../ado-net-overview.md)
