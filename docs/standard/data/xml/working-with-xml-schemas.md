---
title: Trabajo con esquemas XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: bbbcc70c-bf9a-4f6a-af72-1bab5384a187
ms.openlocfilehash: 0fd7313e800024ebb7e3563cb4323c5780cbf1c3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710016"
---
# <a name="working-with-xml-schemas"></a>Trabajo con esquemas XML
Para definir la estructura de un documento XML, así como las relaciones de sus elementos, tipos de datos y restricciones de contenido, se utiliza una definición de tipo de documento (DTD) o esquema del lenguaje de definición de esquemas (XSD). Aunque se considera que un documento XML es correcto si cumple todos los requisitos sintácticos que define la recomendación del Lenguaje de marcado extensible (XML) 1.0 del W3C (World Wide Web Consortium), no se considera válido a menos que sea correcto y además cumpla las restricciones que define su DTD o esquema. Por lo tanto, aunque todos los documentos XML válidos sean correctos, no todos los documentos XML correctos son válidos.  
  
 Para obtener más información acerca de XML, vea [XML 1.0 - W3C Recommendation](https://www.w3.org/TR/REC-xml/). Para obtener más información sobre el esquema XML, vea las recomendaciones de la [Parte 1 del esquema XML de W3C: recomendación de estructuras](https://www.w3.org/TR/xmlschema-1/) y la [Parte 2 del esquema XML de W3C: recomendación de tipos de datos](https://www.w3.org/TR/xmlschema-2/).  
  
## <a name="in-this-section"></a>En esta sección  
 [Modelo de objetos de esquema XML (SOM)](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)  
 Describe el Modelo de objetos de esquema (SOM) del espacio de nombres <xref:System.Xml.Schema?displayProperty=nameWithType> que incluye un conjunto de clases que le permiten leer un esquema del lenguaje de definición de esquemas (XSD) desde un archivo o crear un esquema en memoria mediante programación.  
  
 [XmlSchemaSet para compilación de esquemas](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 Describe la clase <xref:System.Xml.Schema.XmlSchemaSet> que es una caché en la que se pueden almacenar y validar esquemas XSD.  
  
 [Validación basada en inserción de XmlSchemaValidator](../../../../docs/standard/data/xml/xmlschemavalidator-push-based-validation.md)  
 Describe la clase <xref:System.Xml.Schema.XmlSchemaValidator> que incluye un mecanismo eficiente y de alto rendimiento para validar datos XML con esquemas XSD mediante inserción.  
  
 [Deducción de esquema XML](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)  
 Describe cómo utilizar la clase <xref:System.Xml.Schema.XmlSchemaInference> para deducir un esquema XSD de la estructura de un documento XML.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Validación de un documento XML en DOM](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
 Describe cómo validar el XML en el Modelo de objetos de documento (DOM). Puede validarlo a medida que se carga en el DOM o validar un documento XML no validado previamente en el DOM.  
  
 [Validación de esquemas con XPathNavigator](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)  
 Describe cómo validar el XML que se está editando y por el que se está navegando utilizando la clase <xref:System.Xml.XPath.XPathNavigator>.
