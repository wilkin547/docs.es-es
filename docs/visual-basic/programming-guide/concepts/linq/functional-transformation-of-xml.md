---
title: "Transformación funcional de XML (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: fdbe5b91-f457-4b4e-a11b-def4bdd77bab
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a188ad5182b757a798f7f29414536ba2d1a88c2b
ms.lasthandoff: 03/13/2017


---
# <a name="functional-transformation-of-xml-visual-basic"></a>Transformación funcional de XML (Visual Basic)
Este tema trata acerca de la aproximación enfocada a la transformación funcional pura para modificar documentos XML, comparándola con la aproximación basada en procedimientos.  
  
## <a name="modifying-an-xml-document"></a>Modificar un documento XML  
 Una de las tareas más comunes que deben llevar a cabo los programadores de XML es la de transformar XML de una forma a otra. La forma de un documento XML es la estructura del documento, que incluye lo siguiente:  
  
-   La jerarquía expresada por el documento.  
  
-   Los nombres de elementos y atributos.  
  
-   Los tipos de datos de los elementos y atributos.  
  
 En general, la aproximación que resulta más efectiva a la hora de transformar un XML de una forma a otra, es realizar una transformación funcional pura. De esta forma, la principal tarea del programador es crear una transformación que se aplique a todo el documento XML (o a uno o más nodos estrictamente definidos). Se puede argüir que la transformación funcional es la más sencilla de programar (siempre y cuando el programador esté familiarizado con esta técnica), que genera un código muy fácil de mantener y que, a menudo, es una alternativa más compacta que las otras.  
  
### <a name="xml-functional-transformational-technologies"></a>Tecnologías de transformación funcional de XML  
 Microsoft ofrece dos tecnologías de transformación funcional que pueden utilizarse con documentos XML: XSLT y LINQ to XML. XSLT es compatible con la <xref:System.Xml.Xsl>espacio de nombres administrado y en la implementación nativa COM de MSXML.</xref:System.Xml.Xsl> Aunque XSLT es una tecnología robusta para manipular documentos XML, requiere experiencia en un campo muy especializado, el lenguaje XSLT y sus API de apoyo.  
  
 LINQ to XML proporciona las herramientas necesarias para programar potentes transformaciones funcionales puras mediante expresiones, utilizando código C# o Visual Basic. Por ejemplo, muchos de los ejemplos incluidos en la documentación de LINQ to XML utilizan una aproximación funcional pura. Además, en la [Tutorial: manipular contenido en un documento WordprocessingML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial, utilizamos LINQ to XML en un enfoque funcional para manipular información en un documento de Microsoft Word.  
  
 Para una comparación más exhaustiva entre LINQ to XML con otras tecnologías XML de Microsoft, consulte [LINQ to XML frente a. Otras tecnologías XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md).  
  
 XSLT es una herramienta recomendada para transformaciones basadas en el documento, cuando el origen de éste tiene una estructura irregular. No obstante, LINQ to XML también puede realizar transformaciones basadas en el documento. Para obtener más información, consulte [Cómo: usar anotaciones para transformar árboles LINQ to XML en un estilo XSLT (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-use-annotation-trees-to-transform-linq-to-xml-trees-in-an-xslt-style.md).  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las transformaciones funcionales puras (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)   
 [LINQ to XML frente a Otras tecnologías XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md)   
 [LINQ to XML frente a otras tecnologías XML](http://msdn.microsoft.com/library/7ba1eecf-f09a-42de-bc80-22ca5b2e42d3)
