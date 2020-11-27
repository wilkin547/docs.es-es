---
title: 221 - MessageReceivedFromTransport
ms.date: 03/30/2017
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
ms.openlocfilehash: 47e871b70e3ef2419543b4710c2988736665cb46
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263105"
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="4c02b-102">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="4c02b-102">221 - MessageReceivedFromTransport</span></span>

## <a name="properties"></a><span data-ttu-id="4c02b-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4c02b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4c02b-104">ID</span><span class="sxs-lookup"><span data-stu-id="4c02b-104">ID</span></span>|<span data-ttu-id="4c02b-105">221</span><span class="sxs-lookup"><span data-stu-id="4c02b-105">221</span></span>|  
|<span data-ttu-id="4c02b-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="4c02b-106">Keywords</span></span>|<span data-ttu-id="4c02b-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4c02b-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="4c02b-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="4c02b-108">Level</span></span>|<span data-ttu-id="4c02b-109">Información</span><span class="sxs-lookup"><span data-stu-id="4c02b-109">Information</span></span>|  
|<span data-ttu-id="4c02b-110">Canal</span><span class="sxs-lookup"><span data-stu-id="4c02b-110">Channel</span></span>|<span data-ttu-id="4c02b-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="4c02b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4c02b-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c02b-112">Description</span></span>  

 <span data-ttu-id="4c02b-113">Este evento se emite cuando el modelo de servicio recibe un mensaje del transporte.</span><span class="sxs-lookup"><span data-stu-id="4c02b-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4c02b-114">Message</span><span class="sxs-lookup"><span data-stu-id="4c02b-114">Message</span></span>  

 <span data-ttu-id="4c02b-115">El distribuidor recibió un mensaje del transporte.</span><span class="sxs-lookup"><span data-stu-id="4c02b-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="4c02b-116">Id. de correlación == '%1'.</span><span class="sxs-lookup"><span data-stu-id="4c02b-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4c02b-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="4c02b-117">Details</span></span>  
  
|<span data-ttu-id="4c02b-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4c02b-118">Data Item Name</span></span>|<span data-ttu-id="4c02b-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="4c02b-119">Data Item Type</span></span>|<span data-ttu-id="4c02b-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c02b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4c02b-121">Id. de correlación</span><span class="sxs-lookup"><span data-stu-id="4c02b-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="4c02b-122">El identificador de actividad usado para poner en correlación un evento `MessageSentToTransport` de un servicio o cliente con su `MessageReceivedFromTransport` correspondiente en el otro extremo.</span><span class="sxs-lookup"><span data-stu-id="4c02b-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="4c02b-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="4c02b-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="4c02b-124">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="4c02b-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="4c02b-125">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="4c02b-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="4c02b-126">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="4c02b-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="4c02b-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4c02b-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4c02b-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="4c02b-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
