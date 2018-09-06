---
title: Aplicar una transformación XSL a un DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09f2e4ee-1d08-4ba8-8936-83394fee319d
ms.openlocfilehash: abcb3231aa92bd62edefc7f7341da5fcb3321e4b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43734751"
---
# <a name="applying-an-xslt-transform-to-a-dataset"></a><span data-ttu-id="8ae9d-102">Aplicar una transformación XSL a un DataSet</span><span class="sxs-lookup"><span data-stu-id="8ae9d-102">Applying an XSLT Transform to a DataSet</span></span>
<span data-ttu-id="8ae9d-103">El **WriteXml** método de la <xref:System.Data.DataSet> le permite escribir el contenido de un **DataSet** como datos XML.</span><span class="sxs-lookup"><span data-stu-id="8ae9d-103">The **WriteXml** method of the <xref:System.Data.DataSet> enables you to write the contents of a **DataSet** as XML data.</span></span> <span data-ttu-id="8ae9d-104">Normalmente se transforma ese XML en otro formato mediante transformaciones XSL (XSLT).</span><span class="sxs-lookup"><span data-stu-id="8ae9d-104">A common task is to then transform that XML to another format using XSL transformations (XSLT).</span></span> <span data-ttu-id="8ae9d-105">Sin embargo, la sincronización un **DataSet** con un <xref:System.Xml.XmlDataDocument> le permite aplicar una hoja de estilos XSLT al contenido de un **conjunto de datos** sin tener que escribir primero el contenido de la  **Conjunto de datos** como datos XML mediante **WriteXml**.</span><span class="sxs-lookup"><span data-stu-id="8ae9d-105">However, synchronizing a **DataSet** with an <xref:System.Xml.XmlDataDocument> enables you to apply an XSLT stylesheet to the contents of a **DataSet** without having to first write the contents of the **DataSet** as XML data using **WriteXml**.</span></span>  
  
 <span data-ttu-id="8ae9d-106">En el ejemplo siguiente se rellena un **DataSet** con tablas y relaciones, se sincroniza el **DataSet** con un **XmlDataDocument**y escribe una parte de la  **Conjunto de datos** como un archivo HTML utilizando una hoja de estilos XSLT.</span><span class="sxs-lookup"><span data-stu-id="8ae9d-106">The following example populates a **DataSet** with tables and relationships, synchronizes the **DataSet** with an **XmlDataDocument**, and writes a portion of the **DataSet** as an HTML file using an XSLT stylesheet.</span></span> <span data-ttu-id="8ae9d-107">A continuación se muestra el contenido de la hoja de estilos XSLT.</span><span class="sxs-lookup"><span data-stu-id="8ae9d-107">Following are the contents of the XSLT stylesheet.</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
  
<xsl:template match="CustomerOrders">  
  <HTML>  
  <STYLE>  
  BODY {font-family:verdana;font-size:9pt}  
  TD   {font-size:8pt}  
  </STYLE>  
    <BODY>  
    <TABLE BORDER="1">  
      <xsl:apply-templates select="Customers"/>  
    </TABLE>  
    </BODY>  
  </HTML>  
</xsl:template>  
  
<xsl:template match="Customers">  
    <TR><TD>  
      <xsl:value-of select="ContactName"/>, <xsl:value-of select="Phone"/><BR/>  
    </TD></TR>  
      <xsl:apply-templates select="Orders"/>  
</xsl:template>  
  
<xsl:template match="Orders">  
  <TABLE BORDER="1">  
    <TR><TD valign="top"><B>Order:</B></TD><TD valign="top"><xsl:value-of select="OrderID"/></TD></TR>  
    <TR><TD valign="top"><B>Date:</B></TD><TD valign="top"><xsl:value-of select="OrderDate"/></TD></TR>  
    <TR><TD valign="top"><B>Ship To:</B></TD>  
        <TD valign="top"><xsl:value-of select="ShipName"/><BR/>  
        <xsl:value-of select="ShipAddress"/><BR/>  
        <xsl:value-of select="ShipCity"/>, <xsl:value-of select="ShipRegion"/>  <xsl:value-of select="ShipPostalCode"/><BR/>  
        <xsl:value-of select="ShipCountry"/></TD></TR>  
  </TABLE>  
</xsl:template>  
  
</xsl:stylesheet>  
```  
  
 <span data-ttu-id="8ae9d-108">El siguiente código rellena la **DataSet** y se aplica a la hoja de estilos XSLT.</span><span class="sxs-lookup"><span data-stu-id="8ae9d-108">The following code fills the **DataSet** and applies the XSLT style sheet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ae9d-109">Si aplica una hoja de estilos XSLT a un **conjunto de datos** que contenga relaciones, lograr el mejor rendimiento si establece la **Nested** propiedad de la <xref:System.Data.DataRelation> a **true**para cada relación anidada.</span><span class="sxs-lookup"><span data-stu-id="8ae9d-109">If you are applying an XSLT style sheet to a **DataSet** that contains relations, you achieve best performance if you set the **Nested** property of the <xref:System.Data.DataRelation> to **true** for each nested relation.</span></span> <span data-ttu-id="8ae9d-110">Esto le permite utilizar hojas de estilos XSLT que implementan un procesamiento natural, de arriba abajo, para navegar por la jerarquía y transformar los datos, en lugar de utilizar ejes de ubicación XPath de rendimiento intensivo (por ejemplo, el elemento anterior y el siguiente en expresiones de prueba de nodos de la hoja de estilos) para navegar por ésta.</span><span class="sxs-lookup"><span data-stu-id="8ae9d-110">This allows you to use XSLT style sheets that implement natural top-down processing to navigate the hierarchy and transform the data, as opposed to using performance-intensive XPath location axes (for example, preceding-sibling and following-sibling in style sheet node test expressions) to navigate it.</span></span> <span data-ttu-id="8ae9d-111">Para obtener más información sobre las relaciones anidadas, vea [anidar objetos DataRelation](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span><span class="sxs-lookup"><span data-stu-id="8ae9d-111">For more information on nested relations, see [Nesting DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md).</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim dataSet As DataSet = New DataSet("CustomerOrders")  
  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Customers", connection)  
customerAdapter.Fill(dataSet, "Customers")  
  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM Orders", connection)  
orderAdapter.Fill(dataSet, "Orders")  
  
connection.Close()  
  
dataSet.Relations.Add("CustOrders", _  
dataSet.Tables("Customers").Columns("CustomerID"), _  
dataSet.Tables("Orders").Columns("CustomerID")).Nested = true  
  
Dim xmlDoc As XmlDataDocument = New XmlDataDocument(dataSet)   
  
Dim xslTran As XslTransform = New XslTransform  
xslTran.Load("transform.xsl")  
  
Dim writer As XmlTextWriter = New XmlTextWriter( _  
  "xslt_output.html", System.Text.Encoding.UTF8)  
  
xslTran.Transform(xmlDoc, Nothing, writer)  
writer.Close()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
connection.Open();  
  
DataSet custDS = new DataSet("CustomerDataSet");  
  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
  "SELECT * FROM Customers", connection);  
customerAdapter.Fill(custDS, "Customers");  
  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
  "SELECT * FROM Orders", connection);  
orderAdapter.Fill(custDS, "Orders");  
  
connection.Close();  
  
custDS.Relations.Add("CustOrders",  
  custDS.Tables["Customers"].Columns["CustomerID"],  
                     custDS.Tables["Orders"].Columns["CustomerID"]).Nested = true;  
  
XmlDataDocument xmlDoc = new XmlDataDocument(custDS);   
  
XslTransform xslTran = new XslTransform();  
xslTran.Load("transform.xsl");  
  
XmlTextWriter writer = new XmlTextWriter("xslt_output.html",   
  System.Text.Encoding.UTF8);  
  
xslTran.Transform(xmlDoc, null, writer);  
writer.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ae9d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ae9d-112">See Also</span></span>  
 [<span data-ttu-id="8ae9d-113">Sincronización de DataSet y XmlDataDocument</span><span class="sxs-lookup"><span data-stu-id="8ae9d-113">DataSet and XmlDataDocument Synchronization</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md)  
 [<span data-ttu-id="8ae9d-114">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="8ae9d-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
