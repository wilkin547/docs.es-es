---
title: Atomización previa de objetos XName (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 06ea104b-f44c-4bb2-9c34-889ae025c80d
ms.openlocfilehash: c0e75afa797d2b20f32fc55e6c19d0c1593d174c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740782"
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-visual-basic"></a><span data-ttu-id="a5e12-102">Atomización previa de objetos XName (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5e12-102">Pre-Atomization of XName Objects (LINQ to XML) (Visual Basic)</span></span>

<span data-ttu-id="a5e12-103">Una manera de mejorar el rendimiento en LINQ to XML es realizar una atomización previa de los objetos <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="a5e12-103">One way to improve performance in LINQ to XML is to pre-atomize <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="a5e12-104">La atomización previa significa que asigna una cadena a un <xref:System.Xml.Linq.XName> objeto antes de crear el árbol XML mediante los constructores de las clases <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a5e12-104">Pre-atomization means that you assign a string to an <xref:System.Xml.Linq.XName> object before you create the XML tree by using the constructors of the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> classes.</span></span> <span data-ttu-id="a5e12-105">A continuación, en lugar de pasar una cadena al constructor, que utilizaría la conversión implícita de cadena a <xref:System.Xml.Linq.XName>, pasa el objeto <xref:System.Xml.Linq.XName> inicializado.</span><span class="sxs-lookup"><span data-stu-id="a5e12-105">Then, instead of passing a string to the constructor, which would use the implicit conversion from string to <xref:System.Xml.Linq.XName>, you pass the initialized <xref:System.Xml.Linq.XName> object.</span></span>

<span data-ttu-id="a5e12-106">Esto mejora el rendimiento si crear un árbol XML de gran tamaño en el que se repiten nombres específicos.</span><span class="sxs-lookup"><span data-stu-id="a5e12-106">This improves performance when you create a large XML tree in which specific names are repeated.</span></span> <span data-ttu-id="a5e12-107">Para ello, debe declarar e inicializar los objetos <xref:System.Xml.Linq.XName> antes de construir el árbol XML y, a continuación, utilizar los objetos <xref:System.Xml.Linq.XName> en lugar de especificar las cadenas para los nombres de atributo y elemento.</span><span class="sxs-lookup"><span data-stu-id="a5e12-107">To do this, you declare and initialize <xref:System.Xml.Linq.XName> objects before you construct the XML tree, and then use the <xref:System.Xml.Linq.XName> objects instead of specifying strings for the element and attribute names.</span></span> <span data-ttu-id="a5e12-108">Esta técnica puede producir un aumento significativo del rendimiento si va a crear un gran número de elementos (o atributos) con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="a5e12-108">This technique can yield significant performance gains if you are creating a large number of elements (or attributes) with the same name.</span></span>

<span data-ttu-id="a5e12-109">Debería probar la atomización previa con su situación para decidir si debe utilizarla.</span><span class="sxs-lookup"><span data-stu-id="a5e12-109">You should test pre-atomization with your scenario to decide if you should use it.</span></span>

## <a name="example"></a><span data-ttu-id="a5e12-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a5e12-110">Example</span></span>

<span data-ttu-id="a5e12-111">En el siguiente ejemplo se muestra esto:</span><span class="sxs-lookup"><span data-stu-id="a5e12-111">The following example demonstrates this:</span></span>

```vb
Dim root1 As XName = "Root"
Dim data As XName = "Data"
Dim id As XName = "ID"

Dim root2 As New XElement(root1, New XElement(data, New XAttribute(id, "1"), "4,100,000"),
                          New XElement(data, New XAttribute(id, "2"), "3,700,000"),
                          New XElement(data, New XAttribute(id, "3"), "1,150,000"))

Console.WriteLine(root2)
```

<span data-ttu-id="a5e12-112">En este ejemplo se produce la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="a5e12-112">This example produces the following output:</span></span>

```xml
<Root>
  <Data ID="1">4,100,000</Data>
  <Data ID="2">3,700,000</Data>
  <Data ID="3">1,150,000</Data>
</Root>
```

<span data-ttu-id="a5e12-113">En el siguiente ejemplo se muestra la misma técnica donde el documento XML se encuentra en un espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="a5e12-113">The following example shows the same technique where the XML document is in a namespace:</span></span>

```vb
Dim aw As XNamespace = "http://www.adventure-works.com"
Dim root1 As XName = aw + "Root"
Dim data As XName = aw + "Data"
Dim id As XName = "ID"

Dim root2 As New XElement(root1, New XAttribute(XNamespace.Xmlns + "aw", aw),
                          New XElement(data, New XAttribute(id, "1"), "4,100,000"),
                          New XElement(data, New XAttribute(id, "2"), "3,700,000"),
                          New XElement(data, New XAttribute(id, "3"), "1,150,000"))

Console.WriteLine(root2)
```

<span data-ttu-id="a5e12-114">En este ejemplo se produce la siguiente salida:</span><span class="sxs-lookup"><span data-stu-id="a5e12-114">This example produces the following output:</span></span>

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com">
  <aw:Data ID="1">4,100,000</aw:Data>
  <aw:Data ID="2">3,700,000</aw:Data>
  <aw:Data ID="3">1,150,000</aw:Data>
</aw:Root>
```

<span data-ttu-id="a5e12-115">El ejemplo siguiente es más similar a lo que probablemente encontrará en el mundo real.</span><span class="sxs-lookup"><span data-stu-id="a5e12-115">The following example is more similar to what you will likely encounter in the real world.</span></span> <span data-ttu-id="a5e12-116">En este ejemplo, una consulta proporciona el contenido del elemento:</span><span class="sxs-lookup"><span data-stu-id="a5e12-116">In this example, the content of the element is supplied by a query:</span></span>

```vb
Dim root1 As XName = "Root"
Dim data As XName = "Data"
Dim id As XName = "ID"
  
Dim sw As Stopwatch = Stopwatch.StartNew()
Dim root2 As New XElement(root1, From i In Enumerable.Range(1, 100000)
                                 Select New XElement(data, New XAttribute(ID, i), i * 5))
sw.Stop()
Console.WriteLine($"Time to construct: {sw.ElapsedMilliseconds} milliseconds")
```  

<span data-ttu-id="a5e12-117">El ejemplo anterior se ejecuta mejor que el siguiente, en el que los nombres no se atomizan previamente:</span><span class="sxs-lookup"><span data-stu-id="a5e12-117">The previous example performs better than the following example, in which names are not pre-atomized:</span></span>

```vb
Dim sw As Stopwatch = Stopwatch.StartNew()
Dim root As New XElement("Root", From i In Enumerable.Range(1, 100000)
                                 Select New XElement("Data", New XAttribute("ID", i), i * 5))
sw.Stop()
Console.WriteLine($"Time to construct: {sw.ElapsedMilliseconds} milliseconds")
```

## <a name="see-also"></a><span data-ttu-id="a5e12-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a5e12-118">See also</span></span>

- [<span data-ttu-id="a5e12-119">Rendimiento (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5e12-119">Performance (LINQ to XML) (Visual Basic)</span></span>](performance-linq-to-xml.md)
- [<span data-ttu-id="a5e12-120">Objetos XName y XNamespace atomizados (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5e12-120">Atomized XName and XNamespace Objects (LINQ to XML) (Visual Basic)</span></span>](atomized-xname-and-xnamespace-objects-linq-to-xml.md)
