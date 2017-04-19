---
title: "Construcción funcional (LINQ to XML) (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: feac4273-39ab-43ae-bab7-4059c807a785
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9fa8cb3c97a1e23a863296c828c82b240e9ab5db
ms.lasthandoff: 03/13/2017

---
# <a name="functional-construction-linq-to-xml-visual-basic"></a>Construcción funcional (LINQ to XML) (Visual Basic)
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]Proporciona una manera eficaz de crear elementos XML denominados *construcción funcional*. La construcción funcional es la capacidad de crear un árbol XML en una sola instrucción.  
  
 Hay varias características fundamentales de la interfaz de programación de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] que permiten la construcción funcional:  
  
-   El <xref:System.Xml.Linq.XElement>constructor toma varios tipos de argumentos para el contenido.</xref:System.Xml.Linq.XElement> Por ejemplo, puede pasar otro <xref:System.Xml.Linq.XElement>objeto, que se convierte en un elemento secundario.</xref:System.Xml.Linq.XElement> Puede pasar un <xref:System.Xml.Linq.XAttribute>objeto, que se convierte en un atributo del elemento.</xref:System.Xml.Linq.XAttribute> O bien, puede pasar cualquier otro tipo de objeto, que se convierte en una cadena y en el contenido de texto del elemento.  
  
-   El <xref:System.Xml.Linq.XElement>constructor toma un `params` matriz de tipo <xref:System.Object>, por lo que puede pasar cualquier número de objetos al constructor.</xref:System.Object> </xref:System.Xml.Linq.XElement> Esto permite crear un elemento que tiene un contenido complejo.  
  
-   Si un objeto implementa <xref:System.Collections.Generic.IEnumerable%601>, se enumera la colección en el objeto y se agregan todos los elementos de la colección.</xref:System.Collections.Generic.IEnumerable%601> Si la colección contiene <xref:System.Xml.Linq.XElement>o <xref:System.Xml.Linq.XAttribute>objetos, cada elemento de la colección se agrega por separado.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> Esto es importante porque permite pasar los resultados de una [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] consulta al constructor.  
  
 A continuación se muestra un ejemplo:  
  
 Estas características permiten escribir código mediante literales XML para crear un árbol XML y también escribir código que utiliza los resultados de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] las consultas cuando se crea un árbol XML:  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where CInt(el) > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="see-also"></a>Vea también  
 [Crear árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
