---
title: Se expanden las referencias de entidad pero no se preservan
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: ffd97806-ab43-4538-8de2-5828bfbbde57
ms.openlocfilehash: 1d26e9a35497bb0d5293e8a5b630bf4356325401
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84292051"
---
# <a name="entity-references-are-expanded-and-not-preserved"></a>Se expanden las referencias de entidad pero no se preservan
Cuando se expande la referencia de entidad y se reemplaza por el texto que representa, no se crea el nodo **XmlEntityReference**. En su lugar, se analiza la declaración de entidad y los nodos creados a partir del contenido de la declaración se copian en lugar del nodo **XmlEntityReference**. Por tanto, en el ejemplo de `&publisher;`, `&publisher;` no se guarda, sino que se crea un nodo **XmlText**.  
  
 ![estructura de árbol expandida](media/xmlentityref-expanded-nodes.gif "xmlentityref_expanded_nodes")  
Estructura de árbol para referencias de entidad que se expanden  
  
 Las entidades de caracteres, como `B` o `<`, no se conservan. En su lugar, siempre se expanden y se representan como nodos de texto.  
  
 Para preservar los nodos **XmlEntityReference** y los nodos secundarios de referencias de entidad asociados a ellos, configure la marca **EntityHandling** como **ExpandCharEntities**. De lo contrario, deje la marca **EntityHandling** con el valor predeterminado, que es **ExpandEntities**. En este caso, no verá los nodos de referencia de entidad de DOM. Los nodos se reemplazan por las copias de los nodos secundarios de la declaración de entidad.  
  
 Un efecto secundario que se produce si no se preservan las referencias de entidad es que al guardar el documento y pasarlo a otra aplicación, la aplicación receptora no sabe qué nodos fueron generados por una referencia de entidad. Sin embargo, cuando se preservan las referencias de entidad, una aplicación receptora ve una referencia de entidad y lee nodos secundarios. Es aparente que los nodos secundarios representan la información que estaba en la declaración de identidad. Por ejemplo, teóricamente, DOM tiene la siguiente estructura si se conservan referencias de entidad.  
  
 XmlElement: publisher  
  
 XmlEntityReference: `&publisher;`  
  
 XmlText: Microsoft Press  
  
 Si se expanden las referencias de entidad en DOM, que es el sistema predeterminado, la estructura tiene este tipo de árbol:  
  
 XmlElement: publisher  
  
 XmlText: Microsoft Press  
  
 Observe que desaparece todo el nodo de referencia de entidad y la aplicación receptora no puede indicar que el nodo **XmlText** que contiene "Microsoft Press" se creó a partir de una declaración de entidad.  
  
 Si utiliza un sistema de lectura que no puede resolver entidades, el método **Load** inicia una excepción al encontrar una referencia de entidad.  
  
## <a name="see-also"></a>Vea también

- [Document Object Model (DOM) para XML](xml-document-object-model-dom.md)
