---
title: "Efecto del espacio de nombres en la expansión de referencias de entidad de nuevos nodos que contienen elementos y atributos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64359aee-aab0-4042-9a32-d19789af6ca7
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9b59f85eb0ef6646345eaef2a409f622c6fe4651
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="namespace-affect-on-entity-reference-expansion-for-new-nodes-containing-elements-and-attributes"></a>Efecto del espacio de nombres en la expansión de referencias de entidad de nuevos nodos que contienen elementos y atributos
Puesto que el contenido de una declaración de entidad puede incluir prácticamente cualquier cosa, cabe la posibilidad de que pueda incluir un elemento como `<!ENTITY aname "<elem>test</elem>">` .  
  
 Al analizar el código XML, en el momento del análisis `&aname;` no se expande con su contenido de reemplazo. La expansión de XML no se realiza porque la resolución del espacio de nombres del elemento no puede producirse hasta que el nodo se coloque en el documento. Hasta ese momento, se desconoce qué espacio de nombres se encuentra dentro del ámbito. Cuando se coloca el nodo en el documento, se produce la resolución del espacio de nombres y se analiza el contenido de la entidad resultante en sus nodos correspondientes.  
  
> [!NOTE]
>  Una vez que se produce la expansión en un nodo de referencia de entidad recién creado, nunca se vuelve a repetir. Por tanto, los espacios de nombres utilizados en el texto de reemplazo del elemento están enlazados al momento en que se establece el nodo primario. No obstante, se puede cambiar el espacio de nombres para los nodos de referencia de entidad existentes, cuando se quitan o insertan en otro lugar, o en nodos de referencia de entidad clonados mediante el método **CloneNode**.  
  
## <a name="see-also"></a>Vea también  
 [Document Object Model (DOM) para XML](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
