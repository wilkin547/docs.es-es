---
title: Coincidencia de nodos con XPathNavigator
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: e6848c47-ee5d-401a-89a5-50b5eed40f30
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 06849e20386f0eecb55fdf906f78896828b9946e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="matching-nodes-using-xpathnavigator"></a><span data-ttu-id="dbad5-102">Coincidencia de nodos con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="dbad5-102">Matching Nodes using XPathNavigator</span></span>
<span data-ttu-id="dbad5-103">La clase <xref:System.Xml.XPath.XPathNavigator> incluye el método <xref:System.Xml.XPath.XPathNavigator.Matches%2A> para determinar si un nodo coincide con una expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="dbad5-103">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method to determine if a node matches an XPath expression.</span></span> <span data-ttu-id="dbad5-104">El método <xref:System.Xml.XPath.XPathNavigator.Matches%2A> toma una expresión XPath como entrada y devuelve <xref:System.Boolean> que indica si el nodo actual coincide con la expresión XPath especificada o el objeto <xref:System.Xml.XPath.XPathExpression> compilado especificado.</span><span class="sxs-lookup"><span data-stu-id="dbad5-104">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method takes an XPath expression as input and returns a <xref:System.Boolean> that indicates if the current node matches the given XPath expression or the given compiled <xref:System.Xml.XPath.XPathExpression> object.</span></span>  
  
## <a name="matching-nodes"></a><span data-ttu-id="dbad5-105">Coincidencia de nodos</span><span class="sxs-lookup"><span data-stu-id="dbad5-105">Matching Nodes</span></span>  
 <span data-ttu-id="dbad5-106">El método <xref:System.Xml.XPath.XPathNavigator.Matches%2A> devuelve `true` si el nodo actual coincide con la expresión XPath especificada.</span><span class="sxs-lookup"><span data-stu-id="dbad5-106">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method returns `true` if the current node matches the XPath expression specified.</span></span> <span data-ttu-id="dbad5-107">Por ejemplo, en el siguiente código de ejemplo, el método <xref:System.Xml.XPath.XPathNavigator.Matches%2A> devolverá `true` si el nodo actual es el elemento `b` y el elemento `b` tiene el atributo `c`.</span><span class="sxs-lookup"><span data-stu-id="dbad5-107">For example, in the code example that follows, the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method will return `true` if the current node is the element `b`, and element `b` has an attribute `c`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dbad5-108">El método <xref:System.Xml.XPath.XPathNavigator.Matches%2A> no cambia el estado de <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="dbad5-108">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method does not change the state of the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
```vb  
Dim document as XPathDocument = New XPathDocument("input.xml")  
Dim navigator as XPathNavigator = document.CreateNavigator()  
  
navigator.Matches("b[@c]")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.Matches("b[@c]");  
```  
  
## <a name="see-also"></a><span data-ttu-id="dbad5-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbad5-109">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="dbad5-110">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="dbad5-110">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="dbad5-111">Seleccionar datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="dbad5-111">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="dbad5-112">Evaluación de expresiones XPath con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="dbad5-112">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)  
 [<span data-ttu-id="dbad5-113">Tipos de nodos reconocidos con consultas XPath</span><span class="sxs-lookup"><span data-stu-id="dbad5-113">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)  
 [<span data-ttu-id="dbad5-114">Espacios de nombres y consultas XPath</span><span class="sxs-lookup"><span data-stu-id="dbad5-114">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)  
 [<span data-ttu-id="dbad5-115">Expresiones XPath compiladas</span><span class="sxs-lookup"><span data-stu-id="dbad5-115">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
