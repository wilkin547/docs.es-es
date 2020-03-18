---
title: Transformación funcional de XML (C#)
ms.date: 07/20/2015
ms.assetid: 0ccb9251-38d7-44e3-9b84-1b5fe25e4b59
ms.openlocfilehash: 83ecd97f9319027dc50f346abf7a9888b5c23862
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75336794"
---
# <a name="functional-transformation-of-xml-c"></a>Transformación funcional de XML (C#)
Este tema trata acerca de la aproximación enfocada a la transformación funcional pura para modificar documentos XML, comparándola con la aproximación basada en procedimientos.  
  
## <a name="modifying-an-xml-document"></a>Modificar un documento XML  
 Una de las tareas más comunes que deben llevar a cabo los programadores de XML es la de transformar XML de una forma a otra. La forma de un documento XML es la estructura del documento, que incluye lo siguiente:  
  
- La jerarquía expresada por el documento.  
  
- Los nombres de elementos y atributos.  
  
- Los tipos de datos de los elementos y atributos.  
  
 En general, la aproximación que resulta más efectiva a la hora de transformar un XML de una forma a otra, es realizar una transformación funcional pura. De esta forma, la principal tarea del programador es crear una transformación que se aplique a todo el documento XML (o a uno o más nodos estrictamente definidos). Se puede argüir que la transformación funcional es la más sencilla de programar (siempre y cuando el programador esté familiarizado con esta técnica), que genera un código muy fácil de mantener y que, a menudo, es una alternativa más compacta que las otras.  
  
### <a name="xml-functional-transformational-technologies"></a>Tecnologías de transformación funcional de XML  
 Microsoft ofrece dos tecnologías de transformación funcional que se pueden usar con documentos XML: XSLT y LINQ to XML. XSLT se proporciona a través del espacio de nombres administrado <xref:System.Xml.Xsl> y de la implementación nativa COM de MSXML. Aunque XSLT es una tecnología robusta para manipular documentos XML, requiere experiencia en un campo muy especializado, el lenguaje XSLT y sus API de apoyo.  
  
 LINQ to XML proporciona las herramientas necesarias para programar potentes transformaciones funcionales puras mediante expresiones, utilizando código C# o Visual Basic. Por ejemplo, muchos de los ejemplos incluidos en la documentación de LINQ to XML utilizan una aproximación funcional pura. Además, en el [Tutorial: Manipulación de contenido en un documento WordprocessingML (C#)](./shape-of-wordprocessingml-documents.md), se usa LINQ to XML con un enfoque funcional para manipular la información de un documento de Microsoft Word.  
  
 Para obtener una comparación más completa entre LINQ to XML y otras tecnologías XML de Microsoft, vea [LINQ to XML frente a otras tecnologías XML](./linq-to-xml-vs-other-xml-technologies.md).  
  
XSLT es una herramienta recomendada para transformaciones basadas en el documento, cuando el origen de éste tiene una estructura irregular. No obstante, LINQ to XML también puede realizar transformaciones basadas en el documento. Para más información, consulte [Procedimiento para usar anotaciones para transformar árboles LINQ to XML en un estilo XSLT (C#)](./how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style.md).
  
## <a name="see-also"></a>Vea también

- [Introducción a las transformaciones funcionales puras (C#)](./introduction-to-pure-functional-transformations.md)
- [Tutorial: Manipulación de contenido en un documento WordprocessingML (C#)](./shape-of-wordprocessingml-documents.md)
- [LINQ to XML frente a otras tecnologías XML](./linq-to-xml-vs-other-xml-technologies.md)
