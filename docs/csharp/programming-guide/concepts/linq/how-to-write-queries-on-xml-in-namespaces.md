---
title: Escribir consultas de XML en espacios de nombres (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 7c54df81-15e4-4091-8c81-a87637029130
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 54d8c876ca5f8c6d721eaab13515e70f23a68744
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-queries-on-xml-in-namespaces-c"></a><span data-ttu-id="5ab38-102">Escribir consultas de XML en espacios de nombres (C#)</span><span class="sxs-lookup"><span data-stu-id="5ab38-102">How to: Write Queries on XML in Namespaces (C#)</span></span>
<span data-ttu-id="5ab38-103">Para escribir una consulta en XML que esté en un espacio de nombres, debe usar objetos <xref:System.Xml.Linq.XName> que tengan el espacio de nombres correcto.</span><span class="sxs-lookup"><span data-stu-id="5ab38-103">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="5ab38-104">Para C#, el enfoque más común consiste en inicializar un objeto <xref:System.Xml.Linq.XNamespace> usando una cadena que contiene el identificador URI y, después, usar la sobrecarga del operador de suma para combinar el espacio de nombres con el nombre local.</span><span class="sxs-lookup"><span data-stu-id="5ab38-104">For C#, the most common approach is to initialize an <xref:System.Xml.Linq.XNamespace> using a string that contains the URI, then use the addition operator overload to combine the namespace with the local name.</span></span>  
  
 <span data-ttu-id="5ab38-105">En el primer conjunto de ejemplos de este tema se muestra cómo crear un árbol XML en un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5ab38-105">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="5ab38-106">En el segundo conjunto se muestra cómo crear un árbol XML en un espacio de nombres con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="5ab38-106">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ab38-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ab38-107">Example</span></span>  
 <span data-ttu-id="5ab38-108">En el ejemplo siguiente se crea un árbol XML que está en un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5ab38-108">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="5ab38-109">A continuación recupera una recopilación de elementos.</span><span class="sxs-lookup"><span data-stu-id="5ab38-109">It then retrieves a collection of elements.</span></span>  
  
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
  
 <span data-ttu-id="5ab38-110">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="5ab38-110">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="5ab38-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ab38-111">Example</span></span>  
 <span data-ttu-id="5ab38-112">En C#, las consultas se escribe de la misma forma, independientemente de si se escribe en un árbol XML que usa un espacio de nombres con un prefijo o en un árbol XML con un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5ab38-112">In C#, you write queries in the same way regardless of whether you are writing queries on an XML tree that uses a namespace with a prefix or on an XML tree with a default namespace.</span></span>  
  
 <span data-ttu-id="5ab38-113">En el ejemplo siguiente se crea un árbol XML que está en un espacio de nombres con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="5ab38-113">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="5ab38-114">A continuación recupera una recopilación de elementos.</span><span class="sxs-lookup"><span data-stu-id="5ab38-114">It then retrieves a collection of elements.</span></span>  
  
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
  
 <span data-ttu-id="5ab38-115">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="5ab38-115">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ab38-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ab38-116">See Also</span></span>  
 [<span data-ttu-id="5ab38-117">Trabajar con espacios de nombres XML (C#)</span><span class="sxs-lookup"><span data-stu-id="5ab38-117">Working with XML Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)

