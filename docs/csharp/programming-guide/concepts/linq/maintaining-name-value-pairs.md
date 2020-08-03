---
title: Mantener pares nombre/valor (C#)
description: LINQ to XML contiene métodos que facilitan el mantenimiento de pares nombre-valor, ya sea como atributos o como un conjunto de elementos secundarios.
ms.date: 07/20/2015
ms.assetid: 7b04b0f1-af64-42eb-8737-83f8861b5915
ms.openlocfilehash: 92a45d160cbb1ef470d93bf740d0b6f584681e72
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165274"
---
# <a name="maintaining-namevalue-pairs-c"></a><span data-ttu-id="6670c-103">Mantener pares nombre/valor (C#)</span><span class="sxs-lookup"><span data-stu-id="6670c-103">Maintaining Name/Value Pairs (C#)</span></span>
<span data-ttu-id="6670c-104">Son muchas las aplicaciones que necesitan mantener información que se almacena mejor en forma de pares de nombre/valor.</span><span class="sxs-lookup"><span data-stu-id="6670c-104">Many applications have to maintain information that is best kept as name/value pairs.</span></span> <span data-ttu-id="6670c-105">Esta información podría contener datos sobre configuración o valores globales.</span><span class="sxs-lookup"><span data-stu-id="6670c-105">This information might be configuration information or global settings.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="6670c-106">incluye métodos que facilitan la operación de mantener un conjunto de pares nombre/valor.</span><span class="sxs-lookup"><span data-stu-id="6670c-106">contains some methods that make it easy to keep a set of name/value pairs.</span></span> <span data-ttu-id="6670c-107">Puede almacenar la información como atributos o como un conjunto de elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="6670c-107">You can either keep the information as attributes or as a set of child elements.</span></span>  
  
 <span data-ttu-id="6670c-108">Una diferencia existente entre almacenar la información como atributos o como elementos secundarios es que los atributos tienen, como restricción, que solo puede existir un atributo con un nombre en particular para un elemento.</span><span class="sxs-lookup"><span data-stu-id="6670c-108">One difference between keeping the information as attributes or as child elements is that attributes have the constraint that there can be only one attribute with a particular name for an element.</span></span> <span data-ttu-id="6670c-109">Esto no se aplica a los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="6670c-109">This limitation does not apply to child elements.</span></span>  
  
## <a name="setattributevalue-and-setelementvalue"></a><span data-ttu-id="6670c-110">SetAttributeValue y SetElementValue</span><span class="sxs-lookup"><span data-stu-id="6670c-110">SetAttributeValue and SetElementValue</span></span>  
 <span data-ttu-id="6670c-111">Los dos métodos que facilitan el mantenimiento de pares nombre/valor son <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> y <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="6670c-111">The two methods that facilitate keeping name/value pairs are <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> and <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span></span> <span data-ttu-id="6670c-112">La semántica de ambos métodos es muy similar.</span><span class="sxs-lookup"><span data-stu-id="6670c-112">These two methods have similar semantics.</span></span>  
  
 <span data-ttu-id="6670c-113"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> permite agregar, modificar o eliminar atributos de un elemento.</span><span class="sxs-lookup"><span data-stu-id="6670c-113"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> can add, modify, or remove attributes of an element.</span></span>  
  
- <span data-ttu-id="6670c-114">Si llama al método <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con el nombre de un atributo que no existe, éste creará un nuevo atributo y lo agregará al elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="6670c-114">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an attribute that does not exist, the method creates a new attribute and adds it to the specified element.</span></span>  
  
- <span data-ttu-id="6670c-115">Si llama al método <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con el nombre de un atributo ya existente y con un contenido en particular, se sobrescribirán los contenidos del atributo con el contenido especificado.</span><span class="sxs-lookup"><span data-stu-id="6670c-115">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute and with some specified content, the contents of the attribute are replaced with the specified content.</span></span>  
  
- <span data-ttu-id="6670c-116">Si llama al método <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> con el nombre de un atributo ya existente y pasando nulo en el contenido, se eliminará el atributo de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="6670c-116">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute, and specify null for the content, the attribute is removed from its parent.</span></span>  
  
 <span data-ttu-id="6670c-117"><xref:System.Xml.Linq.XElement.SetElementValue%2A> permite agregar, modificar o eliminar elementos secundarios de un elemento.</span><span class="sxs-lookup"><span data-stu-id="6670c-117"><xref:System.Xml.Linq.XElement.SetElementValue%2A> can add, modify, or remove child elements of an element.</span></span>  
  
- <span data-ttu-id="6670c-118">Si llama al método <xref:System.Xml.Linq.XElement.SetElementValue%2A> con el nombre de un elemento secundario que no existe, éste creará un nuevo elemento y lo agregará al elemento especificado.</span><span class="sxs-lookup"><span data-stu-id="6670c-118">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of a child element that does not exist, the method creates a new element and adds it to the specified element.</span></span>  
  
- <span data-ttu-id="6670c-119">Si llama al método <xref:System.Xml.Linq.XElement.SetElementValue%2A> con el nombre de un elemento ya existente y con un contenido en particular, se sobrescribirán los contenidos del elemento con el contenido especificado.</span><span class="sxs-lookup"><span data-stu-id="6670c-119">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element and with some specified content, the contents of the element are replaced with the specified content.</span></span>  
  
- <span data-ttu-id="6670c-120">Si llama al método <xref:System.Xml.Linq.XElement.SetElementValue%2A> con el nombre de un elemento ya existente y pasando nulo en el contenido, se eliminará el elemento de su elemento primario.</span><span class="sxs-lookup"><span data-stu-id="6670c-120">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element, and specify null for the content, the element is removed from its parent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6670c-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6670c-121">Example</span></span>  
 <span data-ttu-id="6670c-122">El siguiente ejemplo crea un elemento que no tiene atributos.</span><span class="sxs-lookup"><span data-stu-id="6670c-122">The following example creates an element with no attributes.</span></span> <span data-ttu-id="6670c-123">A continuación, utiliza el método <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> para crear y mantener una lista de pares nombre/valor.</span><span class="sxs-lookup"><span data-stu-id="6670c-123">It then uses the <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22);  
root.SetAttributeValue("Left", 20);  
root.SetAttributeValue("Bottom", 122);  
root.SetAttributeValue("Right", 300);  
root.SetAttributeValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
  
// Replace the value of Top.  
root.SetAttributeValue("Top", 10);  
Console.WriteLine(root);  
  
// Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", null);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="6670c-124">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6670c-124">This example produces the following output:</span></span>  
  
```xml  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a><span data-ttu-id="6670c-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6670c-125">Example</span></span>  
 <span data-ttu-id="6670c-126">El siguiente ejemplo crea un elemento que no tiene elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="6670c-126">The following example creates an element with no child elements.</span></span> <span data-ttu-id="6670c-127">A continuación, utiliza el método <xref:System.Xml.Linq.XElement.SetElementValue%2A> para crear y mantener una lista de pares nombre/valor.</span><span class="sxs-lookup"><span data-stu-id="6670c-127">It then uses the <xref:System.Xml.Linq.XElement.SetElementValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22);  
root.SetElementValue("Left", 20);  
root.SetElementValue("Bottom", 122);  
root.SetElementValue("Right", 300);  
root.SetElementValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Replace the value of Top.  
root.SetElementValue("Top", 10);  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Remove DefaultColor.  
root.SetElementValue("DefaultColor", null);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="6670c-128">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="6670c-128">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Top>22</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6670c-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="6670c-129">See also</span></span>

- <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>
- <xref:System.Xml.Linq.XElement.SetElementValue%2A>
- [<span data-ttu-id="6670c-130">Modificar árboles XML (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="6670c-130">Modifying XML Trees (LINQ to XML) (C#)</span></span>](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md)
