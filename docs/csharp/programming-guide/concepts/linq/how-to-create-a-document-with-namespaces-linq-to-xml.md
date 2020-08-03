---
title: Procedimiento para crear un documento con espacios de nombres (C#) (LINQ to XML)
description: Obtenga información sobre cómo crear un documento con un espacio de nombres en LINQ to XML en C# mediante un objeto XNamespace para combinar el espacio de nombres con el nombre local.
ms.date: 07/20/2015
ms.assetid: 37e63c57-f86d-47ac-88a7-2c2d107def30
ms.openlocfilehash: 6472baefc73285af1c6dca0bfe7d874003940fc4
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103397"
---
# <a name="how-to-create-a-document-with-namespaces-c-linq-to-xml"></a>Procedimiento para crear un documento con espacios de nombres (C#) (LINQ to XML)
En este tema se muestra cómo crear documentos con espacios de nombres.  
  
## <a name="example"></a>Ejemplo  
 Para crear un elemento o un atributo que se encuentra en un espacio de nombres, primero debe declarar e inicializar un objeto <xref:System.Xml.Linq.XNamespace>. A continuación debe utilizar la sobrecarga del operador de suma para combinar el espacio de nombres con el nombre local, expresado como una cadena.  
  
 En el ejemplo siguiente se crea un documento con un espacio de nombres. De forma predeterminada, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] serializa este documento con un espacio de nombres predeterminado.  
  
```csharp  
// Create an XML tree in a namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child>child content</Child>  
</Root>  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un documento con un espacio de nombres. También crea un atributo que declara el espacio de nombres con un prefijo. Para crear un atributo que declara un espacio de nombres con un prefijo, debe crearlo de modo que el nombre del atributo sea el prefijo del espacio de nombres y el nombre se encuentre en el espacio de nombres <xref:System.Xml.Linq.XNamespace.Xmlns%2A>. El valor de este atributo es el URI del espacio de nombres.  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra la creación de un documento que contiene dos espacios de nombres. Uno es el espacio de nombres predeterminado. El otro es un espacio de nombres con un prefijo.  
  
 Mediante la inclusión de los atributos de espacio de nombres en el elemento raíz, los espacios de nombres se serializan de modo que `http://www.adventure-works.com` sea el espacio de nombres predeterminado y `www.fourthcoffee.com` se serialice con un prefijo "fc". Para crear un atributo que declare un espacio de nombres predeterminado, debe crear un atributo con el nombre "xmlns", sin un espacio de nombres. El valor del atributo es el URI del espacio de nombres predeterminado.  
  
```csharp  
// The http://www.adventure-works.com namespace is forced to be the default namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute("xmlns", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root xmlns="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <DifferentChild>other content</DifferentChild>  
  </fc:Child>  
  <Child2>c2 content</Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</Root>  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un documento que contiene dos espacios de nombres, todos ellos con prefijos de espacio de nombres.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", aw.NamespaceName),  
    new XAttribute(XNamespace.Xmlns + "fc", fc.NamespaceName),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="example"></a>Ejemplo  
 Otro método para conseguir el mismo resultado consiste en usar nombres expandidos en lugar de declarar y crear un objeto <xref:System.Xml.Linq.XNamespace>.  
  
 Este método tiene implicaciones en el rendimiento. Cada vez que pasa una cadena que contiene un nombre expandido a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] debe analizar el nombre, buscar el espacio de nombres atomizado y buscar el nombre atomizado. Este proceso consume tiempo de la CPU. Si el rendimiento es importante, tal vez quiera declarar y usar explícitamente un objeto <xref:System.Xml.Linq.XNamespace>.  
  
 Si el rendimiento es un problema importante, vea [Atomización previa de objetos XName (LINQ to XML) (C#)](./pre-atomization-of-xname-objects-linq-to-xml.md) para obtener más información.  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XElement root = new XElement("{http://www.adventure-works.com}Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement("{http://www.adventure-works.com}Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="see-also"></a>Vea también

- [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md)
