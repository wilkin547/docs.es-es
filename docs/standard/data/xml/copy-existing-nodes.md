---
title: Copiar nodos existentes
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
ms.openlocfilehash: fb9ccd7b16d00355ba87bb32f5447906feeecd94
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711069"
---
# <a name="copy-existing-nodes"></a><span data-ttu-id="71104-102">Copiar nodos existentes</span><span class="sxs-lookup"><span data-stu-id="71104-102">Copy Existing Nodes</span></span>
<span data-ttu-id="71104-103">Hay muchos métodos y propiedades en Document Object Model (DOM) XML que se pueden utilizar para seleccionar un nodo, como **SelectSingleNode**, **ChildNodes[int i]** y **Attributes[int i]** .</span><span class="sxs-lookup"><span data-stu-id="71104-103">There are many methods and properties in the XML Document Object Model (DOM)you can use to select a node, such as **SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]**.</span></span> <span data-ttu-id="71104-104">Una vez seleccionado el nodo, puede insertarlo en el árbol mediante uno de los métodos de inserción que funcionan para dicho tipo de nodo en particular.</span><span class="sxs-lookup"><span data-stu-id="71104-104">Once the node is selected, you can insert it into the tree using one of the insert methods that work for that particular node type.</span></span> <span data-ttu-id="71104-105">La única restricción a la inserción de un nodo en el árbol es que el documento debe seguir teniendo un formato correcto después de insertarlo.</span><span class="sxs-lookup"><span data-stu-id="71104-105">The only restriction to inserting a node into the tree is that the document must still be well-formed after the node is inserted.</span></span> <span data-ttu-id="71104-106">Al insertar un nodo existente en el árbol DOM, se quita de su posición original y se agrega a su posición de destino.</span><span class="sxs-lookup"><span data-stu-id="71104-106">When an existing node is inserted into the DOM tree, it is removed from its original position and added to its target position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71104-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="71104-107">See also</span></span>

- [<span data-ttu-id="71104-108">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="71104-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
