---
title: 'Cómo: Transformar un fragmento de nodo'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 73a6c582-b9d7-4fa7-9a05-6d931e1f3de8
ms.openlocfilehash: 56e9ef6031a5736acfa066ed6c068f954bd5af8d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710822"
---
# <a name="how-to-transform-a-node-fragment"></a><span data-ttu-id="c19bd-102">Cómo: Transformar un fragmento de nodo</span><span class="sxs-lookup"><span data-stu-id="c19bd-102">How to: Transform a Node Fragment</span></span>
<span data-ttu-id="c19bd-103">Cuando se transforman los datos contenidos en un objeto <xref:System.Xml.XmlDocument> o <xref:System.Xml.XPath.XPathDocument>, las transformaciones XSLT se aplican a un documento completo.</span><span class="sxs-lookup"><span data-stu-id="c19bd-103">When you transform data contained in an <xref:System.Xml.XmlDocument> or <xref:System.Xml.XPath.XPathDocument> object the XSLT transformations apply to a document as a whole.</span></span> <span data-ttu-id="c19bd-104">En otras palabras, si se pasa un nodo distinto del nodo raíz del documento, esto no evita que el proceso de transformación pueda obtener acceso a todos los nodos del documento cargado.</span><span class="sxs-lookup"><span data-stu-id="c19bd-104">In other words, if you pass in a node other than the document root node, this does not prevent the transformation process from accessing all nodes in the loaded document.</span></span> <span data-ttu-id="c19bd-105">Para transformar un fragmento del nodo, debe crear un objeto diferente que contenga el fragmento del nodo y pasar ese objeto al método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="c19bd-105">To transform a node fragment, you must create a separate object containing just the node fragment, and pass that object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="c19bd-106">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="c19bd-106">Procedures</span></span>  
  
#### <a name="to-transform-a-node-fragment"></a><span data-ttu-id="c19bd-107">Para transformar un fragmento de nodo</span><span class="sxs-lookup"><span data-stu-id="c19bd-107">To transform a node fragment</span></span>  
  
1. <span data-ttu-id="c19bd-108">Cree un objeto que contenga el documento de origen.</span><span class="sxs-lookup"><span data-stu-id="c19bd-108">Create an object containing the source document.</span></span>  
  
2. <span data-ttu-id="c19bd-109">Localice el fragmento del nodo que desee transformar.</span><span class="sxs-lookup"><span data-stu-id="c19bd-109">Locate the node fragment you wish to transform.</span></span>  
  
3. <span data-ttu-id="c19bd-110">Cree un objeto diferente solo con el fragmento del nodo.</span><span class="sxs-lookup"><span data-stu-id="c19bd-110">Create separate object with just the node fragment.</span></span>  
  
4. <span data-ttu-id="c19bd-111">Pase el fragmento del nodo al método <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="c19bd-111">Pass the node fragment to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c19bd-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c19bd-112">Example</span></span>  
 <span data-ttu-id="c19bd-113">En el siguiente ejemplo se transforma un fragmento de nodo y los resultados se envían a la consola.</span><span class="sxs-lookup"><span data-stu-id="c19bd-113">The following example transforms a node fragment and outputs the results to the console.</span></span>  
  
 [!code-csharp[XSLT_NodeFrag#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_NodeFrag/CS/xslt_frag.cs#1)]
 [!code-vb[XSLT_NodeFrag#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_NodeFrag/VB/xslt_frag.vb#1)]  
  
### <a name="input"></a><span data-ttu-id="c19bd-114">Input</span><span class="sxs-lookup"><span data-stu-id="c19bd-114">Input</span></span>  
  
##### <a name="booksxml"></a><span data-ttu-id="c19bd-115">books.xml</span><span class="sxs-lookup"><span data-stu-id="c19bd-115">books.xml</span></span>  
 [!code-xml[XML_Core_Files#1](../../../../samples/snippets/xml/VS_Snippets_Data/XML_Core_Files/XML/books.xml#1)]  
  
##### <a name="singlexsl"></a><span data-ttu-id="c19bd-116">single.xsl</span><span class="sxs-lookup"><span data-stu-id="c19bd-116">single.xsl</span></span>  
 [!code-xml[XSLT_NodeFrag#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_NodeFrag/XML/single.xsl#2)]  
  
### <a name="output"></a><span data-ttu-id="c19bd-117">Resultados</span><span class="sxs-lookup"><span data-stu-id="c19bd-117">Output</span></span>  
 <span data-ttu-id="c19bd-118">El título del libro es The Confidence Man.</span><span class="sxs-lookup"><span data-stu-id="c19bd-118">Book title is The Confidence Man.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c19bd-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c19bd-119">See also</span></span>

- [<span data-ttu-id="c19bd-120">Uso de la clase XslCompiledTransform</span><span class="sxs-lookup"><span data-stu-id="c19bd-120">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)
