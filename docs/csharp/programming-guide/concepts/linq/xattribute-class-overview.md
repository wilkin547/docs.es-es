---
title: Información general de la clase XAttribute (C#)
ms.date: 07/20/2015
ms.assetid: 5a630f24-f9ad-400e-831e-c14ebfc9e142
ms.openlocfilehash: 7a806314664c6319fc45cff0dddedbe38027059d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635670"
---
# <a name="xattribute-class-overview-c"></a><span data-ttu-id="558dd-102">Información general de la clase XAttribute (C#)</span><span class="sxs-lookup"><span data-stu-id="558dd-102">XAttribute Class Overview (C#)</span></span>
<span data-ttu-id="558dd-103">Los atributos son pares de nombre y valor asociados a un elemento.</span><span class="sxs-lookup"><span data-stu-id="558dd-103">Attributes are name/value pairs that are associated with an element.</span></span> <span data-ttu-id="558dd-104">La clase <xref:System.Xml.Linq.XAttribute> representa los atributos XML.</span><span class="sxs-lookup"><span data-stu-id="558dd-104">The <xref:System.Xml.Linq.XAttribute> class represents XML attributes.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="558dd-105">Información general</span><span class="sxs-lookup"><span data-stu-id="558dd-105">Overview</span></span>  
 <span data-ttu-id="558dd-106">Trabajar con atributos en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es similar a trabajar con elementos.</span><span class="sxs-lookup"><span data-stu-id="558dd-106">Working with attributes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is similar to working with elements.</span></span> <span data-ttu-id="558dd-107">Sus constructores son similares.</span><span class="sxs-lookup"><span data-stu-id="558dd-107">Their constructors are similar.</span></span> <span data-ttu-id="558dd-108">Los métodos que usa para recuperar colecciones de ellos también son similares.</span><span class="sxs-lookup"><span data-stu-id="558dd-108">The methods that you use to retrieve collections of them are similar.</span></span> <span data-ttu-id="558dd-109">Una expresión de consulta LINQ de una colección de atributos se parece mucho a una expresión de consulta LINQ de una colección de elementos.</span><span class="sxs-lookup"><span data-stu-id="558dd-109">A LINQ query expression for a collection of attributes looks very similar to a LINQ query expression for a collection of elements.</span></span>  
  
 <span data-ttu-id="558dd-110">Se conserva el orden en el que se agregaron los atributos a un elemento.</span><span class="sxs-lookup"><span data-stu-id="558dd-110">The order in which attributes were added to an element is preserved.</span></span> <span data-ttu-id="558dd-111">Es decir, cuando procese una iteración en los atributos, los verá en el mismo orden en el que se agregaron.</span><span class="sxs-lookup"><span data-stu-id="558dd-111">That is, when you iterate through the attributes, you see them in the same order that they were added.</span></span>  
  
## <a name="the-xattribute-constructor"></a><span data-ttu-id="558dd-112">El constructor XAttribute</span><span class="sxs-lookup"><span data-stu-id="558dd-112">The XAttribute Constructor</span></span>  
 <span data-ttu-id="558dd-113">El siguiente constructor de la clase <xref:System.Xml.Linq.XAttribute> es el que usará normalmente:</span><span class="sxs-lookup"><span data-stu-id="558dd-113">The following constructor of the <xref:System.Xml.Linq.XAttribute> class is the one that you will most commonly use:</span></span>  
  
|<span data-ttu-id="558dd-114">Constructor</span><span class="sxs-lookup"><span data-stu-id="558dd-114">Constructor</span></span>|<span data-ttu-id="558dd-115">Description</span><span class="sxs-lookup"><span data-stu-id="558dd-115">Description</span></span>|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|<span data-ttu-id="558dd-116">Crea un objeto <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="558dd-116">Creates an <xref:System.Xml.Linq.XAttribute> object.</span></span> <span data-ttu-id="558dd-117">El argumento `name` especifica el nombre del atributo; `content` especifica el contenido del atributo.</span><span class="sxs-lookup"><span data-stu-id="558dd-117">The `name` argument specifies the name of the attribute; `content` specifies the content of the attribute.</span></span>|  
  
### <a name="creating-an-element-with-an-attribute"></a><span data-ttu-id="558dd-118">Crear un elemento con un atributo</span><span class="sxs-lookup"><span data-stu-id="558dd-118">Creating an Element with an Attribute</span></span>  
 <span data-ttu-id="558dd-119">El siguiente código muestra la tarea habitual de crear un elemento que contiene un atributo:</span><span class="sxs-lookup"><span data-stu-id="558dd-119">The following code shows the common task of creating an element that contains an attribute:</span></span>  
  
```csharp  
XElement phone = new XElement("Phone",  
    new XAttribute("Type", "Home"),  
    "555-555-5555");  
Console.WriteLine(phone);  
```  
  
 <span data-ttu-id="558dd-120">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="558dd-120">This example produces the following output:</span></span>  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a><span data-ttu-id="558dd-121">Construcción funcional de los atributos</span><span class="sxs-lookup"><span data-stu-id="558dd-121">Functional Construction of Attributes</span></span>  
 <span data-ttu-id="558dd-122">Puede construir objetos <xref:System.Xml.Linq.XAttribute> de modo similar a la construcción de los objetos <xref:System.Xml.Linq.XElement>, tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="558dd-122">You can construct <xref:System.Xml.Linq.XAttribute> objects in-line with the construction of <xref:System.Xml.Linq.XElement> objects, as follows:</span></span>  
  
```csharp  
XElement c = new XElement("Customers",  
    new XElement("Customer",  
        new XElement("Name", "John Doe"),  
        new XElement("PhoneNumbers",  
            new XElement("Phone",  
                new XAttribute("type", "home"),  
                "555-555-5555"),  
            new XElement("Phone",  
                new XAttribute("type", "work"),  
                "666-666-6666")  
        )  
    )  
);  
Console.WriteLine(c);  
```  
  
 <span data-ttu-id="558dd-123">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="558dd-123">This example produces the following output:</span></span>  
  
```xml  
<Customers>  
  <Customer>  
    <Name>John Doe</Name>  
    <PhoneNumbers>  
      <Phone type="home">555-555-5555</Phone>  
      <Phone type="work">666-666-6666</Phone>  
    </PhoneNumbers>  
  </Customer>  
</Customers>  
```  
  
### <a name="attributes-are-not-nodes"></a><span data-ttu-id="558dd-124">Los atributos no son nodos</span><span class="sxs-lookup"><span data-stu-id="558dd-124">Attributes Are Not Nodes</span></span>  
 <span data-ttu-id="558dd-125">Existen algunas diferencias entre los atributos y los elementos.</span><span class="sxs-lookup"><span data-stu-id="558dd-125">There are some differences between attributes and elements.</span></span> <span data-ttu-id="558dd-126">Los objetos <xref:System.Xml.Linq.XAttribute> no son nodos en el árbol XML.</span><span class="sxs-lookup"><span data-stu-id="558dd-126"><xref:System.Xml.Linq.XAttribute> objects are not nodes in the XML tree.</span></span> <span data-ttu-id="558dd-127">Son pares de nombre y valor asociados a un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="558dd-127">They are name/value pairs associated with an XML element.</span></span> <span data-ttu-id="558dd-128">A diferencia de Document Object Model (DOM), esto refleja de manera más precisa la estructura del código XML.</span><span class="sxs-lookup"><span data-stu-id="558dd-128">In contrast to the Document Object Model (DOM), this more closely reflects the structure of XML.</span></span> <span data-ttu-id="558dd-129">Aunque los objetos <xref:System.Xml.Linq.XAttribute> no son realmente nodos en el árbol XML, trabajar con objetos <xref:System.Xml.Linq.XAttribute> es muy similar a trabajar con objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="558dd-129">Although <xref:System.Xml.Linq.XAttribute> objects are not actually nodes in the XML tree, working with <xref:System.Xml.Linq.XAttribute> objects is very similar to working with <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="558dd-130">Esta distinción solo resulta de importancia para los desarrolladores que escriban código que trabaje con árboles XML en el nivel de nodo.</span><span class="sxs-lookup"><span data-stu-id="558dd-130">This distinction is primarily important only to developers who are writing code that works with XML trees at the node level.</span></span> <span data-ttu-id="558dd-131">A muchos desarrolladores no les afecta esta distinción.</span><span class="sxs-lookup"><span data-stu-id="558dd-131">Many developers will not be concerned with this distinction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="558dd-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="558dd-132">See also</span></span>

- [<span data-ttu-id="558dd-133">Información general sobre la programación de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="558dd-133">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
