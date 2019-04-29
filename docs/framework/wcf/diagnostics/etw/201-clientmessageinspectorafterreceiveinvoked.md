---
title: 201 - ClientMessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: 9ff637f1-cc26-4400-ab9b-546f70e5057d
ms.openlocfilehash: 96ca318c141d49e2ac5594d5ee101658a2aa8f21
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782044"
---
# <a name="201---clientmessageinspectorafterreceiveinvoked"></a><span data-ttu-id="baff4-102">201 - ClientMessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="baff4-102">201 - ClientMessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="baff4-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="baff4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="baff4-104">ID</span><span class="sxs-lookup"><span data-stu-id="baff4-104">ID</span></span>|<span data-ttu-id="baff4-105">201</span><span class="sxs-lookup"><span data-stu-id="baff4-105">201</span></span>|  
|<span data-ttu-id="baff4-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="baff4-106">Keywords</span></span>|<span data-ttu-id="baff4-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="baff4-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="baff4-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="baff4-108">Level</span></span>|<span data-ttu-id="baff4-109">Información</span><span class="sxs-lookup"><span data-stu-id="baff4-109">Information</span></span>|  
|<span data-ttu-id="baff4-110">Canal</span><span class="sxs-lookup"><span data-stu-id="baff4-110">Channel</span></span>|<span data-ttu-id="baff4-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="baff4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="baff4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="baff4-112">Description</span></span>  
 <span data-ttu-id="baff4-113">Se emite este evento cuando el modelo de servicio ha invocado el método `AfterReceiveReply` en un inspector de mensaje de cliente.</span><span class="sxs-lookup"><span data-stu-id="baff4-113">This event is emitted after the Service Model has invoked the `AfterReceiveReply` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="baff4-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="baff4-114">Message</span></span>  
 <span data-ttu-id="baff4-115">El distribuidor invocó 'AfterReceiveReply' en un ClientMessageInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="baff4-115">The Dispatcher invoked 'AfterReceiveReply' on a ClientMessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="baff4-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="baff4-116">Details</span></span>  
  
|<span data-ttu-id="baff4-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="baff4-117">Data Item Name</span></span>|<span data-ttu-id="baff4-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="baff4-118">Data Item Type</span></span>|<span data-ttu-id="baff4-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="baff4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="baff4-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="baff4-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="baff4-121">El nombre completo (FullName) de CLR del tipo del inspector invocado.</span><span class="sxs-lookup"><span data-stu-id="baff4-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="baff4-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="baff4-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="baff4-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="baff4-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="baff4-124">Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre de la aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="baff4-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="baff4-125">Ejemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="baff4-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="baff4-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="baff4-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="baff4-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="baff4-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
