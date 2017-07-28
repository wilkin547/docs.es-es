---
title: Escribir consultas de XML en espacios de nombres (C#)
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
ms.assetid: 7c54df81-15e4-4091-8c81-a87637029130
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 54d8c876ca5f8c6d721eaab13515e70f23a68744
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-queries-on-xml-in-namespaces-c"></a>Escribir consultas de XML en espacios de nombres (C#)
Para escribir una consulta en XML que esté en un espacio de nombres, debe usar objetos <xref:System.Xml.Linq.XName> que tengan el espacio de nombres correcto.  
  
 Para C#, el enfoque más común consiste en inicializar un objeto <xref:System.Xml.Linq.XNamespace> usando una cadena que contiene el identificador URI y, después, usar la sobrecarga del operador de suma para combinar el espacio de nombres con el nombre local.  
  
 En el primer conjunto de ejemplos de este tema se muestra cómo crear un árbol XML en un espacio de nombres predeterminado. En el segundo conjunto se muestra cómo crear un árbol XML en un espacio de nombres con un prefijo.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un árbol XML que está en un espacio de nombres predeterminado. A continuación recupera una recopilación de elementos.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
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
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
1  
2  
3  
```  
  
## <a name="example"></a>Ejemplo  
 En C#, las consultas se escribe de la misma forma, independientemente de si se escribe en un árbol XML que usa un espacio de nombres con un prefijo o en un árbol XML con un espacio de nombres predeterminado.  
  
 En el ejemplo siguiente se crea un árbol XML que está en un espacio de nombres con un prefijo. A continuación recupera una recopilación de elementos.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
    <aw:Child>1</aw:Child>  
    <aw:Child>2</aw:Child>  
    <aw:Child>3</aw:Child>  
    <aw:AnotherChild>4</aw:AnotherChild>  
    <aw:AnotherChild>5</aw:AnotherChild>  
    <aw:AnotherChild>6</aw:AnotherChild>  
</aw:Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
1  
2  
3  
```  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con espacios de nombres XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)

