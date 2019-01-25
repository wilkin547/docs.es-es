---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.date: 03/30/2017
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
ms.openlocfilehash: f58d4dd9e0d3be8813cb9b08394cb084a9f66f88
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54684110"
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="1b296-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="1b296-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="1b296-103">Se requiere el certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="1b296-103">Client certificate is required.</span></span> <span data-ttu-id="1b296-104">No se encontró ningún certificado en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="1b296-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1b296-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b296-105">Description</span></span>  
 <span data-ttu-id="1b296-106">Este seguimiento de traza indica que el agente de escucha HTTPS recibió una solicitud HTTPS que no estaba asociada con un certificado de cliente.</span><span class="sxs-lookup"><span data-stu-id="1b296-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="1b296-107">Dado que el agente de escucha se configuró para exigir certificados de cliente a todas las solicitudes HTTPS, el agente de escucha no pudo validar la autenticidad del cliente.</span><span class="sxs-lookup"><span data-stu-id="1b296-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b296-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b296-108">See also</span></span>
- [<span data-ttu-id="1b296-109">Traza</span><span class="sxs-lookup"><span data-stu-id="1b296-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="1b296-110">Uso del seguimiento para solucionar problemas de su aplicación</span><span class="sxs-lookup"><span data-stu-id="1b296-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1b296-111">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="1b296-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
