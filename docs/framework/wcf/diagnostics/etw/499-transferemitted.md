---
description: 'Más información acerca de: 499-TransferEmitted'
title: 499 - TransferEmitted
ms.date: 03/30/2017
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
ms.openlocfilehash: d9802ef718ce6091abe1d1092ad6bb7e7fff108a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783578"
---
# <a name="499---transferemitted"></a><span data-ttu-id="e0f18-103">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="e0f18-103">499 - TransferEmitted</span></span>

## <a name="properties"></a><span data-ttu-id="e0f18-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e0f18-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0f18-105">Id.</span><span class="sxs-lookup"><span data-stu-id="e0f18-105">ID</span></span>|<span data-ttu-id="e0f18-106">499</span><span class="sxs-lookup"><span data-stu-id="e0f18-106">499</span></span>|  
|<span data-ttu-id="e0f18-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e0f18-107">Keywords</span></span>|<span data-ttu-id="e0f18-108">Solución de problemas, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="e0f18-108">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="e0f18-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="e0f18-109">Level</span></span>|<span data-ttu-id="e0f18-110">LogAlways</span><span class="sxs-lookup"><span data-stu-id="e0f18-110">LogAlways</span></span>|  
|<span data-ttu-id="e0f18-111">Canal</span><span class="sxs-lookup"><span data-stu-id="e0f18-111">Channel</span></span>|<span data-ttu-id="e0f18-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e0f18-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e0f18-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0f18-113">Description</span></span>  

 <span data-ttu-id="e0f18-114">Se emite este evento cuando tiene lugar el evento de transferencia.</span><span class="sxs-lookup"><span data-stu-id="e0f18-114">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e0f18-115">Message</span><span class="sxs-lookup"><span data-stu-id="e0f18-115">Message</span></span>  

 <span data-ttu-id="e0f18-116">Evento de transferencia emitido.</span><span class="sxs-lookup"><span data-stu-id="e0f18-116">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e0f18-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="e0f18-117">Details</span></span>  
  
|<span data-ttu-id="e0f18-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e0f18-118">Data Item Name</span></span>|<span data-ttu-id="e0f18-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e0f18-119">Data Item Type</span></span>|<span data-ttu-id="e0f18-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0f18-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e0f18-121">HostReference</span><span class="sxs-lookup"><span data-stu-id="e0f18-121">HostReference</span></span>|`xs:string`|<span data-ttu-id="e0f18-122">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="e0f18-122">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e0f18-123">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="e0f18-123">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e0f18-124">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="e0f18-124">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e0f18-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e0f18-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e0f18-126">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e0f18-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
