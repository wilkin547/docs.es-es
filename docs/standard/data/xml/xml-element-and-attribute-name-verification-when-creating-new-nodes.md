---
title: Comprobación de nombres de atributos y elementos XML al crear nodos nuevos
ms.date: 03/30/2017
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
ms.openlocfilehash: 0678f7daf5276a905ce890a5f6a0f64993fb08b0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828822"
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a>Comprobación de nombres de atributos y elementos XML al crear nodos nuevos
El modelo de objetos de documento (DOM) XML comprueba la validez de los nombres cuando se crean nuevos nodos de elementos o de atributos. Si los nombres contienen caracteres no válidos, se produce una excepción. Para asegurarse de que los nombres son válidos y que están codificados correctamente, debe usar la clase **XmlConvert** para codificar el nombre y decodificarlo de nuevo en el nivel de aplicación. La clase **XmlWriter** cuenta con métodos que realizan trabajo adicional para asegurar que se genera XML con el formato correcto.  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](xml-document-object-model-dom.md)
