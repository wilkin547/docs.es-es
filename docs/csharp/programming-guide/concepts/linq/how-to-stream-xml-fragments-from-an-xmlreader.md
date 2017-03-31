---
title: "Cómo: Hacer streaming de fragmentos XML desde un objeto XmlReader (C#) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 4a8f0e45-768a-42e2-bc5f-68bdf0e0a726
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4bb11e120a123b701e45916b983032797c0ea8b6
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-c"></a>Cómo: Hacer streaming de fragmentos XML desde un objeto XmlReader (C#)
Cuando deba procesar archivos XML grandes quizás no sea factible cargar la totalidad del árbol XML en memoria. En este tema se muestra cómo hacer streaming de fragmentos mediante un objeto <xref:System.Xml.XmlReader>.  
  
 Una de las formas más efectivas de usar <xref:System.Xml.XmlReader> para leer objetos <xref:System.Xml.Linq.XElement> consiste en escribir su propio método de eje personalizado. Un método de eje suele devolver una colección como <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement>, como se muestra en el ejemplo de este tema. En el método de eje personalizado, tras crear el fragmento XML llamando al método <xref:System.Xml.Linq.XNode.ReadFrom%2A>, devuelva la colección usando `yield return`. Esto proporciona semántica de ejecución aplazada al método de eje personalizado.  
  
 Cuando se crea un árbol XML desde un objeto <xref:System.Xml.XmlReader>, el objeto <xref:System.Xml.XmlReader> debe estar posicionado en un elemento. El método <xref:System.Xml.Linq.XNode.ReadFrom%2A> no vuelve hasta que lee la etiqueta de cierre del elemento.  
  
 Si quiere crear un árbol parcial, puede crear instancias de <xref:System.Xml.XmlReader>, situar el lector en el nodo que quiere convertir en un árbol de <xref:System.Xml.Linq.XElement> y, después, crear el objeto <xref:System.Xml.Linq.XElement>.  
  
 El tema [Cómo: Hacer streaming de fragmentos XML con acceso a la información del encabezado (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) contiene información y un ejemplo sobre cómo hacer streaming de un documento más complejo.  
  
 El tema [Cómo: Realizar una transformación de streaming de documentos XML grandes (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) contiene un ejemplo del uso de LINQ to XML para transformar documentos XML extremadamente grandes manteniendo una superficie de memoria pequeña.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo crea un método de eje personalizado. Puede consultarlo usando una consulta de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]. El método de eje personalizado, `StreamRootChildDoc`, es un método que está específicamente diseñado para leer un documento que tiene un elemento `Child` que se repite.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Este ejemplo produce el siguiente resultado:  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 En este ejemplo el documento de origen es muy pequeño. No obstante, aunque hubiera millones de elementos `Child`, este ejemplo seguiría teniendo una superficie de memoria pequeña.  
  
## <a name="see-also"></a>Vea también  
 [Analizar XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
