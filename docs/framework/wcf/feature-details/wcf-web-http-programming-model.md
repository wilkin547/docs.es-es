---
title: "Modelo de programación de web HTTP de WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- web services programming model [WCF]
- POX
- REST
ms.assetid: 2312a8d3-b66e-4623-ba42-978434300c7f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f008cfe874ae9e38a71eb3cf5d6b2ed4e6cbdf7c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-web-http-programming-model"></a><span data-ttu-id="5771d-102">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="5771d-102">WCF Web HTTP Programming Model</span></span>
<span data-ttu-id="5771d-103">El modelo de programación web HTTP de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] permite a los programadores exponer operaciones de servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] a extremos que no son SOAP.</span><span class="sxs-lookup"><span data-stu-id="5771d-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web HTTP Programming Model allows developers to expose [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service operations to non-SOAP endpoints.</span></span> <span data-ttu-id="5771d-104">Los temas de esta sección examinan en detalle esta característica.</span><span class="sxs-lookup"><span data-stu-id="5771d-104">The topics in this section examine the feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5771d-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="5771d-105">In This Section</span></span>  
 [<span data-ttu-id="5771d-106">Información general del modelo de programación web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="5771d-106">WCF Web HTTP Programming Model Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)  
 <span data-ttu-id="5771d-107">Proporciona información general sobre el modelo de programación web HTTP de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5771d-107">Provides an overview of the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web HTTP Programming Model.</span></span>  
  
 [<span data-ttu-id="5771d-108">Modelo de objetos de programación web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="5771d-108">WCF Web HTTP Programming Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)  
 <span data-ttu-id="5771d-109">Describe el modelo de programación web HTTP de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="5771d-109">Discusses the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web HTTP Programming Model and how it works.</span></span>  
  
 [<span data-ttu-id="5771d-110">Creación de un servicio básico web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="5771d-110">How to: Create a Basic WCF Web HTTP Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md)  
 <span data-ttu-id="5771d-111">Describe cómo escribir un servicio básico que exponga un punto de conexión que no sea SOAP.</span><span class="sxs-lookup"><span data-stu-id="5771d-111">Describes how to write a basic service that exposes a non-SOAP endpoint.</span></span>  
  
 [<span data-ttu-id="5771d-112">Exposición de un contrato a clientes web y de SOAP</span><span class="sxs-lookup"><span data-stu-id="5771d-112">How to: Expose a Contract to SOAP and Web Clients</span></span>](../../../../docs/framework/wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md)  
 <span data-ttu-id="5771d-113">Describe cómo escribir un servicio básico que exponga el mismo contrato tanto a clientes SOAP como a clientes que no sean SOAP.</span><span class="sxs-lookup"><span data-stu-id="5771d-113">Describes how to write a basic service that exposes the same contract to both SOAP and non-SOAP clients.</span></span>  
  
 [<span data-ttu-id="5771d-114">UriTemplate y UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="5771d-114">UriTemplate and UriTemplateTable</span></span>](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md)  
 <span data-ttu-id="5771d-115">Describe como controlar los URI mediante <xref:System.UriTemplate> y <xref:System.UriTemplateTable>.</span><span class="sxs-lookup"><span data-stu-id="5771d-115">Describes how to control URIs using <xref:System.UriTemplate> and <xref:System.UriTemplateTable>.</span></span>  
  
 [<span data-ttu-id="5771d-116">Soporte de almacenamiento en memoria caché para servicios web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="5771d-116">Caching Support for WCF Web HTTP Services</span></span>](../../../../docs/framework/wcf/feature-details/caching-support-for-wcf-web-http-services.md)  
 <span data-ttu-id="5771d-117">Describe cómo especificar el comportamiento de almacenamiento en caché de un servicio web HTTP de WCF.</span><span class="sxs-lookup"><span data-stu-id="5771d-117">Describes how to specify caching behavior for a WCF Web HTTP service.</span></span>  
  
 [<span data-ttu-id="5771d-118">Formato de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="5771d-118">WCF Web HTTP Formatting</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)  
 <span data-ttu-id="5771d-119">Describe cómo especificar el formato de la respuesta de un servicio web HTTP de WCF.</span><span class="sxs-lookup"><span data-stu-id="5771d-119">Describes how to specify the format of the response from a WCF Web HTTP service.</span></span>  
  
 [<span data-ttu-id="5771d-120">Control de errores de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="5771d-120">WCF Web HTTP Error Handling</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-error-handling.md)  
 <span data-ttu-id="5771d-121">Describe cómo devolver los errores a los clientes web de WCF incluyendo los códigos de estado HTTP y datos del error adicionales definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="5771d-121">Describes how to return errors to WCF Web clients including HTTP status codes and additional user-defined error data.</span></span>  
  
 [<span data-ttu-id="5771d-122">Llamada a un servicio de estilo REST desde un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="5771d-122">Calling a REST-style service from a WCF service</span></span>](../../../../docs/framework/wcf/feature-details/calling-a-rest-style-service-from-a-wcf-service.md)  
 <span data-ttu-id="5771d-123">Describe cómo llamar a un servicio de tipo REST desde un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="5771d-123">Describes how to call a REST-style service from inside a WCF service.</span></span>
