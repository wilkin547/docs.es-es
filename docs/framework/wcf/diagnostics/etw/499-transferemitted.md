---
title: 499 - TransferEmitted
ms.date: 03/30/2017
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
ms.openlocfilehash: dc47aa36b5a409c89aaf7963ce51f11cdf84b0fc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247582"
---
# <a name="499---transferemitted"></a><span data-ttu-id="5d879-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="5d879-102">499 - TransferEmitted</span></span>

## <a name="properties"></a><span data-ttu-id="5d879-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="5d879-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5d879-104">ID</span><span class="sxs-lookup"><span data-stu-id="5d879-104">ID</span></span>|<span data-ttu-id="5d879-105">499</span><span class="sxs-lookup"><span data-stu-id="5d879-105">499</span></span>|  
|<span data-ttu-id="5d879-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5d879-106">Keywords</span></span>|<span data-ttu-id="5d879-107">Solución de problemas, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="5d879-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="5d879-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="5d879-108">Level</span></span>|<span data-ttu-id="5d879-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="5d879-109">LogAlways</span></span>|  
|<span data-ttu-id="5d879-110">Canal</span><span class="sxs-lookup"><span data-stu-id="5d879-110">Channel</span></span>|<span data-ttu-id="5d879-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="5d879-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5d879-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d879-112">Description</span></span>  

 <span data-ttu-id="5d879-113">Se emite este evento cuando tiene lugar el evento de transferencia.</span><span class="sxs-lookup"><span data-stu-id="5d879-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5d879-114">Message</span><span class="sxs-lookup"><span data-stu-id="5d879-114">Message</span></span>  

 <span data-ttu-id="5d879-115">Evento de transferencia emitido.</span><span class="sxs-lookup"><span data-stu-id="5d879-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5d879-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="5d879-116">Details</span></span>  
  
|<span data-ttu-id="5d879-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5d879-117">Data Item Name</span></span>|<span data-ttu-id="5d879-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5d879-118">Data Item Type</span></span>|<span data-ttu-id="5d879-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d879-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5d879-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="5d879-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="5d879-121">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="5d879-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="5d879-122">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="5d879-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="5d879-123">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="5d879-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="5d879-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5d879-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5d879-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5d879-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
