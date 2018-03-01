---
title: "Cómo quitar el contenido de los nodos en el DOM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 45a8d5006599b23165a174770f4d72974ea0e5ec
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="removing-node-content-in-the-dom"></a><span data-ttu-id="a0564-102">Cómo quitar el contenido de los nodos en el DOM</span><span class="sxs-lookup"><span data-stu-id="a0564-102">Removing Node Content in the DOM</span></span>
<span data-ttu-id="a0564-103">En el caso de los tipos de nodos que heredan de <xref:System.Xml.XmlCharacterData>, que son los tipos de nodos <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace> y <xref:System.Xml.XmlSignificantWhitespace>, se pueden quitar caracteres utilizando el método <xref:System.Xml.XmlCharacterData.DeleteData%2A>, que elimina un intervalo de caracteres del nodo.</span><span class="sxs-lookup"><span data-stu-id="a0564-103">For node types that inherit from <xref:System.Xml.XmlCharacterData>, which are the <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace>, and <xref:System.Xml.XmlSignificantWhitespace> node types, you can remove characters using the <xref:System.Xml.XmlCharacterData.DeleteData%2A> method, which removes a range of characters from the node.</span></span> <span data-ttu-id="a0564-104">Si desea quitar todo el contenido, debe eliminar el nodo que incluye el contenido.</span><span class="sxs-lookup"><span data-stu-id="a0564-104">If you want to remove content completely, you remove the node that contains the content.</span></span> <span data-ttu-id="a0564-105">Si quiere conservar el nodo, pero el contenido no es correcto, debe modificar el contenido.</span><span class="sxs-lookup"><span data-stu-id="a0564-105">If you want to keep the node, but the content is incorrect, then modify the content.</span></span> <span data-ttu-id="a0564-106">Para obtener información sobre la modificación del contenido de un nodo, vea [Modificación de nodos, contenido y valores en un documento XML](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="a0564-106">For information on modifying the content of a node, see [Modifying Nodes, Content, and Values in an XML Document](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0564-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0564-107">See Also</span></span>  
 [<span data-ttu-id="a0564-108">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="a0564-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
