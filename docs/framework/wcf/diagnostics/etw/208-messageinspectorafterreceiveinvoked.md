---
description: 'Más información acerca de: 208-MessageInspectorAfterReceiveInvoked'
title: 208 - MessageInspectorAfterReceiveInvoked
ms.date: 03/30/2017
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
ms.openlocfilehash: 29935f5dc8c5dd53c0bf427bfdc9b3858d7fb8fd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728059"
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="505b4-103">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="505b4-103">208 - MessageInspectorAfterReceiveInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="505b4-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="505b4-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="505b4-105">Id.</span><span class="sxs-lookup"><span data-stu-id="505b4-105">ID</span></span>|<span data-ttu-id="505b4-106">208</span><span class="sxs-lookup"><span data-stu-id="505b4-106">208</span></span>|  
|<span data-ttu-id="505b4-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="505b4-107">Keywords</span></span>|<span data-ttu-id="505b4-108">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="505b4-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="505b4-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="505b4-109">Level</span></span>|<span data-ttu-id="505b4-110">Información</span><span class="sxs-lookup"><span data-stu-id="505b4-110">Information</span></span>|  
|<span data-ttu-id="505b4-111">Canal</span><span class="sxs-lookup"><span data-stu-id="505b4-111">Channel</span></span>|<span data-ttu-id="505b4-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="505b4-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="505b4-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="505b4-113">Description</span></span>  

 <span data-ttu-id="505b4-114">Se emite este evento cuando el modelo de servicio ha invocado el método `AfterReceive` en un inspector de mensaje.</span><span class="sxs-lookup"><span data-stu-id="505b4-114">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="505b4-115">Message</span><span class="sxs-lookup"><span data-stu-id="505b4-115">Message</span></span>  

 <span data-ttu-id="505b4-116">El distribuidor invocó 'AfterReceiveReply' en un MessageInspector del tipo '%1'.</span><span class="sxs-lookup"><span data-stu-id="505b4-116">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="505b4-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="505b4-117">Details</span></span>  
  
|<span data-ttu-id="505b4-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="505b4-118">Data Item Name</span></span>|<span data-ttu-id="505b4-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="505b4-119">Data Item Type</span></span>|<span data-ttu-id="505b4-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="505b4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="505b4-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="505b4-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="505b4-122">Nombre completo (FullName) de CLR del tipo del `MessageInspector` invocado.</span><span class="sxs-lookup"><span data-stu-id="505b4-122">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="505b4-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="505b4-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="505b4-124">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="505b4-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="505b4-125">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="505b4-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="505b4-126">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="505b4-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="505b4-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="505b4-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="505b4-128">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="505b4-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
