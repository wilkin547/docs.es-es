---
title: Copiar nodos existentes
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 2aa8f65c-cc62-4638-9c46-129dc15be786
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2e7f5638d0d1f7bf450be526d7c295d4bb6a79eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="copy-existing-nodes"></a>Copiar nodos existentes
Hay muchos métodos y propiedades en Document Object Model (DOM) XML que se pueden utilizar para seleccionar un nodo, como **SelectSingleNode**, **ChildNodes[int i]** y **Attributes[int i]**. Una vez seleccionado el nodo, puede insertarlo en el árbol mediante uno de los métodos de inserción que funcionan para dicho tipo de nodo en particular. La única restricción a la inserción de un nodo en el árbol es que el documento debe seguir teniendo un formato correcto después de insertarlo. Al insertar un nodo existente en el árbol DOM, se quita de su posición original y se agrega a su posición de destino.  
  
## <a name="see-also"></a>Vea también  
 [Document Object Model (DOM) para XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
