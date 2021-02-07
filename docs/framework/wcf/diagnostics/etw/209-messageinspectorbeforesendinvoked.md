---
description: 'Más información acerca de: 209-MessageInspectorBeforeSendInvoked'
title: 209 - MessageInspectorBeforeSendInvoked
ms.date: 03/30/2017
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
ms.openlocfilehash: 337ed7d4c62d41d72cb2b4710c9f98f863305aee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728007"
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="2aae7-103">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="2aae7-103">209 - MessageInspectorBeforeSendInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="2aae7-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="2aae7-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2aae7-105">Id.</span><span class="sxs-lookup"><span data-stu-id="2aae7-105">ID</span></span>|<span data-ttu-id="2aae7-106">209</span><span class="sxs-lookup"><span data-stu-id="2aae7-106">209</span></span>|  
|<span data-ttu-id="2aae7-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="2aae7-107">Keywords</span></span>|<span data-ttu-id="2aae7-108">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2aae7-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="2aae7-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="2aae7-109">Level</span></span>|<span data-ttu-id="2aae7-110">Información</span><span class="sxs-lookup"><span data-stu-id="2aae7-110">Information</span></span>|  
|<span data-ttu-id="2aae7-111">Canal</span><span class="sxs-lookup"><span data-stu-id="2aae7-111">Channel</span></span>|<span data-ttu-id="2aae7-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="2aae7-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2aae7-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="2aae7-113">Description</span></span>  

 <span data-ttu-id="2aae7-114">Se emite este evento cuando el modelo de servicio ha invocado el método `BeforeSend` en un inspector de mensaje.</span><span class="sxs-lookup"><span data-stu-id="2aae7-114">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2aae7-115">Message</span><span class="sxs-lookup"><span data-stu-id="2aae7-115">Message</span></span>  

 <span data-ttu-id="2aae7-116">El distribuidor invocó 'BeforeSendRequest' en un MessageInspector de tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="2aae7-116">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2aae7-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="2aae7-117">Details</span></span>  
  
|<span data-ttu-id="2aae7-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="2aae7-118">Data Item Name</span></span>|<span data-ttu-id="2aae7-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="2aae7-119">Data Item Type</span></span>|<span data-ttu-id="2aae7-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="2aae7-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2aae7-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="2aae7-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="2aae7-122">Nombre completo (FullName) de CLR del tipo del `MessageInspector` invocado.</span><span class="sxs-lookup"><span data-stu-id="2aae7-122">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="2aae7-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="2aae7-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="2aae7-124">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="2aae7-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="2aae7-125">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="2aae7-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="2aae7-126">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="2aae7-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="2aae7-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2aae7-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="2aae7-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="2aae7-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
