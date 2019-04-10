---
title: ICLRPolicyManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2eeccc4dfd7a7147fe791444eeeca2bd3a844305
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211054"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="b7d2d-102">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7d2d-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="b7d2d-103">Proporciona métodos que permiten al host especificar acciones de directiva que se realizarán en el caso de errores y tiempos de espera.</span><span class="sxs-lookup"><span data-stu-id="b7d2d-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7d2d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b7d2d-104">Methods</span></span>  
  
|<span data-ttu-id="b7d2d-105">Método</span><span class="sxs-lookup"><span data-stu-id="b7d2d-105">Method</span></span>|<span data-ttu-id="b7d2d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7d2d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7d2d-107">Método SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="b7d2d-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="b7d2d-108">Especifica la acción de directiva que common language runtime (CLR) debe realizar cuando se produce el error especificado.</span><span class="sxs-lookup"><span data-stu-id="b7d2d-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="b7d2d-109">Método SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="b7d2d-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="b7d2d-110">Especifica la acción de directiva que CLR debe realizar cuando se agota el tiempo de espera de la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="b7d2d-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="b7d2d-111">Método SetDefaultAction</span><span class="sxs-lookup"><span data-stu-id="b7d2d-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="b7d2d-112">Especifica la acción de directiva, que el CLR debe realizar cuando se produce la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="b7d2d-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="b7d2d-113">Método SetTimeout</span><span class="sxs-lookup"><span data-stu-id="b7d2d-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="b7d2d-114">Establece un valor de tiempo de espera para la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="b7d2d-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="b7d2d-115">Método SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="b7d2d-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="b7d2d-116">Establece un valor de tiempo de espera para la operación especificada y especifica la acción de directiva, que el CLR debe realizar cuando se produce la operación.</span><span class="sxs-lookup"><span data-stu-id="b7d2d-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="b7d2d-117">Método SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="b7d2d-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="b7d2d-118">Especifica el comportamiento de CLR cuando se produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="b7d2d-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b7d2d-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7d2d-119">Requirements</span></span>  
 <span data-ttu-id="b7d2d-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7d2d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7d2d-121">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b7d2d-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7d2d-122">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b7d2d-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="b7d2d-123">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b7d2d-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b7d2d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7d2d-124">See also</span></span>

- [<span data-ttu-id="b7d2d-125">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b7d2d-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="b7d2d-126">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b7d2d-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="b7d2d-127">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b7d2d-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="b7d2d-128">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7d2d-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
