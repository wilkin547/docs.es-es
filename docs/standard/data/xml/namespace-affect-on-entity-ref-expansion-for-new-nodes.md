---
title: Efecto del espacio de nombres en la expansión de referencias de entidad de nuevos nodos que contienen elementos y atributos
ms.date: 03/30/2017
ms.assetid: 64359aee-aab0-4042-9a32-d19789af6ca7
ms.openlocfilehash: 8ef86f05d2b39639ad5faae792eb9b2854ff0673
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830173"
---
# <a name="namespace-affect-on-entity-reference-expansion-for-new-nodes-containing-elements-and-attributes"></a><span data-ttu-id="7feae-102">Efecto del espacio de nombres en la expansión de referencias de entidad de nuevos nodos que contienen elementos y atributos</span><span class="sxs-lookup"><span data-stu-id="7feae-102">Namespace Affect on Entity Reference Expansion for New Nodes Containing Elements and Attributes</span></span>
<span data-ttu-id="7feae-103">Puesto que el contenido de una declaración de entidad puede incluir prácticamente cualquier cosa, cabe la posibilidad de que pueda incluir un elemento como `<!ENTITY aname "<elem>test</elem>">` .</span><span class="sxs-lookup"><span data-stu-id="7feae-103">Because the content of an entity declaration can contain almost anything, there is a possibility that the content could contain an element like `<!ENTITY aname "<elem>test</elem>">`.</span></span>  
  
 <span data-ttu-id="7feae-104">Al analizar el código XML, en el momento del análisis `&aname;` no se expande con su contenido de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="7feae-104">When the XML is parsed, `&aname;` is not expanded with its replacement content at parse time.</span></span> <span data-ttu-id="7feae-105">La expansión de XML no se realiza porque la resolución del espacio de nombres del elemento no puede producirse hasta que el nodo se coloque en el documento.</span><span class="sxs-lookup"><span data-stu-id="7feae-105">The expansion of the XML is not done because resolution of the namespace for the element cannot occur until the node is placed in the document.</span></span> <span data-ttu-id="7feae-106">Hasta ese momento, se desconoce qué espacio de nombres se encuentra dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="7feae-106">Until that time, there is no knowledge of what namespace is in scope.</span></span> <span data-ttu-id="7feae-107">Cuando se coloca el nodo en el documento, se produce la resolución del espacio de nombres y se analiza el contenido de la entidad resultante en sus nodos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="7feae-107">When the node is put into the document, then the namespace resolution occurs, and the resulting entity content is parsed into its appropriate nodes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7feae-108">Una vez que se produce la expansión en un nodo de referencia de entidad recién creado, nunca se vuelve a repetir.</span><span class="sxs-lookup"><span data-stu-id="7feae-108">Once the expansion occurs on a newly created entity reference node, it never reoccurs.</span></span> <span data-ttu-id="7feae-109">Por tanto, los espacios de nombres utilizados en el texto de reemplazo del elemento están enlazados al momento en que se establece el nodo primario.</span><span class="sxs-lookup"><span data-stu-id="7feae-109">Therefore, the namespaces used in the replacement text for the element are bound at the time that the parent node is set.</span></span> <span data-ttu-id="7feae-110">No obstante, se puede cambiar el espacio de nombres para los nodos de referencia de entidad existentes, cuando se quitan o insertan en otro lugar, o en nodos de referencia de entidad clonados mediante el método **CloneNode**.</span><span class="sxs-lookup"><span data-stu-id="7feae-110">However, the namespace can be changed for existing entity reference nodes when you remove and insert them somewhere else, or on entity reference nodes that are cloned with the **CloneNode** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7feae-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="7feae-111">See also</span></span>

- [<span data-ttu-id="7feae-112">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="7feae-112">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
