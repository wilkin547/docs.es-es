---
title: Negociación de seguridad y tiempos de espera
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
ms.openlocfilehash: 4ccc7e5539b1a772be6f9edb5a4cb4d94a8d1c1b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275988"
---
# <a name="security-negotiation-and-timeouts"></a>Negociación de seguridad y tiempos de espera

Cuando los clientes y servicios se autentican, Windows Communication Foundation (WCF) admite un modo en el que se negocia la credencial de servicio como parte de la autenticación. En tales escenarios, se produce un intercambio potencial de autenticación mutua entre el cliente y el servicio para propagar la credencial del servicio al cliente. La propiedad <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> controla cuánto tiempo puede tardar en completarse el intercambio de autenticación mutua. Sin embargo, este tiempo de espera sólo se aplica si el intercambio tarda más realmente que una solicitud-respuesta. En casos donde la negociación se completa en un viaje de ida y vuelta (round trip) único, el tiempo de espera no se aplica.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [Procedimiento para establecer un sesgo de reloj máximo](how-to-set-a-max-clock-skew.md)
