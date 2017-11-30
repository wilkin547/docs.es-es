---
title: Crear nuevas referencias de entidad
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a42f81b3-0403-4e34-b346-7d2129804e54
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 22e9b66f58275141cf9da154573ca43a0b90affc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-entity-references"></a>Crear nuevas referencias de entidad
El **CreateEntityReference** método crea un nuevo **XmlEntityReference** nodo. El Modelo de objetos de documento (DOM) busca si el nombre de entidad al que se hace referencia ya se ha declarado. Si lo tiene, los nodos secundarios del **XmlEntityReference** nodo se copian desde el nodo de declaración de entidad. Si no hay declaración de entidad equivalente, se adjunta un nodo de texto vacío como el único nodo secundario del nodo de referencia de entidad. Dado que los nodos secundarios de la **XmlEntityReference** se copian de otros nodos, los siguientes nodos secundarios son de solo lectura y no se puede modificar.  
  
 Al copiar los nodos, puede haber un espacio de nombres en el punto de la referencia de entidad. Este espacio de nombres afecta la configuración de los elementos o nodos de atributo generados.  
  
> [!NOTE]
>  DOM agrega nodos secundarios a la **EntityReference** solo cuando se inserta el **EntityReference** nodo en el documento. Acaba de crear **EntityReference** nodos no tienen nodos secundarios.  
  
 Aunque la **XmlDataDocument** es una clase derivada de la **XmlDocument**, **XmlDataDocument** no admite la creación de referencias de entidad. Esto es porque **EntityReference** elementos secundarios son de solo lectura. Los elementos secundarios de un **EntityReference** nodo puede abarcar más de una región. En este caso, parte de una fila asociada a la región que contiene una parte de un **EntityReference** serán de sólo lectura.  
  
## <a name="see-also"></a>Vea también  
 [Modelo de objetos de documento (DOM) de XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
