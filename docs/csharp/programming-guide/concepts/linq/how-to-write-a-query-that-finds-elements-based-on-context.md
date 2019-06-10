---
title: Procedimiento para escribir una consulta que busca elementos en función del contexto (C#)
ms.date: 07/20/2015
ms.assetid: 3ff79ef0-fc8b-42fe-8cc0-10dc32b06b4e
ms.openlocfilehash: 92cbed3edc62b06be65fdd458e509108343d9e59
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66484646"
---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-c"></a>Procedimiento para escribir una consulta que busca elementos en función del contexto (C#)
Es posible que alguna vez tenga que escribir una consulta que seleccione elementos basándose en su contexto. Quizás desea filtrar basándose en elementos de mismo nivel precedentes o siguientes. Quizás desea filtrar basándose e elementos secundarios o elementos antecesores.  
  
 Puede hacerlo escribiendo una consulta y utilizando los resultados de la consulta en la cláusula `where`. Si primero tiene que realizar una prueba con valores NULL y después probar el valor, resulta más cómodo realizar la consulta en una cláusula `let` y después utilizar los resultados en la cláusula `where`.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo selecciona todos los elementos `p` que van seguidos inmediatamente por un elemento `ul`.  
  
```csharp  
XElement doc = XElement.Parse(@"<Root>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants("p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name.LocalName == "ul"  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 Este código genera el siguiente resultado:  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres. Para obtener más información, vea [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md) (Trabajar con espacios de nombres XML [C#]).  
  
```csharp  
XElement doc = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
XNamespace ad = "http://www.adatum.com";  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants(ad + "p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name == ad.GetName("ul")  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 Este código genera el siguiente resultado:  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XElement.Parse%2A>
- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>
- <xref:System.Linq.Enumerable.FirstOrDefault%2A>
