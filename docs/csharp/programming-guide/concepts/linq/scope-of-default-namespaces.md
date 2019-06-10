---
title: Ámbito del espacio de nombres predeterminado de C#
ms.date: 07/20/2015
ms.assetid: fe826236-830f-457a-9027-7ad62c909fae
ms.openlocfilehash: 2eee1b0c79f585710962d8e84fe584bca6b8228b
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66483605"
---
# <a name="scope-of-default-namespaces-in-c"></a>Ámbito del espacio de nombres predeterminado de C\#
Los espacios de nombres predeterminados del árbol XML no se encuentran en el ámbito de las consultas. Si tiene código XML en un espacio de nombres predeterminado, debe declarar una variable <xref:System.Xml.Linq.XNamespace> y combinarla con el nombre local para convertirla en un nombre completo que se usará en la consulta.  
  
 Uno de los problemas más habituales al consultar árboles XML es que si el árbol XML tiene un espacio de nombres predeterminado, el desarrollador a veces escribe la consulta como si el código XML no estuviera en un espacio de nombres.  
  
 El primer conjunto de ejemplos de este tema muestra una forma habitual de cargar XML en un espacio de nombres predeterminado con una consulta incorrecta.  
  
 El segundo conjunto de ejemplos muestra las correcciones necesarias para que pueda consultar el código XML en un espacio de nombres.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra la creación de XML en un espacio de nombres y una consulta que devuelve un conjunto de resultados vacío.  
  
### <a name="code"></a>Código  
  
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
  
### <a name="comments"></a>Comentarios  
 Este ejemplo genera el siguiente resultado:  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestra la creación de XML en un espacio de nombres y una consulta que se codifica correctamente.  
  
 A diferencia del anterior ejemplo de código incorrecto, el enfoque adecuado al usar C# consiste en declarar e inicializar un objeto <xref:System.Xml.Linq.XNamespace> y usarlo cuando se especifiquen objetos <xref:System.Xml.Linq.XName>. En este caso, el argumento para el método <xref:System.Xml.Linq.XContainer.Elements%2A> es un objeto <xref:System.Xml.Linq.XName>.  
  
### <a name="code"></a>Código  
  
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
  
### <a name="comments"></a>Comentarios  
 Este ejemplo genera el siguiente resultado:  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a>Vea también

- [Trabajar con espacios de nombres XML (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md)
