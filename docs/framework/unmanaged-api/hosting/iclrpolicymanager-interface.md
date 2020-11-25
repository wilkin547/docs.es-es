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
ms.openlocfilehash: 7092a1c792fee7f6173dcde211b8e807f6ab02a3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725591"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="6dbc9-102">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6dbc9-102">ICLRPolicyManager Interface</span></span>

<span data-ttu-id="6dbc9-103">Proporciona métodos que permiten al host especificar las acciones de directiva que deben realizarse en caso de que se produzcan errores y tiempos de espera.</span><span class="sxs-lookup"><span data-stu-id="6dbc9-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6dbc9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="6dbc9-104">Methods</span></span>  
  
|<span data-ttu-id="6dbc9-105">Método</span><span class="sxs-lookup"><span data-stu-id="6dbc9-105">Method</span></span>|<span data-ttu-id="6dbc9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="6dbc9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6dbc9-107">Método SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="6dbc9-107">SetActionOnFailure Method</span></span>](iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="6dbc9-108">Especifica la acción de la Directiva que debe realizar el Common Language Runtime (CLR) cuando se produce el error especificado.</span><span class="sxs-lookup"><span data-stu-id="6dbc9-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="6dbc9-109">Método SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="6dbc9-109">SetActionOnTimeout Method</span></span>](iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="6dbc9-110">Especifica la acción de la Directiva que el CLR debe realizar cuando se agota el tiempo de espera de la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="6dbc9-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="6dbc9-111">Método SetDefaultAction</span><span class="sxs-lookup"><span data-stu-id="6dbc9-111">SetDefaultAction Method</span></span>](iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="6dbc9-112">Especifica la acción de la Directiva que el CLR debe realizar cuando se produce la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="6dbc9-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="6dbc9-113">Método SetTimeout</span><span class="sxs-lookup"><span data-stu-id="6dbc9-113">SetTimeout Method</span></span>](iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="6dbc9-114">Establece un valor de tiempo de espera para la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="6dbc9-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="6dbc9-115">Método SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="6dbc9-115">SetTimeoutAndAction Method</span></span>](iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="6dbc9-116">Establece un valor de tiempo de espera para la operación especificada y especifica la acción de la Directiva que el CLR debe realizar cuando se produce la operación.</span><span class="sxs-lookup"><span data-stu-id="6dbc9-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="6dbc9-117">Método SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="6dbc9-117">SetUnhandledExceptionPolicy Method</span></span>](iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="6dbc9-118">Especifica el comportamiento de CLR cuando se produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="6dbc9-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6dbc9-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6dbc9-119">Requirements</span></span>  

 <span data-ttu-id="6dbc9-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6dbc9-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6dbc9-121">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6dbc9-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6dbc9-122">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6dbc9-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6dbc9-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6dbc9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dbc9-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6dbc9-124">See also</span></span>

- [<span data-ttu-id="6dbc9-125">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6dbc9-125">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="6dbc9-126">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6dbc9-126">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="6dbc9-127">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6dbc9-127">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="6dbc9-128">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6dbc9-128">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
