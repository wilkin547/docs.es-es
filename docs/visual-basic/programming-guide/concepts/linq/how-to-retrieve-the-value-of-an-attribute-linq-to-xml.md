---
title: 'Cómo: recuperar el valor de un atributo (LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
ms.openlocfilehash: 6f9a5936c962111eb75a05f5e3704f7132618143
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320474"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a>Cómo: recuperar el valor de un atributo (LINQ to XML) (Visual Basic)
Este tema muestra cómo obtener el valor de los atributos. Hay dos formas principales: puede convertir un elemento <xref:System.Xml.Linq.XAttribute> al tipo deseado; el operador de conversión explícita convierte el contenido del elemento o del atributo al tipo especificado. Como alternativa, puede usar la propiedad <xref:System.Xml.Linq.XAttribute.Value%2A>. Sin embargo, la conversión suele ser el mejor método. Si convierte el atributo a un tipo que admite valores NULL, resulta más fácil escribir el código al recuperar el valor de un atributo que podría existir o no. Para obtener ejemplos de esta técnica, vea [Cómo: recuperar el valor de un elemento (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).  
  
## <a name="example"></a>Ejemplo  
 En Visual Basic, puede usar la propiedad del atributo integrado para recuperar el valor de un atributo.  
  
```vb  
Dim root As XElement = <Root Attr="abcde"/>  
Console.WriteLine(root)  
Dim str As String = root.@Attr  
Console.WriteLine(str)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a>Ejemplo  
 En Visual Basic, puede usar la propiedad del atributo integrado para establecer el valor de un atributo. Asimismo, si usa la propiedad del atributo integrado para establecer el valor de un atributo que no existe, se creará el atributo.  
  
```vb  
Dim root As XElement = <Root Att1="content"/>  
root.@Att1 = "new content"  
root.@Att2 = "new attribute"  
Console.WriteLine(root)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root Att1="new content" Att2="new attribute" />  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra cómo recuperar el valor de un atributo, en el que el atributo se encuentra en un espacio de nombres. Para obtener más información, vea [información general sobre los espacios de nombres (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root aw:Attr="abcde"/>  
        Dim str As String = root.@aw:Attr  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```console  
abcde  
```  
  
## <a name="see-also"></a>Vea también

- [Ejes de LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
