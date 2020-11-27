---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
ms.openlocfilehash: 4aa0f41b0b772551d9257920e5c15051961b7332
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267824"
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="16fc6-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="16fc6-102">208 - MessageInspectorAfterReceiveInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="16fc6-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="16fc6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="16fc6-104">ID</span><span class="sxs-lookup"><span data-stu-id="16fc6-104">ID</span></span>|<span data-ttu-id="16fc6-105">208</span><span class="sxs-lookup"><span data-stu-id="16fc6-105">208</span></span>|  
|<span data-ttu-id="16fc6-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="16fc6-106">Keywords</span></span>|<span data-ttu-id="16fc6-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="16fc6-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="16fc6-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="16fc6-108">Level</span></span>|<span data-ttu-id="16fc6-109">Información</span><span class="sxs-lookup"><span data-stu-id="16fc6-109">Information</span></span>|  
|<span data-ttu-id="16fc6-110">Canal</span><span class="sxs-lookup"><span data-stu-id="16fc6-110">Channel</span></span>|<span data-ttu-id="16fc6-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="16fc6-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="16fc6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="16fc6-112">Description</span></span>  

 <span data-ttu-id="16fc6-113">Se emite este evento cuando el modelo de servicio ha invocado el método `AfterReceive` en un inspector de mensaje.</span><span class="sxs-lookup"><span data-stu-id="16fc6-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="16fc6-114">Message</span><span class="sxs-lookup"><span data-stu-id="16fc6-114">Message</span></span>  

 <span data-ttu-id="16fc6-115">El distribuidor invocó 'AfterReceiveReply' en un MessageInspector del tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="16fc6-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="16fc6-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="16fc6-116">Details</span></span>  
  
|<span data-ttu-id="16fc6-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="16fc6-117">Data Item Name</span></span>|<span data-ttu-id="16fc6-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="16fc6-118">Data Item Type</span></span>|<span data-ttu-id="16fc6-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="16fc6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="16fc6-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="16fc6-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="16fc6-121">Nombre completo (FullName) de CLR del tipo del `MessageInspector` invocado.</span><span class="sxs-lookup"><span data-stu-id="16fc6-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="16fc6-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="16fc6-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="16fc6-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="16fc6-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="16fc6-124">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="16fc6-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="16fc6-125">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="16fc6-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="16fc6-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="16fc6-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="16fc6-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="16fc6-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
