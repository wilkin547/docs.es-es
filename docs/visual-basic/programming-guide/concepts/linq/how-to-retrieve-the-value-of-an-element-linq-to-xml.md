---
title: "Cómo: recuperar el valor de un elemento (LINQ to XML) (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: 76b9b2a5-b3ba-49da-ba74-82100e1bd21c
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d38928df51006a8db9417d34ccbe6cd03091db66
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-visual-basic"></a>Cómo: recuperar el valor de un elemento (LINQ to XML) (Visual Basic)
Este tema muestra cómo obtener el valor de los elementos. Existen dos formas principales de hacerlo. Una forma consiste en convertir un <xref:System.Xml.Linq.XElement>o un <xref:System.Xml.Linq.XAttribute>al tipo deseado.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> El operador de conversión explícita convierte el contenido del elemento o del atributo al tipo especificado y lo asigna a la variable. Como alternativa, puede utilizar el <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>propiedad o <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>propiedad.</xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>  
  
 Con Visual Basic, el mejor enfoque es usar el <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>propiedad.</xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>  
  
## <a name="example"></a>Ejemplo  
 Para recuperar el valor de un elemento, basta con convertir el <xref:System.Xml.Linq.XElement>objeto al tipo deseado.</xref:System.Xml.Linq.XElement> Siempre puede convertir un elemento a una cadena, como se indica a continuación:  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a>Ejemplo  
 También puede convertir elementos a tipos diferentes a una cadena. Por ejemplo, si tiene un elemento que contiene un entero, puede convertirlo a `int`, tal como se muestra en el código siguiente:  
  
```vb  
Dim e As XElement = <Age>44</Age>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & CInt(e))  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]Proporciona los mismos operadores de conversión para <xref:System.Xml.Linq.XAttribute>objetos.</xref:System.Xml.Linq.XAttribute>  
  
## <a name="example"></a>Ejemplo  
 Puede usar el <xref:System.Xml.Linq.XElement.Value%2A>propiedad para recuperar el contenido de un elemento:</xref:System.Xml.Linq.XElement.Value%2A>  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a>Ejemplo  
 A veces, intenta recuperar el valor de un elemento aunque no esté seguro de que exista. En este caso, al asignar el elemento convertido a un tipo que acepta valores null (ya sea `string` o uno de los tipos que aceptan valores NULL en la [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]), si el elemento no existe el asignado variable solo se establece en `Nothing`. El código siguiente muestra que cuando el elemento podría o no exista, es más fácil de usar de conversión que el <xref:System.Xml.Linq.XElement.Value%2A>propiedad.</xref:System.Xml.Linq.XElement.Value%2A>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child1>child 1 content</Child1>  
                           <Child2>2</Child2>  
                       </Root>  
  
' The following assignments show why it is easier to use  
' casting when the element might or might not exist.  
  
Dim c1 As String = CStr(root.Element("Child1"))  
Console.WriteLine("c1:{0}", IIf(c1 Is Nothing, "element does not exist", c1))  
  
Dim c2 As Nullable(Of Integer) = CType(root.Element("Child2"), Nullable(Of Integer))  
Console.WriteLine("c2:{0}", IIf(Not (c2.HasValue), "element does not exist", c2.ToString()))  
  
Dim c3 As String = CStr(root.Element("Child3"))  
Console.WriteLine("c3:{0}", IIf(c3 Is Nothing, "element does not exist", c3))  
  
Dim c4 As Nullable(Of Integer) = CType(root.Element("Child4"), Nullable(Of Integer))  
Console.WriteLine("c4:{0}", IIf(Not (c4.HasValue), "element does not exist", c4.ToString()))  
  
Console.WriteLine()  
  
' The following assignments show the required code when using  
' the Value property when the attribute might or might not exist.  
' Notice that this is more difficult than the casting approach.  
  
Dim e1 As XElement = root.Element("Child1")  
Dim v1 As String  
If (e1 Is Nothing) Then  
    v1 = Nothing  
Else  
    v1 = e1.Value  
End If  
Console.WriteLine("v1:{0}", IIf(v1 Is Nothing, "element does not exist", v1))  
  
Dim e2 As XElement = root.Element("Child2")  
Dim v2 As Nullable(Of Integer)  
If (e2 Is Nothing) Then  
    v2 = Nothing  
Else  
    v2 = e2.Value  
End If  
Console.WriteLine("v2:{0}", IIf(Not (v2.HasValue), "element does not exist", v2))  
  
Dim e3 As XElement = root.Element("Child3")  
Dim v3 As String  
If (e3 Is Nothing) Then  
    v3 = Nothing  
Else  
    v3 = e3.Value  
End If  
Console.WriteLine("v3:{0}", IIf(v3 Is Nothing, "element does not exist", v3))  
  
Dim e4 As XElement = root.Element("Child4")  
Dim v4 As Nullable(Of Integer)  
If (e4 Is Nothing) Then  
    v4 = Nothing  
Else  
    v4 = e4.Value  
End If  
Console.WriteLine("v4:{0}", IIf(Not (v4.HasValue), "element does not exist", v4))  
```  
  
 Este código genera el siguiente resultado:  
  
```  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 Por lo general, puede escribir un código más simple al usar la conversión para recuperar el contenido de los elementos y los atributos.  
  
## <a name="see-also"></a>Vea también  
 [Ejes LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
