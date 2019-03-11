---
title: Procedimiento para depurar conjuntos de resultados de consulta vacíos (C#)
ms.date: 07/20/2015
ms.assetid: b569f0dc-425e-45a6-acbf-770fb761c981
ms.openlocfilehash: d77a92acf54420b5add3bb9ae8b3f0b8c5448d18
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357916"
---
# <a name="how-to-debug-empty-query-results-sets-c"></a>Procedimiento para depurar conjuntos de resultados de consulta vacíos (C#)
Uno de los problemas más habituales al consultar árboles XML es que si el árbol XML tiene un espacio de nombres predeterminado, el desarrollador a veces escribe la consulta como si el código XML no estuviera en un espacio de nombres.  
  
 El primer conjunto de ejemplos de este tema muestra una forma habitual de cargar XML en un espacio de nombres predeterminado con una consulta incorrecta.  
  
 El segundo conjunto de ejemplos muestra las correcciones necesarias para que pueda consultar el código XML en un espacio de nombres.  
  
 Para obtener más información, vea [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md) (Trabajar con espacios de nombres XML [C#]).  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo muestra la creación de XML en un espacio de nombres, y una consulta que devuelve un conjunto de resultados vacío.  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements("Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 Este ejemplo genera el siguiente resultado:  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo muestra la creación de XML en un espacio de nombres, y una consulta que se codifica correctamente.  
  
 La solución consiste en declarar e inicializar un objeto <xref:System.Xml.Linq.XNamespace>, y usarlo cuando se especifiquen objetos <xref:System.Xml.Linq.XName>. En este caso, el argumento para el método <xref:System.Xml.Linq.XContainer.Elements%2A> es un objeto <xref:System.Xml.Linq.XName>.  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 Este ejemplo genera el siguiente resultado:  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a>Vea también

- [Consultas básicas (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
