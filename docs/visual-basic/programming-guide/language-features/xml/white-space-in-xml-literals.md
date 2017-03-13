---
title: "Espacio en blanco en literales XML (Visual Basic) | Microsoft Docs"
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
  - "espacio en blanco [XML en Visual Basic]"
  - "literales XML [Visual Basic], espacio en blanco"
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Espacio en blanco en literales XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El compilador de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] incorpora únicamente los caracteres de espacio en blanco significativos de un literal XML cuando crea un objeto de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)].  No se incorporan los caracteres de espacio en blanco no significativos.  
  
## Espacio en blanco significativo y no significativo  
 Los caracteres de espacio en blanco en literales XML son significativos únicamente en tres áreas:  
  
-   Cuando están en un valor de atributo.  
  
-   Cuando forman parte del contenido de texto de un elemento y el texto también contiene otros caracteres.  
  
-   Cuando están en una expresión incrustada para el contenido de texto de un elemento.  
  
 De lo contrario, el compilador considera los caracteres de espacio en blanco como no significativos y no los incluye en el objeto de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] del literal.  
  
 Para incluir un espacio en blanco no significativo en un literal XML, use una expresión incrustada que contenga un literal de cadena con el espacio en blanco.  
  
> [!NOTE]
>  Si el atributo `xml:space` aparece en un literal de elemento XML, el compilador de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] lo incluye en el objeto <xref:System.Xml.Linq.XElement> pero, al agregar este atributo, no cambia la forma en que el compilador trata el espacio en blanco.  
  
## Ejemplos  
 El ejemplo siguiente contiene dos elementos XML, uno externo y otro interno.  Ambos elementos contienen espacio en blanco en su contenido de texto.  El espacio en blanco en el elemento externo es no significativo porque únicamente contiene espacio en blanco y un elemento XML.  El espacio en blanco en el elemento interno es significativo porque contiene espacio en blanco y texto.  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 Cuando se ejecuta, este código muestra el siguiente texto.  
  
```  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## Vea también  
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)