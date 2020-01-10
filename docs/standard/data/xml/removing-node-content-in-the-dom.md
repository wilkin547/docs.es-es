---
title: Cómo quitar el contenido de los nodos en el DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
ms.openlocfilehash: f5086bdea8ff1f0ee5329f347223ebb4a6bd71da
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710341"
---
# <a name="removing-node-content-in-the-dom"></a>Cómo quitar el contenido de los nodos en el DOM
En el caso de los tipos de nodos que heredan de <xref:System.Xml.XmlCharacterData>, que son los tipos de nodos <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace> y <xref:System.Xml.XmlSignificantWhitespace>, se pueden quitar caracteres utilizando el método <xref:System.Xml.XmlCharacterData.DeleteData%2A>, que elimina un intervalo de caracteres del nodo. Si desea quitar todo el contenido, debe eliminar el nodo que incluye el contenido. Si quiere conservar el nodo, pero el contenido no es correcto, debe modificar el contenido. Para obtener información sobre la modificación del contenido de un nodo, vea [Modificación de nodos, contenido y valores en un documento XML](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
