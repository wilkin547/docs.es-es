---
title: Se expanden las referencias de entidad pero no se preservan
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffd97806-ab43-4538-8de2-5828bfbbde57
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 069d3b94a0269917400e75fdbe975ec39dcfdb71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="entity-references-are-expanded-and-not-preserved"></a>Se expanden las referencias de entidad pero no se preservan
Cuando se expande la referencia de entidad y se reemplaza por el texto que representa, el **XmlEntityReference** no se crea el nodo. En su lugar, se analiza la declaración de entidad y los nodos creados a partir del contenido de la declaración se copian en lugar de la **XmlEntityReference**. Por lo tanto, en la `&publisher;` ejemplo, el `&publisher;` no se guarda, pero en su lugar, un **XmlText** se crea el nodo.  
  
 ![expande la estructura de árbol](../../../../docs/standard/data/xml/media/xmlentityref-expanded-nodes.gif "xmlentityref_expanded_nodes")  
Estructura de árbol para referencias de entidad que se expanden  
  
 Las entidades de caracteres, como `B` o `<`, no se conservan. En su lugar, siempre se expanden y se representan como nodos de texto.  
  
 Para conservar la **XmlEntityReference** nodos y los nodos secundarios de la referencia de entidad asociados a ellos, establezca el **EntityHandling** indicador en **ExpandCharEntities**. De lo contrario, deje el **EntityHandling** marca con el valor predeterminado, que consiste en **ExpandEntities**. En este caso, no verá los nodos de referencia de entidad de DOM. Los nodos se reemplazan por las copias de los nodos secundarios de la declaración de entidad.  
  
 Un efecto secundario que se produce si no se preservan las referencias de entidad es que al guardar el documento y pasarlo a otra aplicación, la aplicación receptora no sabe qué nodos fueron generados por una referencia de entidad. Sin embargo, cuando se preservan las referencias de entidad, una aplicación receptora ve una referencia de entidad y lee nodos secundarios. Es aparente que los nodos secundarios representan la información que estaba en la declaración de identidad. Por ejemplo, teóricamente, DOM tiene la siguiente estructura si se conservan referencias de entidad.  
  
 XmlElement: publisher  
  
 XmlEntityReference: `&publisher;`  
  
 XmlText: Microsoft Press  
  
 Si se expanden las referencias de entidad en DOM, que es el sistema predeterminado, la estructura tiene este tipo de árbol:  
  
 XmlElement: publisher  
  
 XmlText: Microsoft Press  
  
 Observe que desaparece todo el nodo de referencia de entidad y la aplicación receptora no puede indicar que el **XmlText** nodo que contiene "Microsoft Press" se creó a partir de una declaración de entidad.  
  
 Si utiliza un lector que no se puede resolver entidades, el **carga** método produce una excepción cuando encuentra una referencia de entidad.  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
