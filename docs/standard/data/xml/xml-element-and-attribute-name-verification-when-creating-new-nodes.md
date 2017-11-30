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
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c041d5d2830222f3fae09a39f1ea10eb08772388
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a><span data-ttu-id="7d7a2-102">Comprobación de nombres de atributos y elementos XML al crear nodos nuevos</span><span class="sxs-lookup"><span data-stu-id="7d7a2-102">XML Element and Attribute Name Verification when Creating New Nodes</span></span>
<span data-ttu-id="7d7a2-103">El modelo de objetos de documento (DOM) XML comprueba la validez de los nombres cuando se crean nuevos nodos de elementos o de atributos.</span><span class="sxs-lookup"><span data-stu-id="7d7a2-103">The XML Document Object Model (DOM) checks the validity of the names when creating new element nodes or attribute nodes.</span></span> <span data-ttu-id="7d7a2-104">Si los nombres contienen caracteres no válidos, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="7d7a2-104">If the names contain illegal characters, an exception is thrown.</span></span> <span data-ttu-id="7d7a2-105">Para garantizar que los nombres son válidos y codificados correctamente, debe usar el **XmlConvert** clase para codificar el nombre y decodificarlo de nuevo en un nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d7a2-105">To ensure that names are valid and encoded correctly, you need to use the **XmlConvert** class to encode the name and decode it back at an application level.</span></span> <span data-ttu-id="7d7a2-106">El **XmlWriter** tiene métodos que realizan trabajo adicional para asegurarse de que se genera XML con formato correcto.</span><span class="sxs-lookup"><span data-stu-id="7d7a2-106">The **XmlWriter** has methods that do additional work to ensure well-formed XML is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d7a2-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d7a2-107">See Also</span></span>  
 [<span data-ttu-id="7d7a2-108">Modelo de objetos de documento (DOM) de XML</span><span class="sxs-lookup"><span data-stu-id="7d7a2-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
