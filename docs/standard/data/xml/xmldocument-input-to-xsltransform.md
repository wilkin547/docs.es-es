---
title: "Entrada de XmlDocument en XslTransform | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 97115892-410a-4657-ab47-1e14dfba73f8
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Entrada de XmlDocument en XslTransform
La clase <xref:System.Xml.XmlDocument> permite modificar un documento XML. Si el XML necesita editarse o modificarse antes de ser enviado al método <xref:System.Xml.Xsl.XslTransform.Transform%2A>, cargue el XML en <xref:System.Xml.XmlDocument>, edítelo y envíelo a <xref:System.Xml.Xsl.XslTransform>.  
  
> [!NOTE]
>  La clase <xref:System.Xml.Xsl.XslTransform> es obsoleta en [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]. Puede llevar a cabo Extensible Stylesheet Language for Transformations \(XSLT\) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Para obtener más información, vea [Uso de la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 <xref:System.Xml.XmlDocument> implementa la interfaz <xref:System.Xml.XPath.IXPathNavigable>, de forma que el documento puede pasarse al método <xref:System.Xml.Xsl.XslTransform.Transform%2A> después de la edición.  
  
 Debido a la capacidad de edición de <xref:System.Xml.XmlDocument>, utilizar la clase <xref:System.Xml.XmlDocument> como entrada a una transformación es más lento que usar <xref:System.Xml.XPath.XPathDocument> para las transformaciones Extensible Stylesheet Language for Transformations \(XSLT\), ya que <xref:System.Xml.XPath.XPathDocument> se optimiza para las consultas XML Path Language \(XPath\) debido al almacenamiento interno.  
  
## Ejemplo  
 El siguiente ejemplo de código muestra cómo <xref:System.Xml.XmlDocument> puede suministrarse a <xref:System.Xml.Xsl.XslTransform>, con el resultado enviado a <xref:System.Xml.XmlReader>.  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.Load("books.xml")  
Dim trans As XslTransform = new XslTransform()  
trans.Load("book.xsl")  
Dim rdr As XmlReader = trans.Transform(doc, Nothing, Nothing)  
while (rdr.Read())  
end while  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.Load("books.xml");  
XslTransform trans = new XslTransform();  
trans.Load("book.xsl");  
XmlReader rdr = trans.Transform(doc, null, null);  
while (rdr.Read()) {}  
```  
  
## Vea también  
 <xref:System.Xml.XmlDocument>   
 [Transformaciones XSLT con la clase XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)   
 [La clase XslTransform implementa el procesador XSLT](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)   
 [XPathNavigator en transformaciones](../../../../docs/standard/data/xml/xpathnavigator-in-transformations.md)   
 [XPathNodeIterator en transformaciones](../../../../docs/standard/data/xml/xpathnodeiterator-in-transformations.md)   
 [Entrada XPathDocument Input para XslTransform](../../../../docs/standard/data/xml/xpathdocument-input-to-xsltransform.md)   
 [Entrada de XmlDataDocument en XslTransform](../../../../docs/standard/data/xml/xmldatadocument-input-to-xsltransform.md)