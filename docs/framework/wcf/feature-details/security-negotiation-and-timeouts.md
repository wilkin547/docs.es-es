---
title: Negociación de seguridad y tiempos de espera
ms.date: 03/30/2017
ms.assetid: 02a428f1-84e5-4d28-a11f-53ce31d63196
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 508d648acf148f13076327bb312d0a0b08471ac1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497469"
---
# <a name="security-negotiation-and-timeouts"></a><span data-ttu-id="f08a2-102">Negociación de seguridad y tiempos de espera</span><span class="sxs-lookup"><span data-stu-id="f08a2-102">Security Negotiation and Timeouts</span></span>
<span data-ttu-id="f08a2-103">Cuando los clientes y servicios autentican, Windows Communication Foundation (WCF) admite un modo donde se negocia la credencial de servicio como parte de la autenticación.</span><span class="sxs-lookup"><span data-stu-id="f08a2-103">When clients and services authenticate, Windows Communication Foundation (WCF) supports a mode where the service credential is negotiated as part of authentication.</span></span> <span data-ttu-id="f08a2-104">En tales escenarios, se produce un intercambio potencial de autenticación mutua entre el cliente y el servicio para propagar la credencial del servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="f08a2-104">In such scenarios, a potentially multi-leg exchange occurs between the client and the service to propagate the service credential to the client.</span></span> <span data-ttu-id="f08a2-105">La propiedad <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> controla cuánto tiempo puede tardar en completarse el intercambio de autenticación mutua.</span><span class="sxs-lookup"><span data-stu-id="f08a2-105">The <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property controls how long the multi-leg exchange can take to complete.</span></span> <span data-ttu-id="f08a2-106">Sin embargo, este tiempo de espera sólo se aplica si el intercambio tarda más realmente que una solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="f08a2-106">However, this timeout only applies if the exchange actually takes more that a single request-response.</span></span> <span data-ttu-id="f08a2-107">En casos donde la negociación se completa en un viaje de ida y vuelta (round trip) único, el tiempo de espera no se aplica.</span><span class="sxs-lookup"><span data-stu-id="f08a2-107">In cases where the negotiation completes in a single round trip, the timeout does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f08a2-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="f08a2-108">See Also</span></span>  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 [<span data-ttu-id="f08a2-109">Definición de un sesgo de reloj máximo</span><span class="sxs-lookup"><span data-stu-id="f08a2-109">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)
