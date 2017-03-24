---
title: LINQ to XML eventos (Visual Basic) | Documentos de Microsoft
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
ms.assetid: 34923928-b99c-4004-956e-38f6db25e910
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
ms.openlocfilehash: 2b7756845f155c4683015d54b41f2ecc09b29333
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-events-visual-basic"></a>LINQ to XML eventos (Visual Basic)
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]eventos permiten recibir una notificación cuando se modifica un árbol XML.  
  
 Puede agregar eventos a una instancia de cualquier <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject> El controlador de eventos recibirá entonces eventos para realizar modificaciones en el que <xref:System.Xml.Linq.XObject>y cualquiera de sus descendientes.</xref:System.Xml.Linq.XObject> Por ejemplo, puede agregar un controlador de evento a la raíz del árbol y controlar todas las modificaciones que se realicen al árbol desde ese controlador de eventos.  
  
 Para obtener ejemplos de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] <xref:System.Xml.Linq.XObject.Changing>y <xref:System.Xml.Linq.XObject.Changed>.</xref:System.Xml.Linq.XObject.Changed> </xref:System.Xml.Linq.XObject.Changing> los eventos, vea  
  
## <a name="types-and-events"></a>Tipos y eventos  
 Puede utilizar los siguientes tipos a la hora de trabajar con eventos:  
  
|Tipo|Descripción|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange></xref:System.Xml.Linq.XObjectChange>|Especifica el tipo de evento cuando se produce un evento para un <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject>|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs></xref:System.Xml.Linq.XObjectChangeEventArgs>|Proporciona datos para el <xref:System.Xml.Linq.XObject.Changing>y <xref:System.Xml.Linq.XObject.Changed>eventos.</xref:System.Xml.Linq.XObject.Changed> </xref:System.Xml.Linq.XObject.Changing>|  
  
 Los siguientes eventos se generan cuando se modifica un árbol XML:  
  
|Evento|Descripción|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing></xref:System.Xml.Linq.XObject.Changing>|Se produce justo antes de que esto <xref:System.Xml.Linq.XObject>o cualquiera de sus descendientes se vayan a modificar.</xref:System.Xml.Linq.XObject>|  
|<xref:System.Xml.Linq.XObject.Changed></xref:System.Xml.Linq.XObject.Changed>|Se produce cuando un <xref:System.Xml.Linq.XObject>ha cambiado o cualquiera de sus descendientes han cambiado.</xref:System.Xml.Linq.XObject>|  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Descripción  
 Los eventos resultan útiles cuando desea mantener cierta información de agregado en un árbol XML. Por ejemplo, quizá desee mantener el total de una factura que es la suma de los conceptos de la factura. Este ejemplo utiliza eventos para mantener el total de todos los elementos secundarios que se encuentran bajo el elemento complejo `Items`.  
  
### <a name="code"></a>Código  
  
```vb  
Module Module1  
    Dim WithEvents items As XElement = Nothing  
    Dim total As XElement = Nothing  
    Dim root As XElement = _  
            <Root>  
                <Total>0</Total>  
                <Items></Items>  
            </Root>  
  
    Private Sub XObjectChanged( _  
            ByVal sender As Object, _  
            ByVal cea As XObjectChangeEventArgs) _  
            Handles items.Changed  
        Select Case cea.ObjectChange  
            Case XObjectChange.Add  
                If sender.GetType() Is GetType(XElement) Then  
                    total.Value = CStr(CInt(total.Value) + _  
                            CInt((DirectCast(sender, XElement)).Value))  
                End If  
                If sender.GetType() Is GetType(XText) Then  
                    total.Value = CStr(CInt(total.Value) + _  
                            CInt((DirectCast(sender, XText)).Value))  
                End If  
            Case XObjectChange.Remove  
                If sender.GetType() Is GetType(XElement) Then  
                    total.Value = CStr(CInt(total.Value) - _  
                            CInt((DirectCast(sender, XElement)).Value))  
                End If  
                If sender.GetType() Is GetType(XText) Then  
                    total.Value = CStr(CInt(total.Value) - _  
                            CInt((DirectCast(sender, XText)).Value))  
                End If  
        End Select  
        Console.WriteLine("Changed {0} {1}", _  
                            sender.GetType().ToString(), _  
                            cea.ObjectChange.ToString())  
    End Sub  
  
    Sub Main()  
        total = root.<Total>(0)  
        items = root.<Items>(0)  
        items.SetElementValue("Item1", 25)  
        items.SetElementValue("Item2", 50)  
        items.SetElementValue("Item2", 75)  
        items.SetElementValue("Item3", 133)  
        items.SetElementValue("Item1", Nothing)  
        items.SetElementValue("Item4", 100)  
        Console.WriteLine("Total:{0}", CInt(total))  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
### <a name="comments"></a>Comentarios  
 Este código genera el siguiente resultado:  
  
```  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XText Remove  
Changed System.Xml.Linq.XText Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Remove  
Changed System.Xml.Linq.XElement Add  
Total:308  
<Root>  
  <Total>308</Total>  
  <Items>  
    <Item2>75</Item2>  
    <Item3>133</Item3>  
    <Item4>100</Item4>  
  </Items>  
</Root>  
```  
  
## <a name="see-also"></a>Vea también  
 [Avanzada de LINQ to XML Programming (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
