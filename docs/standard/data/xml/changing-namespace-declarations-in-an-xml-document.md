---
title: Cambiar declaraciones de espacio de nombres en un documento XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 627882efcbc41310ee177cba984e4add5b07bd15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a><span data-ttu-id="0518a-102">Cambiar declaraciones de espacio de nombres en un documento XML</span><span class="sxs-lookup"><span data-stu-id="0518a-102">Changing Namespace Declarations in an XML Document</span></span>
<span data-ttu-id="0518a-103">El **XmlDocument** expone declaraciones de espacio de nombres y **xmlns** atributos como parte del modelo de objetos de documento.</span><span class="sxs-lookup"><span data-stu-id="0518a-103">The **XmlDocument** exposes namespace declarations and **xmlns** attributes as part of the document object model.</span></span> <span data-ttu-id="0518a-104">Estos se almacenan en la **XmlDocument**, por lo que cuando guarda el documento, puede conservar la ubicación de estos atributos.</span><span class="sxs-lookup"><span data-stu-id="0518a-104">These are stored in the **XmlDocument**, so when you save the document, it can preserve the location of those attributes.</span></span> <span data-ttu-id="0518a-105">Si se cambian estos atributos no tiene ningún efecto el **nombre**, **NamespaceURI**, y **prefijo** propiedades de otros nodos que ya estén en el árbol.</span><span class="sxs-lookup"><span data-stu-id="0518a-105">Changing these attributes has no affect on the **Name**, **NamespaceURI**, and **Prefix** properties of other nodes already in the tree.</span></span> <span data-ttu-id="0518a-106">Por ejemplo, si carga el documento siguiente, la `test` elemento tiene **NamespaceURI**`123.`</span><span class="sxs-lookup"><span data-stu-id="0518a-106">For example, if you load the following document, then the `test` element has **NamespaceURI** `123.`</span></span>  
  
```xml  
<test xmlns="123"/>  
```  
  
 <span data-ttu-id="0518a-107">Si quita el `xmlns` atributo como sigue, entonces, el `test` elemento todavía tiene la **NamespaceURI** de `123`.</span><span class="sxs-lookup"><span data-stu-id="0518a-107">If you remove the `xmlns` attribute as follows, then the `test` element still has the **NamespaceURI** of `123`.</span></span>  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 <span data-ttu-id="0518a-108">Del mismo modo, si agrega otro `xmlns` atribuir a la `doc` elemento tal como sigue, entonces, el `test` elemento todavía tiene **NamespaceURI** `123`.</span><span class="sxs-lookup"><span data-stu-id="0518a-108">Likewise, if you add a different `xmlns` attribute to the `doc` element as follows, then the `test` element still has **NamespaceURI** `123`.</span></span>  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 <span data-ttu-id="0518a-109">Por lo tanto, cambiar `xmlns` atributos no tendrán ningún efecto hasta que guardar y volver a cargar la **XmlDocument** objeto.</span><span class="sxs-lookup"><span data-stu-id="0518a-109">Therefore, changing `xmlns` attributes will have no affect until you save and reload the **XmlDocument** object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0518a-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0518a-110">See Also</span></span>  
 [<span data-ttu-id="0518a-111">Modelo de objetos de documento (DOM) de XML</span><span class="sxs-lookup"><span data-stu-id="0518a-111">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
