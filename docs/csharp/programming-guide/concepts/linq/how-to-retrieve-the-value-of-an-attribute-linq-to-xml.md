---
title: "Cómo: Recuperar el valor de un atributo (LINQ to XML) (C#) | Microsoft Docs"
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
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 687a9d6da80259d41f6ed541cee4c579cdff23d8
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-c"></a>Cómo: Recuperar el valor de un atributo (LINQ to XML) (C#)
Este tema muestra cómo obtener el valor de los atributos. Hay dos formas principales: se puede convertir un elemento <xref:System.Xml.Linq.XAttribute> al tipo deseado. El operador de conversión explícita convierte el contenido del elemento o del atributo al tipo especificado. Como alternativa, se puede usar la propiedad <xref:System.Xml.Linq.XAttribute.Value%2A>. Sin embargo, la conversión suele ser el mejor método. Si convierte el atributo a un tipo que admite valores NULL, resulta más fácil escribir el código al recuperar el valor de un atributo que podría existir o no. Para obtener ejemplos de esta técnica, vea [Cómo: Recuperar el valor de un elemento (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).  
  
## <a name="example"></a>Ejemplo  
 Para recuperar el valor de un atributo, basta con convertir el objeto <xref:System.Xml.Linq.XAttribute> al tipo deseado.  
  
```csharp  
XElement root = new XElement("Root",  
                    new XAttribute("Attr", "abcde")  
                );  
Console.WriteLine(root);  
string str = (string)root.Attribute("Attr");  
Console.WriteLine(str);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra cómo recuperar el valor de un atributo, en el que el atributo se encuentra en un espacio de nombres. Para obtener más información, vea [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md) (Trabajar con espacios de nombres XML [C#]).  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
                    new XAttribute(aw + "Attr", "abcde")  
                );  
string str = (string)root.Attribute(aw + "Attr");  
Console.WriteLine(str);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
abcde  
```  
  
## <a name="see-also"></a>Vea también  
 [LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md) (Ejes de LINQ to XML [C#])
