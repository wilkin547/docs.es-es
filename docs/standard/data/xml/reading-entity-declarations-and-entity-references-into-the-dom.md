---
title: Leer declaraciones de entidad y referencias de entidad en DOM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86dba977-5cc4-4567-964f-027ffabc47b2
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6370db06cbe7ff8d46258b0315059f5c37587fea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="reading-entity-declarations-and-entity-references-into-the-dom"></a>Leer declaraciones de entidad y referencias de entidad en DOM
Una entidad es una declaración que establece un nombre que se va a utilizar en el código XML en lugar de contenido o marcado. Para las entidades hay dos partes. En primer lugar, se debe asociar un nombre al contenido de reemplazo, utilizando una declaración de entidad. Una declaración de entidad se crea mediante la sintaxis `<!ENTITY name "value">` incluida o en una DTD o esquema XML. En segundo lugar, el nombre definido en la declaración de entidad se utiliza posteriormente en el XML. Al utilizarlo en el código XML, se conoce como referencia de entidad. Por ejemplo, en la declaración de entidad siguiente se declara una entidad del nombre `publisher` que está asociada al contenido de "Microsoft Press".  
  
```xml  
<!ENTITY publisher "Microsoft Press">  
```  
  
 En el ejemplo siguiente se muestra el uso de esta declaración de entidad en XML como una referencia de entidad.  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 Algunos analizadores expanden las entidades automáticamente al cargar un documento en la memoria. Por tanto, cuando se lee el XML en la memoria, se recuerdan y guardan las declaraciones de entidad. Cuando el analizador encuentra posteriormente caracteres `&;`, que identifican una referencia de entidad general, el analizador busca dicho nombre en una tabla de declaraciones de entidad. La referencia, `&publisher;`, se reemplaza por el contenido que representa. Con el siguiente código XML,  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 que expande la referencia de entidad y se reemplaza `&publisher;` por el contenido de Microsoft Press, se proporciona el siguiente código XML expandido.  
  
 **Salida**  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by Microsoft Press</pubinfo>  
```  
  
 Hay muchos tipos de entidades. En el diagrama siguiente se muestra la división de los tipos de entidades y terminología.  
  
 ![diagrama de flujo de jerarquía de tipos de entidad](../../../../docs/standard/data/xml/media/entity-hierarchy.gif "Entity_hierarchy")  
  
 El valor predeterminado para la implementación de Microsoft .NET Framework de XML Document Object Model (DOM) es preservar las referencias de entidades y no expandir las entidades cuando se carga XML. La implicación de esto es que, tal y como se carga un documento en DOM, un **XmlEntityReference** nodo que contiene la variable de referencia `&publisher;` está creado, con nodos secundarios que representan el contenido de la entidad declarado en la DTD.  
  
 Mediante el `<!ENTITY publisher "Microsoft Press">` declaración de entidad, el siguiente diagrama muestra la **XmlEntity** y **XmlText** nodos creados a partir de esta declaración.  
  
 ![nodos creados a partir de la declaración de entidad](../../../../docs/standard/data/xml/media/xml-entitydeclaration-node2.png "xml_entitydeclaration_node2")  
  
 Las diferencias existentes al expandir o no referencias de entidad determinan los nodos generados en el árbol DOM, en la memoria. La diferencia en los nodos generados se explica en los temas [se preservan las referencias de entidad](../../../../docs/standard/data/xml/entity-references-are-preserved.md) y [las referencias de entidad son expandida y no conserva](../../../../docs/standard/data/xml/entity-references-are-expanded-and-not-preserved.md).  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
