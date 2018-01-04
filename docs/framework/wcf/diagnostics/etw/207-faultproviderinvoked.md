---
title: 207 - FaultProviderInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9035739f8625a07e8bf2b9bce2fe109880676405
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="44081-102">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="44081-102">207 - FaultProviderInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="44081-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="44081-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44081-104">Id.</span><span class="sxs-lookup"><span data-stu-id="44081-104">ID</span></span>|<span data-ttu-id="44081-105">207</span><span class="sxs-lookup"><span data-stu-id="44081-105">207</span></span>|  
|<span data-ttu-id="44081-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="44081-106">Keywords</span></span>|<span data-ttu-id="44081-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="44081-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="44081-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="44081-108">Level</span></span>|<span data-ttu-id="44081-109">Información</span><span class="sxs-lookup"><span data-stu-id="44081-109">Information</span></span>|  
|<span data-ttu-id="44081-110">Canal</span><span class="sxs-lookup"><span data-stu-id="44081-110">Channel</span></span>|<span data-ttu-id="44081-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="44081-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="44081-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="44081-112">Description</span></span>  
 <span data-ttu-id="44081-113">Este evento se emite una vez invocado `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="44081-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="44081-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="44081-114">Message</span></span>  
 <span data-ttu-id="44081-115">El distribuidor invocó un FaultProvider del tipo '%1' con una excepción del tipo '%2'.</span><span class="sxs-lookup"><span data-stu-id="44081-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="44081-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="44081-116">Details</span></span>  
  
|<span data-ttu-id="44081-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="44081-117">Data Item Name</span></span>|<span data-ttu-id="44081-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="44081-118">Data Item Type</span></span>|<span data-ttu-id="44081-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="44081-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="44081-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="44081-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="44081-121">Nombre completo (FullName) de CLR del tipo del `FaultProvider` invocado.</span><span class="sxs-lookup"><span data-stu-id="44081-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="44081-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="44081-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="44081-123">El nombre completo (FullName) de CLR de la excepción en la que ha funcionado `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="44081-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="44081-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="44081-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="44081-125">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="44081-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="44081-126">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="44081-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="44081-127">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="44081-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="44081-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="44081-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="44081-129">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="44081-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
