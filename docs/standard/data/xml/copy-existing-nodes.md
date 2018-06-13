---
title: Copiar nodos existentes
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2e7f5638d0d1f7bf450be526d7c295d4bb6a79eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567918"
---
# <a name="copy-existing-nodes"></a><span data-ttu-id="2ab5e-102">Copiar nodos existentes</span><span class="sxs-lookup"><span data-stu-id="2ab5e-102">Copy Existing Nodes</span></span>
<span data-ttu-id="2ab5e-103">Hay muchos métodos y propiedades en Document Object Model (DOM) XML que se pueden utilizar para seleccionar un nodo, como **SelectSingleNode**, **ChildNodes[int i]** y **Attributes[int i]**.</span><span class="sxs-lookup"><span data-stu-id="2ab5e-103">There are many methods and properties in the XML Document Object Model (DOM)you can use to select a node, such as **SelectSingleNode**, **ChildNodes[int i]**, **Attributes[int i]**.</span></span> <span data-ttu-id="2ab5e-104">Una vez seleccionado el nodo, puede insertarlo en el árbol mediante uno de los métodos de inserción que funcionan para dicho tipo de nodo en particular.</span><span class="sxs-lookup"><span data-stu-id="2ab5e-104">Once the node is selected, you can insert it into the tree using one of the insert methods that work for that particular node type.</span></span> <span data-ttu-id="2ab5e-105">La única restricción a la inserción de un nodo en el árbol es que el documento debe seguir teniendo un formato correcto después de insertarlo.</span><span class="sxs-lookup"><span data-stu-id="2ab5e-105">The only restriction to inserting a node into the tree is that the document must still be well-formed after the node is inserted.</span></span> <span data-ttu-id="2ab5e-106">Al insertar un nodo existente en el árbol DOM, se quita de su posición original y se agrega a su posición de destino.</span><span class="sxs-lookup"><span data-stu-id="2ab5e-106">When an existing node is inserted into the DOM tree, it is removed from its original position and added to its target position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab5e-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ab5e-107">See Also</span></span>  
 [<span data-ttu-id="2ab5e-108">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="2ab5e-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
