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
ms.openlocfilehash: 32e7cb3a340865530b6a8d76609eb246184363b0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-web-http-programming-model"></a><span data-ttu-id="f8402-102">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="f8402-102">WCF Web HTTP Programming Model</span></span>
<span data-ttu-id="f8402-103">El modelo de programación web HTTP de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] permite a los programadores exponer operaciones de servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] a extremos que no son SOAP.</span><span class="sxs-lookup"><span data-stu-id="f8402-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web HTTP Programming Model allows developers to expose [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service operations to non-SOAP endpoints.</span></span> <span data-ttu-id="f8402-104">Los temas de esta sección examinan en detalle esta característica.</span><span class="sxs-lookup"><span data-stu-id="f8402-104">The topics in this section examine the feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f8402-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f8402-105">In This Section</span></span>  
 [<span data-ttu-id="f8402-106">Información general del modelo de programación Web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="f8402-106">WCF Web HTTP Programming Model Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)  
 <span data-ttu-id="f8402-107">Proporciona información general sobre el modelo de programación web HTTP de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8402-107">Provides an overview of the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web HTTP Programming Model.</span></span>  
  
 [<span data-ttu-id="f8402-108">Modelo de objetos de programación Web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="f8402-108">WCF Web HTTP Programming Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)  
 <span data-ttu-id="f8402-109">Describe el modelo de programación web HTTP de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="f8402-109">Discusses the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web HTTP Programming Model and how it works.</span></span>  
  
 [<span data-ttu-id="f8402-110">Cómo: crear un servicio Web HTTP de WCF básico</span><span class="sxs-lookup"><span data-stu-id="f8402-110">How to: Create a Basic WCF Web HTTP Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md)  
 <span data-ttu-id="f8402-111">Describe cómo escribir un servicio básico que exponga un punto de conexión que no sea SOAP.</span><span class="sxs-lookup"><span data-stu-id="f8402-111">Describes how to write a basic service that exposes a non-SOAP endpoint.</span></span>  
  
 [<span data-ttu-id="f8402-112">Cómo: exponer un contrato para clientes Web y SOAP</span><span class="sxs-lookup"><span data-stu-id="f8402-112">How to: Expose a Contract to SOAP and Web Clients</span></span>](../../../../docs/framework/wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md)  
 <span data-ttu-id="f8402-113">Describe cómo escribir un servicio básico que exponga el mismo contrato tanto a clientes SOAP como a clientes que no sean SOAP.</span><span class="sxs-lookup"><span data-stu-id="f8402-113">Describes how to write a basic service that exposes the same contract to both SOAP and non-SOAP clients.</span></span>  
  
 [<span data-ttu-id="f8402-114">UriTemplate y UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="f8402-114">UriTemplate and UriTemplateTable</span></span>](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md)  
 <span data-ttu-id="f8402-115">Describe como controlar los URI mediante <xref:System.UriTemplate> y <xref:System.UriTemplateTable>.</span><span class="sxs-lookup"><span data-stu-id="f8402-115">Describes how to control URIs using <xref:System.UriTemplate> and <xref:System.UriTemplateTable>.</span></span>  
  
 [<span data-ttu-id="f8402-116">Compatibilidad con almacenamiento en caché para los servicios Web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="f8402-116">Caching Support for WCF Web HTTP Services</span></span>](../../../../docs/framework/wcf/feature-details/caching-support-for-wcf-web-http-services.md)  
 <span data-ttu-id="f8402-117">Describe cómo especificar el comportamiento de almacenamiento en caché de un servicio web HTTP de WCF.</span><span class="sxs-lookup"><span data-stu-id="f8402-117">Describes how to specify caching behavior for a WCF Web HTTP service.</span></span>  
  
 [<span data-ttu-id="f8402-118">Formato de Web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="f8402-118">WCF Web HTTP Formatting</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)  
 <span data-ttu-id="f8402-119">Describe cómo especificar el formato de la respuesta de un servicio web HTTP de WCF.</span><span class="sxs-lookup"><span data-stu-id="f8402-119">Describes how to specify the format of the response from a WCF Web HTTP service.</span></span>  
  
 [<span data-ttu-id="f8402-120">Control de errores de HTTP de Web WCF</span><span class="sxs-lookup"><span data-stu-id="f8402-120">WCF Web HTTP Error Handling</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-error-handling.md)  
 <span data-ttu-id="f8402-121">Describe cómo devolver los errores a los clientes web de WCF incluyendo los códigos de estado HTTP y datos del error adicionales definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="f8402-121">Describes how to return errors to WCF Web clients including HTTP status codes and additional user-defined error data.</span></span>  
  
 [<span data-ttu-id="f8402-122">Llamar a un servicio basado en REST desde un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="f8402-122">Calling a REST-style service from a WCF service</span></span>](../../../../docs/framework/wcf/feature-details/calling-a-rest-style-service-from-a-wcf-service.md)  
 <span data-ttu-id="f8402-123">Describe cómo llamar a un servicio de tipo REST desde un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="f8402-123">Describes how to call a REST-style service from inside a WCF service.</span></span>
