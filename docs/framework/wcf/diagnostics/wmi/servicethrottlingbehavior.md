---
title: ServiceThrottlingBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 59f85a148d6707876a4df512d5cfbd07ca0e54b7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="eae30-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="eae30-102">ServiceThrottlingBehavior</span></span>
<span data-ttu-id="eae30-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="eae30-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eae30-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eae30-104">Syntax</span></span>  
  
```  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="eae30-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="eae30-105">Methods</span></span>  
 <span data-ttu-id="eae30-106">La clase ServiceThrottlingBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="eae30-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="eae30-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="eae30-107">Properties</span></span>  
 <span data-ttu-id="eae30-108">La clase ServiceThrottlingBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="eae30-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="eae30-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="eae30-109">MaxConcurrentCalls</span></span>  
 <span data-ttu-id="eae30-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="eae30-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="eae30-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="eae30-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eae30-112">El número máximo de mensajes que se procesan activamente en todos los objetos de distribuidor en un ServiceHost.</span><span class="sxs-lookup"><span data-stu-id="eae30-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="eae30-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="eae30-113">MaxConcurrentInstances</span></span>  
 <span data-ttu-id="eae30-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="eae30-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="eae30-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="eae30-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eae30-116">El número máximo de objetos de servicio que se pueden ejecutar simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="eae30-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="eae30-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="eae30-117">MaxConcurrentSessions</span></span>  
 <span data-ttu-id="eae30-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="eae30-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="eae30-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="eae30-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eae30-120">El número máximo de sesiones que un host puede aceptar al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="eae30-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eae30-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eae30-121">Requirements</span></span>  
  
|<span data-ttu-id="eae30-122">MOF</span><span class="sxs-lookup"><span data-stu-id="eae30-122">MOF</span></span>|<span data-ttu-id="eae30-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="eae30-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="eae30-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="eae30-124">Namespace</span></span>|<span data-ttu-id="eae30-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="eae30-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eae30-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="eae30-126">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
