---
title: Procedimiento para recuperar el valor de un elemento (LINQ to XML) (C#)
description: Aprenda a obtener el valor de los elementos. Vea ejemplos en los que se usa la conversión de cadenas, la conversión de enteros y la propiedad Value.
ms.date: 07/20/2015
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
ms.openlocfilehash: eb750927d74c3068d7ab06caba9835110bd77a09
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301546"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a><span data-ttu-id="0b567-104">Procedimiento para recuperar el valor de un elemento (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0b567-104">How to retrieve the value of an element (LINQ to XML) (C#)</span></span>

<span data-ttu-id="0b567-105">En este artículo se muestra cómo obtener el valor de los elementos.</span><span class="sxs-lookup"><span data-stu-id="0b567-105">This article shows how to get the value of elements.</span></span> <span data-ttu-id="0b567-106">Existen dos formas principales de hacerlo:</span><span class="sxs-lookup"><span data-stu-id="0b567-106">There are two main ways to get the value:</span></span>

- <span data-ttu-id="0b567-107">Convertir un objeto <xref:System.Xml.Linq.XElement> o un objeto <xref:System.Xml.Linq.XAttribute> al tipo deseado.</span><span class="sxs-lookup"><span data-stu-id="0b567-107">Cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="0b567-108">El operador de conversión explícita convierte el contenido del elemento o del atributo al tipo especificado y lo asigna a la variable.</span><span class="sxs-lookup"><span data-stu-id="0b567-108">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span>

- <span data-ttu-id="0b567-109">Use las propiedades <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> y <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0b567-109">Use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> or <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> properties.</span></span> <span data-ttu-id="0b567-110">También puede establecer el valor con estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="0b567-110">You can also set the value using these properties.</span></span>

<span data-ttu-id="0b567-111">Con C#, la conversión suele ser el mejor método.</span><span class="sxs-lookup"><span data-stu-id="0b567-111">With C#, casting is generally the better approach.</span></span> <span data-ttu-id="0b567-112">Si convierte el elemento o el atributo a un tipo que admite valores NULL, resulta más fácil escribir el código al recuperar el valor de un elemento (o atributo) que podría existir o no.</span><span class="sxs-lookup"><span data-stu-id="0b567-112">If you cast the element or attribute to a nullable value type, the code is simpler to write when retrieving the value of an element (or attribute) that might or might not exist.</span></span> <span data-ttu-id="0b567-113">En el [último ejemplo](#element-might-not-exist-example) de este artículo se muestra que la conversión es más sencilla en caso de que el elemento no exista.</span><span class="sxs-lookup"><span data-stu-id="0b567-113">The [last example](#element-might-not-exist-example) in this article demonstrates that casting is simpler in the case where the element might not exist.</span></span> <span data-ttu-id="0b567-114">No obstante, no puede establecer el contenido de un elemento mediante la conversión del mismo modo que con la propiedad <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0b567-114">However, you cannot set the contents of an element through casting, as you can through <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="string-cast-example"></a><span data-ttu-id="0b567-115">Ejemplo de conversión de cadena</span><span class="sxs-lookup"><span data-stu-id="0b567-115">String cast example</span></span>  
 <span data-ttu-id="0b567-116">Para recuperar el valor de un elemento, convierta el objeto <xref:System.Xml.Linq.XElement> al tipo deseado.</span><span class="sxs-lookup"><span data-stu-id="0b567-116">To retrieve the value of an element, cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="0b567-117">Siempre puede convertir un elemento en cadena, tal y como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="0b567-117">You can cast an element to a string, as follows:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 <span data-ttu-id="0b567-118">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0b567-118">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="integer-cast-example"></a><span data-ttu-id="0b567-119">Ejemplo de conversión de enteros</span><span class="sxs-lookup"><span data-stu-id="0b567-119">Integer cast example</span></span>  
 <span data-ttu-id="0b567-120">También puede convertir elementos a tipos diferentes a una cadena.</span><span class="sxs-lookup"><span data-stu-id="0b567-120">You can also cast elements to types other than string.</span></span> <span data-ttu-id="0b567-121">Por ejemplo, si tiene un elemento que contiene un entero, puede convertirlo a `int`, tal como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0b567-121">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 <span data-ttu-id="0b567-122">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0b567-122">This example produces the following output:</span></span>  
  
```output  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="0b567-123">proporciona operadores de conversión explícita para los tipos de datos siguientes: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` y `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="0b567-123">provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="0b567-124">proporciona los mismos operadores de conversión para los objetos <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0b567-124">provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="value-property-example"></a><span data-ttu-id="0b567-125">Ejemplo de la propiedad Value</span><span class="sxs-lookup"><span data-stu-id="0b567-125">Value property example</span></span>  
 <span data-ttu-id="0b567-126">Puede usar la propiedad <xref:System.Xml.Linq.XElement.Value%2A> para recuperar el contenido de un elemento:</span><span class="sxs-lookup"><span data-stu-id="0b567-126">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 <span data-ttu-id="0b567-127">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0b567-127">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="element-might-not-exist-example"></a><span data-ttu-id="0b567-128">Ejemplo de elemento que podría no existir</span><span class="sxs-lookup"><span data-stu-id="0b567-128">Element might not exist example</span></span>
 <span data-ttu-id="0b567-129">A veces, intenta recuperar el valor de un elemento aunque no esté seguro de que exista.</span><span class="sxs-lookup"><span data-stu-id="0b567-129">Sometimes you try to retrieve the value of an element even though you're not sure if it exists.</span></span> <span data-ttu-id="0b567-130">En este caso, al asignar el elemento convertido a un tipo de referencia que acepta valores NULL o a un tipo de valor que acepta valores NULL, si el elemento no existe, la variable asignada se establece en `null`.</span><span class="sxs-lookup"><span data-stu-id="0b567-130">In this case, when you assign the casted element to a nullable reference type or nullable value type, if the element does not exist, the assigned variable is set to `null`.</span></span> <span data-ttu-id="0b567-131">El código siguiente demuestra que cuando el elemento podría existir o no, resulta más fácil usar la conversión que la propiedad <xref:System.Xml.Linq.XElement.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="0b567-131">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
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
  
 <span data-ttu-id="0b567-132">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0b567-132">This code produces the following output:</span></span>  
  
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
  
 <span data-ttu-id="0b567-133">Por lo general, puede escribir un código más simple al usar la conversión para recuperar el contenido de los elementos y los atributos.</span><span class="sxs-lookup"><span data-stu-id="0b567-133">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b567-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b567-134">See also</span></span>

- [<span data-ttu-id="0b567-135">Ejes de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="0b567-135">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
