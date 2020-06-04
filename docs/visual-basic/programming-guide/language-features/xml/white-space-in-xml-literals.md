---
title: Espacio en blanco en literales XML
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: b3caf7ac052f3fed3fe5427da0cc96bbdd955ea6
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360480"
---
# <a name="white-space-in-xml-literals-visual-basic"></a>Espacio en blanco en literales XML (Visual Basic)
El compilador de Visual Basic incorpora solo los caracteres de espacio en blanco significativos de un literal XML cuando crea un [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto. No se incorporan los caracteres de espacio en blanco insignificantes.  
  
## <a name="significant-and-insignificant-white-space"></a>Espacio en blanco significativo e insignificante  
 Los caracteres de espacio en blanco de los literales XML solo son significativos en tres áreas:  
  
- Cuando se encuentran en un valor de atributo.  
  
- Cuando forman parte del contenido de texto de un elemento y el texto también contiene otros caracteres.  
  
- Cuando están en una expresión incrustada para el contenido de texto de un elemento.  
  
 De lo contrario, el compilador trata los caracteres de espacio en blanco como insignificantes y no incluye en el [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objeto para el literal.  
  
 Para incluir un espacio en blanco insignificante en un literal XML, use una expresión incrustada que contenga un literal de cadena con el espacio en blanco.  
  
> [!NOTE]
> Si el `xml:space` atributo aparece en un literal de elemento XML, el compilador Visual Basic incluye el atributo en el <xref:System.Xml.Linq.XElement> objeto, pero al agregar este atributo no se cambia el modo en que el compilador trata los espacios en blanco.  
  
## <a name="examples"></a>Ejemplos  
 El ejemplo siguiente contiene dos elementos XML, Outer e Inner. Ambos elementos contienen espacios en blanco en el contenido de texto. El espacio en blanco del elemento exterior es insignificante porque solo contiene espacios en blanco y un elemento XML. El espacio en blanco del elemento interno es significativo porque contiene un espacio en blanco y texto.  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 Cuando se ejecuta, este código muestra el texto siguiente.  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>Consulte también

- [Crear XML en Visual Basic](creating-xml.md)
