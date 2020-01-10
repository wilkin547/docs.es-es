---
title: Conjunto de información posterior a la compilación de esquemas
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 7f1bc7f4-401b-459f-9078-f099cc711fde
ms.openlocfilehash: 016032b2b37ced5592edc18934ed183c475f5598
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710484"
---
# <a name="post-schema-compilation-infoset"></a>Conjunto de información posterior a la compilación de esquemas
La [recomendación de esquemas XML del W3C (World Wide Web Consortium)](https://www.w3.org/XML/Schema) trata acerca del conjunto de información que debe presentarse para la validación del esquema previo y para la compilación del esquema posterior. El Modelo de objetos de esquema XML (SOM) consulta esta información antes y después de llamar al método <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> de <xref:System.Xml.Schema.XmlSchemaSet>.  
  
 El conjunto de información previo a la validación del esquema se crea durante la edición del esquema. El conjunto de información posterior a la compilación del esquema se genera después de llamar al método <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> de <xref:System.Xml.Schema.XmlSchemaSet> durante la compilación del esquema, y se proporciona como propiedades.  
  
 El SOM es el modelo de objetos que representa los conjuntos de información previos a la validación del esquema y posteriores a la compilación del esquema; consta de las clases del espacio de nombres <xref:System.Xml.Schema?displayProperty=nameWithType>. Todas las propiedades de lectura y escritura de las clases del espacio de nombres <xref:System.Xml.Schema> pertenecen al conjunto de información previo a la validación del esquema, mientras que todas las propiedades de solo lectura de las clases del espacio de nombres <xref:System.Xml.Schema> pertenecen al conjunto de información posterior a la compilación del esquema. Las siguientes propiedades son la excepción a esta norma, ya que se trata de propiedades del conjunto de información previo a la validación del esquema y del conjunto de información posterior a la compilación del esquema.  
  
|Clase|La propiedad|  
|-----------|--------------|  
|<xref:System.Xml.Schema.XmlSchemaObject>|<xref:System.Xml.Schema.XmlSchemaObject.Parent%2A>|  
|<xref:System.Xml.Schema.XmlSchema>|<xref:System.Xml.Schema.XmlSchema.AttributeFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.BlockDefault%2A>, <xref:System.Xml.Schema.XmlSchema.ElementFormDefault%2A>, <xref:System.Xml.Schema.XmlSchema.FinalDefault%2A>, <xref:System.Xml.Schema.XmlSchema.TargetNamespace%2A>|  
|<xref:System.Xml.Schema.XmlSchemaExternal>|<xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A>|  
|<xref:System.Xml.Schema.XmlSchemaAttributeGroup>|<xref:System.Xml.Schema.XmlSchemaAttributeGroup.AnyAttribute%2A>|  
|<xref:System.Xml.Schema.XmlSchemaParticle>|<xref:System.Xml.Schema.XmlSchemaParticle.MaxOccurs%2A>, <xref:System.Xml.Schema.XmlSchemaParticle.MinOccurs%2A>|  
|<xref:System.Xml.Schema.XmlSchemaComplexType>|<xref:System.Xml.Schema.XmlSchemaComplexType.AnyAttribute%2A>|  
  
 Por ejemplo, las clases <xref:System.Xml.Schema.XmlSchemaElement> y <xref:System.Xml.Schema.XmlSchemaComplexType> tienen las propiedades `BlockResolved` y `FinalResolved`. Estas propiedades se utilizan para contener los valores de las propiedades `Block` y `Final` después de compilar y validar el esquema. `BlockResolved` y `FinalResolved` son propiedades de solo lectura que forman parte del conjunto de información posterior a la compilación del esquema.  
  
 En el siguiente ejemplo se muestra la propiedad <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> de la clase <xref:System.Xml.Schema.XmlSchemaElement> que se establece después de validar el esquema. Antes de la validación, la propiedad contiene una referencia `null` y el <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> está establecido en el nombre del tipo en cuestión. Después de la validación, <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> se resuelve como un tipo válido y el objeto de tipo está disponible a través de la propiedad <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A>.  
  
 [!code-cpp[PsciSample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/PsciSample/CPP/PsciSample.cpp#1)]
 [!code-csharp[PsciSample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/PsciSample/CS/PsciSample.cs#1)]
 [!code-vb[PsciSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/PsciSample/VB/PsciSample.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Modelo de objetos de esquema XML (SOM)](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)
