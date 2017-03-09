---
title: "Obtener acceso a XML en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "obtener acceso a XML [Visual Basic], propiedades de eje"
  - "LINQ to XML [Visual Basic], obtener acceso a XML"
  - "código de Visual Basic, XML"
  - "XML [Visual Basic], obtener acceso"
  - "XML [Visual Basic], propiedades de eje"
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Obtener acceso a XML en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] proporciona propiedades de eje XML para obtener acceso y navegar por las estructuras de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)].  Estas propiedades usan una sintaxis especial que permite obtener acceso a los elementos y atributos especificando los nombres XML.  
  
 En la siguiente tabla se enumeran las características del lenguaje que permiten obtener acceso a los elementos y atributos XML en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
### Propiedades de eje XML  
  
|Descripción de la propiedad|Ejemplo|Descripción|  
|---------------------------------|-------------|-----------------|  
|*eje secundario*|`contact.<phone>`|Obtiene todos los elementos `phone` que son elementos secundarios del elemento `contact`.|  
|*eje de atributo*|`phone.@type`|Obtiene todos los atributos `type` del elemento `phone`.|  
|*eje descendiente*|`contacts...<name>`|Obtiene todos los elementos `name` del elemento `contacts`, sin tener en cuenta lo profundo que se encuentren dentro de la jerarquía.|  
|*indizador de extensión*|`contacts...<name>(0)`|Obtiene el primer elemento `name` de la secuencia.|  
|*value*|`contacts...<name>.Value`|Obtiene la representación de cadena del primer objeto en la secuencia, o bien, `Nothing` si la secuencia está vacía.|  
  
## En esta sección  
 [Cómo: Obtener acceso a elementos descendientes XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 Muestra cómo usar una propiedad de eje descendiente para obtener acceso a todos los elementos XML que tienen el nombre especificado y están incluidos en el elemento XML especificado.  
  
 [Cómo: Obtener acceso a elementos secundarios XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 Muestra cómo usar una propiedad de eje secundario para obtener acceso a todos los elementos secundarios XML que tienen el nombre especificado en un elemento XML.  
  
 [Cómo: Obtener acceso a atributos XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 Muestra cómo usar una propiedad de eje de atributo para obtener acceso a todos los atributos XML que tiene el nombre especificado en un elemento XML.  
  
 [Cómo: Declarar y usar prefijos de espacio de nombres XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 Muestra cómo declarar un prefijo de espacio de nombres XML y usarlo para crear y obtener acceso a elementos XML.  
  
## Secciones relacionadas  
 [Propiedades de eje XML](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 Proporciona vínculos a secciones en las que se describen las diversas propiedades de acceso a XML.  
  
 [Información general sobre LINQ to XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 Proporciona una introducción al uso de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] en Visual Basic.  
  
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Proporciona una introducción al uso de literales XML en Visual Basic.  
  
 [Manipular XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 Proporciona vínculos a secciones con información sobre cómo cargar y modificar XML en Visual Basic.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 Proporciona vínculos a secciones en las que se describe cómo usar [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] en Visual Basic.