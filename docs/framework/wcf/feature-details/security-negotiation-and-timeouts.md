---
title: Negociación de seguridad y tiempos de espera
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: a02c9d7b42eadf9a5ce9af8022fe292d6c23249c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180653"
---
# <a name="security-negotiation-and-timeouts"></a>Negociación de seguridad y tiempos de espera
Cuando los clientes y servicios autentican, Windows Communication Foundation (WCF) admite un modo donde se negocia la credencial de servicio como parte de la autenticación. En tales escenarios, se produce un intercambio potencial de autenticación mutua entre el cliente y el servicio para propagar la credencial del servicio al cliente. La propiedad <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> controla cuánto tiempo puede tardar en completarse el intercambio de autenticación mutua. Sin embargo, este tiempo de espera sólo se aplica si el intercambio tarda más realmente que una solicitud-respuesta. En casos donde la negociación se completa en un viaje de ida y vuelta (round trip) único, el tiempo de espera no se aplica.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [Cómo: Conjunto un sesgo de reloj máximo](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
