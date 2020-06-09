---
title: WCF y WebSockets
ms.date: 03/30/2017
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
ms.openlocfilehash: df4a251eb5a570c9fedf19d385a027e23481afed
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594951"
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
