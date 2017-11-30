---
title: Copiar nodos existentes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 11f3915dfebd7ad9d3144c9bedcd7f42b4754359
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="copy-existing-nodes"></a><span data-ttu-id="452d3-102">Copiar nodos existentes</span><span class="sxs-lookup"><span data-stu-id="452d3-102">Copy Existing Nodes</span></span>
<span data-ttu-id="452d3-103">Hay muchos métodos y propiedades en el XML Document Object Model (DOM) que puede utilizar para seleccionar un nodo, como **SelectSingleNode**, **ChildNodes [int]**, **atributos [int]**.</span><span class="sxs-lookup"><span data-stu-id="452d3-103">There are many methods and properties in the XML Document Object Model (DOM)you can use to select a node, such as **SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]**.</span></span> <span data-ttu-id="452d3-104">Una vez seleccionado el nodo, puede insertarlo en el árbol mediante uno de los métodos de inserción que funcionan para dicho tipo de nodo en particular.</span><span class="sxs-lookup"><span data-stu-id="452d3-104">Once the node is selected, you can insert it into the tree using one of the insert methods that work for that particular node type.</span></span> <span data-ttu-id="452d3-105">La única restricción a la inserción de un nodo en el árbol es que el documento debe seguir teniendo un formato correcto después de insertarlo.</span><span class="sxs-lookup"><span data-stu-id="452d3-105">The only restriction to inserting a node into the tree is that the document must still be well-formed after the node is inserted.</span></span> <span data-ttu-id="452d3-106">Al insertar un nodo existente en el árbol DOM, se quita de su posición original y se agrega a su posición de destino.</span><span class="sxs-lookup"><span data-stu-id="452d3-106">When an existing node is inserted into the DOM tree, it is removed from its original position and added to its target position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="452d3-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="452d3-107">See Also</span></span>  
 [<span data-ttu-id="452d3-108">Modelo de objetos de documento (DOM) de XML</span><span class="sxs-lookup"><span data-stu-id="452d3-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
