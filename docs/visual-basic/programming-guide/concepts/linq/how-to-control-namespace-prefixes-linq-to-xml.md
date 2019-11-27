---
title: 'Cómo: controlar prefijos de espacios de nombres (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 5ba415452a8671466c3a4c71a88731e5bd3cda60
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348386"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a>Cómo: Controlar prefijos de espacio de nombres (Visual Basic) (LINQ to XML)
En este tema se describe cómo puede controlar prefijos de espacios de nombres.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 Este ejemplo declara dos espacios de nombres. Especifica que el espacio de nombres `http://www.adventure-works.com` tiene el prefijo `aw`y que el espacio de nombres `www.fourthcoffee.com` tiene el prefijo `fc`.  
  
### <a name="code"></a>Código  
  
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
  
### <a name="comments"></a>Comentarios  
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
