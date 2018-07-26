---
title: Espacio en blanco en literales XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 60ee90c69aeda38f95107a6043801a4994972079
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245164"
---
# <a name="white-space-in-xml-literals-visual-basic"></a>Espacio en blanco en literales XML (Visual Basic)
El compilador de Visual Basic incorpore solo los caracteres de espacio en blanco significativo de un literal XML cuando crea un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto. No se incorporan los caracteres de espacios en blanco insignificantes.  
  
## <a name="significant-and-insignificant-white-space"></a>Espacio en blanco significativo y no significativo  
 Caracteres de espacio en blanco en literales XML son significativos en sólo tres áreas:  
  
-   Cuando se encuentran en un valor de atributo.  
  
-   Cuando forman parte de un elemento contenido de texto y el texto también contiene otros caracteres.  
  
-   Cuando se encuentran en una expresión incrustada para el contenido de texto de un elemento.  
  
 En caso contrario, el compilador trata los caracteres de espacio en blanco como insignificantes y no se incluye a continuación, en el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto para el literal.  
  
 Para incluir espacios en blanco insignificantes en un literal XML, use una expresión incrustada que contiene una cadena literal con el espacio en blanco.  
  
> [!NOTE]
>  Si el `xml:space` atributo aparece en un literal de elemento XML, el compilador de Visual Basic incluye el atributo en el <xref:System.Xml.Linq.XElement> objeto, pero agregar este atributo no cambia el modo en que el compilador trata los espacios en blanco.  
  
## <a name="examples"></a>Ejemplos  
 En el siguiente ejemplo contiene dos elementos XML, externos e internos. Ambos elementos contienen espacios en blanco en su contenido de texto. El espacio en blanco en el elemento exterior es insignificante, ya que contiene solo espacios en blanco y un elemento XML. El espacio en blanco en el elemento interno es significativo porque contiene espacios en blanco y texto.  
  
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
