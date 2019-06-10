---
title: Procedimiento para buscar un elemento con un elemento secundario específico (C#)
ms.date: 07/20/2015
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: 71068774b93581fdd82a0fe57651bc7780ca1ef1
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66485573"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a><span data-ttu-id="a4763-102">Procedimiento para buscar un elemento con un elemento secundario específico (C#)</span><span class="sxs-lookup"><span data-stu-id="a4763-102">How to: Find an Element with a Specific Child Element (C#)</span></span>
<span data-ttu-id="a4763-103">Este tema muestra cómo encontrar un elemento en particular que tenga un elemento secundario con un valor específico.</span><span class="sxs-lookup"><span data-stu-id="a4763-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4763-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4763-104">Example</span></span>  
 <span data-ttu-id="a4763-105">El ejemplo busca el elemento `Test` que tenga un elemento secundario `CommandLine` con el valor de "Examp2.EXE".</span><span class="sxs-lookup"><span data-stu-id="a4763-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="a4763-106">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Configuración de prueba (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a4763-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="a4763-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="a4763-107">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="example"></a><span data-ttu-id="a4763-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4763-108">Example</span></span>  
 <span data-ttu-id="a4763-109">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a4763-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="a4763-110">Para obtener más información, vea [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md) (Trabajar con espacios de nombres XML [C#]).</span><span class="sxs-lookup"><span data-stu-id="a4763-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="a4763-111">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Configuración de prueba en un espacio de nombres](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md).</span><span class="sxs-lookup"><span data-stu-id="a4763-111">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfigInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<XElement> tests =  
    from el in root.Elements(ad + "Test")  
    where (string)el.Element(ad + "CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="a4763-112">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="a4763-112">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4763-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4763-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- <span data-ttu-id="a4763-114">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="a4763-114">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)</span></span>
- <span data-ttu-id="a4763-115">[Projection Operations (C#)](../../../../csharp/programming-guide/concepts/linq/projection-operations.md) (Operaciones de proyección [C#])</span><span class="sxs-lookup"><span data-stu-id="a4763-115">[Projection Operations (C#)](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)</span></span>
