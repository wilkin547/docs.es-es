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
# <a name="security-negotiation-and-timeouts"></a><span data-ttu-id="7c774-102">Negociación de seguridad y tiempos de espera</span><span class="sxs-lookup"><span data-stu-id="7c774-102">Security Negotiation and Timeouts</span></span>

<span data-ttu-id="7c774-103">Cuando los clientes y servicios se autentican, Windows Communication Foundation (WCF) admite un modo en el que se negocia la credencial de servicio como parte de la autenticación.</span><span class="sxs-lookup"><span data-stu-id="7c774-103">When clients and services authenticate, Windows Communication Foundation (WCF) supports a mode where the service credential is negotiated as part of authentication.</span></span> <span data-ttu-id="7c774-104">En tales escenarios, se produce un intercambio potencial de autenticación mutua entre el cliente y el servicio para propagar la credencial del servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="7c774-104">In such scenarios, a potentially multi-leg exchange occurs between the client and the service to propagate the service credential to the client.</span></span> <span data-ttu-id="7c774-105">La propiedad <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> controla cuánto tiempo puede tardar en completarse el intercambio de autenticación mutua.</span><span class="sxs-lookup"><span data-stu-id="7c774-105">The <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property controls how long the multi-leg exchange can take to complete.</span></span> <span data-ttu-id="7c774-106">Sin embargo, este tiempo de espera sólo se aplica si el intercambio tarda más realmente que una solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="7c774-106">However, this timeout only applies if the exchange actually takes more that a single request-response.</span></span> <span data-ttu-id="7c774-107">En casos donde la negociación se completa en un viaje de ida y vuelta (round trip) único, el tiempo de espera no se aplica.</span><span class="sxs-lookup"><span data-stu-id="7c774-107">In cases where the negotiation completes in a single round trip, the timeout does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c774-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c774-108">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- [<span data-ttu-id="7c774-109">Procedimiento para establecer un sesgo de reloj máximo</span><span class="sxs-lookup"><span data-stu-id="7c774-109">How to: Set a Max Clock Skew</span></span>](how-to-set-a-max-clock-skew.md)
