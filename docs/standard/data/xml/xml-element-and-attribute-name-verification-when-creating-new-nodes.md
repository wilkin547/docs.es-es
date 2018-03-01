---
title: "Comprobación de nombres de atributos y elementos XML al crear nodos nuevos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 36b9761cefb1dba47c88d053773c89e4312dee9d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a><span data-ttu-id="2999c-102">Comprobación de nombres de atributos y elementos XML al crear nodos nuevos</span><span class="sxs-lookup"><span data-stu-id="2999c-102">XML Element and Attribute Name Verification when Creating New Nodes</span></span>
<span data-ttu-id="2999c-103">El modelo de objetos de documento (DOM) XML comprueba la validez de los nombres cuando se crean nuevos nodos de elementos o de atributos.</span><span class="sxs-lookup"><span data-stu-id="2999c-103">The XML Document Object Model (DOM) checks the validity of the names when creating new element nodes or attribute nodes.</span></span> <span data-ttu-id="2999c-104">Si los nombres contienen caracteres no válidos, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="2999c-104">If the names contain illegal characters, an exception is thrown.</span></span> <span data-ttu-id="2999c-105">Para asegurarse de que los nombres son válidos y que están codificados correctamente, debe usar la clase **XmlConvert** para codificar el nombre y decodificarlo de nuevo en el nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2999c-105">To ensure that names are valid and encoded correctly, you need to use the **XmlConvert** class to encode the name and decode it back at an application level.</span></span> <span data-ttu-id="2999c-106">La clase **XmlWriter** cuenta con métodos que realizan trabajo adicional para asegurar que se genera XML con el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="2999c-106">The **XmlWriter** has methods that do additional work to ensure well-formed XML is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2999c-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="2999c-107">See Also</span></span>  
 [<span data-ttu-id="2999c-108">Document Object Model (DOM) para XML</span><span class="sxs-lookup"><span data-stu-id="2999c-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
