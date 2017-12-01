---
title: Trabajo con esquemas XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbbcc70c-bf9a-4f6a-af72-1bab5384a187
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e21d402dce02ecb332d041f0cda651df911979ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="working-with-xml-schemas"></a>Trabajo con esquemas XML
Para definir la estructura de un documento XML, así como las relaciones de sus elementos, tipos de datos y restricciones de contenido, se utiliza una definición de tipo de documento (DTD) o esquema del lenguaje de definición de esquemas (XSD). Aunque se considera que un documento XML es correcto si cumple todos los requisitos sintácticos que define la recomendación del Lenguaje de marcado extensible (XML) 1.0 del W3C (World Wide Web Consortium), no se considera válido a menos que sea correcto y además cumpla las restricciones que define su DTD o esquema. Por lo tanto, aunque todos los documentos XML válidos sean correctos, no todos los documentos XML correctos son válidos.  
  
 Para obtener más información acerca de XML, vea el [recomendación XML 1.0 del W3C](http://go.microsoft.com/fwlink/?linkid=7269). Para obtener más información sobre el esquema XML, vea el [W3C XML Schema Part 1: recomendación de estructuras](http://go.microsoft.com/fwlink/?linkid=48881) y [W3C XML Schema Part 2: Datatypes Recommendation](http://go.microsoft.com/fwlink/?linkid=17392) recomendaciones.  
  
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
 [Validación de un documento XML en el DOM](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
 Describe cómo validar el XML en el Modelo de objetos de documento (DOM). Puede validarlo a medida que se carga en el DOM o validar un documento XML no validado previamente en el DOM.  
  
 [Validación de esquemas con XPathNavigator](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)  
 Describe cómo validar el XML que se está editando y por el que se está navegando utilizando la clase <xref:System.Xml.XPath.XPathNavigator>.
