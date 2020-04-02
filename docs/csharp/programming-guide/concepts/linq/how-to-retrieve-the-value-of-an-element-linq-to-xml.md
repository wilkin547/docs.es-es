---
title: Procedimiento para recuperar el valor de un elemento (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
ms.openlocfilehash: 17a7dac464e1ec40db357194000f5745cdf2f3a8
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249212"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a><span data-ttu-id="fdb07-102">Procedimiento para recuperar el valor de un elemento (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="fdb07-102">How to retrieve the value of an element (LINQ to XML) (C#)</span></span>
<span data-ttu-id="fdb07-103">Este tema muestra cómo obtener el valor de los elementos.</span><span class="sxs-lookup"><span data-stu-id="fdb07-103">This topic shows how to get the value of elements.</span></span> <span data-ttu-id="fdb07-104">Existen dos formas principales de hacerlo.</span><span class="sxs-lookup"><span data-stu-id="fdb07-104">There are two main ways to do this.</span></span> <span data-ttu-id="fdb07-105">Una forma consiste en convertir un elemento <xref:System.Xml.Linq.XElement> o un atributo <xref:System.Xml.Linq.XAttribute> al tipo deseado.</span><span class="sxs-lookup"><span data-stu-id="fdb07-105">One way is to cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="fdb07-106">El operador de conversión explícita convierte el contenido del elemento o del atributo al tipo especificado y lo asigna a la variable.</span><span class="sxs-lookup"><span data-stu-id="fdb07-106">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span> <span data-ttu-id="fdb07-107">Como alternativa, se puede usar la propiedad <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> o la propiedad <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fdb07-107">Alternatively, you can use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property or the <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="fdb07-108">Sin embargo, con C#, la conversión suele ser el mejor método.</span><span class="sxs-lookup"><span data-stu-id="fdb07-108">With C#, however, casting is generally the better approach.</span></span> <span data-ttu-id="fdb07-109">Si convierte el elemento o el atributo a un tipo que admite valores NULL, resulta más fácil escribir el código al recuperar el valor de un elemento (o atributo) que podría existir o no.</span><span class="sxs-lookup"><span data-stu-id="fdb07-109">If you cast the element or attribute to a nullable value type, the code is simpler to write when retrieving the value of an element (or attribute) that might or might not exist.</span></span> <span data-ttu-id="fdb07-110">El último ejemplo de este tema muestra este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="fdb07-110">The last example in this topic demonstrates this.</span></span> <span data-ttu-id="fdb07-111">No obstante, no puede establecer el contenido de un elemento mediante la conversión del mismo modo que con la propiedad <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fdb07-111">However, you cannot set the contents of an element through casting, as you can through <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdb07-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdb07-112">Example</span></span>  
 <span data-ttu-id="fdb07-113">Para recuperar el valor de un elemento, basta con convertir el objeto <xref:System.Xml.Linq.XElement> al tipo deseado.</span><span class="sxs-lookup"><span data-stu-id="fdb07-113">To retrieve the value of an element, you just cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="fdb07-114">Siempre puede convertir un elemento a una cadena, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="fdb07-114">You can always cast an element to a string, as follows:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 <span data-ttu-id="fdb07-115">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="fdb07-115">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="fdb07-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdb07-116">Example</span></span>  
 <span data-ttu-id="fdb07-117">También puede convertir elementos a tipos diferentes a una cadena.</span><span class="sxs-lookup"><span data-stu-id="fdb07-117">You can also cast elements to types other than string.</span></span> <span data-ttu-id="fdb07-118">Por ejemplo, si tiene un elemento que contiene un entero, puede convertirlo a `int`, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="fdb07-118">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 <span data-ttu-id="fdb07-119">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="fdb07-119">This example produces the following output:</span></span>  
  
```output  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="fdb07-120">proporciona operadores de conversión explícita para los tipos de datos siguientes: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` y `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="fdb07-120">provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="fdb07-121">proporciona los mismos operadores de conversión para los objetos <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="fdb07-121">provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdb07-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdb07-122">Example</span></span>  
 <span data-ttu-id="fdb07-123">Puede usar la propiedad <xref:System.Xml.Linq.XElement.Value%2A> para recuperar el contenido de un elemento:</span><span class="sxs-lookup"><span data-stu-id="fdb07-123">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 <span data-ttu-id="fdb07-124">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="fdb07-124">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="fdb07-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdb07-125">Example</span></span>  
 <span data-ttu-id="fdb07-126">A veces, intenta recuperar el valor de un elemento aunque no esté seguro de que exista.</span><span class="sxs-lookup"><span data-stu-id="fdb07-126">Sometimes you try to retrieve the value of an element even though you are not sure it exists.</span></span> <span data-ttu-id="fdb07-127">En este caso, al asignar el elemento convertido a un tipo de referencia que acepta valores NULL, o a un tipo de valor que acepta valores NULL, si el elemento no existe, la variable asignada solo se establece en `null`.</span><span class="sxs-lookup"><span data-stu-id="fdb07-127">In this case, when you assign the casted element to a nullable reference type, or nullable value type, if the element does not exist the assigned variable is just set to `null`.</span></span> <span data-ttu-id="fdb07-128">El código siguiente demuestra que cuando el elemento podría existir o no, resulta más fácil usar la conversión que la propiedad <xref:System.Xml.Linq.XElement.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="fdb07-128">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "child 1 content"),  
    new XElement("Child2", "2")  
);  
  
// The following assignments show why it is easier to use  
// casting when the element might or might not exist.  
  
string c1 = (string)root.Element("Child1");  
Console.WriteLine("c1:{0}", c1 == null ? "element does not exist" : c1);  
  
int? c2 = (int?)root.Element("Child2");  
Console.WriteLine("c2:{0}", c2 == null ? "element does not exist" : c2.ToString());  
  
string c3 = (string)root.Element("Child3");  
Console.WriteLine("c3:{0}", c3 == null ? "element does not exist" : c3);  
  
int? c4 = (int?)root.Element("Child4");  
Console.WriteLine("c4:{0}", c4 == null ? "element does not exist" : c4.ToString());  
  
Console.WriteLine();  
  
// The following assignments show the required code when using  
// the Value property when the element might or might not exist.  
// Notice that this is more difficult than the casting approach.  
  
XElement e1 = root.Element("Child1");  
string v1;  
if (e1 == null)  
    v1 = null;  
else  
    v1 = e1.Value;  
Console.WriteLine("v1:{0}", v1 == null ? "element does not exist" : v1);  
  
XElement e2 = root.Element("Child2");  
int? v2;  
if (e2 == null)  
    v2 = null;  
else  
    v2 = Int32.Parse(e2.Value);  
Console.WriteLine("v2:{0}", v2 == null ? "element does not exist" : v2.ToString());  
  
XElement e3 = root.Element("Child3");  
string v3;  
if (e3 == null)  
    v3 = null;  
else  
    v3 = e3.Value;  
Console.WriteLine("v3:{0}", v3 == null ? "element does not exist" : v3);  
  
XElement e4 = root.Element("Child4");  
int? v4;  
if (e4 == null)  
    v4 = null;  
else  
    v4 = Int32.Parse(e4.Value);  
Console.WriteLine("v4:{0}", v4 == null ? "element does not exist" : v4.ToString());  
```  
  
 <span data-ttu-id="fdb07-129">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="fdb07-129">This code produces the following output:</span></span>  
  
```output  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 <span data-ttu-id="fdb07-130">Por lo general, puede escribir un código más simple al usar la conversión para recuperar el contenido de los elementos y los atributos.</span><span class="sxs-lookup"><span data-stu-id="fdb07-130">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb07-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdb07-131">See also</span></span>

- [<span data-ttu-id="fdb07-132">Ejes de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="fdb07-132">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
