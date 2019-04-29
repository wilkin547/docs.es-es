---
title: 499 - TransferEmitted
ms.date: 03/30/2017
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
ms.openlocfilehash: b1ade828ee6519288165e272e7d9f36fd6aca9ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774938"
---
# <a name="499---transferemitted"></a><span data-ttu-id="46b9e-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="46b9e-102">499 - TransferEmitted</span></span>
## <a name="properties"></a><span data-ttu-id="46b9e-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="46b9e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46b9e-104">ID</span><span class="sxs-lookup"><span data-stu-id="46b9e-104">ID</span></span>|<span data-ttu-id="46b9e-105">499</span><span class="sxs-lookup"><span data-stu-id="46b9e-105">499</span></span>|  
|<span data-ttu-id="46b9e-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="46b9e-106">Keywords</span></span>|<span data-ttu-id="46b9e-107">Solución de problemas, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="46b9e-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="46b9e-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="46b9e-108">Level</span></span>|<span data-ttu-id="46b9e-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="46b9e-109">LogAlways</span></span>|  
|<span data-ttu-id="46b9e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="46b9e-110">Channel</span></span>|<span data-ttu-id="46b9e-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="46b9e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="46b9e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="46b9e-112">Description</span></span>  
 <span data-ttu-id="46b9e-113">Se emite este evento cuando tiene lugar el evento de transferencia.</span><span class="sxs-lookup"><span data-stu-id="46b9e-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="46b9e-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="46b9e-114">Message</span></span>  
 <span data-ttu-id="46b9e-115">Evento de transferencia emitido.</span><span class="sxs-lookup"><span data-stu-id="46b9e-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="46b9e-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="46b9e-116">Details</span></span>  
  
|<span data-ttu-id="46b9e-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="46b9e-117">Data Item Name</span></span>|<span data-ttu-id="46b9e-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="46b9e-118">Data Item Type</span></span>|<span data-ttu-id="46b9e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="46b9e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="46b9e-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="46b9e-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="46b9e-121">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="46b9e-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="46b9e-122">Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre de la aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="46b9e-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="46b9e-123">Ejemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="46b9e-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="46b9e-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="46b9e-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="46b9e-125">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="46b9e-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
