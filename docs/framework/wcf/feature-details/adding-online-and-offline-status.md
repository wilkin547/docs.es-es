---
title: Cómo agregar el estado en línea y sin conexión
ms.date: 03/30/2017
ms.assetid: 05e5f51d-81b6-4c17-b364-9dda447a5fce
ms.openlocfilehash: da170bbc22d04dcbf5f7cd4ac084a004bb4b026e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597688"
---
# <a name="adding-online-and-offline-status"></a><span data-ttu-id="64374-102">Cómo agregar el estado en línea y sin conexión</span><span class="sxs-lookup"><span data-stu-id="64374-102">Adding Online and Offline Status</span></span>
<span data-ttu-id="64374-103">En muchos casos, es importante que una aplicación supervise los detalles concretos del estado de una conexión de canal del mismo nivel.</span><span class="sxs-lookup"><span data-stu-id="64374-103">In many cases, it is important for an application to monitor specific details about the status of a Peer Channel connection.</span></span> <span data-ttu-id="64374-104">Puede obtener esta información llamando al método `GetProperty` en una implementación de la interfaz <xref:System.ServiceModel.IOnlineStatus>.</span><span class="sxs-lookup"><span data-stu-id="64374-104">You can obtain this information by calling the `GetProperty` method on an implementation of the <xref:System.ServiceModel.IOnlineStatus> interface.</span></span> <span data-ttu-id="64374-105">Un objeto con una implementación de esta interfaz puede supervisar el estado de la conexión o registrarse  para los controladores de eventos, como `OnOnline` y `OnOffline`, y reaccionar inmediatamente en cuanto se produzcan cambios en el estado en línea.</span><span class="sxs-lookup"><span data-stu-id="64374-105">An object with an implementation of this interface can monitor connection status or register for event handlers, such as `OnOnline` and `OnOffline`, and react immediately as changes to online status occur.</span></span>  
  
 <span data-ttu-id="64374-106">En la infraestructura de canal del mismo nivel, se considera que un cliente está en línea si está conectado al menos a a otro del mismo nivel; de lo contrario estará sin conexión.</span><span class="sxs-lookup"><span data-stu-id="64374-106">In the Peer Channel infrastructure, a client is considered to be online if it is connected to at least one other peer and offline otherwise.</span></span> <span data-ttu-id="64374-107">Esto puede ser particularmente útil en la depuración de aplicaciones de desarrollo o en la visualización de información detallada en el usuario final.</span><span class="sxs-lookup"><span data-stu-id="64374-107">This can be particularly useful in both debugging a developing applications or displaying detailed information to the end user.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="64374-108">Un controlador de eventos en línea debería asegurarse primero que el nodo esté abierto antes de enviar cualquier mensaje.</span><span class="sxs-lookup"><span data-stu-id="64374-108">An online event handler should first ensure that the node is open before sending any messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64374-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="64374-109">See also</span></span>

- [<span data-ttu-id="64374-110">Creación de una aplicación de canal del mismo nivel</span><span class="sxs-lookup"><span data-stu-id="64374-110">Building a Peer Channel Application</span></span>](building-a-peer-channel-application.md)
