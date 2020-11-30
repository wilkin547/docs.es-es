---
title: Atributos que controlan la serialización XML
description: Este artículo contiene atributos que se pueden aplicar a clases y miembros de clase para controlar la forma en que XmlSerializer serializa o deserializa una instancia de una clase.
ms.date: 03/30/2017
helpviewer_keywords:
- classes, serializing
- XmlSerializer class, serializing
- XML serialization, attributes
- attributes [.NET], XML serialization
- serialization, attributes
- XML Schema, serializing
ms.assetid: 414b820f-a696-4206-b576-2711d85490c7
ms.openlocfilehash: 55c36ea6313bfd3000b1d8502d4eda7c552e08cf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717934"
---
# <a name="attributes-that-control-xml-serialization"></a>Atributos que controlan la serialización XML

Se pueden aplicar atributos a clases y a miembros de clase en la siguiente tabla para controlar la manera en que <xref:System.Xml.Serialization.XmlSerializer> serializa o deserializa una instancia de la clase. Para entender cómo controlan estos atributos la serialización XML, vea [Controlar la serialización XML mediante atributos](controlling-xml-serialization-using-attributes.md).  
  
 Estos atributos también se pueden utilizar para controlar los mensajes SOAP de estilo literales generados por un servicio Web XML. Para más información sobre la aplicación de estos atributos a un método de servicios web XML, vea [Serialización XML con servicios web XML](xml-serialization-with-xml-web-services.md).  
  
 Para obtener más información sobre atributos, vea [Atributos](../attributes/index.md).  
  
|Atributo|Se aplica a|Especifica|  
|---------------|----------------|---------------|  
|<xref:System.Xml.Serialization.XmlAnyAttributeAttribute>|El campo público, propiedad, parámetro o valor devuelto que devuelve una matriz de objetos <xref:System.Xml.XmlAttribute> objects.|Al deserializar, la matriz estará llena de objetos <xref:System.Xml.XmlAttribute> que representan todos los atributos XML desconocidos para el esquema.|  
|<xref:System.Xml.Serialization.XmlAnyElementAttribute>|El campo público, propiedad, parámetro o valor devuelto que devuelve una matriz de objetos <xref:System.Xml.XmlElement> objects.|Al deserializar, la matriz estará llena de objetos <xref:System.Xml.XmlElement> que representan todos los atributos XML desconocidos para el esquema|  
|<xref:System.Xml.Serialization.XmlArrayAttribute>|El campo público, propiedad, parámetro o valor devuelto que devuelve una matriz de objetos complejos.|Los miembros de la matriz se generarán como miembros de una matriz de XML.|  
|<xref:System.Xml.Serialization.XmlArrayItemAttribute>|El campo público, propiedad, parámetro o valor devuelto que devuelve una matriz de objetos complejos.|Los tipos derivados que se pueden insertar en una matriz. Normalmente aplicado junto con un <xref:System.Xml.Serialization.XmlArrayAttribute>.|  
|<xref:System.Xml.Serialization.XmlAttributeAttribute>|Campo público, propiedad, parámetro o valor devuelto.|El miembro se serializará como un atributo XML.|  
|<xref:System.Xml.Serialization.XmlChoiceIdentifierAttribute>|Campo público, propiedad, parámetro o valor devuelto.|El miembro se puede desambiguar adicionalmente utilizando una enumeración.|  
|<xref:System.Xml.Serialization.XmlElementAttribute>|Campo público, propiedad, parámetro o valor devuelto.|El campo o propiedad se serializará como un elemento XML.|  
|<xref:System.Xml.Serialization.XmlEnumAttribute>|Campo público que es un identificador de enumeración.|Nombre de elemento del miembro de una enumeración.|  
|<xref:System.Xml.Serialization.XmlIgnoreAttribute>|Propiedades públicas y campos.|Se debería omitir la propiedad o campo cuando se serializa la clase contenedora.|  
|<xref:System.Xml.Serialization.XmlIncludeAttribute>|Declaraciones de clase derivada públicas y valores devueltos de métodos públicos para los documentos de lenguaje de descripción de servicios Web (WSDL).|La clase debería estar incluida al generar los esquemas (para ser reconocido cuando se serializa).|  
|<xref:System.Xml.Serialization.XmlRootAttribute>|Declaraciones de clase públicas.|Controla la serialización XML del destino de atributo como elemento raíz XML. Utilice el atributo para especificar el espacio de nombres y nombre de elemento.|  
|<xref:System.Xml.Serialization.XmlTextAttribute>|Propiedades públicas y campos.|La propiedad o campo se debería serializar como texto XML.|  
|<xref:System.Xml.Serialization.XmlTypeAttribute>|Declaraciones de clase públicas.|El nombre y espacio de nombres del tipo XML.|  
  
 Además de estos atributos, que se encuentran todos en el espacio de nombres <xref:System.Xml.Serialization> también se puede aplicar el atributo <xref:System.ComponentModel.DefaultValueAttribute> a un campo. **DefaultValueAttribute** establece el valor que se asignará automáticamente al miembro si no se especifica ningún valor.  
  
 Para controlar la serialización SOAP y XML codificada, vea [Atributos que controlan la serialización SOAP codificada](attributes-that-control-encoded-soap-serialization.md).  
  
## <a name="see-also"></a>Vea también

- [Serialización SOAP y XML](xml-and-soap-serialization.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Controlar la serialización XML mediante atributos](controlling-xml-serialization-using-attributes.md)
- [Cómo: Especificar un nombre de elemento alternativo para una secuencia XML](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)
- [Cómo: Serialización de un objeto](how-to-serialize-an-object.md)
- [Cómo: Deserialización de un objeto](how-to-deserialize-an-object.md)
