---
description: 'Más información acerca de: 207-FaultProviderInvoked'
title: 207 - FaultProviderInvoked
ms.date: 03/30/2017
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
ms.openlocfilehash: 03c4f1669fc61019ccf4d23d2994f136e231fbec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728072"
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="20230-103">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="20230-103">207 - FaultProviderInvoked</span></span>

## <a name="properties"></a><span data-ttu-id="20230-104">Propiedades</span><span class="sxs-lookup"><span data-stu-id="20230-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="20230-105">Id.</span><span class="sxs-lookup"><span data-stu-id="20230-105">ID</span></span>|<span data-ttu-id="20230-106">207</span><span class="sxs-lookup"><span data-stu-id="20230-106">207</span></span>|  
|<span data-ttu-id="20230-107">Palabras clave</span><span class="sxs-lookup"><span data-stu-id="20230-107">Keywords</span></span>|<span data-ttu-id="20230-108">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="20230-108">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="20230-109">Nivel</span><span class="sxs-lookup"><span data-stu-id="20230-109">Level</span></span>|<span data-ttu-id="20230-110">Información</span><span class="sxs-lookup"><span data-stu-id="20230-110">Information</span></span>|  
|<span data-ttu-id="20230-111">Canal</span><span class="sxs-lookup"><span data-stu-id="20230-111">Channel</span></span>|<span data-ttu-id="20230-112">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="20230-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="20230-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="20230-113">Description</span></span>  

 <span data-ttu-id="20230-114">Este evento se emite una vez invocado `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="20230-114">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="20230-115">Message</span><span class="sxs-lookup"><span data-stu-id="20230-115">Message</span></span>  

 <span data-ttu-id="20230-116">El distribuidor invocó un FaultProvider del tipo '%1' con una excepción del tipo '%2'.</span><span class="sxs-lookup"><span data-stu-id="20230-116">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="20230-117">Detalles</span><span class="sxs-lookup"><span data-stu-id="20230-117">Details</span></span>  
  
|<span data-ttu-id="20230-118">Nombre del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="20230-118">Data Item Name</span></span>|<span data-ttu-id="20230-119">Tipo del elemento de datos</span><span class="sxs-lookup"><span data-stu-id="20230-119">Data Item Type</span></span>|<span data-ttu-id="20230-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="20230-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="20230-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="20230-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="20230-122">Nombre completo (FullName) de CLR del tipo del `FaultProvider` invocado.</span><span class="sxs-lookup"><span data-stu-id="20230-122">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="20230-123">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="20230-123">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="20230-124">El nombre completo (FullName) de CLR de la excepción en la que ha funcionado `FaultProvider`.</span><span class="sxs-lookup"><span data-stu-id="20230-124">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="20230-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="20230-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="20230-126">En el caso de los servicios hospedados en web, este campo identifica de manera única el servicio en la jerarquía web.</span><span class="sxs-lookup"><span data-stu-id="20230-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="20230-127">Su formato se define como ' ruta de acceso virtual de la aplicación de nombre de sitio web&#124;ruta de acceso virtual del servicio&#124;ServiceName '.</span><span class="sxs-lookup"><span data-stu-id="20230-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="20230-128">Ejemplo: ' sitio web predeterminado/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService '.</span><span class="sxs-lookup"><span data-stu-id="20230-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="20230-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="20230-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="20230-130">La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="20230-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
