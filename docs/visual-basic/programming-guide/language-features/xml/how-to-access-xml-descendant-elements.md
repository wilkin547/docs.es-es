---
title: "C&#243;mo: Obtener acceso a elementos descendientes XML (Visual Basic) | Microsoft Docs"
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
  - "propiedad de eje para elementos descendientes [Visual Basic]"
  - "XML [Visual Basic], obtener acceso"
  - "eje XML [Visual Basic], descendiente"
  - "propiedad de eje para elementos XML descendientes [Visual Basic]"
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# C&#243;mo: Obtener acceso a elementos descendientes XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En este ejemplo se muestra cómo usar una propiedad de eje descendiente para obtener acceso a todos los elementos XML que tienen el nombre especificado y están incluidos en un elemento XML.  Concretamente, se usa la propiedad `Value` para obtener el valor del primer elemento en la colección que la propiedad de eje descendiente `name` devuelve.  La propiedad de eje descendiente `name` obtiene todos los elementos denominados `name` que se incluyen en el objeto `contacts`.  En este ejemplo también se usa la propiedad de eje descendiente `phone` para obtener acceso a todos los descendientes denominados `phone` que se incluyen en el objeto `contacts`.  
  
## Ejemplo  
 [!code-vb[VbXMLSamples#31](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-access-xml-descen_1.vb)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una referencia al espacio de nombres <xref:System.Xml.Linq>.  
  
## Vea también  
 <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName>   
 [Propiedad de eje descendiente XML](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)   
 [Propiedad Value de XML](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)   
 [Obtener acceso a XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)