---
title: Integración de AJAX y compatibilidad de JSON
ms.date: 03/30/2017
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
ms.openlocfilehash: bcf1cab9386d9d9503af6258c1bb39f8744c073b
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "46479629"
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="6352b-102">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="6352b-102">AJAX Integration and JSON Support</span></span>
<span data-ttu-id="6352b-103">La compatibilidad de Windows Communication Foundation (WCF) para ASP.NET Asynchronous JavaScript y XML (AJAX) y el formato de datos JavaScript Object Notation (JSON) permiten a los servicios WCF exponer las operaciones a los clientes de AJAX.</span><span class="sxs-lookup"><span data-stu-id="6352b-103">The Windows Communication Foundation (WCF) support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow WCF services to expose operations to AJAX clients.</span></span> <span data-ttu-id="6352b-104">Los clientes de AJAX son páginas Web que ejecutan código JavaScript y obtener acceso a estos servicios WCF mediante solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="6352b-104">AJAX clients are Web pages running JavaScript code and accessing these WCF services using HTTP requests.</span></span> <span data-ttu-id="6352b-105">Los temas de esta sección proporcionan información sobre esta compatibilidad y sobre cómo implementarla.</span><span class="sxs-lookup"><span data-stu-id="6352b-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 <span data-ttu-id="6352b-106">Para obtener más información sobre ASP.NET AJAX y su integración con ASP.NET 2.0, consulte [ASP.NET AJAX Overview](https://go.microsoft.com/fwlink/?LinkId=96725).</span><span class="sxs-lookup"><span data-stu-id="6352b-106">For more information about ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](https://go.microsoft.com/fwlink/?LinkId=96725).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6352b-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6352b-107">In This Section</span></span>  
 [<span data-ttu-id="6352b-108">Creación de servicios WCF para AJAX de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6352b-108">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="6352b-109">Describe cómo se puede exponer un servicio WCF a los clientes AJAX agregando el punto de conexión de AJAX adecuado, ya sea a través de configuración o mediante el uso de un generador de host de servicio personalizado para generar un host de servicio que configura automáticamente el punto de conexión de AJAX.</span><span class="sxs-lookup"><span data-stu-id="6352b-109">Describes how an WCF service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="6352b-110">Creación de servicios AJAX WCF sin ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6352b-110">Creating WCF AJAX Services without ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="6352b-111">Describe cómo crear un servicio WCF sin utilizar ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6352b-111">Describes how to create an WCF service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="6352b-112">Compatibilidad con JSON y otros formatos de transferencia de datos</span><span class="sxs-lookup"><span data-stu-id="6352b-112">Support for JSON and Other Data Transfer Formats</span></span>](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="6352b-113">Describe la compatibilidad del formato de JSON utilizada normalmente (en lugar de XML) para la mensajería con servicios de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6352b-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="6352b-114">Migración de servicios web de ASP.NET con AJAX habilitado a WCF</span><span class="sxs-lookup"><span data-stu-id="6352b-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="6352b-115">Describe cómo migrar un servicio Web de ASP.NET con AJAX habilitado a un servicio Web WCF.</span><span class="sxs-lookup"><span data-stu-id="6352b-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a WCF Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6352b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6352b-116">See Also</span></span>  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>  
 [<span data-ttu-id="6352b-117">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="6352b-117">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
