---
title: 499 - TransferEmitted
ms.date: 03/30/2017
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
ms.openlocfilehash: b1ade828ee6519288165e272e7d9f36fd6aca9ff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33469513"
---
# <a name="499---transferemitted"></a><span data-ttu-id="9ece0-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="9ece0-102">499 - TransferEmitted</span></span>
## <a name="properties"></a><span data-ttu-id="9ece0-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9ece0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9ece0-104">Id.</span><span class="sxs-lookup"><span data-stu-id="9ece0-104">ID</span></span>|<span data-ttu-id="9ece0-105">499</span><span class="sxs-lookup"><span data-stu-id="9ece0-105">499</span></span>|  
|<span data-ttu-id="9ece0-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="9ece0-106">Keywords</span></span>|<span data-ttu-id="9ece0-107">Solución de problemas, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="9ece0-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="9ece0-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="9ece0-108">Level</span></span>|<span data-ttu-id="9ece0-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="9ece0-109">LogAlways</span></span>|  
|<span data-ttu-id="9ece0-110">Canal</span><span class="sxs-lookup"><span data-stu-id="9ece0-110">Channel</span></span>|<span data-ttu-id="9ece0-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="9ece0-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9ece0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ece0-112">Description</span></span>  
 <span data-ttu-id="9ece0-113">Se emite este evento cuando tiene lugar el evento de transferencia.</span><span class="sxs-lookup"><span data-stu-id="9ece0-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9ece0-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="9ece0-114">Message</span></span>  
 <span data-ttu-id="9ece0-115">Evento de transferencia emitido.</span><span class="sxs-lookup"><span data-stu-id="9ece0-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9ece0-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="9ece0-116">Details</span></span>  
  
|<span data-ttu-id="9ece0-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9ece0-117">Data Item Name</span></span>|<span data-ttu-id="9ece0-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="9ece0-118">Data Item Type</span></span>|<span data-ttu-id="9ece0-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ece0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9ece0-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="9ece0-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="9ece0-121">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="9ece0-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="9ece0-122">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="9ece0-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="9ece0-123">Ejemplo: ' predeterminado sitio Web/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="9ece0-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="9ece0-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9ece0-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="9ece0-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="9ece0-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
