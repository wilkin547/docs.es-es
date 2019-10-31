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
ms.openlocfilehash: 59aa904d4c67326b60381d3476eaab179d7fa42b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140804"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="beee3-102">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="beee3-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="beee3-103">Proporciona métodos que permiten al host especificar las acciones de directiva que deben realizarse en caso de que se produzcan errores y tiempos de espera.</span><span class="sxs-lookup"><span data-stu-id="beee3-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="beee3-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="beee3-104">Methods</span></span>  
  
|<span data-ttu-id="beee3-105">Método</span><span class="sxs-lookup"><span data-stu-id="beee3-105">Method</span></span>|<span data-ttu-id="beee3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="beee3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="beee3-107">SetActionOnFailure (método)</span><span class="sxs-lookup"><span data-stu-id="beee3-107">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="beee3-108">Especifica la acción de la Directiva que debe realizar el Common Language Runtime (CLR) cuando se produce el error especificado.</span><span class="sxs-lookup"><span data-stu-id="beee3-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="beee3-109">SetActionOnTimeout (método)</span><span class="sxs-lookup"><span data-stu-id="beee3-109">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="beee3-110">Especifica la acción de la Directiva que el CLR debe realizar cuando se agota el tiempo de espera de la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="beee3-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="beee3-111">SetDefaultAction (método)</span><span class="sxs-lookup"><span data-stu-id="beee3-111">SetDefaultAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="beee3-112">Especifica la acción de la Directiva que el CLR debe realizar cuando se produce la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="beee3-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="beee3-113">SetTimeout (método)</span><span class="sxs-lookup"><span data-stu-id="beee3-113">SetTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="beee3-114">Establece un valor de tiempo de espera para la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="beee3-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="beee3-115">SetTimeoutAndAction (método)</span><span class="sxs-lookup"><span data-stu-id="beee3-115">SetTimeoutAndAction Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="beee3-116">Establece un valor de tiempo de espera para la operación especificada y especifica la acción de la Directiva que el CLR debe realizar cuando se produce la operación.</span><span class="sxs-lookup"><span data-stu-id="beee3-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="beee3-117">SetUnhandledExceptionPolicy (método)</span><span class="sxs-lookup"><span data-stu-id="beee3-117">SetUnhandledExceptionPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="beee3-118">Especifica el comportamiento de CLR cuando se produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="beee3-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="beee3-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="beee3-119">Requirements</span></span>  
 <span data-ttu-id="beee3-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beee3-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="beee3-121">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="beee3-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="beee3-122">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="beee3-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="beee3-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="beee3-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beee3-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="beee3-124">See also</span></span>

- [<span data-ttu-id="beee3-125">EClrFailure (enumeración)</span><span class="sxs-lookup"><span data-stu-id="beee3-125">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="beee3-126">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="beee3-126">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="beee3-127">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="beee3-127">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="beee3-128">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="beee3-128">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
