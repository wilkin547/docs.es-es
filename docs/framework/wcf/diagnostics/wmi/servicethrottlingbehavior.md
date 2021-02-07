---
description: 'Más información acerca de: ServiceThrottlingBehavior'
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: c4cf354c96340b910807bf7904e63a08dc01764b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715449"
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="c912b-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="c912b-103">ServiceThrottlingBehavior</span></span>

<span data-ttu-id="c912b-104">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="c912b-104">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c912b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c912b-105">Syntax</span></span>  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c912b-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="c912b-106">Methods</span></span>  

 <span data-ttu-id="c912b-107">La clase ServiceThrottlingBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="c912b-107">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c912b-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c912b-108">Properties</span></span>  

 <span data-ttu-id="c912b-109">La clase ServiceThrottlingBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="c912b-109">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="c912b-110">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="c912b-110">MaxConcurrentCalls</span></span>  

 <span data-ttu-id="c912b-111">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="c912b-111">Data type: sint32</span></span>  
  
 <span data-ttu-id="c912b-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c912b-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c912b-113">El número máximo de mensajes que se procesan activamente en todos los objetos de distribuidor en un ServiceHost.</span><span class="sxs-lookup"><span data-stu-id="c912b-113">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="c912b-114">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="c912b-114">MaxConcurrentInstances</span></span>  

 <span data-ttu-id="c912b-115">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="c912b-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="c912b-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c912b-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c912b-117">El número máximo de objetos de servicio que se pueden ejecutar simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="c912b-117">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="c912b-118">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="c912b-118">MaxConcurrentSessions</span></span>  

 <span data-ttu-id="c912b-119">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="c912b-119">Data type: sint32</span></span>  
  
 <span data-ttu-id="c912b-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="c912b-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c912b-121">El número máximo de sesiones que un host puede aceptar al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c912b-121">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c912b-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c912b-122">Requirements</span></span>  
  
|<span data-ttu-id="c912b-123">MOF</span><span class="sxs-lookup"><span data-stu-id="c912b-123">MOF</span></span>|<span data-ttu-id="c912b-124">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c912b-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c912b-125">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="c912b-125">Namespace</span></span>|<span data-ttu-id="c912b-126">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c912b-126">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c912b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="c912b-127">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
