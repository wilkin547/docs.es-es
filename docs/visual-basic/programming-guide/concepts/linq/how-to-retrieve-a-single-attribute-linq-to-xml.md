---
title: Procedimiento para recuperar un único atributo (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 11b938d7-c011-4048-900e-8b9183c41c94
ms.openlocfilehash: 34c390fbffc1aea68a2fd8ae64b17d2637a1f4f1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397861"
---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-visual-basic"></a><span data-ttu-id="c81f3-102">Cómo: recuperar un único atributo (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c81f3-102">How to: Retrieve a Single Attribute (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="c81f3-103">Este tema explica cómo recuperar un atributo concreto de un elemento, proporcionando el nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="c81f3-103">This topic explains how to retrieve a single attribute of an element, given the attribute name.</span></span> <span data-ttu-id="c81f3-104">Esto puede resultar útil para escribir expresiones de consulta mediante las cuales encontrar un elemento que contiene un atributo en particular.</span><span class="sxs-lookup"><span data-stu-id="c81f3-104">This is useful for writing query expressions where you want to find an element that has a particular attribute.</span></span>  
  
 <span data-ttu-id="c81f3-105">El método <xref:System.Xml.Linq.XElement.Attribute%2A> de la clase <xref:System.Xml.Linq.XElement> devuelve el <xref:System.Xml.Linq.XAttribute> con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="c81f3-105">The <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement> class returns the <xref:System.Xml.Linq.XAttribute> with the specified name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c81f3-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c81f3-106">Example</span></span>  
 <span data-ttu-id="c81f3-107">El siguiente ejemplo utiliza el método <xref:System.Xml.Linq.XElement.Attribute%2A>.</span><span class="sxs-lookup"><span data-stu-id="c81f3-107">The following example uses the <xref:System.Xml.Linq.XElement.Attribute%2A> method.</span></span>  
  
```vb  
Dim cust As XElement = <PhoneNumbers>  
                           <Phone type="home">555-555-5555</Phone>  
                           <Phone type="work">555-555-6666</Phone>  
                       </PhoneNumbers>  
Dim elList = From el In cust...<Phone>  
For Each e As XElement In elList  
    Console.WriteLine(e.@type)  
Next  
```  
  
 <span data-ttu-id="c81f3-108">Este ejemplo encuentra todos los descendientes en el árbol cuyo nombre es `Phone` y, a continuación, encuentra aquel atributo cuyo nombre es `type`.</span><span class="sxs-lookup"><span data-stu-id="c81f3-108">This example finds all the descendants in the tree named `Phone`, and then finds the attribute named `type`.</span></span>  
  
 <span data-ttu-id="c81f3-109">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c81f3-109">This code produces the following output:</span></span>  
  
```console  
home  
work  
```  
  
## <a name="example"></a><span data-ttu-id="c81f3-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c81f3-110">Example</span></span>  
 <span data-ttu-id="c81f3-111">Si desea recuperar el valor del atributo, puede convertirlo, de la misma forma que lo haría con los objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="c81f3-111">If you want to retrieve the value of the attribute, you can cast it, just as you do for with <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="c81f3-112">En el siguiente ejemplo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="c81f3-112">The following example demonstrates this.</span></span>  
  
```vb  
Dim cust As XElement = <PhoneNumbers>  
                           <Phone type="home">555-555-5555</Phone>  
                           <Phone type="work">555-555-6666</Phone>  
                       </PhoneNumbers>  
Dim elList As IEnumerable(Of XElement) = _  
    From el In cust...<Phone> _  
    Select el  
For Each el As XElement In elList  
    Console.WriteLine(el.@type)  
Next  
```  
  
 <span data-ttu-id="c81f3-113">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c81f3-113">This code produces the following output:</span></span>  
  
```console  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="c81f3-114">proporciona operadores de conversión explícita para la clase <xref:System.Xml.Linq.XAttribute> a `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` y `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="c81f3-114">provides explicit cast operators for the <xref:System.Xml.Linq.XAttribute> class to `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c81f3-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c81f3-115">Example</span></span>  
 <span data-ttu-id="c81f3-116">El siguiente ejemplo muestra el mismo código para un atributo que se encuentre en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c81f3-116">The following example shows the same code for an attribute that is in a namespace.</span></span> <span data-ttu-id="c81f3-117">Para obtener más información, vea [información general sobre los espacios de nombres (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c81f3-117">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim cust As XElement = _  
            <aw:PhoneNumbers>  
                <aw:Phone aw:type="home">555-555-5555</aw:Phone>  
                <aw:Phone aw:type="work">555-555-6666</aw:Phone>  
            </aw:PhoneNumbers>  
        Dim elList As IEnumerable(Of XElement) = _  
            From el In cust...<aw:Phone> _  
            Select el  
        For Each el As XElement In elList  
            Console.WriteLine(el.@aw:type)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="c81f3-118">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c81f3-118">This code produces the following output:</span></span>  
  
```console  
home  
work  
```  
  
## <a name="see-also"></a><span data-ttu-id="c81f3-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c81f3-119">See also</span></span>

- [<span data-ttu-id="c81f3-120">Ejes de LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c81f3-120">LINQ to XML Axes (Visual Basic)</span></span>](linq-to-xml-axes.md)
