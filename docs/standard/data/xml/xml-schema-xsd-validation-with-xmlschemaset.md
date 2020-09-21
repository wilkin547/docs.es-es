---
title: Validación de esquema XML (XSD) con XmlSchemaSet
description: Aprenda a validar documentos XML en un esquema del lenguaje de definición de esquema XML (XSD) con una clase XmlSchemaSet en .NET.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 359b10eb-ec05-4cc6-ac96-c2b060afc4de
ms.openlocfilehash: 5963ba1b382740b1774c944b74c6a54b13db4f76
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554520"
---
# <a name="xml-schema-xsd-validation-with-xmlschemaset"></a>Validación de esquema XML (XSD) con XmlSchemaSet

Los documentos XML se pueden validar con un esquema del lenguaje de definición de esquemas (XSD) en un <xref:System.Xml.Schema.XmlSchemaSet>.  
  
## <a name="validate-xml-documents"></a>Validación de documentos XML  
 El método <xref:System.Xml.XmlReader.Create%2A> de la clase <xref:System.Xml.XmlReader> valida los documentos XML. Para validar un documento XML, construya un objeto <xref:System.Xml.XmlReaderSettings> que contiene un esquema XSD con el que validar el documento XML.  
  
> [!NOTE]
> El espacio de nombres <xref:System.Xml.Schema> contiene métodos de extensión que facilitan el proceso de validar un árbol XML en un archivo XSD cuando se utiliza [LINQ to XML (C#)](../../linq/linq-xml-overview.md) y [LINQ to XML (Visual Basic)](../../linq/linq-xml-overview.md). Para obtener más información sobre cómo validar documentos XML con LINQ to XML, vea [Procedimiento para realizar validaciones con XSD (LINQ to XML) (C#)](../../linq/validate-xsd.md) y [Cómo: Validar con XSD (LINQ to XML) (Visual Basic)](../../linq/validate-xsd.md).
  
 Es posible agregar un esquema en particular o un conjunto de esquemas (como un <xref:System.Xml.Schema.XmlSchemaSet>) a un <xref:System.Xml.Schema.XmlSchemaSet> pasando uno de ellos como parámetro del método <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> de <xref:System.Xml.Schema.XmlSchemaSet>. Cuando se valida un documento, el espacio de nombres de destino del documento debe coincidir con el espacio de nombres de destino del esquema que forma parte del conjunto.  
  
 El siguiente es un ejemplo de un documento XML.  
  
 [!code-xml[XSDInference Examples #5](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xml#5)]  
  
 El siguiente es el esquema que valida el ejemplo del documento XML.  
  
 [!code-xml[XSDInference Examples #6](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xsd#6)]  
  
 En el código de ejemplo siguiente, se agrega el esquema anterior a la propiedad <xref:System.Xml.XmlReaderSettings.Schemas%2A> del objeto <xref:System.Xml.XmlReaderSettings>. El objeto <xref:System.Xml.XmlReaderSettings> se pasa como parámetro del método <xref:System.Xml.XmlReader.Create%2A> del objeto <xref:System.Xml.XmlReader>, el cual valida el documento XML anterior.  
  
 La propiedad <xref:System.Xml.XmlReaderSettings.ValidationType%2A> del objeto <xref:System.Xml.XmlReaderSettings> se establece en `Schema` para exigir la validación del documento XML por medio del método <xref:System.Xml.XmlReader.Create%2A> del objeto <xref:System.Xml.XmlReader>. Se agrega un <xref:System.Xml.Schema.ValidationEventHandler> al objeto <xref:System.Xml.XmlReaderSettings> para controlar cualquier evento <xref:System.Xml.Schema.XmlSeverityType.Warning> o <xref:System.Xml.Schema.XmlSeverityType.Error> que inicien los errores encontrados durante el proceso de validación del documento XML y del esquema.  
  
 [!code-cpp[XmlSchemaSetOverall Example #1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaSetOverall Example/CPP/xmlschemasetexample.cpp#1)]
 [!code-csharp[XmlSchemaSetOverall Example #1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaSetOverall Example/CS/xmlschemasetexample.cs#1)]
 [!code-vb[XmlSchemaSetOverall Example #1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaSetOverall Example/VB/xmlschemasetexample.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [XmlSchemaSet para compilación de esquemas](xmlschemaset-for-schema-compilation.md)
- [Trabajo con esquemas XML](working-with-xml-schemas.md)
