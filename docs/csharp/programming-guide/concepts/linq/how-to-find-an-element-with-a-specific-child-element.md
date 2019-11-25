---
title: Procedimiento para buscar un elemento con un elemento secundario específico (C#)
ms.date: 07/20/2015
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: 0536b1b92d4d7fc18b5d406bbcd24aefc6a840c6
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141148"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a><span data-ttu-id="0b358-102">Procedimiento para buscar un elemento con un elemento secundario específico (C#)</span><span class="sxs-lookup"><span data-stu-id="0b358-102">How to find an element with a specific child element (C#)</span></span>
<span data-ttu-id="0b358-103">Este tema muestra cómo encontrar un elemento en particular que tenga un elemento secundario con un valor específico.</span><span class="sxs-lookup"><span data-stu-id="0b358-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b358-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b358-104">Example</span></span>  
 <span data-ttu-id="0b358-105">El ejemplo busca el elemento `Test` que tenga un elemento secundario `CommandLine` con el valor de "Examp2.EXE".</span><span class="sxs-lookup"><span data-stu-id="0b358-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="0b358-106">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Configuración de prueba (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0b358-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="0b358-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0b358-107">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="example"></a><span data-ttu-id="0b358-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b358-108">Example</span></span>  
 <span data-ttu-id="0b358-109">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="0b358-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="0b358-110">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0b358-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="0b358-111">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Configuración de prueba en un espacio de nombres](./sample-xml-file-test-configuration-in-a-namespace1.md).</span><span class="sxs-lookup"><span data-stu-id="0b358-111">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](./sample-xml-file-test-configuration-in-a-namespace1.md).</span></span>  
  
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
  
 <span data-ttu-id="0b358-112">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0b358-112">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b358-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b358-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- <span data-ttu-id="0b358-114">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="0b358-114">[Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)</span></span>
- <span data-ttu-id="0b358-115">[Projection Operations (C#)](./projection-operations.md) (Operaciones de proyección [C#])</span><span class="sxs-lookup"><span data-stu-id="0b358-115">[Projection Operations (C#)](./projection-operations.md)</span></span>
