---
title: Se preservan las referencias de entidad
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 770c714e8f5942ea733c417ae9b06f69e4acf1a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="entity-references-are-preserved"></a>Se preservan las referencias de entidad
Cuando no se expande toda la referencia de entidad, sino que se conserva, el modelo de objetos de documento (DOM) XML compila un **XmlEntityReference** nodo cuando encuentra una referencia de entidad.  
  
 Con el siguiente código XML,  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 el DOM compila un **XmlEntityReference** nodo cuando encuentra el `&publisher;` referencia. El **XmlEntityReference** contiene nodos secundarios copiados a partir del contenido en la declaración de entidad. El ejemplo de código anterior contiene texto en la declaración de entidad, de forma que un **XmlText** se crea el nodo como nodo secundario del nodo de referencia de entidad.  
  
 ![Estructura para referencias de entidades conservadas de árbol](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")  
Estructura de árbol para referencias de entidad que se preservan  
  
 Los nodos secundarios de la **XmlEntityReference** son nodos creados a partir de copias de todos los secundarios del **XmlEntity** nodo cuando se encuentra la declaración de entidad.  
  
> [!NOTE]
>  Los nodos copiados de la **XmlEntity** no son siempre copias exactas una vez situados bajo el nodo de referencia de entidad. Puede haber espacios de nombres que estén en el ámbito de un nodo de referencia de entidad y que afecten a la configuración final de los nodos secundarios.  
  
 De forma predeterminada, las entidades generales como `&abc;` se conservan y **XmlEntityReference** siempre se crean nodos.  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
