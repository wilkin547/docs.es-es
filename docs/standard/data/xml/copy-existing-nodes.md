---
title: Copiar nodos existentes
ms.date: 03/30/2017
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
ms.openlocfilehash: 651e9fc9dc0d1a50a2d15d382b3ca65f7fd4b7fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701437"
---
# <a name="copy-existing-nodes"></a>Copiar nodos existentes

Hay muchos métodos y propiedades en Document Object Model (DOM) XML que se pueden utilizar para seleccionar un nodo, como **SelectSingleNode**, **ChildNodes[int i]** y **Attributes[int i]** . Una vez seleccionado el nodo, puede insertarlo en el árbol mediante uno de los métodos de inserción que funcionan para dicho tipo de nodo en particular. La única restricción a la inserción de un nodo en el árbol es que el documento debe seguir teniendo un formato correcto después de insertarlo. Al insertar un nodo existente en el árbol DOM, se quita de su posición original y se agrega a su posición de destino.  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](xml-document-object-model-dom.md)
