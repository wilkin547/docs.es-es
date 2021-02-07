---
description: Más información acerca de cómo aplicar una transformación XSLT a un conjunto de información
title: Aplicar una transformación XSL a un DataSet
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 09f2e4ee-1d08-4ba8-8936-83394fee319d
ms.openlocfilehash: c7fc25441091112f7fbb7e4c1f8dd210d8cd0c5d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725121"
---
# <a name="applying-an-xslt-transform-to-a-dataset"></a>Aplicar una transformación XSL a un DataSet

El método **WriteXml** de <xref:System.Data.DataSet> le permite escribir el contenido de un **DataSet** como datos XML. Normalmente se transforma ese XML en otro formato mediante transformaciones XSL (XSLT). Sin embargo, la sincronización de un **conjunto** de datos con un <xref:System.Xml.XmlDataDocument> le permite aplicar una hoja de estilos XSLT al contenido de un **conjunto** de datos sin tener que escribir primero el contenido del **conjunto** de datos como datos XML mediante **WriteXml**.  
  
 En el ejemplo siguiente se rellena un **DataSet** con tablas y relaciones, se sincroniza el **DataSet** con un **XmlDataDocument** y se escribe una parte del **conjunto** de elementos como un archivo HTML mediante una hoja de estilos XSLT. A continuación se muestran los contenidos de la hoja de estilos XSLT:
  
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
  
 En el código siguiente se rellena el **conjunto** de elementos y se aplica la hoja de estilos XSLT.  
  
> [!NOTE]
> Si va a aplicar una hoja de estilos XSLT a un **conjunto** de resultados que contiene relaciones, obtendrá un rendimiento óptimo si establece la propiedad **Nested** de <xref:System.Data.DataRelation> en **true** para cada relación anidada. Esto le permite utilizar hojas de estilos XSLT que implementan un procesamiento natural, de arriba abajo, para navegar por la jerarquía y transformar los datos, en lugar de utilizar ejes de ubicación XPath de rendimiento intensivo (por ejemplo, el elemento anterior y el siguiente en expresiones de prueba de nodos de la hoja de estilos) para navegar por ésta. Para obtener más información sobre las relaciones anidadas, vea anidamiento de objetos [DataRelation](nesting-datarelations.md).  
  
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
  
## <a name="see-also"></a>Vea también

- [Sincronización de DataSet y XmlDataDocument](dataset-and-xmldatadocument-synchronization.md)
- [Información general de ADO.NET](../ado-net-overview.md)
