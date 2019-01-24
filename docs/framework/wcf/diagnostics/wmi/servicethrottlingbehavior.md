---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 98e8a720e92547ca0a893dd988b91cb7907660b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689856"
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="a62ec-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="a62ec-102">ServiceThrottlingBehavior</span></span>
<span data-ttu-id="a62ec-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="a62ec-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a62ec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a62ec-104">Syntax</span></span>  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a62ec-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a62ec-105">Methods</span></span>  
 <span data-ttu-id="a62ec-106">La clase ServiceThrottlingBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="a62ec-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a62ec-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a62ec-107">Properties</span></span>  
 <span data-ttu-id="a62ec-108">La clase ServiceThrottlingBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="a62ec-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="a62ec-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="a62ec-109">MaxConcurrentCalls</span></span>  
 <span data-ttu-id="a62ec-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="a62ec-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="a62ec-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="a62ec-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a62ec-112">El número máximo de mensajes que se procesan activamente en todos los objetos de distribuidor en un ServiceHost.</span><span class="sxs-lookup"><span data-stu-id="a62ec-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="a62ec-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="a62ec-113">MaxConcurrentInstances</span></span>  
 <span data-ttu-id="a62ec-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="a62ec-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="a62ec-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="a62ec-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a62ec-116">El número máximo de objetos de servicio que se pueden ejecutar simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="a62ec-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="a62ec-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="a62ec-117">MaxConcurrentSessions</span></span>  
 <span data-ttu-id="a62ec-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="a62ec-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="a62ec-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="a62ec-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a62ec-120">El número máximo de sesiones que un host puede aceptar al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="a62ec-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a62ec-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a62ec-121">Requirements</span></span>  
  
|<span data-ttu-id="a62ec-122">MOF</span><span class="sxs-lookup"><span data-stu-id="a62ec-122">MOF</span></span>|<span data-ttu-id="a62ec-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="a62ec-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a62ec-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="a62ec-124">Namespace</span></span>|<span data-ttu-id="a62ec-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a62ec-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a62ec-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a62ec-126">See also</span></span>
- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
