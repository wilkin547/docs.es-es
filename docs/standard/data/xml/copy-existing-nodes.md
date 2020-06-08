---
title: Copiar nodos existentes
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
ms.openlocfilehash: 392490d04ff713529d501e199ac2496ff37de1a0
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289218"
---
# <a name="copy-existing-nodes"></a>Copiar nodos existentes
Hay muchos métodos y propiedades en Document Object Model (DOM) XML que se pueden utilizar para seleccionar un nodo, como **SelectSingleNode**, **ChildNodes[int i]** y **Attributes[int i]** . Una vez seleccionado el nodo, puede insertarlo en el árbol mediante uno de los métodos de inserción que funcionan para dicho tipo de nodo en particular. La única restricción a la inserción de un nodo en el árbol es que el documento debe seguir teniendo un formato correcto después de insertarlo. Al insertar un nodo existente en el árbol DOM, se quita de su posición original y se agrega a su posición de destino.  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](xml-document-object-model-dom.md)
