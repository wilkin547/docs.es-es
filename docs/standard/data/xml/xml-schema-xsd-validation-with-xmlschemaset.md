---
title: "Validación de esquema XML (XSD) con XmlSchemaSet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 359b10eb-ec05-4cc6-ac96-c2b060afc4de
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a6cf857ccecbdac88453fd1fba6e93d609196b1a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xml-schema-xsd-validation-with-xmlschemaset"></a>Validación de esquema XML (XSD) con XmlSchemaSet
Los documentos XML se pueden validar con un esquema del lenguaje de definición de esquemas (XSD) en un <xref:System.Xml.Schema.XmlSchemaSet>.  
  
## <a name="validating-xml-documents"></a>Validación de documentos XML  
 El método <xref:System.Xml.XmlReader.Create%2A> de la clase <xref:System.Xml.XmlReader> valida los documentos XML. Para validar un documento XML, construya un objeto <xref:System.Xml.XmlReaderSettings> que contiene un esquema XSD con el que validar el documento XML.  
  
> [!NOTE]
>  El <xref:System.Xml.Schema> espacio de nombres contiene métodos de extensión que resulten fácil validar un árbol XML contra un archivo XSD al usar [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13). Para obtener más información sobre la validación de documentos XML con LINQ to XML, vea [Cómo: validar XSD utilizando](http://msdn.microsoft.com/library/481a97fa-6e96-46f2-8c9a-415555fac33b).  
  
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
 [XmlSchemaSet para compilación de esquemas](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 [Trabajar con esquemas XML](../../../../docs/standard/data/xml/working-with-xml-schemas.md)
