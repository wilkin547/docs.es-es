---
title: Cómo quitar el contenido de los nodos en el DOM
ms.date: 03/30/2017
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
ms.openlocfilehash: 7b33ebfea244dbe81879c61be3809adcb2a1f5d3
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828873"
---
# <a name="removing-node-content-in-the-dom"></a><span data-ttu-id="35bfd-102">Cómo quitar el contenido de los nodos en el DOM</span><span class="sxs-lookup"><span data-stu-id="35bfd-102">Removing Node Content in the DOM</span></span>
<span data-ttu-id="35bfd-103">En el caso de los tipos de nodos que heredan de <xref:System.Xml.XmlCharacterData>, que son los tipos de nodos <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace> y <xref:System.Xml.XmlSignificantWhitespace>, se pueden quitar caracteres utilizando el método <xref:System.Xml.XmlCharacterData.DeleteData%2A>, que elimina un intervalo de caracteres del nodo.</span><span class="sxs-lookup"><span data-stu-id="35bfd-103">For node types that inherit from <xref:System.Xml.XmlCharacterData>, which are the <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace>, and <xref:System.Xml.XmlSignificantWhitespace> node types, you can remove characters using the <xref:System.Xml.XmlCharacterData.DeleteData%2A> method, which removes a range of characters from the node.</span></span> <span data-ttu-id="35bfd-104">Si desea quitar todo el contenido, debe eliminar el nodo que incluye el contenido.</span><span class="sxs-lookup"><span data-stu-id="35bfd-104">If you want to remove content completely, you remove the node that contains the content.</span></span> <span data-ttu-id="35bfd-105">Si quiere conservar el nodo, pero el contenido no es correcto, debe modificar el contenido.</span><span class="sxs-lookup"><span data-stu-id="35bfd-105">If you want to keep the node, but the content is incorrect, then modify the content.</span></span> <span data-ttu-id="35bfd-106">Para obtener información sobre la modificación del contenido de un nodo, vea [Modificación de nodos, contenido y valores en un documento XML](modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="35bfd-106">For information on modifying the content of a node, see [Modifying Nodes, Content, and Values in an XML Document](modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35bfd-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="35bfd-107">See also</span></span>

- [<span data-ttu-id="35bfd-108">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="35bfd-108">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
