---
title: 209 - MessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
ms.openlocfilehash: 50a9424f445781cac70d7d7fde58beea10231cfa
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267759"
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="5b3a7-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="5b3a7-102">209 - MessageInspectorBeforeSendInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="5b3a7-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="5b3a7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b3a7-104">ID</span><span class="sxs-lookup"><span data-stu-id="5b3a7-104">ID</span></span>|<span data-ttu-id="5b3a7-105">209</span><span class="sxs-lookup"><span data-stu-id="5b3a7-105">209</span></span>|  
|<span data-ttu-id="5b3a7-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="5b3a7-106">Keywords</span></span>|<span data-ttu-id="5b3a7-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5b3a7-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="5b3a7-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="5b3a7-108">Level</span></span>|<span data-ttu-id="5b3a7-109">Información</span><span class="sxs-lookup"><span data-stu-id="5b3a7-109">Information</span></span>|  
|<span data-ttu-id="5b3a7-110">Canal</span><span class="sxs-lookup"><span data-stu-id="5b3a7-110">Channel</span></span>|<span data-ttu-id="5b3a7-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="5b3a7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5b3a7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b3a7-112">Description</span></span>  

 <span data-ttu-id="5b3a7-113">Se emite este evento cuando el modelo de servicio ha invocado el método `BeforeSend` en un inspector de mensaje.</span><span class="sxs-lookup"><span data-stu-id="5b3a7-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5b3a7-114">Message</span><span class="sxs-lookup"><span data-stu-id="5b3a7-114">Message</span></span>  

 <span data-ttu-id="5b3a7-115">El distribuidor invocó 'BeforeSendRequest' en un MessageInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="5b3a7-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5b3a7-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="5b3a7-116">Details</span></span>  
  
|<span data-ttu-id="5b3a7-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5b3a7-117">Data Item Name</span></span>|<span data-ttu-id="5b3a7-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="5b3a7-118">Data Item Type</span></span>|<span data-ttu-id="5b3a7-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b3a7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5b3a7-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="5b3a7-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="5b3a7-121">Nombre completo (FullName) de CLR del tipo del `MessageInspector` invocado.</span><span class="sxs-lookup"><span data-stu-id="5b3a7-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="5b3a7-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="5b3a7-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="5b3a7-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="5b3a7-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="5b3a7-124">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="5b3a7-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="5b3a7-125">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="5b3a7-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="5b3a7-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5b3a7-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5b3a7-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="5b3a7-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
