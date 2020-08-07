---
title: Atomización previa de objetos XName (LINQ to XML) (C#)
description: Aprenda sobre la atomización previa de objetos XName. La atomización previa de los objetos mejora el rendimiento al crear un árbol XML de gran tamaño en el que se repiten nombres específicos.
ms.date: 07/20/2015
ms.assetid: e84fbbe7-f072-4771-bfbb-059d18e1ad15
ms.openlocfilehash: 4d217f6c78dc5d83ce424fb3ba95785f2dac0b73
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302833"
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-c"></a><span data-ttu-id="e44d5-104">Atomización previa de objetos XName (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="e44d5-104">Pre-Atomization of XName Objects (LINQ to XML) (C#)</span></span>
<span data-ttu-id="e44d5-105">Una manera de mejorar el rendimiento en LINQ to XML es realizar una atomización previa de los objetos <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="e44d5-105">One way to improve performance in LINQ to XML is to pre-atomize <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="e44d5-106">La atomización previa significa que asigna una cadena a un objeto <xref:System.Xml.Linq.XName> antes de crear el árbol XML utilizando los constructores de las clases <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e44d5-106">Pre-atomization means that you assign a string to an <xref:System.Xml.Linq.XName> object before you create the XML tree by using the constructors of the <xref:System.Xml.Linq.XElement> and  <xref:System.Xml.Linq.XAttribute> classes.</span></span> <span data-ttu-id="e44d5-107">A continuación, en lugar de pasar una cadena al constructor, que utilizaría la conversión implícita de cadena a <xref:System.Xml.Linq.XName>, pasa el objeto <xref:System.Xml.Linq.XName> inicializado.</span><span class="sxs-lookup"><span data-stu-id="e44d5-107">Then, instead of passing a string to the constructor, which would use the implicit conversion from string to <xref:System.Xml.Linq.XName>, you pass the initialized <xref:System.Xml.Linq.XName> object.</span></span>  
  
 <span data-ttu-id="e44d5-108">Esto mejora el rendimiento si crear un árbol XML de gran tamaño en el que se repiten nombres específicos.</span><span class="sxs-lookup"><span data-stu-id="e44d5-108">This improves performance when you create a large XML tree in which specific names are repeated.</span></span> <span data-ttu-id="e44d5-109">Para ello, debe declarar e inicializar los objetos <xref:System.Xml.Linq.XName> antes de construir el árbol XML y, a continuación, utilizar los objetos <xref:System.Xml.Linq.XName> en lugar de especificar las cadenas para los nombres de atributo y elemento.</span><span class="sxs-lookup"><span data-stu-id="e44d5-109">To do this, you declare and initialize <xref:System.Xml.Linq.XName> objects before you construct the XML tree, and then use the <xref:System.Xml.Linq.XName> objects instead of specifying strings for the element and attribute names.</span></span> <span data-ttu-id="e44d5-110">Esta técnica puede producir un aumento significativo del rendimiento si va a crear un gran número de elementos (o atributos) con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="e44d5-110">This technique can yield significant performance gains if you are creating a large number of elements (or attributes) with the same name.</span></span>  
  
 <span data-ttu-id="e44d5-111">Debería probar la atomización previa con su situación para decidir si debe utilizarla.</span><span class="sxs-lookup"><span data-stu-id="e44d5-111">You should test pre-atomization with your scenario to decide if you should use it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e44d5-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e44d5-112">Example</span></span>  
 <span data-ttu-id="e44d5-113">En el siguiente ejemplo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="e44d5-113">The following example demonstrates this.</span></span>  
  
```csharp  
XName Root = "Root";  
XName Data = "Data";  
XName ID = "ID";  
  
XElement root = new XElement(Root,  
    new XElement(Data,  
        new XAttribute(ID, "1"),  
        "4,100,000"),  
    new XElement(Data,  
        new XAttribute(ID, "2"),  
        "3,700,000"),  
    new XElement(Data,  
        new XAttribute(ID, "3"),  
        "1,150,000")  
);  
  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="e44d5-114">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e44d5-114">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Data ID="1">4,100,000</Data>  
  <Data ID="2">3,700,000</Data>  
  <Data ID="3">1,150,000</Data>  
</Root>  
```  
  
 <span data-ttu-id="e44d5-115">En el siguiente ejemplo se muestra la misma técnica donde el documento XML se encuentra en un espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="e44d5-115">The following example shows the same technique where the XML document is in a namespace:</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XName Root = aw + "Root";  
XName Data = aw + "Data";  
XName ID = "ID";  
  
XElement root = new XElement(Root,  
    new XAttribute(XNamespace.Xmlns + "aw", aw),  
    new XElement(Data,  
        new XAttribute(ID, "1"),  
        "4,100,000"),  
    new XElement(Data,  
        new XAttribute(ID, "2"),  
        "3,700,000"),  
    new XElement(Data,  
        new XAttribute(ID, "3"),  
        "1,150,000")  
);  
  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="e44d5-116">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e44d5-116">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Data ID="1">4,100,000</aw:Data>  
  <aw:Data ID="2">3,700,000</aw:Data>  
  <aw:Data ID="3">1,150,000</aw:Data>  
</aw:Root>  
```  
  
 <span data-ttu-id="e44d5-117">El ejemplo siguiente es más similar a lo que probablemente encontrará en el mundo real.</span><span class="sxs-lookup"><span data-stu-id="e44d5-117">The following example is more similar to what you will likely encounter in the real world.</span></span> <span data-ttu-id="e44d5-118">En este ejemplo, una consulta proporciona el contenido del elemento:</span><span class="sxs-lookup"><span data-stu-id="e44d5-118">In this example, the content of the element is supplied by a query:</span></span>  
  
```csharp  
XName Root = "Root";  
XName Data = "Data";  
XName ID = "ID";  
  
DateTime t1 = DateTime.Now;  
XElement root = new XElement(Root,  
    from i in System.Linq.Enumerable.Range(1, 100000)  
    select new XElement(Data,  
        new XAttribute(ID, i),  
        i * 5)  
);  
DateTime t2 = DateTime.Now;  
  
Console.WriteLine("Time to construct:{0}", t2 - t1);  
```  
  
 <span data-ttu-id="e44d5-119">El ejemplo anterior se ejecuta mejor que el siguiente, en el que los nombres no se atomizan previamente:</span><span class="sxs-lookup"><span data-stu-id="e44d5-119">The previous example performs better than the following example, in which names are not pre-atomized:</span></span>  
  
```csharp  
DateTime t1 = DateTime.Now;  
XElement root = new XElement("Root",  
    from i in System.Linq.Enumerable.Range(1, 100000)  
    select new XElement("Data",  
        new XAttribute("ID", i),  
        i * 5)  
);  
DateTime t2 = DateTime.Now;  
  
Console.WriteLine("Time to construct:{0}", t2 - t1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="e44d5-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e44d5-120">See also</span></span>

- [<span data-ttu-id="e44d5-121">Objetos XName y XNamespace atomizados (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="e44d5-121">Atomized XName and XNamespace Objects (LINQ to XML) (C#)</span></span>](./atomized-xname-and-xnamespace-objects-linq-to-xml.md)
