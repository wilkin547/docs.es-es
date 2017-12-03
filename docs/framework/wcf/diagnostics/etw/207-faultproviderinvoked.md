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
ms.openlocfilehash: 71fce60ca658c159df11588be149cda17ad2303d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="7db47-102">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="7db47-102">207 - FaultProviderInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="7db47-103">Propiedades</span><span class="sxs-lookup"><span data-stu-id="7db47-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7db47-104">Id.</span><span class="sxs-lookup"><span data-stu-id="7db47-104">ID</span></span>|<span data-ttu-id="7db47-105">207</span><span class="sxs-lookup"><span data-stu-id="7db47-105">207</span></span>|  
|<span data-ttu-id="7db47-106">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="7db47-106">Keywords</span></span>|<span data-ttu-id="7db47-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7db47-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="7db47-108">Nivel</span><span class="sxs-lookup"><span data-stu-id="7db47-108">Level</span></span>|<span data-ttu-id="7db47-109">Información</span><span class="sxs-lookup"><span data-stu-id="7db47-109">Information</span></span>|  
|<span data-ttu-id="7db47-110">Canal</span><span class="sxs-lookup"><span data-stu-id="7db47-110">Channel</span></span>|<span data-ttu-id="7db47-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="7db47-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7db47-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="7db47-112">Description</span></span>  
 <span data-ttu-id="7db47-113">Este evento se emite una vez invocado `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="7db47-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7db47-114">Mensaje</span><span class="sxs-lookup"><span data-stu-id="7db47-114">Message</span></span>  
 <span data-ttu-id="7db47-115">El distribuidor invocó un FaultProvider del tipo '%1' con una excepción del tipo '%2'.</span><span class="sxs-lookup"><span data-stu-id="7db47-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7db47-116">Detalles</span><span class="sxs-lookup"><span data-stu-id="7db47-116">Details</span></span>  
  
|<span data-ttu-id="7db47-117">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7db47-117">Data Item Name</span></span>|<span data-ttu-id="7db47-118">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="7db47-118">Data Item Type</span></span>|<span data-ttu-id="7db47-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="7db47-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7db47-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="7db47-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="7db47-121">Nombre completo (FullName) de CLR del tipo del `FaultProvider` invocado.</span><span class="sxs-lookup"><span data-stu-id="7db47-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="7db47-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="7db47-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="7db47-123">El nombre completo (FullName) de CLR de la excepción en la que ha funcionado `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="7db47-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="7db47-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="7db47-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="7db47-125">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="7db47-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="7db47-126">El formato se define como ' ruta de acceso Virtual de sitio Web de nombre de aplicación &#124; Ruta de acceso Virtual del servicio &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="7db47-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="7db47-127">Ejemplo: ' sitio Web/CalculatorApplication &#124;/CalculatorService.svc &#124; predeterminada CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="7db47-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="7db47-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7db47-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7db47-129">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="7db47-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
