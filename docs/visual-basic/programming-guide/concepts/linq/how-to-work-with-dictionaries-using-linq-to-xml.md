---
title: Procedimiento para trabajar con diccionarios mediante LINQ to XML
ms.date: 07/20/2015
ms.assetid: 6cb3f969-1986-414a-b850-87418712edea
ms.openlocfilehash: 14c9c35693f323292849f01af79ae81f92921611
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397679"
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-visual-basic"></a><span data-ttu-id="b0659-102">Cómo: trabajar con diccionarios mediante LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b0659-102">How to: Work with Dictionaries Using LINQ to XML (Visual Basic)</span></span>
<span data-ttu-id="b0659-103">A menudo resulta cómodo convertir variedades de estructuras de datos a XML y de XML a otras estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="b0659-103">It is often convenient to convert varieties of data structures to XML, and XML back to other data structures.</span></span> <span data-ttu-id="b0659-104">Este tema muestra una implementación específica de este enfoque general convirtiendo un <xref:System.Collections.Generic.Dictionary%602> a XML y de XML.</span><span class="sxs-lookup"><span data-stu-id="b0659-104">This topic shows a specific implementation of this general approach by converting a <xref:System.Collections.Generic.Dictionary%602> to XML and back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0659-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0659-105">Example</span></span>  
 <span data-ttu-id="b0659-106">En este ejemplo se usan literales XML y una consulta en una expresión incrustada.</span><span class="sxs-lookup"><span data-stu-id="b0659-106">This example uses XML literals and a query in an embedded expression.</span></span> <span data-ttu-id="b0659-107">La consulta proyecta nuevos <xref:System.Xml.Linq.XElement> objetos, que se convierten en el nuevo contenido del `Root` <xref:System.Xml.Linq.XElement> objeto.</span><span class="sxs-lookup"><span data-stu-id="b0659-107">The query projects new <xref:System.Xml.Linq.XElement> objects, which then become the new content for the `Root` <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```vb  
Dim dict As Dictionary(Of String, String) = New Dictionary(Of String, String)()  
dict.Add("Child1", "Value1")  
dict.Add("Child2", "Value2")  
dict.Add("Child3", "Value3")  
dict.Add("Child4", "Value4")  
Dim root As XElement = _  
    <Root>  
        <%= From keyValue In dict _  
            Select New XElement(keyValue.Key, keyValue.Value) %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="b0659-108">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b0659-108">This code produces the following output:</span></span>  
  
```xml  
          <Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="b0659-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0659-109">Example</span></span>  
 <span data-ttu-id="b0659-110">El siguiente código genera un diccionario de XML.</span><span class="sxs-lookup"><span data-stu-id="b0659-110">The following code creates a dictionary from XML.</span></span>  
  
```vb  
Dim root As XElement = _  
        <Root>  
            <Child1>Value1</Child1>  
            <Child2>Value2</Child2>  
            <Child3>Value3</Child3>  
            <Child4>Value4</Child4>  
        </Root>  
  
Dim dict As Dictionary(Of String, String) = New Dictionary(Of String, String)  
For Each el As XElement In root.Elements  
    dict.Add(el.Name.LocalName, el.Value)  
Next  
For Each str As String In dict.Keys  
    Console.WriteLine("{0}:{1}", str, dict(str))  
Next  
```  
  
 <span data-ttu-id="b0659-111">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b0659-111">This code produces the following output:</span></span>  
  
```console  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0659-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b0659-112">See also</span></span>

- [<span data-ttu-id="b0659-113">Proyecciones y transformaciones (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b0659-113">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](projections-and-transformations-linq-to-xml.md)
