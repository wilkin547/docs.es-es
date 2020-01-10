---
title: Se preservan las referencias de entidad
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
ms.openlocfilehash: 0fd427388a065bd4c689d087c22fd6d69046b8a9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710926"
---
# <a name="entity-references-are-preserved"></a><span data-ttu-id="f2107-102">Se preservan las referencias de entidad</span><span class="sxs-lookup"><span data-stu-id="f2107-102">Entity References are Preserved</span></span>
<span data-ttu-id="f2107-103">Cuando no se expande toda la referencia de entidad, sino que se conserva, el modelo Document Object Model (DOM) XML compila un nodo **XmlEntityReference** al encontrar una.</span><span class="sxs-lookup"><span data-stu-id="f2107-103">When the entity reference is not expanded, but preserved, the XML Document Object Model (DOM) builds an **XmlEntityReference** node when it encounters an entity reference.</span></span>  
  
 <span data-ttu-id="f2107-104">Con el siguiente código XML,</span><span class="sxs-lookup"><span data-stu-id="f2107-104">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="f2107-105">DOM compila un nodo **XmlEntityReference** cuando encuentra la referencia `&publisher;`.</span><span class="sxs-lookup"><span data-stu-id="f2107-105">the DOM builds an **XmlEntityReference** node when it encounters the `&publisher;` reference.</span></span> <span data-ttu-id="f2107-106">La referencia **XmlEntityReference** contiene nodos secundarios copiados a partir del contenido en la declaración de entidad.</span><span class="sxs-lookup"><span data-stu-id="f2107-106">The **XmlEntityReference** contains child nodes copied from the content in the entity declaration.</span></span> <span data-ttu-id="f2107-107">El ejemplo de código anterior contiene texto en la declaración de entidad, de forma que se crea un nodo **XmlText** como nodo secundario del nodo de referencia de entidad.</span><span class="sxs-lookup"><span data-stu-id="f2107-107">The preceding code example contains text in the entity declaration, so an **XmlText** node is created as the child node of the entity reference node.</span></span>  
  
 <span data-ttu-id="f2107-108">![Estructura de árbol para referencias de entidades conservadas](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span><span class="sxs-lookup"><span data-stu-id="f2107-108">![Tree structure for preserved entity references](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span></span>  
<span data-ttu-id="f2107-109">Estructura de árbol para referencias de entidad que se preservan</span><span class="sxs-lookup"><span data-stu-id="f2107-109">Tree structure for entity references that are preserved</span></span>  
  
 <span data-ttu-id="f2107-110">Los nodos secundarios de la referencia **XmlEntityReference** son copias de todos los nodos secundarios creados a partir del nodo **XmlEntity** al encontrar la declaración de entidad.</span><span class="sxs-lookup"><span data-stu-id="f2107-110">The child nodes of the **XmlEntityReference** are copies of all the child nodes created from the **XmlEntity** node when the entity declaration was encountered.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f2107-111">Los nodos copiados de **XmlEntity** no son siempre copias exactas una vez situados bajo el nodo de referencia de entidad.</span><span class="sxs-lookup"><span data-stu-id="f2107-111">The nodes copied from the **XmlEntity** are not always exact copies once placed under the entity reference node.</span></span> <span data-ttu-id="f2107-112">Puede haber espacios de nombres que estén en el ámbito de un nodo de referencia de entidad y que afecten a la configuración final de los nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="f2107-112">There can be namespaces that are in scope at the entity reference node, and that affects the final configuration of the child nodes.</span></span>  
  
 <span data-ttu-id="f2107-113">De forma predeterminada, se conservan las entidades generales como `&abc;` y siempre se crean nodos **XmlEntityReference**.</span><span class="sxs-lookup"><span data-stu-id="f2107-113">By default, general entities like `&abc;` are preserved and **XmlEntityReference** nodes always created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2107-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2107-114">See also</span></span>

- [<span data-ttu-id="f2107-115">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="f2107-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
