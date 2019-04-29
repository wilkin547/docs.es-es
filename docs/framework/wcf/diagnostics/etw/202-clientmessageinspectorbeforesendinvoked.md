---
title: 202 - ClientMessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 0b02ca82-8a55-45e3-b2e2-ddfe28a7269c
ms.openlocfilehash: 98de1d7e8e5e87ec7fbd783092f7fbc212fec65d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781997"
---
# <a name="202---clientmessageinspectorbeforesendinvoked"></a><span data-ttu-id="6c160-102">202 - ClientMessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="6c160-102">202 - ClientMessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="6c160-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="6c160-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6c160-104">ID</span><span class="sxs-lookup"><span data-stu-id="6c160-104">ID</span></span>|<span data-ttu-id="6c160-105">202</span><span class="sxs-lookup"><span data-stu-id="6c160-105">202</span></span>|  
|<span data-ttu-id="6c160-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="6c160-106">Keywords</span></span>|<span data-ttu-id="6c160-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6c160-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="6c160-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="6c160-108">Level</span></span>|<span data-ttu-id="6c160-109">Información</span><span class="sxs-lookup"><span data-stu-id="6c160-109">Information</span></span>|  
|<span data-ttu-id="6c160-110">Canal</span><span class="sxs-lookup"><span data-stu-id="6c160-110">Channel</span></span>|<span data-ttu-id="6c160-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="6c160-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6c160-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c160-112">Description</span></span>  
 <span data-ttu-id="6c160-113">Se emite este evento cuando el modelo de servicio ha invocado el método `BeforeSendRequest` en un inspector de mensaje de cliente.</span><span class="sxs-lookup"><span data-stu-id="6c160-113">This event is emitted after the Service Model has invoked the `BeforeSendRequest` method on a client message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6c160-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="6c160-114">Message</span></span>  
 <span data-ttu-id="6c160-115">El distribuidor invocó 'BeforeSendRequest' en un ClientMessageInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="6c160-115">The Dispatcher invoked 'BeforeSendRequest' on a ClientMessageInspector of type  '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6c160-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="6c160-116">Details</span></span>  
  
|<span data-ttu-id="6c160-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6c160-117">Data Item Name</span></span>|<span data-ttu-id="6c160-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="6c160-118">Data Item Type</span></span>|<span data-ttu-id="6c160-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c160-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6c160-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="6c160-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="6c160-121">El nombre completo (FullName) de CLR del tipo del inspector invocado.</span><span class="sxs-lookup"><span data-stu-id="6c160-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="6c160-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="6c160-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="6c160-123">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="6c160-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="6c160-124">Su formato se define como ' ruta de acceso Virtual de sitio Web de nombre de la aplicación&#124;ruta de acceso Virtual del servicio&#124;ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="6c160-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="6c160-125">Ejemplo: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="6c160-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="6c160-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="6c160-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="6c160-127">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="6c160-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
