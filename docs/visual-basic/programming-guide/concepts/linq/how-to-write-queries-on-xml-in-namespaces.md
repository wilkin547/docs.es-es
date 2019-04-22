---
title: Procedimiento Escribir consultas de XML en espacios de nombres (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 7d4131b5-3288-414f-b77c-b2edc2a1f465
ms.openlocfilehash: 4efa1de254a0264752514c5ae6e601a66fa56f95
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833443"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-visual-basic"></a>Procedimiento Escribir consultas de XML en espacios de nombres (Visual Basic)
Para escribir una consulta en XML que esté en un espacio de nombres, debe usar objetos <xref:System.Xml.Linq.XName> que tengan el espacio de nombres correcto.  
  
 En Visual Basic, el enfoque más común consiste en definir un espacio de nombres global y después utilizar literales XML y propiedades XML que usen el espacio de nombres global. Puede definir un espacio de nombres predeterminado global, en cuyo caso los elementos de los literales XML estarán en el espacio de nombres de forma predeterminada. De forma alternativa puede definir un espacio de nombres global con un prefijo y después usar el prefijo según se requiera en los literales XML y en las propiedades XML. Al igual que con otras formas de XML, los atributos no están nunca en ningún espacio de nombres de forma predeterminada.  
  
 En el primer conjunto de ejemplos de este tema se muestra cómo crear un árbol XML en un espacio de nombres predeterminado. En el segundo conjunto se muestra cómo crear un árbol XML en un espacio de nombres con un prefijo.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un árbol XML que está en un espacio de nombres predeterminado. A continuación recupera una recopilación de elementos.  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
    End Sub  
End Module  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
1  
2  
3  
```  
  
## <a name="example"></a>Ejemplo  
 En Visual Basic, sin embargo, escribir consultas en un árbol XML que utiliza un espacio de nombres con un prefijo es bastante diferente de consultar un árbol XML en un espacio de nombres predeterminado. Normalmente se usa la instrucción `Imports` para importar el espacio de nombres con un prefijo. A continuación se utiliza el prefijo en los nombres del elemento y del atributo cuando se construye el árbol XML. También se utiliza el prefijo al consultar un árbol XML con propiedades XML.  
  
 En el ejemplo siguiente se crea un árbol XML que está en un espacio de nombres con un prefijo. A continuación recupera una recopilación de elementos.  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>1</aw:Child>  
                <aw:Child>2</aw:Child>  
                <aw:Child>3</aw:Child>  
                <aw:AnotherChild>4</aw:AnotherChild>  
                <aw:AnotherChild>5</aw:AnotherChild>  
                <aw:AnotherChild>6</aw:AnotherChild>  
            </aw:Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<aw:Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
    End Sub  
End Module  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
1  
2  
3  
```  
  
## <a name="see-also"></a>Vea también

- [Trabajar con espacios de nombres XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
