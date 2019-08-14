---
title: Procedimiento para recuperar el valor de un atributo (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
ms.openlocfilehash: e099c20a519563eba2a060320b36761ebe54e0f1
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710073"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-c"></a><span data-ttu-id="8665d-102">Procedimiento para recuperar el valor de un atributo (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="8665d-102">How to: Retrieve the Value of an Attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="8665d-103">Este tema muestra cómo obtener el valor de los atributos.</span><span class="sxs-lookup"><span data-stu-id="8665d-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="8665d-104">Existen dos formas principales: puede convertir un elemento <xref:System.Xml.Linq.XAttribute> al tipo deseado; el operador de conversión explícita convierte el contenido del elemento o del atributo al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="8665d-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="8665d-105">Como alternativa, puede usar la propiedad <xref:System.Xml.Linq.XAttribute.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="8665d-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="8665d-106">Sin embargo, la conversión suele ser el mejor método.</span><span class="sxs-lookup"><span data-stu-id="8665d-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="8665d-107">Si convierte el atributo a un tipo que admite valores NULL, resulta más fácil escribir el código al recuperar el valor de un atributo que podría existir o no.</span><span class="sxs-lookup"><span data-stu-id="8665d-107">If you cast the attribute to a nullable type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="8665d-108">Para obtener ejemplos de esta técnica, vea [Cómo: Recuperar el valor de un elemento (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8665d-108">For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8665d-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8665d-109">Example</span></span>  
 <span data-ttu-id="8665d-110">Para recuperar el valor de un atributo, basta con convertir el objeto <xref:System.Xml.Linq.XAttribute> al tipo deseado.</span><span class="sxs-lookup"><span data-stu-id="8665d-110">To retrieve the value of an attribute, you just cast the <xref:System.Xml.Linq.XAttribute> object to your desired type.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
                    new XAttribute("Attr", "abcde")  
                );  
Console.WriteLine(root);  
string str = (string)root.Attribute("Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="8665d-111">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8665d-111">This example produces the following output:</span></span>  
  
```  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="8665d-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8665d-112">Example</span></span>  
 <span data-ttu-id="8665d-113">El siguiente ejemplo muestra cómo recuperar el valor de un atributo, en el que el atributo se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="8665d-113">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="8665d-114">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8665d-114">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
                    new XAttribute(aw + "Attr", "abcde")  
                );  
string str = (string)root.Attribute(aw + "Attr");  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="8665d-115">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8665d-115">This example produces the following output:</span></span>  
  
```  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="8665d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8665d-116">See also</span></span>

- <span data-ttu-id="8665d-117">[LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md) (Ejes de LINQ to XML [C#])</span><span class="sxs-lookup"><span data-stu-id="8665d-117">[LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)</span></span>
