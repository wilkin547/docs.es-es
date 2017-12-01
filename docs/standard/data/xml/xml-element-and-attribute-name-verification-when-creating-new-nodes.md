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
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a>Comprobación de nombres de atributos y elementos XML al crear nodos nuevos
El modelo de objetos de documento (DOM) XML comprueba la validez de los nombres cuando se crean nuevos nodos de elementos o de atributos. Si los nombres contienen caracteres no válidos, se produce una excepción. Para garantizar que los nombres son válidos y codificados correctamente, debe usar el **XmlConvert** clase para codificar el nombre y decodificarlo de nuevo en un nivel de aplicación. El **XmlWriter** tiene métodos que realizan trabajo adicional para asegurarse de que se genera XML con formato correcto.  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
