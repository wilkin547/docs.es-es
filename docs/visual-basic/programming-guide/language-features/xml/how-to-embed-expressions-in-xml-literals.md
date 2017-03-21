---
title: "Cómo: Incrustar expresiones en literales XML (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 40b0e4273223093262bc54a2b13d28fc93a44c69
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a>Cómo: Incrustar expresiones en literales XML (Visual Basic)
Puede combinar los literales XML con expresiones incrustadas para crear un documento XML, fragmento o elemento que incluye contenido creado en tiempo de ejecución. Los ejemplos siguientes muestran cómo utilizar expresiones incrustadas para rellenar el contenido de los elementos, atributos y nombres de elemento en tiempo de ejecución.  
  
 La sintaxis de una expresión incrustada es `<%=` `exp` `%>`, que es la misma sintaxis que [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] utiliza. Para obtener más información, consulte [expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 También puede utilizar el [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] API para crear [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objetos. Para obtener más información, consulte <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement>  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-insert-text-as-element-content"></a>Para insertar texto como contenido del elemento  
  
-   En el ejemplo siguiente se muestra cómo insertar el texto que se encuentra en la `contactName` variable entre los elementos de nombre de apertura y cierre.  
  
     [!code-vb[VbXMLSamples&#39;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     Este ejemplo produce el siguiente resultado:  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a>Para insertar texto como un valor de atributo  
  
-   En el ejemplo siguiente se muestra cómo insertar el texto que se encuentra en la `phoneType` variable como el valor de la `type` atributo.  
  
     [!code-vb[VbXMLSamples Nº&40;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     Este ejemplo produce el siguiente resultado:  
  
    ```  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a>Para insertar texto para un nombre de elemento  
  
-   En el ejemplo siguiente se muestra cómo insertar el texto que se encuentra en la `elementName` variable como el nombre de un elemento.  
  
     Al crear elementos mediante esta técnica, debe cerrarlos con la \</ > etiqueta.  
  
     [!code-vb[VbXMLSamples nº&41;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     Este ejemplo produce el siguiente resultado:  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Cómo: crear literales XML](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)   
 [Expresiones incrustadas en XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
