---
title: Procedimiento para recuperar el valor de un elemento (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 76b9b2a5-b3ba-49da-ba74-82100e1bd21c
ms.openlocfilehash: b8ff44416f0fbb590119af7e11714e449185d977
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397796"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-visual-basic"></a><span data-ttu-id="7cc6b-102">Cómo: recuperar el valor de un elemento (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7cc6b-102">How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="7cc6b-103">Este tema muestra cómo obtener el valor de los elementos.</span><span class="sxs-lookup"><span data-stu-id="7cc6b-103">This topic shows how to get the value of elements.</span></span> <span data-ttu-id="7cc6b-104">Existen dos formas principales de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="7cc6b-104">There are two main ways to do this.</span></span> <span data-ttu-id="7cc6b-105">Una forma consiste en convertir un elemento <xref:System.Xml.Linq.XElement> o un atributo <xref:System.Xml.Linq.XAttribute> al tipo deseado.</span><span class="sxs-lookup"><span data-stu-id="7cc6b-105">One way is to cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="7cc6b-106">El operador de conversión explícita convierte el contenido del elemento o del atributo al tipo especificado y lo asigna a la variable.</span><span class="sxs-lookup"><span data-stu-id="7cc6b-106">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span> <span data-ttu-id="7cc6b-107">Como alternativa, se puede usar la propiedad <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> o la propiedad <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7cc6b-107">Alternatively, you can use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property or the <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="7cc6b-108">Con Visual Basic, el mejor método consiste en usar la propiedad <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7cc6b-108">With Visual Basic, the best approach is to use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cc6b-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7cc6b-109">Example</span></span>  
 <span data-ttu-id="7cc6b-110">Para recuperar el valor de un elemento, basta con convertir el objeto <xref:System.Xml.Linq.XElement> al tipo deseado.</span><span class="sxs-lookup"><span data-stu-id="7cc6b-110">To retrieve the value of an element, you just cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="7cc6b-111">Siempre puede convertir un elemento a una cadena, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="7cc6b-111">You can always cast an element to a string, as follows:</span></span>  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 <span data-ttu-id="7cc6b-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="7cc6b-112">This example produces the following output:</span></span>  
  
```xml  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="7cc6b-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7cc6b-113">Example</span></span>  
 <span data-ttu-id="7cc6b-114">También puede convertir elementos a tipos diferentes a una cadena.</span><span class="sxs-lookup"><span data-stu-id="7cc6b-114">You can also cast elements to types other than string.</span></span> <span data-ttu-id="7cc6b-115">Por ejemplo, si tiene un elemento que contiene un entero, puede convertirlo a `int`, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="7cc6b-115">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```vb  
Dim e As XElement = <Age>44</Age>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & CInt(e))  
```  
  
 <span data-ttu-id="7cc6b-116">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="7cc6b-116">This example produces the following output:</span></span>  
  
```xml  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="7cc6b-117">proporciona operadores de conversión explícita para los tipos de datos siguientes: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` y `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="7cc6b-117">provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="7cc6b-118">proporciona los mismos operadores de conversión para los objetos <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="7cc6b-118">provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7cc6b-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7cc6b-119">Example</span></span>  
 <span data-ttu-id="7cc6b-120">Puede usar la propiedad <xref:System.Xml.Linq.XElement.Value%2A> para recuperar el contenido de un elemento:</span><span class="sxs-lookup"><span data-stu-id="7cc6b-120">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 <span data-ttu-id="7cc6b-121">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="7cc6b-121">This example produces the following output:</span></span>  
  
```xml  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="7cc6b-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7cc6b-122">Example</span></span>  
 <span data-ttu-id="7cc6b-123">A veces, intenta recuperar el valor de un elemento aunque no esté seguro de que exista.</span><span class="sxs-lookup"><span data-stu-id="7cc6b-123">Sometimes you try to retrieve the value of an element even though you are not sure it exists.</span></span> <span data-ttu-id="7cc6b-124">En este caso, al asignar el elemento convertido a un tipo que acepta valores NULL (ya sea `string` o uno de los tipos de valor que aceptan valores NULL en el .NET Framework), si el elemento no existe, la variable asignada se limita a establecer en `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="7cc6b-124">In this case, when you assign the casted element to a nullable type (either `string` or one of the nullable value types in the .NET Framework), if the element does not exist the assigned variable is just set to `Nothing`.</span></span> <span data-ttu-id="7cc6b-125">El código siguiente demuestra que cuando el elemento podría existir o no, resulta más fácil usar la conversión que la propiedad <xref:System.Xml.Linq.XElement.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cc6b-125">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
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
  
 <span data-ttu-id="7cc6b-126">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="7cc6b-126">This code produces the following output:</span></span>  
  
```console  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 <span data-ttu-id="7cc6b-127">Por lo general, puede escribir un código más simple al usar la conversión para recuperar el contenido de los elementos y los atributos.</span><span class="sxs-lookup"><span data-stu-id="7cc6b-127">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cc6b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="7cc6b-128">See also</span></span>

- [<span data-ttu-id="7cc6b-129">Ejes de LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7cc6b-129">LINQ to XML Axes (Visual Basic)</span></span>](linq-to-xml-axes.md)
