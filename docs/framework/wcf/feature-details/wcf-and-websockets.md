---
description: 'Más información sobre: WCF y WebSockets'
title: WCF y WebSockets
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: 6b0d8c33000a65bf3bbf834f66119d65768b3cb6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755985"
---
# <a name="wcf-and-websockets"></a>WCF y WebSockets

.NET Framework 4.5 presenta compatibilidad con WebSockets en Windows Communication Foundation.  WebSockets es una tecnología eficaz basada en estándares que permite la comunicación bidireccional a través de los puertos estándar 80 y 443 de HTTP. El uso de los puertos HTTP estándar permite que WebSockets se comunique a través de la Web mediante intermediarios.  Se han agregado dos nuevos enlaces estándar para admitir la comunicación a través de un transporte WebSocket. <xref:System.ServiceModel.NetHttpBinding> y <xref:System.ServiceModel.NetHttpsBinding>. La configuración específica de WebSockets puede configurarse en <xref:System.ServiceModel.Channels.HttpTransportBindingElement> mediante el acceso a la <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> propiedad.
  
## <a name="in-this-section"></a>En esta sección  

 [Usar NetHttpBinding](using-the-nethttpbinding.md)  
 Describe <xref:System.ServiceModel.NetHttpBinding> y su configuración.  
  
 [Procedimiento para crear un servicio WCF que se comunique a través de WebSockets](how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 Describe cómo crear un servicio WCF que se comunique a través de Websockets.  
  
## <a name="reference"></a>Referencia  
  
## <a name="related-sections"></a>Secciones relacionadas
