---
description: 'Más información sobre: interfaz ICLRPolicyManager'
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
ms.openlocfilehash: 8823f1db8b15b327306ff3c592b46c94537f4331
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637394"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="fef13-103">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fef13-103">ICLRPolicyManager Interface</span></span>

<span data-ttu-id="fef13-104">Proporciona métodos que permiten al host especificar las acciones de directiva que deben realizarse en caso de que se produzcan errores y tiempos de espera.</span><span class="sxs-lookup"><span data-stu-id="fef13-104">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fef13-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="fef13-105">Methods</span></span>  
  
|<span data-ttu-id="fef13-106">Método</span><span class="sxs-lookup"><span data-stu-id="fef13-106">Method</span></span>|<span data-ttu-id="fef13-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fef13-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fef13-108">Método SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="fef13-108">SetActionOnFailure Method</span></span>](iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="fef13-109">Especifica la acción de la Directiva que debe realizar el Common Language Runtime (CLR) cuando se produce el error especificado.</span><span class="sxs-lookup"><span data-stu-id="fef13-109">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="fef13-110">Método SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="fef13-110">SetActionOnTimeout Method</span></span>](iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="fef13-111">Especifica la acción de la Directiva que el CLR debe realizar cuando se agota el tiempo de espera de la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="fef13-111">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="fef13-112">Método SetDefaultAction</span><span class="sxs-lookup"><span data-stu-id="fef13-112">SetDefaultAction Method</span></span>](iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="fef13-113">Especifica la acción de la Directiva que el CLR debe realizar cuando se produce la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="fef13-113">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="fef13-114">Método SetTimeout</span><span class="sxs-lookup"><span data-stu-id="fef13-114">SetTimeout Method</span></span>](iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="fef13-115">Establece un valor de tiempo de espera para la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="fef13-115">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="fef13-116">Método SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="fef13-116">SetTimeoutAndAction Method</span></span>](iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="fef13-117">Establece un valor de tiempo de espera para la operación especificada y especifica la acción de la Directiva que el CLR debe realizar cuando se produce la operación.</span><span class="sxs-lookup"><span data-stu-id="fef13-117">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="fef13-118">Método SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="fef13-118">SetUnhandledExceptionPolicy Method</span></span>](iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="fef13-119">Especifica el comportamiento de CLR cuando se produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="fef13-119">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fef13-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fef13-120">Requirements</span></span>  

 <span data-ttu-id="fef13-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fef13-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fef13-122">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fef13-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fef13-123">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fef13-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fef13-124">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fef13-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef13-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="fef13-125">See also</span></span>

- [<span data-ttu-id="fef13-126">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="fef13-126">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="fef13-127">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="fef13-127">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="fef13-128">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="fef13-128">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="fef13-129">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fef13-129">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
