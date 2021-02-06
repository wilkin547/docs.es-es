---
description: 'Más información sobre: negociación de seguridad y tiempos de espera'
title: Negociación de seguridad y tiempos de espera
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: 50055698f9a9946d0c0110a964cf9ce5b9f4fa28
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632443"
---
# <a name="security-negotiation-and-timeouts"></a>Negociación de seguridad y tiempos de espera

Cuando los clientes y servicios se autentican, Windows Communication Foundation (WCF) admite un modo en el que se negocia la credencial de servicio como parte de la autenticación. En tales escenarios, se produce un intercambio potencial de autenticación mutua entre el cliente y el servicio para propagar la credencial del servicio al cliente. La propiedad <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> controla cuánto tiempo puede tardar en completarse el intercambio de autenticación mutua. Sin embargo, este tiempo de espera sólo se aplica si el intercambio tarda más realmente que una solicitud-respuesta. En casos donde la negociación se completa en un viaje de ida y vuelta (round trip) único, el tiempo de espera no se aplica.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [Procedimiento para establecer un sesgo de reloj máximo](how-to-set-a-max-clock-skew.md)
