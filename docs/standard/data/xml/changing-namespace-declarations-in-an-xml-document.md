---
title: Cambiar declaraciones de espacio de nombres en un documento XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
ms.openlocfilehash: e55486feeb427c95a9394ac83758e6052603921e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291583"
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a><span data-ttu-id="d469e-102">Cambiar declaraciones de espacio de nombres en un documento XML</span><span class="sxs-lookup"><span data-stu-id="d469e-102">Changing Namespace Declarations in an XML Document</span></span>
<span data-ttu-id="d469e-103">**XmlDocument** expone declaraciones de espacios de nombres y atributos **xmlns**como parte del modelo de objetos de documento.</span><span class="sxs-lookup"><span data-stu-id="d469e-103">The **XmlDocument** exposes namespace declarations and **xmlns** attributes as part of the document object model.</span></span> <span data-ttu-id="d469e-104">Estos se almacenan en **XmlDocument**, de modo que, al guardar el documento, puede conservar la ubicación de dichos atributos.</span><span class="sxs-lookup"><span data-stu-id="d469e-104">These are stored in the **XmlDocument**, so when you save the document, it can preserve the location of those attributes.</span></span> <span data-ttu-id="d469e-105">Si se cambian estos atributos, no se produce ningún efecto en las propiedades **Name**, **NamespaceURI** y **Prefix** de otros nodos que ya estén en el árbol.</span><span class="sxs-lookup"><span data-stu-id="d469e-105">Changing these attributes has no affect on the **Name**, **NamespaceURI**, and **Prefix** properties of other nodes already in the tree.</span></span> <span data-ttu-id="d469e-106">Por ejemplo, si carga el documento siguiente, el elemento `test` tiene **NamespaceURI** `123.`</span><span class="sxs-lookup"><span data-stu-id="d469e-106">For example, if you load the following document, then the `test` element has **NamespaceURI** `123.`</span></span>  
  
```xml  
<test xmlns="123"/>  
```  
  
 <span data-ttu-id="d469e-107">Si quita el atributo `xmlns` como sigue, entonces el elemento `test` tiene todavía **NamespaceURI** de `123`.</span><span class="sxs-lookup"><span data-stu-id="d469e-107">If you remove the `xmlns` attribute as follows, then the `test` element still has the **NamespaceURI** of `123`.</span></span>  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 <span data-ttu-id="d469e-108">Del mismo modo, si añade otro atributo `xmlns` al elemento `doc` como se muestra a continuación, el elemento `test` todavía tiene **NamespaceURI** `123`.</span><span class="sxs-lookup"><span data-stu-id="d469e-108">Likewise, if you add a different `xmlns` attribute to the `doc` element as follows, then the `test` element still has **NamespaceURI** `123`.</span></span>  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456")
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 <span data-ttu-id="d469e-109">Por tanto, si se cambian los atributos `xmlns` no se produce ningún efecto hasta que se guarde y se recargue el objeto **XmlDocument**.</span><span class="sxs-lookup"><span data-stu-id="d469e-109">Therefore, changing `xmlns` attributes will have no affect until you save and reload the **XmlDocument** object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d469e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d469e-110">See also</span></span>

- [<span data-ttu-id="d469e-111">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="d469e-111">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
