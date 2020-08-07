---
title: Procedimiento para buscar un elemento con un elemento secundario específico (C#)
description: Aprenda a buscar un elemento que tenga un elemento secundario específico. Vea ejemplos de código y examine recursos adicionales.
ms.date: 07/20/2015
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: 1d02f3d3af0a3711a5361941727e2e0b6c8bbdc9
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301715"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a><span data-ttu-id="230a5-104">Procedimiento para buscar un elemento con un elemento secundario específico (C#)</span><span class="sxs-lookup"><span data-stu-id="230a5-104">How to find an element with a specific child element (C#)</span></span>
<span data-ttu-id="230a5-105">Este tema muestra cómo encontrar un elemento en particular que tenga un elemento secundario con un valor específico.</span><span class="sxs-lookup"><span data-stu-id="230a5-105">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="230a5-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="230a5-106">Example</span></span>  
 <span data-ttu-id="230a5-107">El ejemplo busca el elemento `Test` que tenga un elemento secundario `CommandLine` con el valor de "Examp2.EXE".</span><span class="sxs-lookup"><span data-stu-id="230a5-107">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="230a5-108">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Configuración de prueba (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="230a5-108">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="230a5-109">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="230a5-109">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="example"></a><span data-ttu-id="230a5-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="230a5-110">Example</span></span>  
 <span data-ttu-id="230a5-111">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="230a5-111">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="230a5-112">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="230a5-112">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="230a5-113">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Configuración de prueba en un espacio de nombres](./sample-xml-file-test-configuration-in-a-namespace1.md).</span><span class="sxs-lookup"><span data-stu-id="230a5-113">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](./sample-xml-file-test-configuration-in-a-namespace1.md).</span></span>  
  
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
  
 <span data-ttu-id="230a5-114">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="230a5-114">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="230a5-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="230a5-115">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="230a5-116">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="230a5-116">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="230a5-117">Operaciones de proyección (C#)</span><span class="sxs-lookup"><span data-stu-id="230a5-117">Projection Operations (C#)</span></span>](./projection-operations.md)
