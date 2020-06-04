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
# <a name="linq-to-xml-events-visual-basic"></a><span data-ttu-id="db176-102">Eventos de LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db176-102">LINQ to XML Events (Visual Basic)</span></span>
<span data-ttu-id="db176-103">Los eventos de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] permiten recibir notificaciones cuando se modifica un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="db176-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="db176-104">Puede agregar eventos a una instancia de cualquier <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="db176-104">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="db176-105">El controlador de eventos recibirá entonces eventos relacionados con las modificaciones realizadas en ese <xref:System.Xml.Linq.XObject> y en cualquiera de sus descendientes.</span><span class="sxs-lookup"><span data-stu-id="db176-105">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="db176-106">Por ejemplo, puede agregar un controlador de evento a la raíz del árbol y controlar todas las modificaciones que se realicen al árbol desde ese controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="db176-106">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="db176-107">Para obtener ejemplos de eventos [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], vea <xref:System.Xml.Linq.XObject.Changing> y <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="db176-107">For examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="db176-108">Tipos y eventos</span><span class="sxs-lookup"><span data-stu-id="db176-108">Types and Events</span></span>  
 <span data-ttu-id="db176-109">Puede utilizar los siguientes tipos a la hora de trabajar con eventos:</span><span class="sxs-lookup"><span data-stu-id="db176-109">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="db176-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="db176-110">Type</span></span>|<span data-ttu-id="db176-111">Description</span><span class="sxs-lookup"><span data-stu-id="db176-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|<span data-ttu-id="db176-112">Especifica el tipo de evento cuando se genera éste para un <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="db176-112">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|<span data-ttu-id="db176-113">Proporciona datos para los eventos <xref:System.Xml.Linq.XObject.Changing> y <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="db176-113">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="db176-114">Los siguientes eventos se generan cuando se modifica un árbol XML:</span><span class="sxs-lookup"><span data-stu-id="db176-114">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="db176-115">evento</span><span class="sxs-lookup"><span data-stu-id="db176-115">Event</span></span>|<span data-ttu-id="db176-116">Description</span><span class="sxs-lookup"><span data-stu-id="db176-116">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|<span data-ttu-id="db176-117">Se produce justo antes de que este <xref:System.Xml.Linq.XObject> o cualquiera de sus descendientes se vayan a modificar.</span><span class="sxs-lookup"><span data-stu-id="db176-117">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<xref:System.Xml.Linq.XObject.Changed>|<span data-ttu-id="db176-118">Se produce cuando ha cambiado un <xref:System.Xml.Linq.XObject> o cualquiera de sus descendientes.</span><span class="sxs-lookup"><span data-stu-id="db176-118">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="db176-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="db176-119">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="db176-120">Description</span><span class="sxs-lookup"><span data-stu-id="db176-120">Description</span></span>  
 <span data-ttu-id="db176-121">Los eventos resultan útiles cuando desea mantener cierta información de agregado en un árbol XML.</span><span class="sxs-lookup"><span data-stu-id="db176-121">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="db176-122">Por ejemplo, quizá desee mantener el total de una factura que es la suma de los conceptos de la factura.</span><span class="sxs-lookup"><span data-stu-id="db176-122">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="db176-123">Este ejemplo utiliza eventos para mantener el total de todos los elementos secundarios que se encuentran bajo el elemento complejo `Items`.</span><span class="sxs-lookup"><span data-stu-id="db176-123">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="db176-124">Código</span><span class="sxs-lookup"><span data-stu-id="db176-124">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="db176-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db176-125">Comments</span></span>  
 <span data-ttu-id="db176-126">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="db176-126">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="db176-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db176-127">See also</span></span>

- [<span data-ttu-id="db176-128">Programación de LINQ to XML avanzada (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db176-128">Advanced LINQ to XML Programming (Visual Basic)</span></span>](advanced-linq-to-xml-programming.md)
