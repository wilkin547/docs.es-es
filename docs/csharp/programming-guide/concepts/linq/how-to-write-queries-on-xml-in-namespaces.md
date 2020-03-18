---
title: Procedimiento para escribir consultas de XML en espacios de nombres (C#)
ms.date: 07/20/2015
ms.assetid: 7c54df81-15e4-4091-8c81-a87637029130
ms.openlocfilehash: a8b8d55daaad1ae00e43fed897080ed7a62fafab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75337370"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-c"></a><span data-ttu-id="b7317-102">Procedimiento para escribir consultas de XML en espacios de nombres (C#)</span><span class="sxs-lookup"><span data-stu-id="b7317-102">How to write queries on XML in namespaces (C#)</span></span>
<span data-ttu-id="b7317-103">Para escribir una consulta en XML que esté en un espacio de nombres, debe usar objetos <xref:System.Xml.Linq.XName> que tengan el espacio de nombres correcto.</span><span class="sxs-lookup"><span data-stu-id="b7317-103">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="b7317-104">Para C#, el enfoque más común consiste en inicializar un objeto <xref:System.Xml.Linq.XNamespace> usando una cadena que contiene el identificador URI y, después, usar la sobrecarga del operador de suma para combinar el espacio de nombres con el nombre local.</span><span class="sxs-lookup"><span data-stu-id="b7317-104">For C#, the most common approach is to initialize an <xref:System.Xml.Linq.XNamespace> using a string that contains the URI, then use the addition operator overload to combine the namespace with the local name.</span></span>  
  
 <span data-ttu-id="b7317-105">En el primer conjunto de ejemplos de este tema se muestra cómo crear un árbol XML en un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b7317-105">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="b7317-106">En el segundo conjunto se muestra cómo crear un árbol XML en un espacio de nombres con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="b7317-106">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7317-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b7317-107">Example</span></span>  
 <span data-ttu-id="b7317-108">En el ejemplo siguiente se crea un árbol XML que está en un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b7317-108">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="b7317-109">A continuación recupera una recopilación de elementos.</span><span class="sxs-lookup"><span data-stu-id="b7317-109">It then retrieves a collection of elements.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 <span data-ttu-id="b7317-110">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b7317-110">This example produces the following output:</span></span>  
  
```output  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="b7317-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b7317-111">Example</span></span>  
 <span data-ttu-id="b7317-112">En C#, las consultas se escribe de la misma forma, independientemente de si se escribe en un árbol XML que usa un espacio de nombres con un prefijo o en un árbol XML con un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b7317-112">In C#, you write queries in the same way regardless of whether you are writing queries on an XML tree that uses a namespace with a prefix or on an XML tree with a default namespace.</span></span>  
  
 <span data-ttu-id="b7317-113">En el ejemplo siguiente se crea un árbol XML que está en un espacio de nombres con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="b7317-113">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="b7317-114">A continuación recupera una recopilación de elementos.</span><span class="sxs-lookup"><span data-stu-id="b7317-114">It then retrieves a collection of elements.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
    <aw:Child>1</aw:Child>  
    <aw:Child>2</aw:Child>  
    <aw:Child>3</aw:Child>  
    <aw:AnotherChild>4</aw:AnotherChild>  
    <aw:AnotherChild>5</aw:AnotherChild>  
    <aw:AnotherChild>6</aw:AnotherChild>  
</aw:Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 <span data-ttu-id="b7317-115">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b7317-115">This example produces the following output:</span></span>  
  
```output  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7317-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7317-116">See also</span></span>

- [<span data-ttu-id="b7317-117">Información general sobre los espacios de nombres (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b7317-117">Namespaces Overview (LINQ to XML) (C#)</span></span>](namespaces-overview-linq-to-xml.md)
