---
description: Más información acerca de cómo evitar ataques de reproducción cuando un servicio WCF se hospeda en una granja de servidores Web
title: Prevenir ataques por repetición cuando un servicio WCF está hospedado en una granja web
ms.date: 03/30/2017
ms.assetid: 1c2ed695-7a31-4257-92bd-9e9731b886a5
ms.openlocfilehash: 015059ef650b3ec213c54b89763bac7d46dd218f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793615"
---
# <a name="preventing-replay-attacks-when-a-wcf-service-is-hosted-in-a-web-farm"></a>Prevenir ataques por repetición cuando un servicio WCF está hospedado en una granja web

Cuando se usa seguridad de mensajes, WCF impide los ataques por repetición creando un NONCE a partir del mensaje entrante y comprobando la `InMemoryNonceCache` interna para ver si el NONCE generado está presente. Si lo está, el mensaje se descarta como respuesta. Cuando un servicio de WCF se hospeda en una granja de servidores web, como `InMemoryNonceCache` no se comparte entre los nodos de la granja de servidores web, el servicio es vulnerable a ataques mediante repetición.  Para mitigar este escenario WCF 4.5 proporciona un punto de extensibilidad que le permite implementar su propia memoria caché compartida de NONCE derivando una clase de la clase abstracta <xref:System.ServiceModel.Security.NonceCache>.  
  
## <a name="noncecache-implementation"></a>Implementación de NonceCache  

 Para implementar su propia caché compartida de NONCE, derive una clase de <xref:System.ServiceModel.Security.NonceCache> y reemplace los métodos <xref:System.ServiceModel.Security.NonceCache.CheckNonce%2A> y <xref:System.ServiceModel.Security.NonceCache.TryAddNonce%2A>. <xref:System.ServiceModel.Security.NonceCache.CheckNonce%2A> comprobará para ver si el NONCE especificado existe en la memoria caché. <xref:System.ServiceModel.Security.NonceCache.TryAddNonce%2A> intentará agregar un NONCE a la memoria caché. Una vez implementada la clase, puede enlazarla creando una instancia y asignándola a <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.NonceCache%2A> para la detección de reproducción del lado cliente y a <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NonceCache%2A> para la detección de reproducción del lado servidor. No hay compatibilidad con la configuración lista para usar para esta característica.  
  
## <a name="see-also"></a>Vea también

- [Seguridad de los mensajes](message-security-in-wcf.md)
- [SymmetricSecurityBindingElement](../diagnostics/wmi/symmetricsecuritybindingelement.md)
