---
title: Integración de AJAX y compatibilidad de JSON
ms.date: 03/30/2017
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
ms.openlocfilehash: c895a6dedc22a42adb7104927d39090ab6587f37
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266030"
---
# <a name="ajax-integration-and-json-support"></a><span data-ttu-id="16799-102">Integración de AJAX y compatibilidad de JSON</span><span class="sxs-lookup"><span data-stu-id="16799-102">AJAX Integration and JSON Support</span></span>

<span data-ttu-id="16799-103">La compatibilidad de Windows Communication Foundation (WCF) para JavaScript asincrónico y XML (AJAX) de ASP.NET y el formato de datos de notación de objetos JavaScript (JSON) permiten que los servicios WCF expongan las operaciones a los clientes AJAX.</span><span class="sxs-lookup"><span data-stu-id="16799-103">The Windows Communication Foundation (WCF) support for ASP.NET Asynchronous JavaScript and XML (AJAX) and the JavaScript Object Notation (JSON) data format allow WCF services to expose operations to AJAX clients.</span></span> <span data-ttu-id="16799-104">Los clientes AJAX son páginas web que ejecutan código JavaScript y obtienen acceso a estos servicios WCF mediante solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="16799-104">AJAX clients are Web pages running JavaScript code and accessing these WCF services using HTTP requests.</span></span> <span data-ttu-id="16799-105">Los temas de esta sección proporcionan información sobre esta compatibilidad y sobre cómo implementarla.</span><span class="sxs-lookup"><span data-stu-id="16799-105">The topics in this section provide information about this support and about how to implement it.</span></span>  
  
 <span data-ttu-id="16799-106">Para obtener más información acerca de ASP.NET AJAX y su integración con ASP.NET 2,0, consulte [información general sobre la ASP.NET AJAX](/previous-versions/aspnet/bb398874(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="16799-106">For more information about ASP.NET AJAX and its integration with ASP.NET 2.0, see [ASP.NET AJAX Overview](/previous-versions/aspnet/bb398874(v=vs.100)).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16799-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="16799-107">In This Section</span></span>  

 [<span data-ttu-id="16799-108">Creación de servicios WCF para AJAX de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="16799-108">Creating WCF Services for ASP.NET AJAX</span></span>](creating-wcf-services-for-aspnet-ajax.md)  
 <span data-ttu-id="16799-109">Describe cómo se puede exponer un servicio WCF a los clientes AJAX agregando el punto de conexión de AJAX adecuado bien mediante configuración o mediante un generador de host de servicio personalizado para generar un host de servicio que configure el extremo de AJAX automáticamente.</span><span class="sxs-lookup"><span data-stu-id="16799-109">Describes how a WCF service can be exposed to AJAX clients by adding the appropriate AJAX endpoint either through configuration or by using a service host factory customized to generate a service host that configures the AJAX endpoint automatically.</span></span>  
  
 [<span data-ttu-id="16799-110">Creación de servicios AJAX WCF sin ASP.NET</span><span class="sxs-lookup"><span data-stu-id="16799-110">Creating WCF AJAX Services without ASP.NET</span></span>](creating-wcf-ajax-services-without-aspnet.md)  
 <span data-ttu-id="16799-111">Describe cómo crear un servicio WCF sin usar ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="16799-111">Describes how to create a WCF service without using ASP.NET.</span></span>  
  
 [<span data-ttu-id="16799-112">Compatibilidad con JSON y otros formatos de transferencia de datos</span><span class="sxs-lookup"><span data-stu-id="16799-112">Support for JSON and Other Data Transfer Formats</span></span>](support-for-json-and-other-data-transfer-formats.md)  
 <span data-ttu-id="16799-113">Describe la compatibilidad del formato de JSON utilizada normalmente (en lugar de XML) para la mensajería con servicios de AJAX de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="16799-113">Describes the support of the JSON format typically used (instead of XML) for messaging with ASP.NET AJAX services.</span></span>  
  
 [<span data-ttu-id="16799-114">Procedimiento para migrar servicios web de ASP.NET con AJAX habilitado a WCF</span><span class="sxs-lookup"><span data-stu-id="16799-114">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 <span data-ttu-id="16799-115">Describe cómo migrar un servicio Web ASP.NET con AJAX habilitado a un servicio Web WCF.</span><span class="sxs-lookup"><span data-stu-id="16799-115">Describes how to migrate an AJAX-enabled ASP.NET Web service to a WCF Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16799-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="16799-116">See also</span></span>

- <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>
- [<span data-ttu-id="16799-117">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="16799-117">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
