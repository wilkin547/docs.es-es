---
title: Copiar nodos existentes
ms.date: 03/30/2017
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
ms.openlocfilehash: b4ae24f9776456033a876e8ae4d1515d2f669fe0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830953"
---
# <a name="copy-existing-nodes"></a>Copiar nodos existentes
Hay muchos métodos y propiedades en Document Object Model (DOM) XML que se pueden utilizar para seleccionar un nodo, como **SelectSingleNode**, **ChildNodes[int i]** y **Attributes[int i]** . Una vez seleccionado el nodo, puede insertarlo en el árbol mediante uno de los métodos de inserción que funcionan para dicho tipo de nodo en particular. La única restricción a la inserción de un nodo en el árbol es que el documento debe seguir teniendo un formato correcto después de insertarlo. Al insertar un nodo existente en el árbol DOM, se quita de su posición original y se agrega a su posición de destino.  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](xml-document-object-model-dom.md)
