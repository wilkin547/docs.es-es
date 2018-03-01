---
title: Cambiar propiedades de prefijo de espacio de nombres
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
ms.assetid: d5c87cbe-4d69-429f-aad5-3103c2ca2770
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3cb0db0fbffa5f42fb09f29da2976727451e3741
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="changing-namespace-prefix-properties"></a><span data-ttu-id="a6ab2-102">Cambiar propiedades de prefijo de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="a6ab2-102">Changing Namespace Prefix Properties</span></span>
<span data-ttu-id="a6ab2-103">La clase **XmlNode** permite cambiar el prefijo de espacio de nombres asociado a un nodo concreto.</span><span class="sxs-lookup"><span data-stu-id="a6ab2-103">The **XmlNode** class allows you to change the namespace prefix associated with a given node.</span></span> <span data-ttu-id="a6ab2-104">Por ejemplo, en el código siguiente se muestra el prefijo de un elemento que se está cambiando.</span><span class="sxs-lookup"><span data-stu-id="a6ab2-104">For example, the following code shows the prefix of an element being changed.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "b"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<a:test xmlns:a='123' xmlns:b='456'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "b";  
Console.WriteLine(doc.InnerXml);  
```  
  
 <span data-ttu-id="a6ab2-105">**Salida**</span><span class="sxs-lookup"><span data-stu-id="a6ab2-105">**Output**</span></span>  
  
```xml  
<b:test xmlns:a="123" xmlns:b="456" />  
```  
  
 <span data-ttu-id="a6ab2-106">Si se modifica el prefijo de un nodo, no se cambia su espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a6ab2-106">Changing the prefix of a node does not change its namespace.</span></span> <span data-ttu-id="a6ab2-107">El espacio de nombres solo puede establecerse al crear el nodo.</span><span class="sxs-lookup"><span data-stu-id="a6ab2-107">The namespace can only be set when the node is created.</span></span> <span data-ttu-id="a6ab2-108">Al mantener el árbol, los nuevos atributos de espacio de nombres se pueden mantener de modo que se ajusten al prefijo establecido.</span><span class="sxs-lookup"><span data-stu-id="a6ab2-108">When you persist the tree, new namespace attributes may be persisted out to satisfy the prefix you set.</span></span> <span data-ttu-id="a6ab2-109">Si no se puede crear el nuevo espacio de nombres, se cambia el prefijo de forma que el nodo conserva su nombre local y espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a6ab2-109">If the new namespace cannot be created, then the prefix is changed so the node preserves its local name and namespace.</span></span> <span data-ttu-id="a6ab2-110">En el ejemplo siguiente se muestra la adición de un atributo de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="a6ab2-110">The following example shows a namespace attribute being added.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.LoadXml("<test xmlns='123'/>")  
Dim e as XmlElement = doc.DocumentElement  
e.Prefix = "a"  
Console.WriteLine(doc.InnerXml)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.LoadXml("<test xmlns='123'/>");  
XmlElement e = doc.DocumentElement;         
e.Prefix = "a";  
Console.WriteLine(doc.InnerXml);  
```  
  
 <span data-ttu-id="a6ab2-111">**Salida**</span><span class="sxs-lookup"><span data-stu-id="a6ab2-111">**Output**</span></span>  
  
```xml  
<a:test xmlns="123" xmlns:a="123" />  
```  
  
 <span data-ttu-id="a6ab2-112">Cuando el árbol se mantuvo en una cadena como resultado de la llamada a **doc.InnerXml**, el atributo `xmlns:a='123'` se agregó para conservar el espacio de nombres del elemento `test`.</span><span class="sxs-lookup"><span data-stu-id="a6ab2-112">When the tree was persisted to a string as a result of the call to **doc.InnerXml**, the `xmlns:a='123'` attribute was added to preserve the namespace of the `test` element.</span></span> <span data-ttu-id="a6ab2-113">Era `'123'` y sigue siendo `'123'`.</span><span class="sxs-lookup"><span data-stu-id="a6ab2-113">It was `'123'`, and it remained `'123'`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ab2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6ab2-114">See Also</span></span>  
 [<span data-ttu-id="a6ab2-115">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="a6ab2-115">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
