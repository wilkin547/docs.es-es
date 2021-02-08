---
description: 'Más información acerca de: 221-MessageReceivedFromTransport'
title: 221 - MessageReceivedFromTransport
ms.date: 03/30/2017
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
ms.openlocfilehash: 0cc15fa95ae321083afa2792810807971e909e6b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803508"
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="5b78a-103">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="5b78a-103">221 - MessageReceivedFromTransport</span></span>

## <a name="properties"></a><span data-ttu-id="5b78a-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="5b78a-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b78a-105">Id.</span><span class="sxs-lookup"><span data-stu-id="5b78a-105">ID</span></span>|<span data-ttu-id="5b78a-106">221</span><span class="sxs-lookup"><span data-stu-id="5b78a-106">221</span></span>|  
|<span data-ttu-id="5b78a-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5b78a-107">Keywords</span></span>|<span data-ttu-id="5b78a-108">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5b78a-108">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="5b78a-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="5b78a-109">Level</span></span>|<span data-ttu-id="5b78a-110">Información</span><span class="sxs-lookup"><span data-stu-id="5b78a-110">Information</span></span>|  
|<span data-ttu-id="5b78a-111">Canal</span><span class="sxs-lookup"><span data-stu-id="5b78a-111">Channel</span></span>|<span data-ttu-id="5b78a-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="5b78a-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5b78a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b78a-113">Description</span></span>  

 <span data-ttu-id="5b78a-114">Este evento se emite cuando el modelo de servicio recibe un mensaje del transporte.</span><span class="sxs-lookup"><span data-stu-id="5b78a-114">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5b78a-115">Message</span><span class="sxs-lookup"><span data-stu-id="5b78a-115">Message</span></span>  

 <span data-ttu-id="5b78a-116">El distribuidor recibió un mensaje del transporte.</span><span class="sxs-lookup"><span data-stu-id="5b78a-116">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="5b78a-117">Id. de correlación == '%1'.</span><span class="sxs-lookup"><span data-stu-id="5b78a-117">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5b78a-118">Detalles</span><span class="sxs-lookup"><span data-stu-id="5b78a-118">Details</span></span>  
  
|<span data-ttu-id="5b78a-119">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5b78a-119">Data Item Name</span></span>|<span data-ttu-id="5b78a-120">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5b78a-120">Data Item Type</span></span>|<span data-ttu-id="5b78a-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b78a-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5b78a-122">Id. de correlación</span><span class="sxs-lookup"><span data-stu-id="5b78a-122">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="5b78a-123">El identificador de actividad usado para poner en correlación un evento `MessageSentToTransport` de un servicio o cliente con su `MessageReceivedFromTransport` correspondiente en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="5b78a-123">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="5b78a-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="5b78a-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="5b78a-125">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="5b78a-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="5b78a-126">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="5b78a-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="5b78a-127">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="5b78a-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="5b78a-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5b78a-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5b78a-129">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5b78a-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
