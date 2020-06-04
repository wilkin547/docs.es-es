---
title: Procedimiento para crear un documento con espacios de nombres (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: cc5b0d4d-360c-4ada-94fa-2d2916e989be
ms.openlocfilehash: a440c9d810798eb5ebd025a336cbb17fface23b4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414639"
---
# <a name="how-to-create-a-document-with-namespaces-linq-to-xml-visual-basic"></a>Cómo: Crear un documento con espacios de nombres (LINQ to XML) (Visual Basic)
En este tema se muestra cómo crear un documento con espacios de nombres en Visual Basic.  
  
 Cuando se utilizan literales XML en Visual Basic, los usuarios pueden definir un espacio de nombres XML predeterminado que sea global. Este espacio de nombres será el predeterminado tanto para los literales XML como para las propiedades XML. Es posible definir el espacio de nombres XML predeterminado tanto en el nivel de proyecto como en el nivel de archivo. En caso de definirlo a nivel de archivo, éste reemplazará al espacio de nombres predeterminado que se definió a nivel del proyecto.  
  
 También puede definir otros espacios de nombres y especificar para ellos los prefijos de espacio de nombres.  
  
 Mediante la palabra clave `Imports` podrá definir espacios de nombres predeterminados y espacios de nombres con un prefijo.  
  
 Para obtener más información, vea [Introducción a los literales XML en Visual Basic](introduction-to-xml-literals.md).  
  
 Observe que el espacio de nombres XML predeterminado solo puede aplicarse a los elementos, no a los atributos. De forma predeterminada, los atributos nunca se encuentran en un espacio de nombres. No obstante, puede utilizar un prefijo de espacio de nombres para colocar un atributo en un espacio de nombres.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo crea un documento que contiene un espacio de nombres.  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child aw:Att="attvalue"/>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child aw:Att="attvalue" />  
</aw:Root>  
```  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo crea un documento que contiene dos espacios de nombres, uno de los cuales es el predeterminado.  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child Att="attvalue"/>  
                <fc:Child2>child2 content</fc:Child2>  
            </Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root xmlns:fc="www.fourthcoffee.com" xmlns="http://www.adventure-works.com">  
  <Child Att="attvalue" />  
  <fc:Child2>child2 content</fc:Child2>  
</Root>  
```  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea un documento que contiene varios espacios de nombres, todos ellos con prefijos de espacio de nombres.  
  
 Cuando se serializa un árbol XML, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] emite declaraciones de espacios de nombres a medida que se necesitan, para que cada elemento se encuentre en su espacio de nombres designado.  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a>Vea también

- [Información general sobre espacios de nombres (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)
