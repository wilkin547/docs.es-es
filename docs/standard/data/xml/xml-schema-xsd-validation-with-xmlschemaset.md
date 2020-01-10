---
title: Validación de esquema XML (XSD) con XmlSchemaSet
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 359b10eb-ec05-4cc6-ac96-c2b060afc4de
ms.openlocfilehash: 6bd7525b77d4154193b57f8e6589cb865ace5fd6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709886"
---
# <a name="xml-schema-xsd-validation-with-xmlschemaset"></a>Validación de esquema XML (XSD) con XmlSchemaSet
Los documentos XML se pueden validar con un esquema del lenguaje de definición de esquemas (XSD) en un <xref:System.Xml.Schema.XmlSchemaSet>.  
  
## <a name="validating-xml-documents"></a>Validación de documentos XML  
 El método <xref:System.Xml.XmlReader.Create%2A> de la clase <xref:System.Xml.XmlReader> valida los documentos XML. Para validar un documento XML, construya un objeto <xref:System.Xml.XmlReaderSettings> que contiene un esquema XSD con el que validar el documento XML.  
  
> [!NOTE]
> El espacio de nombres <xref:System.Xml.Schema> contiene métodos de extensión que facilitan el proceso de validar un árbol XML en un archivo XSD cuando se utiliza [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) y [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md). Para obtener más información sobre la validación de documentos XML con LINQ to XML, vea [cómo validar con xsd (LINQ to XMLC#) ()](../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) y [Cómo: validar con xsd (LINQ to XML) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md).
  
 Es posible agregar un esquema en particular o un conjunto de esquemas (como un <xref:System.Xml.Schema.XmlSchemaSet>) a un <xref:System.Xml.Schema.XmlSchemaSet> pasando uno de ellos como parámetro del método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> de <xref:System.Xml.Schema.XmlSchemaSet>. Observe que cuando se valida un documento, el espacio de nombres de destino del documento debe coincidir con el espacio de nombres de destino del esquema que forma parte del conjunto.  
  
 El siguiente es un ejemplo de un documento XML.  
  
 [!code-xml[XSDInference Examples#5](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xml#5)]  
  
 El siguiente es el esquema que valida el ejemplo del documento XML.  
  
 [!code-xml[XSDInference Examples#6](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xsd#6)]  
  
 En el código de ejemplo siguiente, se agrega el esquema anterior a la propiedad <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A> del objeto <xref:System.Xml.XmlReaderSettings>. El objeto <xref:System.Xml.XmlReaderSettings> se pasa como parámetro del método <xref:System.Xml.XmlReader.Create%2A> del objeto <xref:System.Xml.XmlReader>, el cual valida el documento XML anterior.  
  
 La propiedad <xref:System.Xml.XmlReaderSettings.ValidationType%2A> del objeto <xref:System.Xml.XmlReaderSettings> se establece en `Schema` para exigir la validación del documento XML por medio del método <xref:System.Xml.XmlReader.Create%2A> del objeto <xref:System.Xml.XmlReader>. Se agrega un <xref:System.Xml.Schema.ValidationEventHandler> al objeto <xref:System.Xml.XmlReaderSettings> para controlar cualquier evento <xref:System.Xml.Schema.XmlSeverityType.Warning> o <xref:System.Xml.Schema.XmlSeverityType.Error> que inicien los errores encontrados durante el proceso de validación del documento XML y del esquema.  
  
 [!code-cpp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaSetOverall Example/CPP/xmlschemasetexample.cpp#1)]
 [!code-csharp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaSetOverall Example/CS/xmlschemasetexample.cs#1)]
 [!code-vb[XmlSchemaSetOverall Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaSetOverall Example/VB/xmlschemasetexample.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [XmlSchemaSet para compilación de esquemas](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [Trabajo con esquemas XML](../../../../docs/standard/data/xml/working-with-xml-schemas.md)
