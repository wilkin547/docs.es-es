---
title: Espacio en blanco en literales XML (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6d23aa54b150748aac9aa955f4bd86ee88358ea
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="white-space-in-xml-literals-visual-basic"></a>Espacio en blanco en literales XML (Visual Basic)
El compilador de Visual Basic incorpora sólo los caracteres de espacio en blanco significativo de un literal XML cuando crea un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto. No se incorporan los caracteres de espacio en blanco no significativos.  
  
## <a name="significant-and-insignificant-white-space"></a>Espacio en blanco significativo y  
 Caracteres de espacio en blanco en literales XML son significativos únicamente en tres áreas:  
  
-   Cuando se encuentran en un valor de atributo.  
  
-   Cuando forman parte de un elemento contenido de texto y el texto también contiene otros caracteres.  
  
-   Cuando se encuentran en una expresión incrustada para el contenido de texto de un elemento.  
  
 En caso contrario, el compilador trata los caracteres de espacio en blanco como no significativos y no se incluye a continuación, en la [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto para el literal.  
  
 Para incluir espacios en blanco no significativos de un literal XML, use una expresión incrustada que contiene una cadena literal con el espacio en blanco.  
  
> [!NOTE]
>  Si el `xml:space` atributo aparece en un literal de elemento XML, el compilador de Visual Basic incluye el atributo en el <xref:System.Xml.Linq.XElement> objeto, pero agregar este atributo no cambia la forma en que el compilador trata el espacio en blanco.  
  
## <a name="examples"></a>Ejemplos  
 El ejemplo siguiente contiene dos elementos XML, externos e internos. Ambos elementos contienen espacios en blanco en su contenido de texto. El espacio en blanco en el elemento exterior es insignificante porque contiene solo espacios en blanco y un elemento XML. El espacio en blanco en el elemento interno es significativo porque contiene espacios en blanco y texto.  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 Cuando se ejecuta, este código muestra el texto siguiente.  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>Vea también  
 [Crear XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
