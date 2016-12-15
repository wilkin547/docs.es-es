---
title: "C&#243;mo: Obtener acceso a elementos secundarios XML (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "propiedad de eje para elementos secundarios [Visual Basic]"
  - "XML [Visual Basic], obtener acceso"
  - "eje XML [Visual Basic], secundarios"
  - "propiedad de eje para elementos XML secundarios [Visual Basic]"
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Obtener acceso a elementos secundarios XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

En este ejemplo se muestra cómo usar una propiedad de eje secundario para obtener acceso a todos los elementos secundarios XML que tienen el nombre especificado en un elemento XML.  Concretamente, se usa la propiedad <xref:System.Xml.Linq.XElement.Value%2A> para obtener el valor del primer elemento en la colección que la propiedad de eje secundario `name` devuelve.  La propiedad de eje secundario `name` obtiene todos los elementos secundarios denominados `phone` en el objeto `contact`.  En este ejemplo se usa también la propiedad de eje secundario `phone` para obtener acceso a todos los elementos secundarios denominados `phone` que se incluyen en el objeto `contact`.  
  
## Ejemplo  
 [!code-vb[VbXMLSamples#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-child-elements_1.vb)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una referencia al espacio de nombres <xref:System.Xml.Linq>.  
  
## Vea también  
 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>   
 [Propiedades de eje secundario XML](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)   
 [Propiedad Value de XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)   
 [Obtener acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)