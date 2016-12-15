---
title: "Literales XML y la especificaci&#243;n XML 1.0 (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "literales XML [Visual Basic], especificación XML 1.0"
ms.assetid: 46f046e5-293c-41a3-b893-4e5f6e32e78a
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Literales XML y la especificaci&#243;n XML 1.0 (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

La sintaxis de los literales XML en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] admite la mayor parte de la especificación de XML 1.0 \(Lenguaje de marcado extensible\).  Para obtener información detallada sobre la especificación XML 1.0, vea [Extensible Markup Language \(XML\) 1.0](http://go.microsoft.com/fwlink/?LinkId=73927) en el sitio web de W3C.  
  
## Lo que Visual Basic no admite  
  
-   Un literal XML no puede contener una definición de tipo de documento \(DTD\).  
  
-   Un literal de documento XML debe iniciarse con una declaración de documento XML.  
  
-   Un literal XML no puede contener más de 65.535 caracteres en una línea.  
  
-   Los prefijos de espacio de nombres XML, nombres de elemento XML y nombres de atributo XML no pueden contener más de 1.024 caracteres.  
  
## Características adicionales que Visual Basic admite  
  
-   La sintaxis de expresiones incrustadas que se permite en los literales de documento y elemento no es XML válido.  
  
## Vea también  
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Literal de documento XML](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [Literal de elemento XML](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)