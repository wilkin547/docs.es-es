---
title: "Cómo: transmitir por secuencias fragmentos XML de XmlReader (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: f67ce598-4a12-4dcb-9a07-24deca02a111
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c9c60bb4730ef6569390f76f63c40a2cbd1c9524
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-visual-basic"></a>Cómo: transmitir por secuencias fragmentos XML de XmlReader (Visual Basic)
Cuando deba procesar archivos XML grandes quizás no sea factible cargar la totalidad del árbol XML en memoria. Este tema muestra cómo transmitir por secuencias fragmentos usando un <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader>  
  
 Una de las formas más efectivas de usar un <xref:System.Xml.XmlReader>leer <xref:System.Xml.Linq.XElement>objetos es escribir su propio método de eje personalizado.</xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader> Un método de eje suele devolver una recopilación como <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XElement>, como se muestra en el ejemplo de este tema.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> En el método de eje personalizado, tras crear el fragmento XML llamando el <xref:System.Xml.Linq.XNode.ReadFrom%2A>método, devuelva la recopilación usando `yield return`.</xref:System.Xml.Linq.XNode.ReadFrom%2A> Esto proporciona semántica de ejecución aplazada al método de eje personalizado.  
  
 Cuando se crea un árbol XML desde un <xref:System.Xml.XmlReader>objeto, el <xref:System.Xml.XmlReader>debe estar posicionado en un elemento.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> El <xref:System.Xml.Linq.XNode.ReadFrom%2A>método no devuelve hasta que ha leído la etiqueta de cierre del elemento.</xref:System.Xml.Linq.XNode.ReadFrom%2A>  
  
 Si desea crear un árbol parcial, puede crear instancias de un <xref:System.Xml.XmlReader>, sitúe el lector en el nodo que desea convertir en un <xref:System.Xml.Linq.XElement>de árbol y, a continuación, cree la <xref:System.Xml.Linq.XElement>objeto.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader>  
  
 El tema [Cómo: transmitir por secuencias fragmentos de XML con acceso a la información de encabezado (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) contiene información y un ejemplo sobre cómo transmitir un documento más complejo.  
  
 El tema [Cómo: realizar Streaming transformación de documentos XML grandes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) contiene un ejemplo del uso de LINQ to XML para transformar documentos XML extremadamente grandes manteniendo una superficie de memoria pequeña.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo crea un método de eje personalizado. Puede consultarlo usando una consulta de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]. El método de eje personalizado, `StreamRootChildDoc`, es un método que está específicamente diseñado para leer un documento que tiene un elemento `Child` que se repite.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Este ejemplo produce el siguiente resultado:  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 En este ejemplo el documento de origen es muy pequeño. No obstante, aunque hubiera millones de elementos `Child`, este ejemplo seguiría teniendo una superficie de memoria pequeña.  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Implementar IEnumerable(Of T) en Visual Basic](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md)   
 [Analizar XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
