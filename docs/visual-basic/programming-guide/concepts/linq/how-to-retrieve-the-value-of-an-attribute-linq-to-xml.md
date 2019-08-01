---
title: Procedimiento Recuperar el valor de un atributo (LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 5f4b3790-c83f-4eb3-a889-e3587edf3ca1
ms.openlocfilehash: d03b2b146ad2f6b796ba6589cf99d06aa429535d
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710502"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-visual-basic"></a><span data-ttu-id="c68cf-102">Procedimiento Recuperar el valor de un atributo (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c68cf-102">How to: Retrieve the Value of an Attribute (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="c68cf-103">Este tema muestra cómo obtener el valor de los atributos.</span><span class="sxs-lookup"><span data-stu-id="c68cf-103">This topic shows how to obtain the value of attributes.</span></span> <span data-ttu-id="c68cf-104">Existen dos formas principales: puede convertir un elemento <xref:System.Xml.Linq.XAttribute> al tipo deseado; el operador de conversión explícita convierte el contenido del elemento o del atributo al tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="c68cf-104">There are two main ways: You can cast an <xref:System.Xml.Linq.XAttribute> to the desired type; the explicit conversion operator then converts the contents of the element or attribute to the specified type.</span></span> <span data-ttu-id="c68cf-105">Como alternativa, puede usar la propiedad <xref:System.Xml.Linq.XAttribute.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="c68cf-105">Alternatively, you can use the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span> <span data-ttu-id="c68cf-106">Sin embargo, la conversión suele ser el mejor método.</span><span class="sxs-lookup"><span data-stu-id="c68cf-106">However, casting is generally the better approach.</span></span> <span data-ttu-id="c68cf-107">Si convierte el atributo a un tipo que admite valores NULL, resulta más fácil escribir el código al recuperar el valor de un atributo que podría existir o no.</span><span class="sxs-lookup"><span data-stu-id="c68cf-107">If you cast the attribute to a nullable type, the code is simpler to write when retrieving the value of an attribute that might or might not exist.</span></span> <span data-ttu-id="c68cf-108">Para obtener ejemplos de esta técnica, vea [Cómo: Recupera el valor de un elemento (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c68cf-108">For examples of this technique, see [How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c68cf-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c68cf-109">Example</span></span>  
 <span data-ttu-id="c68cf-110">En Visual Basic, puede usar la propiedad del atributo integrado para recuperar el valor de un atributo.</span><span class="sxs-lookup"><span data-stu-id="c68cf-110">In Visual Basic, you can use the integrated attribute property to retrieve the value of an attribute.</span></span>  
  
```vb  
Dim root As XElement = <Root Attr="abcde"/>  
Console.WriteLine(root)  
Dim str As String = root.@Attr  
Console.WriteLine(str)  
```  
  
 <span data-ttu-id="c68cf-111">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c68cf-111">This example produces the following output:</span></span>  
  
```xml  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a><span data-ttu-id="c68cf-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c68cf-112">Example</span></span>  
 <span data-ttu-id="c68cf-113">En Visual Basic, puede usar la propiedad del atributo integrado para establecer el valor de un atributo.</span><span class="sxs-lookup"><span data-stu-id="c68cf-113">In Visual Basic, you can use the integrated attribute property to set the value of an attribute.</span></span> <span data-ttu-id="c68cf-114">Asimismo, si usa la propiedad del atributo integrado para establecer el valor de un atributo que no existe, se creará el atributo.</span><span class="sxs-lookup"><span data-stu-id="c68cf-114">Further, if you use the integrated attribute property to set the value of an attribute that does not exist, the attribute will be created.</span></span>  
  
```vb  
Dim root As XElement = <Root Att1="content"/>  
root.@Att1 = "new content"  
root.@Att2 = "new attribute"  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="c68cf-115">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c68cf-115">This example produces the following output:</span></span>  
  
```xml  
<Root Att1="new content" Att2="new attribute" />  
```  
  
## <a name="example"></a><span data-ttu-id="c68cf-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c68cf-116">Example</span></span>  
 <span data-ttu-id="c68cf-117">El siguiente ejemplo muestra cómo recuperar el valor de un atributo, en el que el atributo se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="c68cf-117">The following example shows how to retrieve the value of an attribute where the attribute is in a namespace.</span></span> <span data-ttu-id="c68cf-118">Para obtener más información, vea [información general sobre los espacios de nombres (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c68cf-118">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root aw:Attr="abcde"/>  
        Dim str As String = root.@aw:Attr  
        Console.WriteLine(str)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="c68cf-119">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="c68cf-119">This example produces the following output:</span></span>  
  
```  
abcde  
```  
  
## <a name="see-also"></a><span data-ttu-id="c68cf-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c68cf-120">See also</span></span>

- [<span data-ttu-id="c68cf-121">Ejes de LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c68cf-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
