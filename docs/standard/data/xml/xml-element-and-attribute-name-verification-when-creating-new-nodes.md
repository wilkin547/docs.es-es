---
title: Comprobación de nombres de atributos y elementos XML al crear nodos nuevos
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
ms.openlocfilehash: 7c99ffa9d139d94d26c562cb1668f1b855bed32d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709951"
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a>Comprobación de nombres de atributos y elementos XML al crear nodos nuevos
El modelo de objetos de documento (DOM) XML comprueba la validez de los nombres cuando se crean nuevos nodos de elementos o de atributos. Si los nombres contienen caracteres no válidos, se produce una excepción. Para asegurarse de que los nombres son válidos y que están codificados correctamente, debe usar la clase **XmlConvert** para codificar el nombre y decodificarlo de nuevo en el nivel de aplicación. La clase **XmlWriter** cuenta con métodos que realizan trabajo adicional para asegurar que se genera XML con el formato correcto.  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
