---
title: Se preservan las referencias de entidad
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 770c714e8f5942ea733c417ae9b06f69e4acf1a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="entity-references-are-preserved"></a><span data-ttu-id="6c803-102">Se preservan las referencias de entidad</span><span class="sxs-lookup"><span data-stu-id="6c803-102">Entity References are Preserved</span></span>
<span data-ttu-id="6c803-103">Cuando no se expande toda la referencia de entidad, sino que se conserva, el modelo de objetos de documento (DOM) XML compila un **XmlEntityReference** nodo cuando encuentra una referencia de entidad.</span><span class="sxs-lookup"><span data-stu-id="6c803-103">When the entity reference is not expanded, but preserved, the XML Document Object Model (DOM) builds an **XmlEntityReference** node when it encounters an entity reference.</span></span>  
  
 <span data-ttu-id="6c803-104">Con el siguiente código XML,</span><span class="sxs-lookup"><span data-stu-id="6c803-104">Using the following XML,</span></span>  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 <span data-ttu-id="6c803-105">el DOM compila un **XmlEntityReference** nodo cuando encuentra el `&publisher;` referencia.</span><span class="sxs-lookup"><span data-stu-id="6c803-105">the DOM builds an **XmlEntityReference** node when it encounters the `&publisher;` reference.</span></span> <span data-ttu-id="6c803-106">El **XmlEntityReference** contiene nodos secundarios copiados a partir del contenido en la declaración de entidad.</span><span class="sxs-lookup"><span data-stu-id="6c803-106">The **XmlEntityReference** contains child nodes copied from the content in the entity declaration.</span></span> <span data-ttu-id="6c803-107">El ejemplo de código anterior contiene texto en la declaración de entidad, de forma que un **XmlText** se crea el nodo como nodo secundario del nodo de referencia de entidad.</span><span class="sxs-lookup"><span data-stu-id="6c803-107">The preceding code example contains text in the entity declaration, so an **XmlText** node is created as the child node of the entity reference node.</span></span>  
  
 <span data-ttu-id="6c803-108">![Estructura para referencias de entidades conservadas de árbol](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span><span class="sxs-lookup"><span data-stu-id="6c803-108">![Tree structure for preserved entity references](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")</span></span>  
<span data-ttu-id="6c803-109">Estructura de árbol para referencias de entidad que se preservan</span><span class="sxs-lookup"><span data-stu-id="6c803-109">Tree structure for entity references that are preserved</span></span>  
  
 <span data-ttu-id="6c803-110">Los nodos secundarios de la **XmlEntityReference** son nodos creados a partir de copias de todos los secundarios del **XmlEntity** nodo cuando se encuentra la declaración de entidad.</span><span class="sxs-lookup"><span data-stu-id="6c803-110">The child nodes of the **XmlEntityReference** are copies of all the child nodes created from the **XmlEntity** node when the entity declaration was encountered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c803-111">Los nodos copiados de la **XmlEntity** no son siempre copias exactas una vez situados bajo el nodo de referencia de entidad.</span><span class="sxs-lookup"><span data-stu-id="6c803-111">The nodes copied from the **XmlEntity** are not always exact copies once placed under the entity reference node.</span></span> <span data-ttu-id="6c803-112">Puede haber espacios de nombres que estén en el ámbito de un nodo de referencia de entidad y que afecten a la configuración final de los nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="6c803-112">There can be namespaces that are in scope at the entity reference node, and that affects the final configuration of the child nodes.</span></span>  
  
 <span data-ttu-id="6c803-113">De forma predeterminada, las entidades generales como `&abc;` se conservan y **XmlEntityReference** siempre se crean nodos.</span><span class="sxs-lookup"><span data-stu-id="6c803-113">By default, general entities like `&abc;` are preserved and **XmlEntityReference** nodes always created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c803-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c803-114">See Also</span></span>  
 [<span data-ttu-id="6c803-115">Modelo de objetos de documento (DOM) de XML</span><span class="sxs-lookup"><span data-stu-id="6c803-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
