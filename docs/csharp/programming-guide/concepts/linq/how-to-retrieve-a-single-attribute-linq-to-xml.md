---
title: Procedimiento para recuperar un único atributo (LINQ to XML) (C#)
description: Aprenda a usar LINQ to XML para recuperar un solo atributo de un elemento de C#, dado el nombre del atributo.
ms.date: 07/20/2015
ms.assetid: 1b6b07b9-933f-47e9-874e-e790cab49dc5
ms.openlocfilehash: 4efcae5324ad5a2e4664e68e35e15ec2053daece
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103440"
---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-c"></a><span data-ttu-id="557ff-103">Procedimiento para recuperar un único atributo (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="557ff-103">How to retrieve a single attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="557ff-104">Este tema explica cómo recuperar un atributo concreto de un elemento, proporcionando el nombre del atributo.</span><span class="sxs-lookup"><span data-stu-id="557ff-104">This topic explains how to retrieve a single attribute of an element, given the attribute name.</span></span> <span data-ttu-id="557ff-105">Esto puede resultar útil para escribir expresiones de consulta mediante las cuales encontrar un elemento que contiene un atributo en particular.</span><span class="sxs-lookup"><span data-stu-id="557ff-105">This is useful for writing query expressions where you want to find an element that has a particular attribute.</span></span>  
  
 <span data-ttu-id="557ff-106">El método <xref:System.Xml.Linq.XElement.Attribute%2A> de la clase <xref:System.Xml.Linq.XElement> devuelve el <xref:System.Xml.Linq.XAttribute> con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="557ff-106">The <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement> class returns the <xref:System.Xml.Linq.XAttribute> with the specified name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="557ff-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="557ff-107">Example</span></span>  
 <span data-ttu-id="557ff-108">El siguiente ejemplo utiliza el método <xref:System.Xml.Linq.XElement.Attribute%2A>.</span><span class="sxs-lookup"><span data-stu-id="557ff-108">The following example uses the <xref:System.Xml.Linq.XElement.Attribute%2A> method.</span></span>  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 <span data-ttu-id="557ff-109">Este ejemplo encuentra todos los descendientes en el árbol cuyo nombre es `Phone` y, a continuación, encuentra aquel atributo cuyo nombre es `type`.</span><span class="sxs-lookup"><span data-stu-id="557ff-109">This example finds all the descendants in the tree named `Phone`, and then finds the attribute named `type`.</span></span>  
  
 <span data-ttu-id="557ff-110">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="557ff-110">This code produces the following output:</span></span>  
  
```output  
home  
work  
```  
  
## <a name="example"></a><span data-ttu-id="557ff-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="557ff-111">Example</span></span>  
 <span data-ttu-id="557ff-112">Si desea recuperar el valor del atributo, puede convertirlo, de la misma forma que lo haría con los objetos <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="557ff-112">If you want to retrieve the value of the attribute, you can cast it, just as you do for with <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="557ff-113">En el siguiente ejemplo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="557ff-113">The following example demonstrates this.</span></span>  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 <span data-ttu-id="557ff-114">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="557ff-114">This code produces the following output:</span></span>  
  
```output  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="557ff-115">proporciona operadores de conversión explícita para la clase <xref:System.Xml.Linq.XAttribute> a `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` y `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="557ff-115">provides explicit cast operators for the <xref:System.Xml.Linq.XAttribute> class to `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="557ff-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="557ff-116">Example</span></span>  
 <span data-ttu-id="557ff-117">El siguiente ejemplo muestra el mismo código para un atributo que se encuentre en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="557ff-117">The following example shows the same code for an attribute that is in a namespace.</span></span> <span data-ttu-id="557ff-118">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="557ff-118">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement cust = new XElement(aw + "PhoneNumbers",  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "home"),  
        "555-555-5555"),  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants(aw + "Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute(aw + "type"));  
```  
  
 <span data-ttu-id="557ff-119">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="557ff-119">This code produces the following output:</span></span>  
  
```output  
home  
work  
```  
  
## <a name="see-also"></a><span data-ttu-id="557ff-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="557ff-120">See also</span></span>

- [<span data-ttu-id="557ff-121">Ejes de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="557ff-121">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
