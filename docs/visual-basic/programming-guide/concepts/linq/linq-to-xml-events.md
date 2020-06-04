---
title: Eventos de LINQ to XML
ms.date: 07/20/2015
ms.assetid: 34923928-b99c-4004-956e-38f6db25e910
ms.openlocfilehash: d00f6f1b2a14ac73c1bcd4a1f74b9714ca304da3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368821"
---
# <a name="linq-to-xml-events-visual-basic"></a>Eventos de LINQ to XML (Visual Basic)
Los eventos de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] permiten recibir notificaciones cuando se modifica un árbol XML.  
  
 Puede agregar eventos a una instancia de cualquier <xref:System.Xml.Linq.XObject>. El controlador de eventos recibirá entonces eventos relacionados con las modificaciones realizadas en ese <xref:System.Xml.Linq.XObject> y en cualquiera de sus descendientes. Por ejemplo, puede agregar un controlador de evento a la raíz del árbol y controlar todas las modificaciones que se realicen al árbol desde ese controlador de eventos.  
  
 Para obtener ejemplos de eventos [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], vea <xref:System.Xml.Linq.XObject.Changing> y <xref:System.Xml.Linq.XObject.Changed>.  
  
## <a name="types-and-events"></a>Tipos y eventos  
 Puede utilizar los siguientes tipos a la hora de trabajar con eventos:  
  
|Tipo|Description|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|Especifica el tipo de evento cuando se genera éste para un <xref:System.Xml.Linq.XObject>.|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|Proporciona datos para los eventos <xref:System.Xml.Linq.XObject.Changing> y <xref:System.Xml.Linq.XObject.Changed>.|  
  
 Los siguientes eventos se generan cuando se modifica un árbol XML:  
  
|evento|Description|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|Se produce justo antes de que este <xref:System.Xml.Linq.XObject> o cualquiera de sus descendientes se vayan a modificar.|  
|<xref:System.Xml.Linq.XObject.Changed>|Se produce cuando ha cambiado un <xref:System.Xml.Linq.XObject> o cualquiera de sus descendientes.|  
  
## <a name="example"></a>Ejemplo  
  
### <a name="description"></a>Description  
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
  
```console  
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
  
## <a name="see-also"></a>Consulte también

- [Programación de LINQ to XML avanzada (Visual Basic)](advanced-linq-to-xml-programming.md)
