---
title: Rendimiento de consultas encadenadas (LINQ to XML) (Visual Basic) | Documentos de Microsoft
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
ms.assetid: 589f2adc-69f9-404d-b9d6-4c28dabea7f7
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dd5b63f255107c5864108cfbb87bef6e53a971a0
ms.lasthandoff: 03/13/2017


---
# <a name="performance-of-chained-queries-linq-to-xml-visual-basic"></a>Rendimiento de consultas encadenadas (LINQ to XML) (Visual Basic)
Una de las ventajas más importantes de LINQ (y LINQ to XML) es que las consultas encadenadas funcionan igual de bien que una sola consulta más grande y complicada.  
  
 Una consulta encadenada es una consulta que usa otra consulta como su origen. Por ejemplo, en el siguiente código simple, `query2` es el origen de `query1`:  
  
```vb  
Dim root As New XElement("Root", New XElement("Child", 1), New XElement("Child", 2), New XElement("Child", 3), New XElement("Child", 4))  
  
Dim query1 = From x In root.Elements("Child") Where CInt(x) >= 3x  
  
Dim query2 = From e In query1 Where CInt(e) Mod 2 = 0e  
  
For Each i As var In query2  
    Console.WriteLine("{0}", CInt(i))  
Next  
  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
4  
```  
  
 Esta consulta encadenada proporciona el mismo perfil de rendimiento que si se recorriese en iteración una lista vinculada.  
  
-   El <xref:System.Xml.Linq.XContainer.Elements%2A>eje tiene básicamente el mismo rendimiento que recorrer una lista vinculada.</xref:System.Xml.Linq.XContainer.Elements%2A> <xref:System.Xml.Linq.XContainer.Elements%2A>se implementa como un iterador con ejecución aplazada.</xref:System.Xml.Linq.XContainer.Elements%2A> Es decir, realiza trabajo adicional además de recorrer en iteración la lista vinculada, como asignar el objeto iterador y mantener el seguimiento del estado de la ejecución. Este trabajo se puede dividir en dos categorías: el trabajo que se realiza cuando se configura el iterador y el que se lleva a cabo durante cada iteración. El trabajo de configuración es un trabajo mínimo y fijo, mientras que el realizado durante cada iteración es proporcional al número de elementos de la colección de origen.  
  
-   En `query1`, `Where` cláusula hace que la consulta llame a la <xref:System.Linq.Enumerable.Where%2A>método.</xref:System.Linq.Enumerable.Where%2A> Este método también se implementa como iterador. El trabajo de configuración está formado por la creación de una instancia del delegado que hará referencia a la expresión lambda, más la configuración normal de un iterador. Con cada iteración, se llama al delegado para que ejecute el predicado. El trabajo de configuración y el realizado durante cada iteración es parecido al llevado a cabo mientras se recorre en iteración el eje.  
  
-   En `query1`, la cláusula select hace que la consulta llamar a la <xref:System.Linq.Enumerable.Select%2A>método.</xref:System.Linq.Enumerable.Select%2A> Este método tiene el mismo perfil de rendimiento que el <xref:System.Linq.Enumerable.Where%2A>método.</xref:System.Linq.Enumerable.Where%2A>  
  
-   En `query2`, tanto la cláusula `Where` como la cláusula `Select` tienen el mismo perfil de rendimiento que en `query1`.  
  
 Por lo tanto, la iteración por `query2` es directamente proporcional al número de elementos del origen de la primera consulta, es decir, tiempo lineal.  
  
## <a name="see-also"></a>Vea también  
 [Rendimiento (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)
