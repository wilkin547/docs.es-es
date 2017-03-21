---
title: Trabajar con espacios de nombres globales (Visual Basic) (LINQ to XML) | Documentos de Microsoft
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
ms.assetid: 0a8064d5-e02f-4315-ad48-6deaa443a2f0
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e20d0c0b670d63ebe2be137a48dc1a1a9a861b9f
ms.lasthandoff: 03/13/2017

---
# <a name="working-with-global-namespaces-visual-basic-linq-to-xml"></a>Trabajar con espacios de nombres globales (Visual Basic) (LINQ to XML)
Una de las características clave de los literales XML en Visual Basic es la capacidad de declarar espacios de nombres XML mediante el `Imports` instrucción. Mediante esta característica puede declarar un espacio de nombres XML que usa un prefijo o bien puede declarar un espacio de nombres XML predeterminado.  
  
 Esta capacidad es útil en dos situaciones. En primer lugar, los espacios de nombres declarados en los literales XML no se mantienen en expresiones incrustadas. La declaración de espacios de nombres globales reduce la cantidad de trabajo que tiene que realizar para usar expresiones incrustadas con espacios de nombres. En segundo lugar, debe declarar espacios de nombres globales para usar espacios de nombres con propiedades XML.  
  
 Puede declarar espacios de nombres globales en el nivel del proyecto. También puede declarar espacios de nombres globales en el nivel del módulo, lo que invalida los espacios de nombres globales de nivel de proyecto. Finalmente, puede reemplazar los espacios de nombres globales en un literal XML.  
  
 Cuando se utilizan literales XML o propiedades XML que están en espacios de nombres declarados globalmente, se puede ver el nombre expandido de las propiedades o los literales XML manteniendo el mouse sobre ellos en Visual Studio. Verá el nombre expandido en una información sobre herramientas.  
  
 Puede obtener un <xref:System.Xml.Linq.XNamespace>objeto que se corresponde con un espacio de nombres global usando el `GetXmlNamespace` método.</xref:System.Xml.Linq.XNamespace>  
  
## <a name="examples-of-global-namespaces"></a>Ejemplos de espacios de nombres globales  
 En el ejemplo siguiente se declara un espacio de nombres global predeterminado usando el `Imports` instrucción y, a continuación, usa un literal XML para inicializar un <xref:System.Xml.Linq.XElement>objeto en ese espacio de nombres:</xref:System.Xml.Linq.XElement>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root xmlns="http://www.adventure-works.com" />  
```  
  
 El siguiente ejemplo declara un espacio de nombres global con un prefijo y después usa un literal XML para inicializar un elemento:  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" />  
```  
  
## <a name="global-namespaces-and-embedded-expressions"></a>Espacios de nombres globales y expresiones incrustadas  
 Los espacios de nombres que se declaran en los literales XML no se mantienen en expresiones incrustadas. El siguiente ejemplo declara un espacio de nombres predeterminado. A continuación usa una expresión incrustada para el elemento `Child`.  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="" />  
</Root>  
```  
  
 Como puede ver, el XML resultante incluye una declaración de un espacio de nombres predeterminado de forma que el elemento `Child` no esté en ningún espacio de nombres.  
  
 Puede volver a declarar el espacio de nombres en la expresión incrustada de ka siguiente manera:  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child xmlns="http://www.adventure-works.com"/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="http://www.adventure-works.com" />  
</Root>  
```  
  
 Sin embargo, esto es más complicado que usar el espacio de nombres global predeterminado, que es un enfoque más adecuado. Con el espacio de nombres global predeterminado, puede utilizar literales XML sin declarar espacios de nombres. El XML resultante estará en el espacio de nombres predeterminado declarado globalmente.  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root>  
                                   <%= <Child/> %>  
                               </Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child />  
</Root>  
```  
  
## <a name="using-namespaces-with-xml-properties"></a>Usar espacios de nombres con propiedades XML  
 Si está trabajando con un árbol XML que está en un espacio de nombres y utiliza propiedades XML, debe usar un espacio de nombres global para que las propiedades XML también estén en el espacio de nombres correcto. En el ejemplo siguiente se declara un árbol XML en un espacio de nombres. Después se muestra el número de elementos `Child`.  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <Child>content</Child>  
    </Root>  
Console.WriteLine(root.<Child>.Count())  
```  
  
 Este ejemplo indica que no hay elementos `Child`. Genera el siguiente resultado:  
  
```  
0  
```  
  
 No obstante, si declara un espacio de nombres global predeterminado, el literal XML y la propiedad XML estarán en el espacio de nombres global predeterminado:  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>content</Child>  
            </Root>  
        Console.WriteLine(root.<Child>.Count())  
    End Sub  
End Module  
```  
  
 Este ejemplo indica que hay un elemento `Child`. Genera el siguiente resultado:  
  
```  
1  
```  
  
 Si declara un espacio de nombres global que no tenga un prefijo, puede usar el prefijo para literales XML y propiedades XML:  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>content</aw:Child>  
            </aw:Root>  
        Console.WriteLine(root.<aw:Child>.Count())  
    End Sub  
End Module  
```  
  
## <a name="xnamespace-and-global-namespaces"></a>XNamespace y espacios de nombres globales  
 Puede obtener un <xref:System.Xml.Linq.XNamespace>objeto usando el `GetXmlNamespace` método:</xref:System.Xml.Linq.XNamespace>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Dim xn As XNamespace = GetXmlNamespace(aw)  
        Console.WriteLine(xn)  
    End Sub  
End Module  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
http://www.adventure-works.com  
```  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con espacios de nombres XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
