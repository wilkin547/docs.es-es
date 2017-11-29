---
title: "Cómo agregar el estado en línea y sin conexión"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05e5f51d-81b6-4c17-b364-9dda447a5fce
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1a9f4cf65febd955e69d81f8dbb8f97aaa24e68c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="adding-online-and-offline-status"></a>Cómo agregar el estado en línea y sin conexión
En muchos casos, es importante que una aplicación supervise los detalles concretos del estado de una conexión de canal del mismo nivel. Puede obtener esta información llamando al método `GetProperty` en una implementación de la interfaz <xref:System.ServiceModel.IOnlineStatus>. Un objeto con una implementación de esta interfaz puede supervisar el estado de la conexión o registrarse  para los controladores de eventos, como `OnOnline` y `OnOffline`, y reaccionar inmediatamente en cuanto se produzcan cambios en el estado en línea.  
  
 En la infraestructura de canal del mismo nivel, se considera que un cliente está en línea si está conectado al menos a a otro del mismo nivel; de lo contrario estará sin conexión. Esto puede ser particularmente útil en la depuración de aplicaciones de desarrollo o en la visualización de información detallada en el usuario final.  
  
> [!NOTE]
>  Un controlador de eventos en línea debería asegurarse primero que el nodo esté abierto antes de enviar cualquier mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Creación de una aplicación de canal del mismo nivel](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
