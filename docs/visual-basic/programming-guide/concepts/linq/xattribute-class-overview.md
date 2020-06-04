---
title: Información general de la clase XAttribute
ms.date: 07/20/2015
ms.assetid: 7781580a-9583-4a1b-ae1e-91c5936eb0b1
ms.openlocfilehash: 5b165044b4bea83e1a0789e3dd00367ed27b43e8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413211"
---
# <a name="xattribute-class-overview-visual-basic"></a><span data-ttu-id="54b05-102">Información general de la clase XAttribute (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54b05-102">XAttribute Class Overview (Visual Basic)</span></span>
<span data-ttu-id="54b05-103">Los atributos son pares de nombre y valor asociados a un elemento.</span><span class="sxs-lookup"><span data-stu-id="54b05-103">Attributes are name/value pairs that are associated with an element.</span></span> <span data-ttu-id="54b05-104">La clase <xref:System.Xml.Linq.XAttribute> representa los atributos XML.</span><span class="sxs-lookup"><span data-stu-id="54b05-104">The <xref:System.Xml.Linq.XAttribute> class represents XML attributes.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="54b05-105">Información general</span><span class="sxs-lookup"><span data-stu-id="54b05-105">Overview</span></span>  
 <span data-ttu-id="54b05-106">Trabajar con atributos en [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es similar a trabajar con elementos.</span><span class="sxs-lookup"><span data-stu-id="54b05-106">Working with attributes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is similar to working with elements.</span></span> <span data-ttu-id="54b05-107">Sus constructores son similares.</span><span class="sxs-lookup"><span data-stu-id="54b05-107">Their constructors are similar.</span></span> <span data-ttu-id="54b05-108">Los métodos que usa para recuperar colecciones de ellos también son similares.</span><span class="sxs-lookup"><span data-stu-id="54b05-108">The methods that you use to retrieve collections of them are similar.</span></span> <span data-ttu-id="54b05-109">Una expresión de consulta LINQ de una colección de atributos se parece mucho a una expresión de consulta LINQ de una colección de elementos.</span><span class="sxs-lookup"><span data-stu-id="54b05-109">A LINQ query expression for a collection of attributes looks very similar to a LINQ query expression for a collection of elements.</span></span>  
  
 <span data-ttu-id="54b05-110">Se conserva el orden en el que se agregaron los atributos a un elemento.</span><span class="sxs-lookup"><span data-stu-id="54b05-110">The order in which attributes were added to an element is preserved.</span></span> <span data-ttu-id="54b05-111">Es decir, cuando procese una iteración en los atributos, los verá en el mismo orden en el que se agregaron.</span><span class="sxs-lookup"><span data-stu-id="54b05-111">That is, when you iterate through the attributes, you see them in the same order that they were added.</span></span>  
  
## <a name="the-xattribute-constructor"></a><span data-ttu-id="54b05-112">El constructor XAttribute</span><span class="sxs-lookup"><span data-stu-id="54b05-112">The XAttribute Constructor</span></span>  
 <span data-ttu-id="54b05-113">El siguiente constructor de la clase <xref:System.Xml.Linq.XAttribute> es el que usará normalmente:</span><span class="sxs-lookup"><span data-stu-id="54b05-113">The following constructor of the <xref:System.Xml.Linq.XAttribute> class is the one that you will most commonly use:</span></span>  
  
|<span data-ttu-id="54b05-114">Constructor</span><span class="sxs-lookup"><span data-stu-id="54b05-114">Constructor</span></span>|<span data-ttu-id="54b05-115">Description</span><span class="sxs-lookup"><span data-stu-id="54b05-115">Description</span></span>|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|<span data-ttu-id="54b05-116">Crea un objeto <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="54b05-116">Creates an <xref:System.Xml.Linq.XAttribute> object.</span></span> <span data-ttu-id="54b05-117">El argumento `name` especifica el nombre del atributo; `content` especifica el contenido del atributo.</span><span class="sxs-lookup"><span data-stu-id="54b05-117">The `name` argument specifies the name of the attribute; `content` specifies the content of the attribute.</span></span>|  
  
### <a name="creating-an-element-with-an-attribute"></a><span data-ttu-id="54b05-118">Crear un elemento con un atributo</span><span class="sxs-lookup"><span data-stu-id="54b05-118">Creating an Element with an Attribute</span></span>  
 <span data-ttu-id="54b05-119">En el código siguiente se muestra un elemento que contiene un atributo utilizando literales XML en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="54b05-119">The following code shows an element that contains an attribute using XML literals in Visual Basic:</span></span>  
  
```vb  
Dim phone As XElement = <Phone Type="Home">555-555-5555</Phone>  
Console.WriteLine(phone)  
```  
  
 <span data-ttu-id="54b05-120">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="54b05-120">This example produces the following output:</span></span>  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a><span data-ttu-id="54b05-121">Construcción funcional de los atributos</span><span class="sxs-lookup"><span data-stu-id="54b05-121">Functional Construction of Attributes</span></span>  
 <span data-ttu-id="54b05-122">Puede construir objetos <xref:System.Xml.Linq.XAttribute> de modo similar a la construcción de los objetos <xref:System.Xml.Linq.XElement>, tal como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="54b05-122">You can construct <xref:System.Xml.Linq.XAttribute> objects in-line with the construction of <xref:System.Xml.Linq.XElement> objects, as follows:</span></span>  
  
```vb  
Dim c As XElement = _  
    <Customers>  
        <Customer>  
            <Name>John Doe</Name>  
            <PhoneNumbers>  
                <Phone type="home">555-555-5555</Phone>  
                <Phone type="work">666-666-6666</Phone>  
            </PhoneNumbers>  
        </Customer>  
    </Customers>  
Console.WriteLine(c)  
```  
  
 <span data-ttu-id="54b05-123">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="54b05-123">This example produces the following output:</span></span>  
  
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
  
### <a name="attributes-are-not-nodes"></a><span data-ttu-id="54b05-124">Los atributos no son nodos</span><span class="sxs-lookup"><span data-stu-id="54b05-124">Attributes Are Not Nodes</span></span>  
 <span data-ttu-id="54b05-125">Existen algunas diferencias entre los atributos y los elementos.</span><span class="sxs-lookup"><span data-stu-id="54b05-125">There are some differences between attributes and elements.</span></span> <span data-ttu-id="54b05-126">Los objetos <xref:System.Xml.Linq.XAttribute> no son nodos en el árbol XML.</span><span class="sxs-lookup"><span data-stu-id="54b05-126"><xref:System.Xml.Linq.XAttribute> objects are not nodes in the XML tree.</span></span> <span data-ttu-id="54b05-127">Son pares de nombre y valor asociados a un elemento XML.</span><span class="sxs-lookup"><span data-stu-id="54b05-127">They are name/value pairs associated with an XML element.</span></span> <span data-ttu-id="54b05-128">A diferencia de Document Object Model (DOM), esto refleja de manera más precisa la estructura del código XML.</span><span class="sxs-lookup"><span data-stu-id="54b05-128">In contrast to the Document Object Model (DOM), this more closely reflects the structure of XML.</span></span> <span data-ttu-id="54b05-129">Aunque los objetos <xref:System.Xml.Linq.XAttribute> no son realmente nodos en el árbol XML, trabajar con objetos <xref:System.Xml.Linq.XAttribute> es muy similar a trabajar con objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="54b05-129">Although <xref:System.Xml.Linq.XAttribute> objects are not actually nodes in the XML tree, working with <xref:System.Xml.Linq.XAttribute> objects is very similar to working with <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="54b05-130">Esta distinción solo resulta de importancia para los desarrolladores que escriban código que trabaje con árboles XML en el nivel de nodo.</span><span class="sxs-lookup"><span data-stu-id="54b05-130">This distinction is primarily important only to developers who are writing code that works with XML trees at the node level.</span></span> <span data-ttu-id="54b05-131">A muchos desarrolladores no les afecta esta distinción.</span><span class="sxs-lookup"><span data-stu-id="54b05-131">Many developers will not be concerned with this distinction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54b05-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="54b05-132">See also</span></span>

- [<span data-ttu-id="54b05-133">Información general sobre la programación de LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54b05-133">LINQ to XML Programming Overview (Visual Basic)</span></span>](linq-to-xml-programming-overview.md)
