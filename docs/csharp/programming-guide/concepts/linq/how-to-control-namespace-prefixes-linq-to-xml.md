---
title: Procedimiento para controlar prefijos de espacios de nombres (C#) (LINQ to XML)
description: Obtenga información sobre cómo controlar los prefijos de espacio de nombres al serializar un árbol XML en LINQ to XML en C#. En algunas situaciones es necesario controlar los prefijos de espacio de nombres.
ms.date: 07/20/2015
ms.assetid: 64de5186-b81a-4ddd-8327-8693df59a01b
ms.openlocfilehash: b0c5cbfa7488f3a7105595830ef6765e6bfb1f12
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105301"
---
# <a name="how-to-control-namespace-prefixes-c-linq-to-xml"></a>Procedimiento para controlar prefijos de espacios de nombres (C#) (LINQ to XML)
En este tema se describe cómo puede controlar los prefijos de espacios de nombres al serializar un árbol XML.  
  
 En muchas situaciones, no es necesario controlar los prefijos de espacios de nombres.  
  
 Sin embargo, ciertas herramientas de programación XML requieren un control específico de los prefijos de espacios de nombres. Por ejemplo, es posible que esté manipulando una hoja de estilos XSLT o un documento XAML que contenga expresiones XPath incrustadas que hagan referencia a prefijos de espacios de nombres; en ese caso, es importante serializar el documento con dichos prefijos.  
  
 Esta es la razón más común para controlar los prefijos de espacio de nombres.  
  
 Otro motivo habitual para controlar prefijos de espacios de nombres se basa en permitir que los usuarios editen el documento XML manualmente y crear prefijos de fácil escritura. Por ejemplo, tal vez esté generando un documento XSD. Las convenciones de los esquemas sugieren el uso de `xs` o `xsd` como prefijo para el espacio de nombres de esquema.  
  
 Para controlar los prefijos de espacios de nombre, inserta atributos que declaran dichos espacios de nombres. Si declara los espacios de nombres con prefijos específicos, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] intentará respetar los prefijos durante la serialización.  
  
 Para crear un atributo que declara un espacio de nombres con un prefijo, puede crear un atributo donde el espacio de nombres del nombre del atributo es <xref:System.Xml.Linq.XNamespace.Xmlns%2A> y el nombre del atributo es el prefijo del espacio de nombres. El valor del atributo es el URI del espacio de nombres.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo declara dos espacios de nombres. Especifica que el espacio de nombres `http://www.adventure-works.com` tiene el prefijo `aw` y que el espacio de nombres `www.fourthcoffee.com` tiene el prefijo `fc`.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
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
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a>Vea también

- [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md)
