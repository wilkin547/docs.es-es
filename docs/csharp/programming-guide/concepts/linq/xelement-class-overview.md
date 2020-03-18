---
title: Información general de la clase XElement (C#)
ms.date: 07/20/2015
ms.assetid: 2b9f0cd8-a1d1-4037-accf-0f38a410fa11
ms.openlocfilehash: 6a93dd4bdaf16fddff800b08b0f3146ecb63f9b7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167899"
---
# <a name="xelement-class-overview-c"></a>Información general de la clase XElement (C#)
La clase <xref:System.Xml.Linq.XElement> es una de las clases fundamentales de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Representa a un elemento XML. Puede utilizar esta clase para crear elementos; cambiar el contenido del elemento; agregar, modificar o eliminar elementos secundarios; agregar atributos a un elemento; o serializar el contenido de un elemento en forma de texto. También puede operar con otras clases de <xref:System.Xml?displayProperty=nameWithType>, como son <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> y <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
Este tema describe la funcionalidad que ofrece la clase <xref:System.Xml.Linq.XElement>.  
  
## <a name="constructing-xml-trees"></a>Construir árboles XML  
 Es posible construir árboles XML de diferentes formas, entre las que se incluyen las siguientes:  
  
- Puede construir un árbol XML mediante código. Para obtener más información, consulte [Crear árboles XML (C#)](./linq-to-xml-overview.md).  
  
- Puede analizar XML a partir de diferentes orígenes, incluyendo un <xref:System.IO.TextReader>, archivos de texto o direcciones web (URL). Para obtener más información, consulte [Analizar XML (C#)](./how-to-parse-a-string.md).  
  
- También puede utilizar un <xref:System.Xml.XmlReader> para rellenar el árbol. Para obtener más información, consulta <xref:System.Xml.Linq.XNode.ReadFrom%2A>.  
  
- Si dispone de un módulo que pueda escribir contenidos en un <xref:System.Xml.XmlWriter>, puede utilizar el método <xref:System.Xml.Linq.XContainer.CreateWriter%2A> para crear un sistema de escritura, para pasar éste al módulo y para utilizar después el contenido que se haya escrito en <xref:System.Xml.XmlWriter> para rellenar el árbol XML.  
  
 No obstante, la forma más habitual de crear un árbol XML es la siguiente:  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 Otra técnica que se usa con frecuencia para crear un árbol XML implica el uso de los resultados de una consulta LINK para rellenar el árbol XML, tal y como se muestra en el ejemplo siguiente:  
  
```csharp  
XElement srcTree = new XElement("Root",  
    new XElement("Element", 1),  
    new XElement("Element", 2),  
    new XElement("Element", 3),  
    new XElement("Element", 4),  
    new XElement("Element", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    from el in srcTree.Elements()  
    where (int)el > 2  
    select el  
);  
Console.WriteLine(xmlTree);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="serializing-xml-trees"></a>Serializar árboles XML  
 Puede serializar un árbol XML en un <xref:System.IO.File>, un <xref:System.IO.TextWriter> o en un <xref:System.Xml.XmlWriter>.  
  
 Para obtener más información, consulte [Serializar árboles XML (C#)](./preserving-white-space-while-serializing.md).  
  
## <a name="retrieving-xml-data-via-axis-methods"></a>Recuperar datos XML mediante los métodos de los ejes  
 Puede utilizar los métodos de los ejes para recuperar atributos, elementos secundarios, elementos descendientes y elementos antecesores. Las consultas LINK operan sobre métodos de eje y proporcionan varias formas flexibles y eficaces de recorrer y procesar árboles XML.  
  
 Para obtener más información, consulte [Ejes de LINQ to XML (C#)](./linq-to-xml-axes-overview.md).  
  
## <a name="querying-xml-trees"></a>Consultar árboles XML  
 Puede escribir consultas LINK que extraigan datos de un árbol XML.  
  
 Para obtener más información, consulte [Consultar árboles XML (C#)](./how-to-find-an-element-with-a-specific-attribute.md).  
  
## <a name="modifying-xml-trees"></a>Modificar árboles XML  
 Puede modificar un elemento de diferentes maneras, incluyendo el cambiar su contenido o sus atributos. También puede eliminar un elemento dependiente de un elemento primario.  
  
 Para obtener más información, consulte [Modificar árboles XML (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre la programación de LINQ to XML (C#)](serializing-to-files-textwriters-and-xmlwriters.md)
