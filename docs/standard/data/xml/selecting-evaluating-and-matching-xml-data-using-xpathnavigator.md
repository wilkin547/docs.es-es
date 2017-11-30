---
title: "Selección, evaluación y coincidencia de datos XML con XPathNavigator"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 46e059f8-4dc8-4185-9236-784be95228ed
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7a86fb36d367342ea0c5bc4968bdd5744bd0524e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="selecting-evaluating-and-matching-xml-data-using-xpathnavigator"></a><span data-ttu-id="d7794-102">Selección, evaluación y coincidencia de datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="d7794-102">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>
<span data-ttu-id="d7794-103">La clase <xref:System.Xml.XPath.XPathNavigator> incluye métodos para seleccionar nodos en una expresión <xref:System.Xml.XPath.XPathDocument> o un objeto <xref:System.Xml.XmlDocument> utilizando una consulta XPath, evaluar y examinar los resultados de una expresión XPath y determinar si un nodo de un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> coincide con una expresión XPath determinada.</span><span class="sxs-lookup"><span data-stu-id="d7794-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to select nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath query, evaluate and examine the results of an XPath expression, and determine if a node in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object matches a given XPath expression.</span></span> <span data-ttu-id="d7794-104">Éstos y otros conceptos que están relacionados con la selección, evaluación y coincidencia de nodos de un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> se describen en los siguientes temas.</span><span class="sxs-lookup"><span data-stu-id="d7794-104">These and other concepts that relate to selecting, evaluating and matching nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object are described in the following topics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d7794-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d7794-105">In This Section</span></span>  
 [<span data-ttu-id="d7794-106">Seleccionar datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="d7794-106">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="d7794-107">Se describe el conjunto de métodos de la clase <xref:System.Xml.XPath.XPathNavigator> que se utilizan para seleccionar un conjunto de nodos de un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> utilizando una expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="d7794-107">Describes the set of <xref:System.Xml.XPath.XPathNavigator> class methods used to select a set of nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath expression.</span></span>  
  
 [<span data-ttu-id="d7794-108">Evaluar expresiones XPath con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="d7794-108">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)  
 <span data-ttu-id="d7794-109">Se describe el método <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> utilizada para evaluar una expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="d7794-109">Describes the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class used to evaluate an XPath expression.</span></span>  
  
 [<span data-ttu-id="d7794-110">Coincidencia de nodos con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="d7794-110">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)  
 <span data-ttu-id="d7794-111">Se describe el método <xref:System.Xml.XPath.XPathNavigator.Matches%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> utilizado para determinar si un nodo coincide con una expresión XPath.</span><span class="sxs-lookup"><span data-stu-id="d7794-111">Describes the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class used to determine if a node matches an XPath expression.</span></span>  
  
 [<span data-ttu-id="d7794-112">Tipos de nodos reconocidos con consultas XPath</span><span class="sxs-lookup"><span data-stu-id="d7794-112">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)  
 <span data-ttu-id="d7794-113">Se describen los tipos de nodos reconocidos en una consulta XPath.</span><span class="sxs-lookup"><span data-stu-id="d7794-113">Describes the types of nodes recognized in an XPath query.</span></span>  
  
 [<span data-ttu-id="d7794-114">Espacios de nombres y consultas XPath</span><span class="sxs-lookup"><span data-stu-id="d7794-114">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)  
 <span data-ttu-id="d7794-115">Se describen los usos de los espacios de nombres en una consulta XPath.</span><span class="sxs-lookup"><span data-stu-id="d7794-115">Describes the use of namespaces in an XPath query.</span></span>  
  
 [<span data-ttu-id="d7794-116">Expresiones XPath compiladas</span><span class="sxs-lookup"><span data-stu-id="d7794-116">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)  
 <span data-ttu-id="d7794-117">Se describe la clase <xref:System.Xml.XPath.XPathExpression> que representa a una consulta XPath compilada.</span><span class="sxs-lookup"><span data-stu-id="d7794-117">Describes the <xref:System.Xml.XPath.XPathExpression> class that represents a compiled XPath query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7794-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7794-118">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="d7794-119">Procesamiento de datos XML con el modelo de datos XPath</span><span class="sxs-lookup"><span data-stu-id="d7794-119">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="d7794-120">Leer datos XML con XPathDocument y XmlDocument</span><span class="sxs-lookup"><span data-stu-id="d7794-120">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 [<span data-ttu-id="d7794-121">Acceso a datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="d7794-121">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="d7794-122">Edición de datos XML con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="d7794-122">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="d7794-123">Validación de esquemas con XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="d7794-123">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)
