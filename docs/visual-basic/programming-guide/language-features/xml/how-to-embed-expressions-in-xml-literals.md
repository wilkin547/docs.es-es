---
description: 'Más información acerca de cómo: incrustar expresiones en literales XML (Visual Basic)'
title: Procedimiento para insertar expresiones en literales XML
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 18bc6164c4466532956f1a5df70c1ff2a8dbbfd5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100480055"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a>Cómo: Incrustar expresiones en literales XML (Visual Basic)

Puede combinar literales XML con expresiones incrustadas para crear un documento, fragmento o elemento XML que contenga contenido creado en tiempo de ejecución. En los siguientes ejemplos se muestra cómo utilizar expresiones incrustadas para rellenar el contenido de los elementos, los atributos y los nombres de elemento en tiempo de ejecución.  
  
 La sintaxis de una expresión incrustada es `<%=` `exp` `%>` , que es la misma sintaxis que utiliza ASP.net. Para obtener más información, vea [expresiones incrustadas en XML](embedded-expressions-in-xml.md).  
  
 También puede usar las [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] API para crear [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objetos. Para obtener más información, vea <xref:System.Xml.Linq.XElement>.  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-insert-text-as-element-content"></a>Para insertar texto como contenido de elemento  
  
- En el ejemplo siguiente se muestra cómo insertar el texto contenido en la `contactName` variable entre los elementos de nombre de apertura y de cierre.  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     Este ejemplo produce el siguiente resultado:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a>Para insertar texto como un valor de atributo  
  
- En el ejemplo siguiente se muestra cómo insertar el texto contenido en la `phoneType` variable como el valor del `type` atributo.  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     Este ejemplo produce el siguiente resultado:  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a>Para insertar texto para un nombre de elemento  
  
- En el ejemplo siguiente se muestra cómo insertar el texto contenido en la `elementName` variable como el nombre de un elemento.  
  
     Al crear elementos mediante esta técnica, debe cerrarlos con la \</> etiqueta.  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     Este ejemplo produce el siguiente resultado:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a>Vea también

- [Procedimiento para crear literales XML](how-to-create-xml-literals.md)
- [Expresiones insertadas en XML](embedded-expressions-in-xml.md)
- [Crear XML en Visual Basic](creating-xml.md)
- [XML](index.md)
