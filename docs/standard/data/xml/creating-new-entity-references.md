---
title: Crear nuevas referencias de entidad
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a42f81b3-0403-4e34-b346-7d2129804e54
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 22e9b66f58275141cf9da154573ca43a0b90affc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-entity-references"></a><span data-ttu-id="4ebeb-102">Crear nuevas referencias de entidad</span><span class="sxs-lookup"><span data-stu-id="4ebeb-102">Creating New Entity References</span></span>
<span data-ttu-id="4ebeb-103">El **CreateEntityReference** método crea un nuevo **XmlEntityReference** nodo.</span><span class="sxs-lookup"><span data-stu-id="4ebeb-103">The **CreateEntityReference** method creates a new **XmlEntityReference** node.</span></span> <span data-ttu-id="4ebeb-104">El Modelo de objetos de documento (DOM) busca si el nombre de entidad al que se hace referencia ya se ha declarado.</span><span class="sxs-lookup"><span data-stu-id="4ebeb-104">The XML Document Object Model (DOM) looks to see if the entity name being referenced has already been declared.</span></span> <span data-ttu-id="4ebeb-105">Si lo tiene, los nodos secundarios del **XmlEntityReference** nodo se copian desde el nodo de declaración de entidad.</span><span class="sxs-lookup"><span data-stu-id="4ebeb-105">If it has, the child nodes of **XmlEntityReference** node are copied from the entity declaration node.</span></span> <span data-ttu-id="4ebeb-106">Si no hay declaración de entidad equivalente, se adjunta un nodo de texto vacío como el único nodo secundario del nodo de referencia de entidad.</span><span class="sxs-lookup"><span data-stu-id="4ebeb-106">If there is no entity declaration that matches, an empty text node is attached as the only child of the entity reference node.</span></span> <span data-ttu-id="4ebeb-107">Dado que los nodos secundarios de la **XmlEntityReference** se copian de otros nodos, los siguientes nodos secundarios son de solo lectura y no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="4ebeb-107">Because the child nodes of the **XmlEntityReference** node are copies of other nodes, these child nodes are read-only and cannot be modified.</span></span>  
  
 <span data-ttu-id="4ebeb-108">Al copiar los nodos, puede haber un espacio de nombres en el punto de la referencia de entidad.</span><span class="sxs-lookup"><span data-stu-id="4ebeb-108">When the nodes are copied, there may be a namespace in scope at the point of the entity reference.</span></span> <span data-ttu-id="4ebeb-109">Este espacio de nombres afecta la configuración de los elementos o nodos de atributo generados.</span><span class="sxs-lookup"><span data-stu-id="4ebeb-109">This namespace affects the configuration of any element or attribute nodes generated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ebeb-110">DOM agrega nodos secundarios a la **EntityReference** solo cuando se inserta el **EntityReference** nodo en el documento.</span><span class="sxs-lookup"><span data-stu-id="4ebeb-110">The DOM adds child nodes to the **EntityReference** only when you insert the **EntityReference** node to the document.</span></span> <span data-ttu-id="4ebeb-111">Acaba de crear **EntityReference** nodos no tienen nodos secundarios.</span><span class="sxs-lookup"><span data-stu-id="4ebeb-111">Newly created **EntityReference** nodes have no child nodes.</span></span>  
  
 <span data-ttu-id="4ebeb-112">Aunque la **XmlDataDocument** es una clase derivada de la **XmlDocument**, **XmlDataDocument** no admite la creación de referencias de entidad.</span><span class="sxs-lookup"><span data-stu-id="4ebeb-112">Even though the **XmlDataDocument** is a derived class of the **XmlDocument**, the **XmlDataDocument** does not support the creation of entity references.</span></span> <span data-ttu-id="4ebeb-113">Esto es porque **EntityReference** elementos secundarios son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="4ebeb-113">This is because **EntityReference** children are read-only.</span></span> <span data-ttu-id="4ebeb-114">Los elementos secundarios de un **EntityReference** nodo puede abarcar más de una región.</span><span class="sxs-lookup"><span data-stu-id="4ebeb-114">The children of an **EntityReference** node can span more than one region.</span></span> <span data-ttu-id="4ebeb-115">En este caso, parte de una fila asociada a la región que contiene una parte de un **EntityReference** serán de sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="4ebeb-115">In this case, part of a row associated with the region that contains a part of an **EntityReference** will be read-only.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ebeb-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ebeb-116">See Also</span></span>  
 [<span data-ttu-id="4ebeb-117">Modelo de objetos de documento (DOM) de XML</span><span class="sxs-lookup"><span data-stu-id="4ebeb-117">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
