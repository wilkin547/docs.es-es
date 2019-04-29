---
title: 221 - MessageReceivedFromTransport
ms.date: 03/30/2017
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
ms.openlocfilehash: 98dbf2728242fa73b3e54b7cf32f9e227e5251b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781724"
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="59b39-102">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="59b39-102">221 - MessageReceivedFromTransport</span></span>
## <a name="properties"></a><span data-ttu-id="59b39-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="59b39-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="59b39-104">ID</span><span class="sxs-lookup"><span data-stu-id="59b39-104">ID</span></span>|<span data-ttu-id="59b39-105">221</span><span class="sxs-lookup"><span data-stu-id="59b39-105">221</span></span>|  
|<span data-ttu-id="59b39-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="59b39-106">Keywords</span></span>|<span data-ttu-id="59b39-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="59b39-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="59b39-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="59b39-108">Level</span></span>|<span data-ttu-id="59b39-109">Información</span><span class="sxs-lookup"><span data-stu-id="59b39-109">Information</span></span>|  
|<span data-ttu-id="59b39-110">Canal</span><span class="sxs-lookup"><span data-stu-id="59b39-110">Channel</span></span>|<span data-ttu-id="59b39-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="59b39-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="59b39-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="59b39-112">Description</span></span>  
 <span data-ttu-id="59b39-113">Este evento se emite cuando el modelo de servicio recibe un mensaje del transporte.</span><span class="sxs-lookup"><span data-stu-id="59b39-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="59b39-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="59b39-114">Message</span></span>  
 <span data-ttu-id="59b39-115">El distribuidor recibió un mensaje del transporte.</span><span class="sxs-lookup"><span data-stu-id="59b39-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="59b39-116">Id. de correlación == '%1'.</span><span class="sxs-lookup"><span data-stu-id="59b39-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="59b39-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="59b39-117">Details</span></span>  
  
|<span data-ttu-id="59b39-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="59b39-118">Data Item Name</span></span>|<span data-ttu-id="59b39-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="59b39-119">Data Item Type</span></span>|<span data-ttu-id="59b39-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="59b39-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="59b39-121">Correlation ID</span><span class="sxs-lookup"><span data-stu-id="59b39-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="59b39-122">El identificador de actividad usado para poner en correlación un evento `MessageSentToTransport` de un servicio o cliente con su `MessageReceivedFromTransport` correspondiente en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="59b39-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="59b39-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="59b39-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="59b39-124">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="59b39-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="59b39-125">Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre de la aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="59b39-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="59b39-126">Ejemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="59b39-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="59b39-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="59b39-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="59b39-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="59b39-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
