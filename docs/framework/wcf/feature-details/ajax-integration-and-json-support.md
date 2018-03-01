---
title: "Integración de AJAX y compatibilidad de JSON"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cd5c84250349f4adaaac68a302d771280328a4e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="91acd-102">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="91acd-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="91acd-103">La compatibilidad de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] con JavaScript asincrónico y XML (AJAX) de ASP.NET y el formato de datos de la notación de objetos JavaScript (JSON) permiten a los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] exponer las operaciones a los clientes de AJAX.</span><span class="sxs-lookup"><span data-stu-id="91acd-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services to expose operations to AJAX clients.</span></span> <span data-ttu-id="91acd-104">Los clientes de AJAX son páginas web que ejecutan código JavaScript y obtienen acceso a estos servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usando solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="91acd-104">AJAX clients are Web pages running JavaScript code and accessing these [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services using HTTP requests.</span></span> <span data-ttu-id="91acd-105">Los temas de esta sección proporcionan información sobre esta compatibilidad y sobre cómo implementarla.</span><span class="sxs-lookup"><span data-stu-id="91acd-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="91acd-106">AJAX de ASP.NET y su integración con ASP.NET 2.0, vea [información general de AJAX de ASP.NET](http://go.microsoft.com/fwlink/?LinkId=96725).</span><span class="sxs-lookup"><span data-stu-id="91acd-106"> ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](http://go.microsoft.com/fwlink/?LinkId=96725).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91acd-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="91acd-107">In This Section</span></span>  
 [<span data-ttu-id="91acd-108">Creación de servicios WCF para AJAX de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="91acd-108">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="91acd-109">Describe cómo un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se puede exponer a clientes AJAX agregando el extremo de AJAX adecuado bien mediante configuración o bien mediante el uso de un generador de host de servicio personalizado para generar un host de servicio que configure automáticamente el extremo de AJAX.</span><span class="sxs-lookup"><span data-stu-id="91acd-109">Describes how an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="91acd-110">Creación de servicios AJAX WCF sin ASP.NET</span><span class="sxs-lookup"><span data-stu-id="91acd-110">Creating WCF AJAX Services without ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="91acd-111">Describe cómo crear un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sin utilizar ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="91acd-111">Describes how to create an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="91acd-112">Compatibilidad con JSON y otros formatos de transferencia de datos</span><span class="sxs-lookup"><span data-stu-id="91acd-112">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="91acd-113">Describe la compatibilidad del formato de JSON utilizada normalmente (en lugar de XML) para la mensajería con servicios de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="91acd-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="91acd-114">Migración de servicios web de ASP.NET con AJAX habilitado a WCF</span><span class="sxs-lookup"><span data-stu-id="91acd-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="91acd-115">Describe cómo migrar un servicio web de ASP.NET con AJAX habilitado a un servicio web de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91acd-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91acd-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="91acd-116">See Also</span></span>  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>  
 [<span data-ttu-id="91acd-117">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="91acd-117">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
