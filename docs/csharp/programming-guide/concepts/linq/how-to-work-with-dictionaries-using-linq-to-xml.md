---
title: Procedimiento para trabajar con diccionarios mediante LINQ to XML (C#)
description: Aprenda a trabajar con diccionarios mediante LINQ to XML. Vea ejemplos de conversión de diccionarios a XML y de XML a otras estructuras de datos.
ms.date: 07/20/2015
ms.assetid: 57bcefe3-8433-4d3b-935a-511c9bcbdfa8
ms.openlocfilehash: bdba7a2b3dfc16fab1e239ac804c317dfefb7d9e
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302625"
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-c"></a><span data-ttu-id="8e67f-104">Procedimiento para trabajar con diccionarios mediante LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="8e67f-104">How to work with dictionaries using LINQ to XML (C#)</span></span>
<span data-ttu-id="8e67f-105">A menudo resulta cómodo convertir variedades de estructuras de datos a XML y de XML a otras estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="8e67f-105">It is often convenient to convert varieties of data structures to XML, and XML back to other data structures.</span></span> <span data-ttu-id="8e67f-106">Este tema muestra una implementación específica de este enfoque general convirtiendo un <xref:System.Collections.Generic.Dictionary%602> a XML y de XML.</span><span class="sxs-lookup"><span data-stu-id="8e67f-106">This topic shows a specific implementation of this general approach by converting a <xref:System.Collections.Generic.Dictionary%602> to XML and back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e67f-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8e67f-107">Example</span></span>  
 <span data-ttu-id="8e67f-108">En este ejemplo se usa una forma de construcción funcional en la que una consulta proyecta nuevos objetos <xref:System.Xml.Linq.XElement> y la colección resultante se pasa como argumento al constructor del objeto raíz <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="8e67f-108">This example uses a form of functional construction in which a query projects new <xref:System.Xml.Linq.XElement> objects, and the resulting collection is passed as an argument to the constructor of the Root <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```csharp  
Dictionary<string, string> dict = new Dictionary<string, string>();  
dict.Add("Child1", "Value1");  
dict.Add("Child2", "Value2");  
dict.Add("Child3", "Value3");  
dict.Add("Child4", "Value4");  
XElement root = new XElement("Root",  
    from keyValue in dict  
    select new XElement(keyValue.Key, keyValue.Value)  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="8e67f-109">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8e67f-109">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="8e67f-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8e67f-110">Example</span></span>  
 <span data-ttu-id="8e67f-111">El siguiente código genera un diccionario de XML.</span><span class="sxs-lookup"><span data-stu-id="8e67f-111">The following code creates a dictionary from XML.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "Value1"),  
    new XElement("Child2", "Value2"),  
    new XElement("Child3", "Value3"),  
    new XElement("Child4", "Value4")  
);  
  
Dictionary<string, string> dict = new Dictionary<string, string>();  
foreach (XElement el in root.Elements())  
    dict.Add(el.Name.LocalName, el.Value);  
foreach (string str in dict.Keys)  
    Console.WriteLine("{0}:{1}", str, dict[str]);  
```  
  
 <span data-ttu-id="8e67f-112">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="8e67f-112">This code produces the following output:</span></span>  
  
```output  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
