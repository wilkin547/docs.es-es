---
title: Objetos XName y XNamespace atomizados (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 21ee7585-7df9-40b4-8c76-a12bb5f29bb3
ms.openlocfilehash: 6a94bc0f2fd8013997e233b300fa19c12671bf29
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84383694"
---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-visual-basic"></a><span data-ttu-id="17847-102">Objetos XName y XNamespace atomizados (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17847-102">Atomized XName and XNamespace Objects (LINQ to XML) (Visual Basic)</span></span>

<span data-ttu-id="17847-103">Los objetos <xref:System.Xml.Linq.XName> y <xref:System.Xml.Linq.XNamespace> se *atomizan*; es decir, si contienen el mismo nombre completo, hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="17847-103"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> objects are *atomized*; that is, if they contain the same qualified name, they refer to the same object.</span></span> <span data-ttu-id="17847-104">De esta forma, se incrementan los beneficios de rendimiento de las consultas: cuando compare la igualdad de dos nombres atomizados, el lenguaje intermedio subyacente solo debe determinar si los dos puntos de referencia apuntan al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="17847-104">This yields performance benefits for queries: When you compare two atomized names for equality, the underlying intermediate language only has to determine whether the two references point to the same object.</span></span> <span data-ttu-id="17847-105">El código subyacente no debe hacer comparaciones de cadenas, ya que sería un proceso muy lento.</span><span class="sxs-lookup"><span data-stu-id="17847-105">The underlying code does not have to do string comparisons, which would be time consuming.</span></span>

## <a name="atomization-semantics"></a><span data-ttu-id="17847-106">Semántica de atomización</span><span class="sxs-lookup"><span data-stu-id="17847-106">Atomization Semantics</span></span>

<span data-ttu-id="17847-107">Atomización significa que si dos objetos <xref:System.Xml.Linq.XName> tienen el mismo nombre local y se encuentran en el mismo espacio de nombres, comparten la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="17847-107">Atomization means that if two <xref:System.Xml.Linq.XName> objects have the same local name, and they are in the same namespace, they share the same instance.</span></span> <span data-ttu-id="17847-108">De igual forma, si dos objetos <xref:System.Xml.Linq.XNamespace> tienen el mismo URI de espacio de nombres, comparten la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="17847-108">In the same way, if two <xref:System.Xml.Linq.XNamespace> objects have the same namespace URI, they share the same instance.</span></span>

<span data-ttu-id="17847-109">Para que una clase habilite objetos atomizados, el constructor de la clase debe ser privado y no público.</span><span class="sxs-lookup"><span data-stu-id="17847-109">For a class to enable atomized objects, the constructor for the class must be private, not public.</span></span> <span data-ttu-id="17847-110">La razón es que si el constructor fuera público, podría crea un objeto no atomizado.</span><span class="sxs-lookup"><span data-stu-id="17847-110">This is because if the constructor were public, you could create a non-atomized object.</span></span> <span data-ttu-id="17847-111">Las clases <xref:System.Xml.Linq.XName> y <xref:System.Xml.Linq.XNamespace> implementan un operador de conversión implícita para convertir una cadena en <xref:System.Xml.Linq.XName> o <xref:System.Xml.Linq.XNamespace>.</span><span class="sxs-lookup"><span data-stu-id="17847-111">The <xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> classes implement an implicit conversion operator to convert a string into an <xref:System.Xml.Linq.XName> or <xref:System.Xml.Linq.XNamespace>.</span></span> <span data-ttu-id="17847-112">De esta forma, obtiene una instancia de estos objetos.</span><span class="sxs-lookup"><span data-stu-id="17847-112">This is how you get an instance of these objects.</span></span> <span data-ttu-id="17847-113">No puede obtener ninguna instancia mediante un constructor, ya que no se puede tener acceso a él.</span><span class="sxs-lookup"><span data-stu-id="17847-113">You cannot get an instance by using a constructor, because the constructor is inaccessible.</span></span>

<span data-ttu-id="17847-114"><xref:System.Xml.Linq.XName> y <xref:System.Xml.Linq.XNamespace> también implementan los operadores de igualdad y desigualdad, para determinar si los dos objetos que se comparan son referencias a la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="17847-114"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> also implement the equality and inequality operators, to determine whether the two objects being compared are references to the same instance.</span></span>

## <a name="example"></a><span data-ttu-id="17847-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17847-115">Example</span></span>

<span data-ttu-id="17847-116">El siguiente código crea algunos objetos <xref:System.Xml.Linq.XElement> y muestra que nombres idénticos comparten la misma instancia.</span><span class="sxs-lookup"><span data-stu-id="17847-116">The following code creates some <xref:System.Xml.Linq.XElement> objects and demonstrates that identical names share the same instance.</span></span>

```vb
Dim r1 As New XElement("Root", "data1")
Dim r2 As XElement = XElement.Parse("<Root>data2</Root>")

If DirectCast(r1.Name, Object) = DirectCast(r2.Name, Object) Then
    Console.WriteLine("r1 and r2 have names that refer to the same instance.")
Else
    Console.WriteLine("Different")
End If

Dim n As XName = "Root"

If DirectCast(n, Object) = DirectCast(r1.Name, Object) Then
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.")
Else
    Console.WriteLine("Different")
End If
```

<span data-ttu-id="17847-117">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="17847-117">This example produces the following output:</span></span>

```console
r1 and r2 have names that refer to the same instance.
The name of r1 and the name in 'n' refer to the same instance.
```

<span data-ttu-id="17847-118">Como se ha mencionado anteriormente, la ventaja de los objetos atomizados es que el usuario utiliza uno de los métodos de eje que toman <xref:System.Xml.Linq.XName> como parámetro, el método de eje solo debe determinar que los dos nombres hagan referencia a la misma instancia para seleccionar los elementos deseados.</span><span class="sxs-lookup"><span data-stu-id="17847-118">As mentioned earlier, the benefit of atomized objects is that when you use one of the axis methods that take an <xref:System.Xml.Linq.XName> as a parameter, the axis method only has to determine that two names reference the same instance to select the desired elements.</span></span>

<span data-ttu-id="17847-119">El siguiente ejemplo pasa <xref:System.Xml.Linq.XName> a la llamada del método <xref:System.Xml.Linq.XContainer.Descendants%2A>, cuyo rendimiento mejora gracias al patrón de atomización.</span><span class="sxs-lookup"><span data-stu-id="17847-119">The following example passes an <xref:System.Xml.Linq.XName> to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method call, which then has better performance because of the atomization pattern.</span></span>

```vb
Dim root As New XElement("Root", New XElement("C1", 1), New XElement("Z1", New XElement("C1", 2), New XElement("C1", 1)))

Dim query = From e In root.Descendants("C1") Where CInt(e) = 1e

For Each z As var In query
    Console.WriteLine(z)
Next
```

<span data-ttu-id="17847-120">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="17847-120">This example produces the following output:</span></span>

```xml
<C1>1</C1>
<C1>1</C1>
```

## <a name="see-also"></a><span data-ttu-id="17847-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="17847-121">See also</span></span>

- [<span data-ttu-id="17847-122">Rendimiento (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17847-122">Performance (LINQ to XML) (Visual Basic)</span></span>](performance-linq-to-xml.md)
