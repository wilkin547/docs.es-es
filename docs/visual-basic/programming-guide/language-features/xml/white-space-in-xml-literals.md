---
title: Espacio en blanco en literales XML (Visual Basic) | Documentos de Microsoft
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
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: 14
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
ms.openlocfilehash: b98a88696f24cc0b95401812471d13acea4faa6d
ms.lasthandoff: 03/13/2017

---
# <a name="white-space-in-xml-literals-visual-basic"></a>Espacio en blanco en literales XML (Visual Basic)
El [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador incorpora únicamente los caracteres de espacios en blanco significativos de un literal XML cuando crea un [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objeto. No se incorporan los caracteres de espacio en blanco no significativo.  
  
## <a name="significant-and-insignificant-white-space"></a>Espacio en blanco significativo y no significativo  
 Caracteres de espacio en blanco en literales XML son significativos únicamente en tres áreas:  
  
-   Cuando están en un valor de atributo.  
  
-   Cuando forman parte de un elemento contenido de texto y el texto también contiene otros caracteres.  
  
-   Cuando están en una expresión incrustada para el contenido de texto de un elemento.  
  
 De lo contrario, el compilador trata los caracteres de espacio en blanco como no significativos y no se incluye a continuación, en la [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objeto del literal.  
  
 Para incluir espacios en blanco insignificantes en un literal XML, use una expresión incrustada que contiene una cadena literal con el espacio en blanco.  
  
> [!NOTE]
>  Si el `xml:space` atributo aparece en un elemento XML literal, el [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador incluye el atributo en el <xref:System.Xml.Linq.XElement>objeto, pero agregar este atributo no cambia la forma en que el compilador trata los espacios en blanco.</xref:System.Xml.Linq.XElement>  
  
## <a name="examples"></a>Ejemplos  
 El ejemplo siguiente contiene dos elementos XML, externos e internos. Ambos elementos contienen espacio en blanco en su contenido de texto. El espacio en blanco en el elemento exterior es insignificante, ya que contiene solo espacios en blanco y un elemento XML. El espacio en blanco en el elemento interno es significativo porque contiene espacio en blanco y texto.  
  
 [!code-vb[VbXMLSamples&#29;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 Cuando se ejecuta, este código muestra el texto siguiente.  
  
```  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>Vea también  
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
