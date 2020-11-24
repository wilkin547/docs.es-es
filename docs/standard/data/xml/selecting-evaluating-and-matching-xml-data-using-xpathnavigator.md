---
title: Selección, evaluación y coincidencia de datos XML con XPathNavigator
ms.date: 03/30/2017
ms.assetid: 46e059f8-4dc8-4185-9236-784be95228ed
ms.openlocfilehash: 249b99a627f3bbcc1723f104a80cb61552404877
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822469"
---
# <a name="selecting-evaluating-and-matching-xml-data-using-xpathnavigator"></a><span data-ttu-id="8ca53-102">Selección, evaluación y coincidencia de datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="8ca53-102">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>
<span data-ttu-id="8ca53-103">La clase <xref:System.Xml.XPath.XPathNavigator> incluye métodos para seleccionar nodos en una expresión <xref:System.Xml.XPath.XPathDocument> o un objeto <xref:System.Xml.XmlDocument> utilizando una consulta XPath, evaluar y examinar los resultados de una expresión XPath y determinar si un nodo de un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> coincide con una expresión XPath determinada.</span><span class="sxs-lookup"><span data-stu-id="8ca53-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to select nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath query, evaluate and examine the results of an XPath expression, and determine if a node in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object matches a given XPath expression.</span></span> <span data-ttu-id="8ca53-104">Éstos y otros conceptos que están relacionados con la selección, evaluación y coincidencia de nodos de un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> se describen en los siguientes temas.</span><span class="sxs-lookup"><span data-stu-id="8ca53-104">These and other concepts that relate to selecting, evaluating and matching nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object are described in the following topics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8ca53-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8ca53-105">In This Section</span></span>  
 [<span data-ttu-id="8ca53-106">Seleccionar datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="8ca53-106">Select XML Data Using XPathNavigator</span></span>](select-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="8ca53-107">Se describe el conjunto de métodos de la clase <xref:System.Xml.XPath.XPathNavigator> que se utilizan para seleccionar un conjunto de nodos de un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> utilizando una expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="8ca53-107">Describes the set of <xref:System.Xml.XPath.XPathNavigator> class methods used to select a set of nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath expression.</span></span>  
  
 [<span data-ttu-id="8ca53-108">Evaluación de expresiones XPath con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="8ca53-108">Evaluate XPath Expressions using XPathNavigator</span></span>](evaluate-xpath-expressions-using-xpathnavigator.md)  
 <span data-ttu-id="8ca53-109">Se describe el método <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> utilizada para evaluar una expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="8ca53-109">Describes the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class used to evaluate an XPath expression.</span></span>  
  
 [<span data-ttu-id="8ca53-110">Coincidencia de nodos con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="8ca53-110">Matching Nodes using XPathNavigator</span></span>](matching-nodes-using-xpathnavigator.md)  
 <span data-ttu-id="8ca53-111">Se describe el método <xref:System.Xml.XPath.XPathNavigator.Matches%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> utilizado para determinar si un nodo coincide con una expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="8ca53-111">Describes the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class used to determine if a node matches an XPath expression.</span></span>  
  
 [<span data-ttu-id="8ca53-112">Tipos de nodos reconocidos con consultas XPath</span><span class="sxs-lookup"><span data-stu-id="8ca53-112">Node Types Recognized with XPath Queries</span></span>](node-types-recognized-with-xpath-queries.md)  
 <span data-ttu-id="8ca53-113">Se describen los tipos de nodos reconocidos en una consulta XPath.</span><span class="sxs-lookup"><span data-stu-id="8ca53-113">Describes the types of nodes recognized in an XPath query.</span></span>  
  
 [<span data-ttu-id="8ca53-114">Espacios de nombres y consultas XPath</span><span class="sxs-lookup"><span data-stu-id="8ca53-114">XPath Queries and Namespaces</span></span>](xpath-queries-and-namespaces.md)  
 <span data-ttu-id="8ca53-115">Se describen los usos de los espacios de nombres en una consulta XPath.</span><span class="sxs-lookup"><span data-stu-id="8ca53-115">Describes the use of namespaces in an XPath query.</span></span>  
  
 [<span data-ttu-id="8ca53-116">Expresiones XPath compiladas</span><span class="sxs-lookup"><span data-stu-id="8ca53-116">Compiled XPath Expressions</span></span>](compiled-xpath-expressions.md)  
 <span data-ttu-id="8ca53-117">Se describe la clase <xref:System.Xml.XPath.XPathExpression> que representa a una consulta XPath compilada.</span><span class="sxs-lookup"><span data-stu-id="8ca53-117">Describes the <xref:System.Xml.XPath.XPathExpression> class that represents a compiled XPath query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ca53-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ca53-118">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="8ca53-119">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="8ca53-119">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="8ca53-120">Lectura de datos XML con XPathDocument y XmlDocument</span><span class="sxs-lookup"><span data-stu-id="8ca53-120">Reading XML Data using XPathDocument and XmlDocument</span></span>](reading-xml-data-using-xpathdocument-and-xmldocument.md)
- [<span data-ttu-id="8ca53-121">Acceso a datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="8ca53-121">Accessing XML Data using XPathNavigator</span></span>](accessing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="8ca53-122">Edición de datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="8ca53-122">Editing XML Data using XPathNavigator</span></span>](editing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="8ca53-123">Validación de esquemas con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="8ca53-123">Schema Validation using XPathNavigator</span></span>](schema-validation-using-xpathnavigator.md)
