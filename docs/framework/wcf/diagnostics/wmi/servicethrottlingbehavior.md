---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 572e458f08c4717207667db9940296c4a957199a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59771782"
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="02933-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="02933-102">ServiceThrottlingBehavior</span></span>
<span data-ttu-id="02933-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="02933-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02933-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02933-104">Syntax</span></span>  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="02933-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="02933-105">Methods</span></span>  
 <span data-ttu-id="02933-106">La clase ServiceThrottlingBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="02933-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="02933-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="02933-107">Properties</span></span>  
 <span data-ttu-id="02933-108">La clase ServiceThrottlingBehavior tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="02933-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="02933-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="02933-109">MaxConcurrentCalls</span></span>  
 <span data-ttu-id="02933-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="02933-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="02933-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="02933-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="02933-112">El número máximo de mensajes que se procesan activamente en todos los objetos de distribuidor en un ServiceHost.</span><span class="sxs-lookup"><span data-stu-id="02933-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="02933-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="02933-113">MaxConcurrentInstances</span></span>  
 <span data-ttu-id="02933-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="02933-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="02933-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="02933-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="02933-116">El número máximo de objetos de servicio que se pueden ejecutar simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="02933-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="02933-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="02933-117">MaxConcurrentSessions</span></span>  
 <span data-ttu-id="02933-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="02933-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="02933-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="02933-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="02933-120">El número máximo de sesiones que un host puede aceptar al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="02933-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02933-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02933-121">Requirements</span></span>  
  
|<span data-ttu-id="02933-122">MOF</span><span class="sxs-lookup"><span data-stu-id="02933-122">MOF</span></span>|<span data-ttu-id="02933-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="02933-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="02933-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="02933-124">Namespace</span></span>|<span data-ttu-id="02933-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="02933-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02933-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="02933-126">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
