---
title: Atributos que controlan la serialización SOAP codificada
description: En este artículo se muestra un conjunto especial de atributos que se encuentran en el espacio de nombres System.Xml.Serialization necesario para ajustarse a la especificación SOAP.
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- serialization, attributes
ms.assetid: 93ee258c-9c0f-4a08-897c-c10db7a00f91
ms.openlocfilehash: d9a4631189d348c02ab36054257a54c9c4673018
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289673"
---
# <a name="attributes-that-control-encoded-soap-serialization"></a>Atributos que controlan la serialización SOAP codificada

El documento de World Wide Web Consortium (W3C) denominado [Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/) contiene una sección opcional (sección 5) que describe cómo se pueden codificar los parámetros SOAP. Para ajustarse a la sección 5 de la especificación, debe usar un conjunto especial de atributos que se encuentra en el espacio de nombres <xref:System.Xml.Serialization>. Aplique según corresponda esos atributos a las clases y miembros de clases y, a continuación, utilice <xref:System.Xml.Serialization.XmlSerializer> para serializar instancias de la clase o clases.

La tabla siguiente muestra los atributos, donde se pueden aplicar, y lo que hacen. Para más información sobre el uso de estos atributos para controlar la serialización de XML, consulte [Cómo: Serializar un objeto como secuencia XML con codificación SOAP](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md) y [Cómo: Invalidar la serialización XML SOAP codificada](how-to-override-encoded-soap-xml-serialization.md).

Para obtener más información sobre atributos, vea [Atributos](../attributes/index.md).

|Atributo|Se aplica a|Especifica|
|---------------|----------------|---------------|
|<xref:System.Xml.Serialization.SoapAttributeAttribute>|Campo público, propiedad, parámetro o valor devuelto.|El miembro de clase se serializará como un atributo XML.|
|<xref:System.Xml.Serialization.SoapElementAttribute>|Campo público, propiedad, parámetro o valor devuelto.|La clase se serializará como un elemento XML.|
|<xref:System.Xml.Serialization.SoapEnumAttribute>|Campo público que es un identificador de enumeración.|Nombre de elemento del miembro de una enumeración.|
|<xref:System.Xml.Serialization.SoapIgnoreAttribute>|Propiedades públicas y campos.|Se debería omitir la propiedad o campo cuando se serializa la clase contenedora.|
|<xref:System.Xml.Serialization.SoapIncludeAttribute>|Declaraciones de clase derivada públicas y métodos públicos para los documentos de lenguaje de descripción de servicios Web (WSDL).|El tipo debería estar incluido al generar los esquemas (para ser reconocido cuando se serializa).|
|<xref:System.Xml.Serialization.SoapTypeAttribute>|Declaraciones de clase públicas.|La clase se debería serializar como un tipo de XML.|

## <a name="see-also"></a>Vea también

- [Serialización SOAP y XML](xml-and-soap-serialization.md)
- [Cómo: Serializar un objeto como secuencia XML con codificación SOAP](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)
- [Cómo: Invalidar la serialización XML SOAP codificada](how-to-override-encoded-soap-xml-serialization.md)
- [Atributos](../attributes/index.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Cómo: Serialización de un objeto](how-to-serialize-an-object.md)
- [Cómo: Deserialización de un objeto](how-to-deserialize-an-object.md)
