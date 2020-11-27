---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
ms.openlocfilehash: d84f6c6f38868f7915caaaf87e15885099b65456
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266680"
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="e2d9e-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="e2d9e-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="e2d9e-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="e2d9e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e2d9e-104">ID</span><span class="sxs-lookup"><span data-stu-id="e2d9e-104">ID</span></span>|<span data-ttu-id="e2d9e-105">201</span><span class="sxs-lookup"><span data-stu-id="e2d9e-105">201</span></span>|  
|<span data-ttu-id="e2d9e-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="e2d9e-106">Keywords</span></span>|<span data-ttu-id="e2d9e-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e2d9e-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="e2d9e-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="e2d9e-108">Level</span></span>|<span data-ttu-id="e2d9e-109">Información</span><span class="sxs-lookup"><span data-stu-id="e2d9e-109">Information</span></span>|  
|<span data-ttu-id="e2d9e-110">Canal</span><span class="sxs-lookup"><span data-stu-id="e2d9e-110">Channel</span></span>|<span data-ttu-id="e2d9e-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="e2d9e-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e2d9e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2d9e-112">Description</span></span>  

 <span data-ttu-id="e2d9e-113">Se emite este evento cuando el modelo de servicio ha invocado el método `AfterReceiveReply` en un inspector de mensaje de cliente.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e2d9e-114">Message</span><span class="sxs-lookup"><span data-stu-id="e2d9e-114">Message</span></span>  

 <span data-ttu-id="e2d9e-115">El distribuidor invocó 'AfterReceiveReply' en un ClientMessageInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e2d9e-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="e2d9e-116">Details</span></span>  
  
|<span data-ttu-id="e2d9e-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e2d9e-117">Data Item Name</span></span>|<span data-ttu-id="e2d9e-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="e2d9e-118">Data Item Type</span></span>|<span data-ttu-id="e2d9e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2d9e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e2d9e-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="e2d9e-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="e2d9e-121">El nombre completo (FullName) de CLR del tipo del inspector invocado.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="e2d9e-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="e2d9e-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="e2d9e-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="e2d9e-124">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="e2d9e-125">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="e2d9e-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e2d9e-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e2d9e-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="e2d9e-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
