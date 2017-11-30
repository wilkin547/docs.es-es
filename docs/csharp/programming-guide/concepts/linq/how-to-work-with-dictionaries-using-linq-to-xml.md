---
title: "Cómo: Trabajar con diccionarios mediante LINQ to XML (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 57bcefe3-8433-4d3b-935a-511c9bcbdfa8
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 422b9381596e06214e6116a3ba3c9d2b63c8651f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-c"></a><span data-ttu-id="2c733-102">Cómo: Trabajar con diccionarios mediante LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="2c733-102">How to: Work with Dictionaries Using LINQ to XML (C#)</span></span>
<span data-ttu-id="2c733-103">A menudo resulta cómodo convertir variedades de estructuras de datos a XML y de XML a otras estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="2c733-103">It is often convenient to convert varieties of data structures to XML, and XML back to other data structures.</span></span> <span data-ttu-id="2c733-104">Este tema muestra una implementación específica de este enfoque general convirtiendo un <xref:System.Collections.Generic.Dictionary%602> a XML y de XML.</span><span class="sxs-lookup"><span data-stu-id="2c733-104">This topic shows a specific implementation of this general approach by converting a <xref:System.Collections.Generic.Dictionary%602> to XML and back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c733-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2c733-105">Example</span></span>  
 <span data-ttu-id="2c733-106">En este ejemplo se usa una forma de construcción funcional en la que una consulta proyecta nuevos objetos <xref:System.Xml.Linq.XElement> y la colección resultante se pasa como argumento al constructor del objeto raíz <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="2c733-106">This example uses a form of functional construction in which a query projects new <xref:System.Xml.Linq.XElement> objects, and the resulting collection is passed as an argument to the constructor of the Root <xref:System.Xml.Linq.XElement> object.</span></span>  
  
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
  
 <span data-ttu-id="2c733-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="2c733-107">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="2c733-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2c733-108">Example</span></span>  
 <span data-ttu-id="2c733-109">El siguiente código genera un diccionario de XML.</span><span class="sxs-lookup"><span data-stu-id="2c733-109">The following code creates a dictionary from XML.</span></span>  
  
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
  
 <span data-ttu-id="2c733-110">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="2c733-110">This code produces the following output:</span></span>  
  
```  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c733-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c733-111">See Also</span></span>  
 [<span data-ttu-id="2c733-112">Proyecciones y transformaciones (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2c733-112">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
