---
title: Seguridad de transporte
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86c94153-e48d-4539-b6cf-cd8060582e7f
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 364326e2ded11f7174adc891a5fd9bcdd3c98334
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="transport-security"></a><span data-ttu-id="c4d73-102">Seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="c4d73-102">Transport Security</span></span>
<span data-ttu-id="c4d73-103">La seguridad de transporte en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] depende del enlace seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c4d73-103">Transport security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] depends on the binding selected.</span></span> <span data-ttu-id="c4d73-104">El transporte que el enlace implementa determina el mecanismo de seguridad real.</span><span class="sxs-lookup"><span data-stu-id="c4d73-104">The transport that the binding implements determines the actual security mechanism.</span></span> <span data-ttu-id="c4d73-105">Los temas de esta sección explican los mecanismos que se implementan y sus opciones.</span><span class="sxs-lookup"><span data-stu-id="c4d73-105">The topics in this section explain the mechanisms that are implemented and their options.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4d73-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c4d73-106">In This Section</span></span>  
 [<span data-ttu-id="c4d73-107">Información general de la seguridad del transporte</span><span class="sxs-lookup"><span data-stu-id="c4d73-107">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="c4d73-108">Explica los fundamentos de seguridad de transporte en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4d73-108">Explains the basics of transport security in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="c4d73-109">Seguridad de transporte HTTP</span><span class="sxs-lookup"><span data-stu-id="c4d73-109">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)  
 <span data-ttu-id="c4d73-110">Explica cómo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa la Capa de sockets seguros (SSL, o HTTPS).</span><span class="sxs-lookup"><span data-stu-id="c4d73-110">Explains how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implements Secure Sockets Layer (SSL, or HTTPS).</span></span>  
  
 [<span data-ttu-id="c4d73-111">Introducción a la autenticación HTTP</span><span class="sxs-lookup"><span data-stu-id="c4d73-111">Understanding HTTP Authentication</span></span>](../../../../docs/framework/wcf/feature-details/understanding-http-authentication.md)  
 <span data-ttu-id="c4d73-112">Describe los esquemas de autenticación de HTTP, como Basic, Digest, NT LAN Manager (NTLM) y otros.</span><span class="sxs-lookup"><span data-stu-id="c4d73-112">Describes HTTP authentication schemes, such as Basic, Digest, NT LAN Manager (NTLM), and others.</span></span>  
  
 [<span data-ttu-id="c4d73-113">Utilización de la suplantación con la seguridad de transporte</span><span class="sxs-lookup"><span data-stu-id="c4d73-113">Using Impersonation with Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/using-impersonation-with-transport-security.md)  
 <span data-ttu-id="c4d73-114">Explica los cinco niveles de suplantación que son posibles con el modo de seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="c4d73-114">Explains the five levels of impersonation that are possible with transport security mode.</span></span>  
  
 [<span data-ttu-id="c4d73-115">Configuración de un puerto con un certificado SSL</span><span class="sxs-lookup"><span data-stu-id="c4d73-115">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 <span data-ttu-id="c4d73-116">Describe los fundamentos para configurar un puerto en un equipo con un certificado X.509 para la seguridad de SSL (transporte).</span><span class="sxs-lookup"><span data-stu-id="c4d73-116">Walks through the basics of configuring a port on a machine with an X.509 certificate for SSL (transport) security.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c4d73-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="c4d73-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="c4d73-118">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="c4d73-118">Related Sections</span></span>  
 [<span data-ttu-id="c4d73-119">Protección de servicios y clientes</span><span class="sxs-lookup"><span data-stu-id="c4d73-119">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="c4d73-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4d73-120">See Also</span></span>  
 [<span data-ttu-id="c4d73-121">Programación de la seguridad de WCF</span><span class="sxs-lookup"><span data-stu-id="c4d73-121">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
