---
title: "C&#243;mo: Incrustar expresiones en literales XML (Visual Basic) | Microsoft Docs"
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
  - "expresiones incrustadas [Visual Basic]"
  - "literales XML [Visual Basic], expresiones incrustadas"
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# C&#243;mo: Incrustar expresiones en literales XML (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Puede combinar literales XML con expresiones incrustadas para crear un documento, fragmento o elemento XML que incluye el contenido creado en tiempo de ejecución.  En los ejemplos siguientes se muestra cómo usar las expresiones incrustadas para rellenar el contenido de elemento, atributos y nombres de elemento en tiempo de ejecución.  
  
 La sintaxis para una expresión incrustada es `<%=` `exp` `%>`, que es la misma sintaxis que usa [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)]. Para obtener más información, vea [Expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 También puede usar las API de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] para crear objetos de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)].  Para obtener más información, consulte <xref:System.Xml.Linq.XElement>.  
  
## Procedimientos  
  
#### Para insertar texto como contenido de elemento  
  
-   En el ejemplo siguiente se muestra cómo insertar el texto incluido en la variable `contactName` entre los elementos de nombre de apertura y cierre.  
  
     [!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     Este ejemplo produce el siguiente resultado.  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### Para insertar texto como un valor de atributo  
  
-   En el ejemplo siguiente se muestra cómo insertar el texto incluido en la variable `phoneType` como valor del atributo `type`.  
  
     [!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     Este ejemplo produce el siguiente resultado.  
  
    ```  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### Para insertar texto como nombre de elemento  
  
-   En el ejemplo siguiente se muestra cómo insertar el texto incluido en la variable `elementName` como el nombre de un elemento.  
  
     Al crear elementos mediante esta técnica, debe cerrarlos con la etiqueta \<\/\>.  
  
     [!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     Este ejemplo produce el siguiente resultado.  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## Vea también  
 [Cómo: Crear literales XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)   
 [Expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)