---
title: Coincidencia de nodos con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: e6848c47-ee5d-401a-89a5-50b5eed40f30
ms.openlocfilehash: f0988c3a112fefc351175de02c790dc25fe6e94a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710692"
---
# <a name="matching-nodes-using-xpathnavigator"></a><span data-ttu-id="dad64-102">Coincidencia de nodos con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="dad64-102">Matching Nodes using XPathNavigator</span></span>
<span data-ttu-id="dad64-103">La clase <xref:System.Xml.XPath.XPathNavigator> incluye el método <xref:System.Xml.XPath.XPathNavigator.Matches%2A> para determinar si un nodo coincide con una expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="dad64-103">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method to determine if a node matches an XPath expression.</span></span> <span data-ttu-id="dad64-104">El método <xref:System.Xml.XPath.XPathNavigator.Matches%2A> toma una expresión XPath como entrada y devuelve <xref:System.Boolean> que indica si el nodo actual coincide con la expresión XPath especificada o el objeto <xref:System.Xml.XPath.XPathExpression> compilado especificado.</span><span class="sxs-lookup"><span data-stu-id="dad64-104">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method takes an XPath expression as input and returns a <xref:System.Boolean> that indicates if the current node matches the given XPath expression or the given compiled <xref:System.Xml.XPath.XPathExpression> object.</span></span>  
  
## <a name="matching-nodes"></a><span data-ttu-id="dad64-105">Coincidencia de nodos</span><span class="sxs-lookup"><span data-stu-id="dad64-105">Matching Nodes</span></span>  
 <span data-ttu-id="dad64-106">El método <xref:System.Xml.XPath.XPathNavigator.Matches%2A> devuelve `true` si el nodo actual coincide con la expresión XPath especificada.</span><span class="sxs-lookup"><span data-stu-id="dad64-106">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method returns `true` if the current node matches the XPath expression specified.</span></span> <span data-ttu-id="dad64-107">Por ejemplo, en el siguiente código de ejemplo, el método <xref:System.Xml.XPath.XPathNavigator.Matches%2A> devolverá `true` si el nodo actual es el elemento `b` y el elemento `b` tiene el atributo `c`.</span><span class="sxs-lookup"><span data-stu-id="dad64-107">For example, in the code example that follows, the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method will return `true` if the current node is the element `b`, and element `b` has an attribute `c`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dad64-108">El método <xref:System.Xml.XPath.XPathNavigator.Matches%2A> no cambia el estado de <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="dad64-108">The <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method does not change the state of the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dad64-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="dad64-109">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="dad64-110">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="dad64-110">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="dad64-111">Seleccionar datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="dad64-111">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="dad64-112">Evaluación de expresiones XPath con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="dad64-112">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)
- [<span data-ttu-id="dad64-113">Tipos de nodos reconocidos con consultas XPath</span><span class="sxs-lookup"><span data-stu-id="dad64-113">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)
- [<span data-ttu-id="dad64-114">Espacios de nombres y consultas XPath</span><span class="sxs-lookup"><span data-stu-id="dad64-114">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)
- [<span data-ttu-id="dad64-115">Expresiones XPath compiladas</span><span class="sxs-lookup"><span data-stu-id="dad64-115">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
