---
title: Modelo de programación de web HTTP de WCF
ms.date: 03/30/2017
helpviewer_keywords:
- web services programming model [WCF]
- POX
- REST
ms.assetid: 2312a8d3-b66e-4623-ba42-978434300c7f
ms.openlocfilehash: dd9cc282750e59e5ccbfec428c7252ab9689395f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589856"
---
# <a name="wcf-web-http-programming-model"></a><span data-ttu-id="e65ca-102">Modelo de programación de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="e65ca-102">WCF Web HTTP Programming Model</span></span>
<span data-ttu-id="e65ca-103">El modelo de programación web HTTP de Windows Communication Foundation (WCF) permite a los desarrolladores exponer las operaciones del servicio WCF a extremos que no son SOAP.</span><span class="sxs-lookup"><span data-stu-id="e65ca-103">The Windows Communication Foundation (WCF) Web HTTP Programming Model allows developers to expose WCF service operations to non-SOAP endpoints.</span></span> <span data-ttu-id="e65ca-104">Los temas de esta sección examinan en detalle esta característica.</span><span class="sxs-lookup"><span data-stu-id="e65ca-104">The topics in this section examine the feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e65ca-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e65ca-105">In This Section</span></span>  
 [<span data-ttu-id="e65ca-106">Información general del modelo de programación web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="e65ca-106">WCF Web HTTP Programming Model Overview</span></span>](wcf-web-http-programming-model-overview.md)  
 <span data-ttu-id="e65ca-107">Proporciona información general sobre el modelo de programación web HTTP de Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="e65ca-107">Provides an overview of the Windows Communication Foundation (WCF) Web HTTP Programming Model.</span></span>  
  
 [<span data-ttu-id="e65ca-108">Modelo de objetos de programación web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="e65ca-108">WCF Web HTTP Programming Object Model</span></span>](wcf-web-http-programming-object-model.md)  
 <span data-ttu-id="e65ca-109">Describe el modelo de programación web HTTP de Windows Communication Foundation (WCF) y cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="e65ca-109">Discusses the Windows Communication Foundation (WCF) Web HTTP Programming Model and how it works.</span></span>  
  
 [<span data-ttu-id="e65ca-110">Procedimiento para crear un servicio básico web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="e65ca-110">How to: Create a Basic WCF Web HTTP Service</span></span>](how-to-create-a-basic-wcf-web-http-service.md)  
 <span data-ttu-id="e65ca-111">Describe cómo escribir un servicio básico que exponga un extremo que no sea SOAP.</span><span class="sxs-lookup"><span data-stu-id="e65ca-111">Describes how to write a basic service that exposes a non-SOAP endpoint.</span></span>  
  
 [<span data-ttu-id="e65ca-112">Procedimiento para exponer un contrato a clientes web y de SOAP</span><span class="sxs-lookup"><span data-stu-id="e65ca-112">How to: Expose a Contract to SOAP and Web Clients</span></span>](how-to-expose-a-contract-to-soap-and-web-clients.md)  
 <span data-ttu-id="e65ca-113">Describe cómo escribir un servicio básico que exponga el mismo contrato tanto a clientes SOAP como a clientes que no sean SOAP.</span><span class="sxs-lookup"><span data-stu-id="e65ca-113">Describes how to write a basic service that exposes the same contract to both SOAP and non-SOAP clients.</span></span>  
  
 [<span data-ttu-id="e65ca-114">UriTemplate y UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="e65ca-114">UriTemplate and UriTemplateTable</span></span>](uritemplate-and-uritemplatetable.md)  
 <span data-ttu-id="e65ca-115">Describe como controlar los URI mediante <xref:System.UriTemplate> y <xref:System.UriTemplateTable>.</span><span class="sxs-lookup"><span data-stu-id="e65ca-115">Describes how to control URIs using <xref:System.UriTemplate> and <xref:System.UriTemplateTable>.</span></span>  
  
 [<span data-ttu-id="e65ca-116">Soporte de almacenamiento en memoria caché para servicios web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="e65ca-116">Caching Support for WCF Web HTTP Services</span></span>](caching-support-for-wcf-web-http-services.md)  
 <span data-ttu-id="e65ca-117">Describe cómo especificar el comportamiento de almacenamiento en caché de un servicio web HTTP de WCF.</span><span class="sxs-lookup"><span data-stu-id="e65ca-117">Describes how to specify caching behavior for a WCF Web HTTP service.</span></span>  
  
 [<span data-ttu-id="e65ca-118">Formato de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="e65ca-118">WCF Web HTTP Formatting</span></span>](wcf-web-http-formatting.md)  
 <span data-ttu-id="e65ca-119">Describe cómo especificar el formato de la respuesta de un servicio web HTTP de WCF.</span><span class="sxs-lookup"><span data-stu-id="e65ca-119">Describes how to specify the format of the response from a WCF Web HTTP service.</span></span>  
  
 [<span data-ttu-id="e65ca-120">Controlar errores de web HTTP de WCF</span><span class="sxs-lookup"><span data-stu-id="e65ca-120">WCF Web HTTP Error Handling</span></span>](wcf-web-http-error-handling.md)  
 <span data-ttu-id="e65ca-121">Describe cómo devolver los errores a los clientes web de WCF incluyendo los códigos de estado HTTP y datos del error adicionales definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="e65ca-121">Describes how to return errors to WCF Web clients including HTTP status codes and additional user-defined error data.</span></span>  
  
 [<span data-ttu-id="e65ca-122">Llamar a un servicio de estilo REST desde un servicio WCF</span><span class="sxs-lookup"><span data-stu-id="e65ca-122">Calling a REST-style service from a WCF service</span></span>](calling-a-rest-style-service-from-a-wcf-service.md)  
 <span data-ttu-id="e65ca-123">Describe cómo llamar a un servicio de tipo REST desde un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="e65ca-123">Describes how to call a REST-style service from inside a WCF service.</span></span>
