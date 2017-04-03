---
title: Rendimiento de consultas encadenadas (LINQ to XML) (C#) | Microsoft Docs
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
ms.assetid: b2f1d715-8946-4dc0-8d56-fb3d1bba54a6
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3429da268df07900ebe59ed206b927d209b1cf7f
ms.lasthandoff: 03/13/2017


---
# <a name="performance-of-chained-queries-linq-to-xml-c"></a>Rendimiento de consultas encadenadas (LINQ to XML) (C#)
Una de las ventajas más importantes de LINQ (y LINQ to XML) es que las consultas encadenadas funcionan igual de bien que una sola consulta más grande y complicada.  
  
 Una consulta encadenada es una consulta que usa otra consulta como su origen. Por ejemplo, en el siguiente código simple, `query2` es el origen de `query1`:  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    new XElement("Child", 3),  
    new XElement("Child", 4)  
);  
  
var query1 = from x in root.Elements("Child")  
             where (int)x >= 3  
             select x;  
  
var query2 = from e in query1  
             where (int)e % 2 == 0  
             select e;  
  
foreach (var i in query2)  
    Console.WriteLine("{0}", (int)i);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
4  
```  
  
 Esta consulta encadenada proporciona el mismo perfil de rendimiento que si se recorriese en iteración una lista vinculada.  
  
-   El eje <xref:System.Xml.Linq.XContainer.Elements%2A> tiene básicamente el mismo rendimiento que si se recorriese en iteración una lista vinculada. <xref:System.Xml.Linq.XContainer.Elements%2A> se implementa como un iterador con ejecución aplazada. Es decir, realiza trabajo adicional además de recorrer en iteración la lista vinculada, como asignar el objeto iterador y mantener el seguimiento del estado de la ejecución. Este trabajo se puede dividir en dos categorías: el trabajo que se realiza cuando se configura el iterador y el que se lleva a cabo durante cada iteración. El trabajo de configuración es un trabajo mínimo y fijo, mientras que el realizado durante cada iteración es proporcional al número de elementos de la colección de origen.  
  
-   En `query1`, la cláusula `where` hace que la consulta llame al método <xref:System.Linq.Enumerable.Where%2A>. Este método también se implementa como iterador. El trabajo de configuración está formado por la creación de una instancia del delegado que hará referencia a la expresión lambda, más la configuración normal de un iterador. Con cada iteración, se llama al delegado para que ejecute el predicado. El trabajo de configuración y el realizado durante cada iteración es parecido al llevado a cabo mientras se recorre en iteración el eje.  
  
-   En `query1`, la cláusula select hace que la consulta llame al método <xref:System.Linq.Enumerable.Select%2A>. Este método tiene el mismo perfil de rendimiento que el método <xref:System.Linq.Enumerable.Where%2A>.  
  
-   En `query2`, tanto la cláusula `where` como la cláusula `select` tienen el mismo perfil de rendimiento que en `query1`.  
  
 Por lo tanto, la iteración por `query2` es directamente proporcional al número de elementos del origen de la primera consulta, es decir, tiempo lineal. Un ejemplo de Visual Basic correspondiente tendría el mismo perfil de rendimiento.  
  
 Para más información sobre iteradores, vea [yield](../../../../csharp/language-reference/keywords/yield.md).  
  
 Para obtener un tutorial más detallado sobre consultas encadenadas, vea [Tutorial: encadenar cadenas juntas](http://msdn.microsoft.com/library/c08d228a-f07a-4c98-810f-1bf0e8f2257c).  
  
## <a name="see-also"></a>Vea también  
 [Rendimiento (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/performance-linq-to-xml.md)
