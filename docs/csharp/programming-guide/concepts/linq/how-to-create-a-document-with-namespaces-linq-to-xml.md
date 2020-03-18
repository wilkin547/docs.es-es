---
title: Procedimiento para crear un documento con espacios de nombres (C#) (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 37e63c57-f86d-47ac-88a7-2c2d107def30
ms.openlocfilehash: 429b0b0b41f2201b983f931e469b25ff406b91ac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141325"
---
# <a name="how-to-create-a-document-with-namespaces-c-linq-to-xml"></a><span data-ttu-id="0d0c8-102">Procedimiento para crear un documento con espacios de nombres (C#) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="0d0c8-102">How to create a document with namespaces (C#) (LINQ to XML)</span></span>
<span data-ttu-id="0d0c8-103">En este tema se muestra cómo crear documentos con espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-103">This topic shows how to create documents with namespaces.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d0c8-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d0c8-104">Example</span></span>  
 <span data-ttu-id="0d0c8-105">Para crear un elemento o un atributo que se encuentra en un espacio de nombres, primero debe declarar e inicializar un objeto <xref:System.Xml.Linq.XNamespace>.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-105">To create an element or an attribute that is in a namespace, you first declare and initialize an <xref:System.Xml.Linq.XNamespace> object.</span></span> <span data-ttu-id="0d0c8-106">A continuación debe utilizar la sobrecarga del operador de suma para combinar el espacio de nombres con el nombre local, expresado como una cadena.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-106">You then use the addition operator overload to combine the namespace with the local name, expressed as a string.</span></span>  
  
 <span data-ttu-id="0d0c8-107">En el ejemplo siguiente se crea un documento con un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-107">The following example creates a document with one namespace.</span></span> <span data-ttu-id="0d0c8-108">De forma predeterminada, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] serializa este documento con un espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-108">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] serializes this document with a default namespace.</span></span>  
  
```csharp  
// Create an XML tree in a namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="0d0c8-109">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0d0c8-109">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child>child content</Child>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="0d0c8-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d0c8-110">Example</span></span>  
 <span data-ttu-id="0d0c8-111">En el ejemplo siguiente se crea un documento con un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-111">The following example creates a document with one namespace.</span></span> <span data-ttu-id="0d0c8-112">También crea un atributo que declara el espacio de nombres con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-112">It also creates an attribute that declares the namespace with a namespace prefix.</span></span> <span data-ttu-id="0d0c8-113">Para crear un atributo que declara un espacio de nombres con un prefijo, debe crearlo de modo que el nombre del atributo sea el prefijo del espacio de nombres y el nombre se encuentre en el espacio de nombres <xref:System.Xml.Linq.XNamespace.Xmlns%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-113">To create an attribute that declares a namespace with a prefix, you create an attribute where the name of the attribute is the namespace prefix, and this name is in the <xref:System.Xml.Linq.XNamespace.Xmlns%2A> namespace.</span></span> <span data-ttu-id="0d0c8-114">El valor de este atributo es el URI del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-114">The value of this attribute is the URI of the namespace.</span></span>  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="0d0c8-115">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0d0c8-115">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="0d0c8-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d0c8-116">Example</span></span>  
 <span data-ttu-id="0d0c8-117">El ejemplo siguiente muestra la creación de un documento que contiene dos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-117">The following example shows the creation of a document that contains two namespaces.</span></span> <span data-ttu-id="0d0c8-118">Uno es el espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-118">One is the default namespace.</span></span> <span data-ttu-id="0d0c8-119">El otro es un espacio de nombres con un prefijo.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-119">Another is a namespace with a prefix.</span></span>  
  
 <span data-ttu-id="0d0c8-120">Mediante la inclusión de los atributos de espacio de nombres en el elemento raíz, los espacios de nombres se serializan de modo que `http://www.adventure-works.com` sea el espacio de nombres predeterminado y `www.fourthcoffee.com` se serialice con un prefijo "fc".</span><span class="sxs-lookup"><span data-stu-id="0d0c8-120">By including namespace attributes in the root element, the namespaces are serialized so that `http://www.adventure-works.com` is the default namespace, and `www.fourthcoffee.com` is serialized with a prefix of "fc".</span></span> <span data-ttu-id="0d0c8-121">Para crear un atributo que declare un espacio de nombres predeterminado, debe crear un atributo con el nombre "xmlns", sin un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-121">To create an attribute that declares a default namespace, you create an attribute with the name "xmlns", without a namespace.</span></span> <span data-ttu-id="0d0c8-122">El valor del atributo es el URI del espacio de nombres predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-122">The value of the attribute is the default namespace URI.</span></span>  
  
```csharp  
// The http://www.adventure-works.com namespace is forced to be the default namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute("xmlns", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="0d0c8-123">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0d0c8-123">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <DifferentChild>other content</DifferentChild>  
  </fc:Child>  
  <Child2>c2 content</Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="0d0c8-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d0c8-124">Example</span></span>  
 <span data-ttu-id="0d0c8-125">En el ejemplo siguiente se crea un documento que contiene dos espacios de nombres, todos ellos con prefijos de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-125">The following example creates a document that contains two namespaces, both with namespace prefixes.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", aw.NamespaceName),  
    new XAttribute(XNamespace.Xmlns + "fc", fc.NamespaceName),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="0d0c8-126">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0d0c8-126">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="0d0c8-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0d0c8-127">Example</span></span>  
 <span data-ttu-id="0d0c8-128">Otro método para conseguir el mismo resultado consiste en usar nombres expandidos en lugar de declarar y crear un objeto <xref:System.Xml.Linq.XNamespace>.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-128">Another way to accomplish the same result is to use expanded names instead of declaring and creating an <xref:System.Xml.Linq.XNamespace> object.</span></span>  
  
 <span data-ttu-id="0d0c8-129">Este método tiene implicaciones en el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-129">This approach has performance implications.</span></span> <span data-ttu-id="0d0c8-130">Cada vez que pasa una cadena que contiene un nombre expandido a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] debe analizar el nombre, buscar el espacio de nombres atomizado y buscar el nombre atomizado.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-130">Each time you pass a string that contains an expanded name to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] must parse the name, find the atomized namespace, and find the atomized name.</span></span> <span data-ttu-id="0d0c8-131">Este proceso consume tiempo de la CPU.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-131">This process takes CPU time.</span></span> <span data-ttu-id="0d0c8-132">Si el rendimiento es importante, tal vez quiera declarar y usar explícitamente un objeto <xref:System.Xml.Linq.XNamespace>.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-132">If performance is important, you might want to declare and use an <xref:System.Xml.Linq.XNamespace> object explicitly.</span></span>  
  
 <span data-ttu-id="0d0c8-133">Si el rendimiento es un problema importante, vea [Atomización previa de objetos XName (LINQ to XML) (C#)](./pre-atomization-of-xname-objects-linq-to-xml.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="0d0c8-133">If performance is an important issue, see [Pre-Atomization of XName Objects (LINQ to XML) (C#)](./pre-atomization-of-xname-objects-linq-to-xml.md) for more information</span></span>  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XElement root = new XElement("{http://www.adventure-works.com}Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement("{http://www.adventure-works.com}Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="0d0c8-134">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0d0c8-134">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d0c8-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d0c8-135">See also</span></span>

- [<span data-ttu-id="0d0c8-136">Información general sobre los espacios de nombres (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0d0c8-136">Namespaces Overview (LINQ to XML) (C#)</span></span>](namespaces-overview-linq-to-xml.md)
